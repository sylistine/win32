---
Description: The LSA provides functions you can use to receive notification when there is a change in policy on the local system.
ms.assetid: 29c693f5-db2b-4fda-847c-4e5220eadfd3
title: Receiving Policy Change Events
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Receiving Policy Change Events

The LSA provides functions you can use to receive notification when there is a change in policy on the local system.

To receive notification, create a new event object by calling the [**CreateEvent**](https://msdn.microsoft.com/library/windows/desktop/ms682396) function, and then call the [**LsaRegisterPolicyChangeNotification**](/windows/win32/Ntsecapi/nf-ntsecapi-lsaregisterpolicychangenotification?branch=master) function. Your application can then call a wait function such as [**WaitForSingleObject**](https://msdn.microsoft.com/library/windows/desktop/ms687032), [**WaitForSingleObjectEx**](https://msdn.microsoft.com/library/windows/desktop/ms687036), or [**RegisterWaitForSingleObject**](https://msdn.microsoft.com/library/windows/desktop/ms685061) to wait for the event to occur. The wait function returns when the event occurs, or when the time-out period expires. Typically, notification events are used in multithreaded applications, in which one thread waits for an event, while other threads continue processing.

When your application no longer needs to receive notifications, it should call [**LsaUnregisterPolicyChangeNotification**](/windows/win32/Ntsecapi/nf-ntsecapi-lsaunregisterpolicychangenotification?branch=master) and then call [**CloseHandle**](https://msdn.microsoft.com/library/windows/desktop/ms724211) to free the event object handle.

The following example shows how a single-threaded application can receive notification events when the system's auditing policy changes.


```C++
#include <windows.h>
#include <stdio.h>

void WaitForPolicyChanges()
{
  HANDLE hEvent;
  NTSTATUS ntsResult;
  DWORD dwResult;

  // Create an event object.
  hEvent = CreateEvent( 
    NULL,  // child processes cannot inherit 
    FALSE, // automatically reset event
    FALSE, // start as a nonsignaled event
    NULL   // do not need a name
  );

  // Check that the event was created.
  if (hEvent == NULL) 
  {
    wprintf(L"Event object creation failed: %d\n",GetLastError());
    return;
  }
  // Register to receive auditing policy change notifications.
  ntsResult = LsaRegisterPolicyChangeNotification(
    PolicyNotifyAuditEventsInformation,
    hEvent
  );
  if (STATUS_SUCCESS != ntsResult)
  {
    wprintf(L"LsaRegisterPolicyChangeNotification failed.\n");
    CloseHandle(hEvent);
    return;
  }

  // Wait for the event to be triggered.
  dwResult = WaitForSingleObject( 
    hEvent, // handle to the event object
    300000  // time-out interval, in milliseconds
  );

  // The wait function returned.
  if (dwResult == WAIT_OBJECT_0)
  {  // received the notification signal
    wprintf(L"Notification received.\n");
  } 
  else 
  {  // received a time-out or error
    wprintf(L"Notification was not received.\n");
  }
  // Unregister for notification.
  LsaUnregisterPolicyChangeNotification(
    PolicyNotifyAuditEventsInformation,
    hEvent
  );

  // Free the event handle.
  CloseHandle(hEvent);
}
```



For more information about event objects, wait functions, and synchronization, see [Using Event Objects](https://msdn.microsoft.com/library/windows/desktop/ms686915).

 

 



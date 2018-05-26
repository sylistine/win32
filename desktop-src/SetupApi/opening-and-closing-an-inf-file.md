---
Description: Before the setup functions can access information in the INF, you must open it with a call to the SetupOpenInfFile function. This function returns a handle to the INF file.
ms.assetid: d838c05c-51e4-49a8-b773-af4924bff7e2
title: Opening and Closing an INF file
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Opening and Closing an INF file

Before the setup functions can access information in the INF, you must open it with a call to the [**SetupOpenInfFile**](/windows/win32/Setupapi/nf-setupapi-setupopeninffilea?branch=master) function. This function returns a handle to the INF file.

If you do not know the name of the INF file that you need to open, you can use the [**SetupGetInfFileList**](/windows/win32/Setupapi/nf-setupapi-setupgetinffilelista?branch=master) function to obtain a list of INF files in a directory.

After you open an INF file, you can append additional INF files to the opened INF file by using the [**SetupOpenAppendInfFile**](/windows/win32/Setupapi/nf-setupapi-setupopenappendinffilea?branch=master) function. This is functionally similar to an include statement. When subsequent setup functions reference an open INF file, they will also be able to access any information stored in the appended files.

If you do not specify an INF file during the call to the [**SetupOpenAppendInfFile**](/windows/win32/Setupapi/nf-setupapi-setupopenappendinffilea?branch=master) function, **SetupOpenAppendInfFile** appends the file(s) specified by the **LayoutFile** key in the **Version** section of the open INF file.

When you no longer need the information in the INF file, call the [**SetupCloseInfFile**](/windows/win32/Setupapi/nf-setupapi-setupcloseinffile?branch=master) function to release resources allocated during the call to [**SetupOpenAppendInfFile**](/windows/win32/Setupapi/nf-setupapi-setupopenappendinffilea?branch=master).

 

 



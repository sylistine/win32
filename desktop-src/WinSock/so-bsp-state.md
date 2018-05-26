---
Description: Returns the local address, local port, remote address, remote port, socket type, and protocol used by a socket.
ms.assetid: 2628f47e-3e73-4e02-91b8-ba4cb0800864
title: SO\_BSP\_STATE socket option
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# SO\_BSP\_STATE socket option

The **SO\_BSP\_STATE** socket option returns the local address, local port, remote address, remote port, socket type, and protocol used by a socket.

To perform this operation, call the [**getsockopt**](/windows/win32/winsock/nf-winsock-getsockopt?branch=master) function with the following parameters.

## Socket option value

The constant that represents this socket option is 0x1009.

## Syntax


```C++
int getsockopt(
  (SOCKET) s,      // descriptor identifying a socket 
  (int) SOL_SOCKET,   // level
  (int) SO_BSP_STATE, // optname
  (char *) optval,         // output buffer,
  (int) *optlen,       // size of output buffer
);
```



## Parameters

<dl> <dt>

*s* \[in\]
</dt> <dd>

A descriptor identifying the socket.

</dd> <dt>

*level* \[in\]
</dt> <dd>

The level at which the option is defined. Use **SOL\_SOCKET** for this operation.

</dd> <dt>

*optname* \[in\]
</dt> <dd>

The socket option for which the value is to be retrieved. Use **SO\_BSP\_STATE** for this operation.

</dd> <dt>

*optval* \[out\]
</dt> <dd>

A pointer to the buffer in which the value for the requested option is to be returned. This parameter should point to buffer equal to or larger than the size of a [**CSADDR\_INFO**](/windows/win32/ws2def/ns-nspapi-_csaddr_info?branch=master) structure.

</dd> <dt>

*optlen* \[in, out\]
</dt> <dd>

A pointer to the size, in bytes, of the *optval* buffer. This size must be equal to or larger than the size of a [**CSADDR\_INFO**](/windows/win32/ws2def/ns-nspapi-_csaddr_info?branch=master) structure.

</dd> </dl>

## Return value

If the operation completes successfully, [**getsockopt**](/windows/win32/winsock/nf-winsock-getsockopt?branch=master) returns zero.

If the operation fails, a value of SOCKET\_ERROR is returned and a specific error code can be retrieved by calling [**WSAGetLastError**](/windows/win32/winsock/nf-winsock-wsagetlasterror?branch=master).



| Error code                                                                                                                                              | Meaning                                                                                                                                                                                                                                                                                    |
|---------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <dl> <dt>**[WSANOTINITIALISED](windows-sockets-error-codes-2.md#wsanotinitialised)**</dt> </dl> | A successful [**WSAStartup**](/windows/win32/winsock/nf-winsock-wsastartup?branch=master) call must occur before using this function.<br/>                                                                                                                                                                                     |
| <dl> <dt>**[WSAENETDOWN](windows-sockets-error-codes-2.md#wsaenetdown)**</dt> </dl>             | The network subsystem has failed.<br/>                                                                                                                                                                                                                                               |
| <dl> <dt>**[WSAEFAULT](windows-sockets-error-codes-2.md#wsaefault)**</dt> </dl>                 | One of the *optval* or the *optlen* parameters point to memory that is not in a valid part of the user address space. This error is also returned if the value pointed to by the *optlen* parameter is less than the size of a [**CSADDR\_INFO**](/windows/win32/ws2def/ns-nspapi-_csaddr_info?branch=master) structure.<br/> |
| <dl> <dt>**[WSAEINPROGRESS](windows-sockets-error-codes-2.md#wsaeinprogress)**</dt> </dl>       | A blocking Windows Sockets 1.1 call is in progress, or the service provider is still processing a callback function.<br/>                                                                                                                                                            |
| <dl> <dt>**[WSAEINVAL](windows-sockets-error-codes-2.md#wsaeinval)**</dt> </dl>                 | The *level* parameter is unknown or invalid.<br/>                                                                                                                                                                                                                                    |
| <dl> <dt>**[WSAENOPROTOOPT](windows-sockets-error-codes-2.md#wsaenoprotoopt)**</dt> </dl>       | The option is unknown or unsupported by the indicated protocol family.<br/>                                                                                                                                                                                                          |
| <dl> <dt>**[WSAENOTSOCK](windows-sockets-error-codes-2.md#wsaenotsock)**</dt> </dl>             | The descriptor is not a socket.<br/>                                                                                                                                                                                                                                                 |



 

## Remarks

The [**getsockopt**](/windows/win32/winsock/nf-winsock-getsockopt?branch=master) function called with the **SO\_BSP\_STATE** socket option retrieves the local address, local port, remote address, remote port, socket type, and protocol used by a socket. The **SO\_BSP\_STATE** socket option works with IPv6 or IPv4 sockets (the **AF\_INET6** and **AF\_INET** address families).

If the [**getsockopt**](/windows/win32/winsock/nf-winsock-getsockopt?branch=master) function is successful, the information is returned in a [**CSADDR\_INFO**](/windows/win32/ws2def/ns-nspapi-_csaddr_info?branch=master) structure in the buffer pointed to by the *optval* parameter. The integer pointed to by *optlen* should originally contain the size of this buffer; on return, it will be set to the length, in bytes, of the value returned in the *optval* parameter.

The **iSocketType** and **iProtocol** members in the returned [**CSADDR\_INFO**](/windows/win32/ws2def/ns-nspapi-_csaddr_info?branch=master) structure are filled in for the socket descriptor in the *s* parameter.

If the socket is in a connected or bound state, then the **LocalAddr** member of the returned [**CSADDR\_INFO**](/windows/win32/ws2def/ns-nspapi-_csaddr_info?branch=master) structure will be set to a [SOCKADDR](sockaddr-2.md) structure representing the local address and port. If the socket is in a connected state, then the **RemoteAddr** member of the returned **CSADDR\_INFO** structure will be set to a SOCKADDR structure representing the remote address and port.

If the socket is not in a connected or bound state, then the **LocalAddr** member of the returned [**CSADDR\_INFO**](/windows/win32/ws2def/ns-nspapi-_csaddr_info?branch=master) structure is returned with a **NULL** pointer in the **lpSockaddr** member and the **iSockaddrLength** member set to zero. If the socket is not in a bound state, then the **RemoteAddr** member of the returned **CSADDR\_INFO** structure is returned with a **NULL** pointer in the **lpSockaddr** member and the **iSockaddrLength** member set to zero.

If the [**getsockopt**](/windows/win32/winsock/nf-winsock-getsockopt?branch=master) function fails, the *optval* and *optlen* parameters are left unchanged and the *optval* parameter does not point to a returned [**CSADDR\_INFO**](/windows/win32/ws2def/ns-nspapi-_csaddr_info?branch=master) structure.

Note that the *Ws2def.h* header file is automatically included in *Winsock2.h*, and should never be used directly.

## Requirements



|                                     |                                                                                                          |
|-------------------------------------|----------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                                           |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/>                                                     |
| Header<br/>                   | <dl> <dt>Ws2def.h (include Winsock2.h)</dt> </dl> |



## See also

<dl> <dt>

[**getsockopt**](/windows/win32/winsock/nf-winsock-getsockopt?branch=master)
</dt> <dt>

[**CSADDR\_INFO**](/windows/win32/ws2def/ns-nspapi-_csaddr_info?branch=master)
</dt> <dt>

[SOCKADDR](sockaddr-2.md)
</dt> </dl>

 

 




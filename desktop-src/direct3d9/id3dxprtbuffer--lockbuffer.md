---
Description: Locks a range of vertex or texel sample data and obtains a pointer to the location in buffer memory.
ms.assetid: 8de2725f-507e-41ee-828d-2fb19cc2252c
title: ID3DXPRTBufferLockBuffer method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# ID3DXPRTBuffer::LockBuffer method

Locks a range of vertex or texel sample data and obtains a pointer to the location in buffer memory.

## Syntax


```C++
HRESULT LockBuffer(
  [in]  UINT  Start,
  [in]  UINT  NumSamples,
  [out] FLOAT **ppData
);
```



## Parameters

<dl> <dt>

*Start* \[in\]
</dt> <dd>

Type: **[**UINT**](winprog.windows_data_types)**

Index of the sample of vertex or texel data.

</dd> <dt>

*NumSamples* \[in\]
</dt> <dd>

Type: **[**UINT**](winprog.windows_data_types)**

Number of vertices (or texels) sampled.

</dd> <dt>

*ppData* \[out\]
</dt> <dd>

Type: **[**FLOAT**](winprog.windows_data_types)\*\***

Pointer to the location in memory where the Start sample begins. The memory layout of the buffer data is:


```
float fData[NumberSamples][NumberChannels][NumberCoefficients]      
```



</dd> </dl>

## Return value

Type: **[**HRESULT**](455d07e9-52c3-4efb-a9dc-2955cbfd38cc)**

If the method succeeds, the return value is S\_OK. If the method fails, the following value will be returned:

## Remarks

## Requirements



|                    |                                                                                        |
|--------------------|----------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3DX9Mesh.h</dt> </dl> |
| Library<br/> | <dl> <dt>D3dx9.lib</dt> </dl>   |



## See also

<dl> <dt>

[ID3DXPRTBuffer](id3dxprtbuffer.md)
</dt> <dt>

[**ID3DXPRTBuffer::GetNumChannels**](id3dxprtbuffer--getnumchannels.md)
</dt> <dt>

[**ID3DXPRTBuffer::GetNumCoeffs**](id3dxprtbuffer--getnumcoeffs.md)
</dt> <dt>

[**ID3DXPRTBuffer::GetNumSamples**](id3dxprtbuffer--getnumsamples.md)
</dt> </dl>

 

 




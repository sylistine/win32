---
Description: Creates a ID3DXCompressedAnimationSet key framed animation set interface that stores key frame data in a compressed format.
ms.assetid: c3f97d35-5654-4d85-a337-d77819ce3874
title: D3DXCreateCompressedAnimationSet function
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# D3DXCreateCompressedAnimationSet function

Creates a [**ID3DXCompressedAnimationSet**](id3dxcompressedanimationset.md) key framed animation set interface that stores key frame data in a compressed format.

## Syntax


```C++
HRESULT D3DXCreateCompressedAnimationSet(
  _In_        LPCSTR                       pName,
  _In_        DOUBLE                       TicksPerSecond,
  _In_        D3DXPLAYBACK_TYPE            Playback,
  _In_        LPD3DXBUFFER                 pCompressedData,
  _In_        UINT                         NumCallbackKeys,
  _In_  const LPD3DXKEY_CALLBACK           *pCallKeys,
  _Out_       LPD3DXCOMPRESSEDANIMATIONSET *ppAnimationSet
);
```



## Parameters

<dl> <dt>

*pName* \[in\]
</dt> <dd>

Type: **[**LPCSTR**](winprog.windows_data_types)**

Pointer to the name of the animation set.

</dd> <dt>

*TicksPerSecond* \[in\]
</dt> <dd>

Type: **[**DOUBLE**](winprog.windows_data_types)**

Number of key frame ticks that elapse per second.

</dd> <dt>

*Playback* \[in\]
</dt> <dd>

Type: **[**D3DXPLAYBACK\_TYPE**](direct3d9.d3dxplayback_type)**

Type of the animation set playback loop. See [**D3DXPLAYBACK\_TYPE**](direct3d9.d3dxplayback_type).

</dd> <dt>

*pCompressedData* \[in\]
</dt> <dd>

Type: **[**LPD3DXBUFFER**](id3dxbuffer.md)**

Pointer to the [**ID3DXBuffer**](id3dxbuffer.md) buffer that stores the animation set as compressed data.

</dd> <dt>

*NumCallbackKeys* \[in\]
</dt> <dd>

Type: **[**UINT**](winprog.windows_data_types)**

Number of callback keys.

</dd> <dt>

*pCallKeys* \[in\]
</dt> <dd>

Type: **const [**LPD3DXKEY\_CALLBACK**](d3dxkey-callback.md)\***

Pointer to a [**D3DXKEY\_CALLBACK**](d3dxkey-callback.md) structure that stores user callback data.

</dd> <dt>

*ppAnimationSet* \[out\]
</dt> <dd>

Type: **[**LPD3DXCOMPRESSEDANIMATIONSET**](id3dxcompressedanimationset.md)\***

Address of a pointer to the [**ID3DXCompressedAnimationSet**](id3dxcompressedanimationset.md) interface that stores key framed animation set data in a compressed format.

</dd> </dl>

## Return value

Type: **[**HRESULT**](455d07e9-52c3-4efb-a9dc-2955cbfd38cc)**

If the function succeeds, the return value is S\_OK. If the function fails, the return value can be one of the following values: D3DERR\_INVALIDCALL, E\_OUTOFMEMORY.

## Requirements



|                    |                                                                                        |
|--------------------|----------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3dx9anim.h</dt> </dl> |
| Library<br/> | <dl> <dt>D3dx9.lib</dt> </dl>   |



## See also

<dl> <dt>

[Animation Functions](dx9-graphics-reference-d3dx-functions-animation.md)
</dt> </dl>

 

 




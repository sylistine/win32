---
Description: Subdivides faces on a mesh, allowing for conservative adaptive sampling that will not eliminate features on the mesh.
ms.assetid: 0d74a01a-de67-4607-99eb-ed98e239f199
title: ID3DXPRTEngineRobustMeshRefine method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# ID3DXPRTEngine::RobustMeshRefine method

Subdivides faces on a mesh, allowing for conservative adaptive sampling that will not eliminate features on the mesh.

## Syntax


```C++
HRESULT RobustMeshRefine(
  [in] FLOAT MinEdgeLength,
  [in] UINT  MaxSubdiv
);
```



## Parameters

<dl> <dt>

*MinEdgeLength* \[in\]
</dt> <dd>

Type: **[**FLOAT**](winprog.windows_data_types)**

Minimum face edge length that will be generated in adaptive sampling. If zero, a reasonable default value will be substituted.

</dd> <dt>

*MaxSubdiv* \[in\]
</dt> <dd>

Type: **[**UINT**](winprog.windows_data_types)**

Maximum level of subdivision of a face that will be used in adaptive sampling. If zero, a default value of 5 will be substituted.

</dd> </dl>

## Return value

Type: **[**HRESULT**](455d07e9-52c3-4efb-a9dc-2955cbfd38cc)**

If the method succeeds, the return value is S\_OK. If the method fails, the return value can be one of the following: D3DERR\_INVALIDCALL, E\_OUTOFMEMORY.

## Requirements



|                    |                                                                                        |
|--------------------|----------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3DX9Mesh.h</dt> </dl> |
| Library<br/> | <dl> <dt>D3dx9.lib</dt> </dl>   |



## See also

<dl> <dt>

[ID3DXPRTEngine](id3dxprtengine.md)
</dt> <dt>

[**ID3DXPRTEngine::ComputeBounceAdaptive**](id3dxprtengine--computebounceadaptive.md)
</dt> <dt>

[**ID3DXPRTEngine::ComputeDirectLightingSHAdaptive**](id3dxprtengine--computedirectlightingshadaptive.md)
</dt> </dl>

 

 




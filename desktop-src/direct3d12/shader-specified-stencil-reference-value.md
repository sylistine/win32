---
title: Shader Specified Stencil Reference Value
description: Enabling pixel shaders to output the Stencil Reference Value, rather than using the API-specified one, enables a very fine granular control over stencil operations.
ms.assetid: F58B1930-F12E-4FA4-A15C-A3C2B8705033
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Shader Specified Stencil Reference Value

Enabling pixel shaders to output the Stencil Reference Value, rather than using the API-specified one, enables a very fine granular control over stencil operations.

The Stencil Reference Value is normally specified by the [**ID3D12GraphicsCommandList::OMSetStencilRef**](/windows/win32/d3d12/nf-d3d12-id3d12graphicscommandlist-omsetstencilref?branch=master) method. This method sets the stencil reference value on a per-draw granularity. However, this value can be overwritten by the pixel shader.

This D3D12 (and D3D11.3) feature enables developers to read and use the Stencil Reference Value (*SV\_StencilRef*) that is output from a pixel shader, enabling a per-pixel or per-sample granularity.

The shader specified value replaces the API-specified reference value for that invocation, which means the change affects both the stencil test, and when the stencil operation D3D12\_STENCIL\_OP\_REPLACE (one member of [**D3D12\_STENCIL\_OP**](/windows/win32/D3D12/ne-d3d12-d3d12_stencil_op?branch=master)) is used to write the reference value to the stencil buffer.

This feature is optional in both D3D12 and D3D11.3. To test for its support, check the *PSSpecifiedStencilRefSupported* boolean field of [**D3D12\_FEATURE\_DATA\_D3D12\_OPTIONS**](/windows/win32/D3D12/ns-d3d12-d3d12_feature_data_d3d12_options?branch=master) using [**CheckFeatureSupport**](/windows/win32/D3D12/nf-d3d12-id3d12device-checkfeaturesupport?branch=master).

Here is an example of the use of *SV\_StencilRef* in a pixel shader:

``` syntax
float main2(float4 c : COORD) : SV_StencilRef
{
    return c;
}
```

## Related topics

<dl> <dt>

[Rendering](rendering.md)
</dt> <dt>

[Resource Binding in HLSL](resource-binding-in-hlsl.md)
</dt> <dt>

[Shader Model 5.1](https://msdn.microsoft.com/library/windows/desktop/dn933277)
</dt> <dt>

[Specifying Root Signatures in HLSL](specifying-root-signatures-in-hlsl.md)
</dt> </dl>

 

 




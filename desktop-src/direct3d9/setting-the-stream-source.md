---
Description: The IDirect3DDevice9SetStreamSource method binds a vertex buffer to a device data stream, creating an association between the vertex data and one of several data stream ports that feed the primitive processing functions.
ms.assetid: ef317537-3095-435d-b0f2-83cb3b385da2
title: Setting the Stream Source (Direct3D 9)
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Setting the Stream Source (Direct3D 9)

The [**IDirect3DDevice9::SetStreamSource**](/windows/win32/d3d9helper/nf-d3d9-idirect3ddevice9-setstreamsource?branch=master) method binds a vertex buffer to a device data stream, creating an association between the vertex data and one of several data stream ports that feed the primitive processing functions. The actual references to the stream data do not occur until a drawing method, such as [**IDirect3DDevice9::DrawPrimitive**](/windows/win32/d3d9helper/nf-d3d9-idirect3ddevice9-drawprimitive?branch=master), is called.

A stream is defined as a uniform array of component data, where each component consists of one or more elements representing a single entity such as position, normal, color, and so on. The Stride parameter specifies the size of the component, in bytes.

The following code demonstrates setting the stream source and drawing its contents. The g\_pVB variable is a LPDIRECT3DVERTEXBUFFER9 that contains vertex data.


```
if( SUCCEEDED( g_pd3dDevice->BeginScene() ) )
{
    // Setup the world, view, and projection matrices
    SetupMatrices();

    // Render the vertex buffer contents
    g_pd3dDevice->SetStreamSource( 0, g_pVB, 0, sizeof(CUSTOMVERTEX) );
    g_pd3dDevice->SetFVF( D3DFVF_CUSTOMVERTEX );
    g_pd3dDevice->DrawPrimitive( D3DPT_TRIANGLESTRIP, 0, 1 );

    // End the scene
    g_pd3dDevice->EndScene();
}
```



For more information about this code see the following tutorial: [Tutorial 3: Using Matrices](2321a1ec-73d7-7ed9-48d1-e2d09bec3217)

## Related topics

<dl> <dt>

[Rendering Primitives](rendering-primitives.md)
</dt> </dl>

 

 



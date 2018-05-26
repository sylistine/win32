---
Description: This section contains info about the structures provided by DXGI.
ms.assetid: 22e98880-bcd1-448a-9223-604fff9173fe
title: DXGI Structures
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# DXGI Structures

This section contains info about the structures provided by DXGI.

## In this section



| Topic                                                                                     | Description                                                                                                                                                                                                                                                                                                |
|-------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [**D3DCOLORVALUE**](d3dcolorvalue.md)<br/>                                         | Represents a color value with alpha, which is used for transparency. <br/>                                                                                                                                                                                                                           |
| [**DXGI\_ADAPTER\_DESC**](/windows/win32/DXGI/ns-dxgi-dxgi_adapter_desc?branch=master)<br/>                               | Describes an adapter (or video card) by using DXGI 1.0.<br/>                                                                                                                                                                                                                                         |
| [**DXGI\_ADAPTER\_DESC1**](/windows/win32/DXGI/ns-dxgi-dxgi_adapter_desc1?branch=master)<br/>                             | Describes an adapter (or video card) using DXGI 1.1.<br/>                                                                                                                                                                                                                                            |
| [**DXGI\_ADAPTER\_DESC2**](/windows/win32/DXGI1_2/ns-dxgi1_2-dxgi_adapter_desc2?branch=master)<br/>                             | Describes an adapter (or video card) that uses Microsoft DirectX Graphics Infrastructure (DXGI) 1.2.<br/>                                                                                                                                                                                            |
| [**DXGI\_ADAPTER\_DESC3**](/windows/win32/DXGI1_6/ns-dxgi1_6-dxgi_adapter_desc3?branch=master)<br/>                             | Describes an adapter (or video card) that uses DXGI 1.6.<br/>                                                                                                                                                                                                                                        |
| [**DXGI\_DECODE\_SWAP\_CHAIN\_DESC**](/windows/win32/dxgi1_3/ns-dxgi1_3-dxgi_decode_swap_chain_desc?branch=master)<br/>         | Used with [**IDXGIFactoryMedia**](/windows/win32/dxgi1_3/nn-dxgi1_3-idxgifactorymedia?branch=master)::[**CreateDecodeSwapChainForCompositionSurfaceHandle**](/windows/win32/dxgi1_3/nf-dxgi1_3-idxgifactorymedia-createdecodeswapchainforcompositionsurfacehandle?branch=master) to describe a decode swap chain.<br/>                                                                       |
| [**DXGI\_DISPLAY\_COLOR\_SPACE**](/windows/win32/dxgi/ns-dxgi-dxgi_display_color_space?branch=master)<br/>                | Don't use this structure; it is not supported and it will be removed from the header in a future release. <br/>                                                                                                                                                                                      |
| [**DXGI\_FRAME\_STATISTICS**](/windows/win32/DXGI/ns-dxgi-dxgi_frame_statistics?branch=master)<br/>                       | Describes timing and presentation statistics for a frame.<br/>                                                                                                                                                                                                                                       |
| [**DXGI\_FRAME\_STATISTICS\_MEDIA**](/windows/win32/dxgi1_3/ns-dxgi1_3-dxgi_frame_statistics_media?branch=master)<br/>          | Used to verify system approval for the app's custom present duration (custom refresh rate).<br/>                                                                                                                                                                                                     |
| [**DXGI\_GAMMA\_CONTROL**](/windows/win32/DXGI/?branch=master)<br/>                             | Controls the settings of a gamma curve.<br/>                                                                                                                                                                                                                                                         |
| [**DXGI\_GAMMA\_CONTROL\_CAPABILITIES**](/windows/win32/DXGI/?branch=master)<br/>  | Controls the gamma capabilities of an adapter.<br/>                                                                                                                                                                                                                                                  |
| [**DXGI\_HDR\_METADATA\_HDR10**](/windows/win32/dxgi1_5/ns-dxgi1_5-dxgi_hdr_metadata_hdr10?branch=master)<br/>                  | Describes the metadata for HDR10, used when video is compressed using High Efficiency Video Coding (HEVC).<br/>                                                                                                                                                                                      |
| [**DXGI\_INFO\_QUEUE\_FILTER**](/windows/win32/DXGIDebug/ns-dxgidebug-dxgi_info_queue_filter?branch=master)<br/>                    | Describes a debug message filter, which contains lists of message types to allow and deny.<br/>                                                                                                                                                                                                      |
| [**DXGI\_INFO\_QUEUE\_FILTER\_DESC**](/windows/win32/DXGIDebug/ns-dxgidebug-dxgi_info_queue_filter_desc?branch=master)<br/>         | Describes the types of messages to allow or deny to pass through a filter.<br/>                                                                                                                                                                                                                      |
| [**DXGI\_INFO\_QUEUE\_MESSAGE**](/windows/win32/DXGIDebug/ns-dxgidebug-dxgi_info_queue_message?branch=master)<br/>                  | Describes a debug message in the information queue.<br/>                                                                                                                                                                                                                                             |
| [**DXGI\_JPEG\_AC\_HUFFMAN\_TABLE**](dxgi-jpeg-ac-huffman-table.md)<br/>           | Describes a JPEG AC huffman table.<br/>                                                                                                                                                                                                                                                              |
| [**DXGI\_JPEG\_DC\_HUFFMAN\_TABLE**](dxgi-jpeg-dc-huffman-table.md)<br/>           | Describes a JPEG DC huffman table.<br/>                                                                                                                                                                                                                                                              |
| [**DXGI\_JPEG\_QUANTIZATION\_TABLE**](dxgi-jpeg-quantization-table.md)<br/>        | Describes a JPEG quantization table.<br/>                                                                                                                                                                                                                                                            |
| [**DXGI\_MATRIX\_3X2\_F**](/windows/win32/dxgi1_3/ns-dxgi1_3-dxgi_matrix_3x2_f?branch=master)<br/>                              | Represents a 3x2 matrix. Used with [**GetMatrixTransform**](/windows/win32/dxgi1_3/nf-dxgi1_3-idxgiswapchain2-getmatrixtransform?branch=master) and [**SetMatrixTransform**](/windows/win32/dxgi1_3/nf-dxgi1_3-idxgiswapchain2-setmatrixtransform?branch=master) to indicate the scaling and translation transform for [**SwapChainPanel**](w_ui_xaml_ctrl.swapchainpanel) swap chains.<br/> |
| [**DXGI\_MAPPED\_RECT**](/windows/win32/DXGI/ns-dxgi-dxgi_mapped_rect?branch=master)<br/>                                 | Describes a mapped rectangle that is used to access a surface.<br/>                                                                                                                                                                                                                                  |
| [**DXGI\_MODE\_DESC**](/windows/win32/DXGI/?branch=master)<br/>                                     | Describes a display mode.<br/>                                                                                                                                                                                                                                                                       |
| [**DXGI\_MODE\_DESC1**](/windows/win32/DXGI1_2/ns-dxgi1_2-dxgi_mode_desc1?branch=master)<br/>                                   | Describes a display mode and whether the display mode supports stereo.<br/>                                                                                                                                                                                                                          |
| [**DXGI\_OUTPUT\_DESC**](/windows/win32/DXGI/ns-dxgi-dxgi_output_desc?branch=master)<br/>                                 | Describes an output or physical connection between the adapter (video card) and a device.<br/>                                                                                                                                                                                                       |
| [**DXGI\_OUTPUT\_DESC1**](/windows/win32/DXGI1_6/ns-dxgi1_6-dxgi_output_desc1?branch=master)<br/>                               | Describes an output or physical connection between the adapter (video card) and a device, including additional information about color capabilities and connection type.<br/>                                                                                                                        |
| [**DXGI\_OUTDUPL\_DESC**](/windows/win32/DXGI1_2/ns-dxgi1_2-dxgi_outdupl_desc?branch=master)<br/>                               | The DXGI\_OUTDUPL\_DESC structure describes the dimension of the output and the surface that contains the desktop image. The format of the desktop image is always [**DXGI\_FORMAT\_B8G8R8A8\_UNORM**](direct3ddxgi.dxgi_format#dxgi-format-b8g8r8a8-unorm).<br/>         |
| [**DXGI\_OUTDUPL\_FRAME\_INFO**](/windows/win32/DXGI1_2/ns-dxgi1_2-dxgi_outdupl_frame_info?branch=master)<br/>                  | The [**DXGI\_OUTDUPL\_FRAME\_INFO**](/windows/win32/DXGI1_2/ns-dxgi1_2-dxgi_outdupl_frame_info?branch=master) structure describes the current desktop image.<br/>                                                                                                                                                                                |
| [**DXGI\_OUTDUPL\_MOVE\_RECT**](/windows/win32/DXGI1_2/ns-dxgi1_2-dxgi_outdupl_move_rect?branch=master)<br/>                    | The [**DXGI\_OUTDUPL\_MOVE\_RECT**](/windows/win32/DXGI1_2/ns-dxgi1_2-dxgi_outdupl_move_rect?branch=master) structure describes the movement of a rectangle.<br/>                                                                                                                                                                                |
| [**DXGI\_OUTDUPL\_POINTER\_POSITION**](/windows/win32/DXGI1_2/ns-dxgi1_2-dxgi_outdupl_pointer_position?branch=master)<br/>      | The [**DXGI\_OUTDUPL\_POINTER\_POSITION**](/windows/win32/DXGI1_2/ns-dxgi1_2-dxgi_outdupl_pointer_position?branch=master) structure describes the position of the hardware cursor.<br/>                                                                                                                                                          |
| [**DXGI\_OUTDUPL\_POINTER\_SHAPE\_INFO**](/windows/win32/DXGI1_2/ns-dxgi1_2-dxgi_outdupl_pointer_shape_info?branch=master)<br/> | The [**DXGI\_OUTDUPL\_POINTER\_SHAPE\_INFO**](/windows/win32/DXGI1_2/ns-dxgi1_2-dxgi_outdupl_pointer_shape_info?branch=master) structure describes information about the cursor shape.<br/>                                                                                                                                                      |
| [**DXGI\_PRESENT\_PARAMETERS**](/windows/win32/DXGI1_2/ns-dxgi1_2-dxgi_present_parameters?branch=master)<br/>                   | Describes information about present that helps the operating system optimize presentation.<br/>                                                                                                                                                                                                      |
| [**DXGI\_QUERY\_VIDEO\_MEMORY\_INFO**](/windows/win32/dxgi1_4/ns-dxgi1_4-dxgi_query_video_memory_info?branch=master)<br/>       | Describes the current video memory budgeting parameters.<br/>                                                                                                                                                                                                                                        |
| [**DXGI\_RATIONAL**](/windows/win32/dxgicommon/ns-dxgicommon-dxgi_rational?branch=master)<br/>                                        | Represents a rational number.<br/>                                                                                                                                                                                                                                                                   |
| [**DXGI\_RGB**](/windows/win32/DXGI/?branch=master)<br/>                                                  | Represents an RGB color.<br/>                                                                                                                                                                                                                                                                        |
| [**DXGI\_RGBA**](dxgi-rgba.md)<br/>                                                | Represents a color value with alpha, which is used for transparency. <br/>                                                                                                                                                                                                                           |
| [**DXGI\_SAMPLE\_DESC**](/windows/win32/dxgicommon/ns-dxgicommon-dxgi_sample_desc?branch=master)<br/>                                 | Describes multi-sampling parameters for a resource.<br/>                                                                                                                                                                                                                                             |
| [**DXGI\_SHARED\_RESOURCE**](/windows/win32/DXGI/ns-dxgi-dxgi_shared_resource?branch=master)<br/>                         | Represents a handle to a shared resource.<br/>                                                                                                                                                                                                                                                       |
| [**DXGI\_SURFACE\_DESC**](/windows/win32/DXGI/ns-dxgi-dxgi_surface_desc?branch=master)<br/>                               | Describes a surface.<br/>                                                                                                                                                                                                                                                                            |
| [**DXGI\_SWAP\_CHAIN\_DESC**](/windows/win32/DXGI/ns-dxgi-dxgi_swap_chain_desc?branch=master)<br/>                        | Describes a swap chain.<br/>                                                                                                                                                                                                                                                                         |
| [**DXGI\_SWAP\_CHAIN\_DESC1**](/windows/win32/DXGI1_2/ns-dxgi1_2-dxgi_swap_chain_desc1?branch=master)<br/>                      | Describes a swap chain.<br/>                                                                                                                                                                                                                                                                         |
| [**DXGI\_SWAP\_CHAIN\_FULLSCREEN\_DESC**](/windows/win32/DXGI1_2/ns-dxgi1_2-dxgi_swap_chain_fullscreen_desc?branch=master)<br/> | Describes full-screen mode for a swap chain.<br/>                                                                                                                                                                                                                                                    |
| [**\_LUID**](/windows/win32/dxgi/ns-dxgi-_luid?branch=master)<br/>                                                        | Describes a local identifier for an adapter.<br/>                                                                                                                                                                                                                                                    |



 

## Related topics

<dl> <dt>

[DXGI Reference](d3d10-graphics-reference-dxgi.md)
</dt> </dl>

 

 




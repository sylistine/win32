---
Description: Instead of drawing a line or curve with a solid color, you can draw with a texture.
ms.assetid: 326170a5-d21f-49d6-9f60-10b9bc8d97b4
title: Drawing a Line Filled with a Texture
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Drawing a Line Filled with a Texture

Instead of drawing a line or curve with a solid color, you can draw with a texture. To draw lines and curves with a texture, create a [**TextureBrush**](/windows/win32/gdiplusbrush/nl-gdiplusbrush-texturebrush?branch=master) object, and pass the address of that **TextureBrush** object to a [**Pen**](/windows/win32/gdipluspen/nl-gdipluspen-pen?branch=master) constructor. The image associated with the texture brush is used to tile the plane (invisibly), and when the pen draws a line or curve, the stroke of the pen uncovers certain pixels of the tiled texture.

The following example creates an [**Image**](/windows/win32/gdiplusheaders/nl-gdiplusheaders-image?branch=master) object from the file Texture1.jpg. That image is used to construct a [**TextureBrush**](/windows/win32/gdiplusbrush/nl-gdiplusbrush-texturebrush?branch=master) object, and the **TextureBrush** object is used to construct a [**Pen**](/windows/win32/gdipluspen/nl-gdipluspen-pen?branch=master) object. The call to [**Graphics::DrawImage**](/windows/win32/Gdiplusgraphics/?branch=master) draws the image with its upper-left corner at (0, 0). The call to [**Graphics::DrawEllipse**](/windows/win32/Gdiplusgraphics/?branch=master) uses the **Pen** object to draw a textured ellipse.


```
Image         image(L"Texture1.jpg");
TextureBrush  tBrush(&amp;image);
Pen           texturedPen(&amp;tBrush, 30);

graphics.DrawImage(&amp;image, 0, 0, image.GetWidth(), image.GetHeight());
graphics.DrawEllipse(&amp;texturedPen, 100, 20, 200, 100);
```



The following illustration shows the image and the textured ellipse.

![illustration showing a small rectangular image, then an elliptical line segment filled with the original image](images/pens7.png)

 

 



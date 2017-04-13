---
title: "Recortar y ajustar la escala de las im&#225;genes en GDI+ | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "comprimir datos, imágenes"
  - "GDI+, recortar imágenes"
  - "GDI+, ajustar la escala de las imágenes"
  - "imágenes [Windows Forms], compresión"
  - "imágenes [Windows Forms], recortar"
  - "imágenes [Windows Forms], expansión"
  - "imágenes [Windows Forms], ajustar la escala"
  - "rectángulos, de destino"
  - "rectángulos, de origen"
ms.assetid: ad5daf26-005f-45bc-a2af-e0e97777a21a
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Recortar y ajustar la escala de las im&#225;genes en GDI+
Puede utilizar el método <xref:System.Drawing.Graphics.DrawImage%2A> de la clase <xref:System.Drawing.Graphics> para dibujar y colocar imágenes vectoriales e imágenes de trama.  <xref:System.Drawing.Graphics.DrawImage%2A> es un método sobrecargado, por lo que existen varias formas de suministrar argumentos a dicho método.  
  
## Variaciones de DrawImage  
 Una variación del método <xref:System.Drawing.Graphics.DrawImage%2A> recibe <xref:System.Drawing.Bitmap> y <xref:System.Drawing.Rectangle>.  El rectángulo especifica el destino para la operación de dibujo, es decir, especifica el rectángulo en el que se va a dibujar la imagen.  Si el tamaño del rectángulo de destino difiere del tamaño de la imagen original, se ajusta la escala de la imagen para que encaje en el rectángulo de destino.  En el siguiente ejemplo de código se muestra cómo dibujar la misma imagen tres veces: una sin ajuste de escala, otra con una expansión y otra con una compresión:  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 En la siguiente ilustración se muestran las tres imágenes.  
  
 ![Cambiar escala](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art06.png "AboutGdip03\_Art06")  
  
 Algunas variaciones del método <xref:System.Drawing.Graphics.DrawImage%2A> tienen, además de un parámetro de rectángulo de destino, un parámetro de rectángulo de origen.  El parámetro de rectángulo de origen especifica la parte de la imagen original que se va a dibujar.  El rectángulo de destino especifica el rectángulo en el que se va a dibujar dicha parte de la imagen.  Si el tamaño del rectángulo de destino difiere del tamaño del rectángulo de origen, se ajusta la escala de la imagen para que encaje en el rectángulo de destino.  
  
 El siguiente ejemplo de código muestra cómo crear un objeto <xref:System.Drawing.Bitmap> a partir del archivo Runner.jpg.  Toda la imagen se dibuja sin ajuste de escala en \(0, 0\).  Después, se dibuja una pequeña parte de la imagen dos veces: una vez con una compresión y otra vez con una expansión.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 En la siguiente ilustración se muestra la imagen sin ajuste de escala, y la parte comprimida y expandida de la imagen.  
  
 ![Recortar y ajustar la escala](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art07.png "AboutGdip03\_Art07")  
  
## Vea también  
 [Imágenes, mapas de bits y metarchivos](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [Trabajar con imágenes, mapas de bits, iconos y metarchivos](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
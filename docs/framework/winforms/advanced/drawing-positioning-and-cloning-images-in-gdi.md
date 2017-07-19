---
title: "Dibujar, colocar y clonar im&#225;genes en GDI+ | Microsoft Docs"
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
  - "dibujar, imágenes"
  - "dibujar, imágenes de trama"
  - "GDI+, clonar imágenes"
  - "GDI+, dibujar imágenes"
  - "GDI+, colocar imágenes"
  - "imágenes [Windows Forms], clonar"
  - "imágenes [Windows Forms], dibujar"
  - "imágenes [Windows Forms], colocar"
  - "imágenes de trama"
ms.assetid: 09f0c07a-19c0-43b4-90a2-862a10545ce8
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Dibujar, colocar y clonar im&#225;genes en GDI+
La clase <xref:System.Drawing.Bitmap> puede utilizarse para cargar y mostrar imágenes de tramas y la clase <xref:System.Drawing.Imaging.Metafile> puede utilizarse para cargar y mostrar imágenes vectoriales.  Las clases <xref:System.Drawing.Bitmap> y <xref:System.Drawing.Imaging.Metafile> heredan de la clase <xref:System.Drawing.Image>.  Para mostrar una imagen vectorial, necesita una instancia de la clase <xref:System.Drawing.Graphics> y <xref:System.Drawing.Imaging.Metafile>.  Para mostrar una imagen de tramas, necesita una instancia de la clase <xref:System.Drawing.Graphics> y <xref:System.Drawing.Bitmap>.  La instancia de la clase <xref:System.Drawing.Graphics> proporciona el método <xref:System.Drawing.Graphics.DrawImage%2A>, que recibe <xref:System.Drawing.Imaging.Metafile> o <xref:System.Drawing.Bitmap> como argumento.  
  
## Tipos de archivos y clonación  
 En el siguiente ejemplo de código se muestra cómo se construye un objeto <xref:System.Drawing.Bitmap> desde el archivo Climber.jpg y se muestra el mapa de bits.  El punto de destino de la esquina superior izquierda de la imagen, \(10, 10\), se especifica en el segundo y tercer parámetros.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#11)]  
  
 En la siguiente ilustración se muestra la imagen.  
  
 ![Ejemplo de imagen](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art04.png "AboutGdip03\_Art04")  
  
 Se pueden construir objetos <xref:System.Drawing.Bitmap> a partir de diversos formatos de archivos de gráficos: BMP, GIF, JPEG, EXIF, PNG, TIFF e ICON.  
  
 En el siguiente ejemplo de código se muestra cómo se construyen objetos <xref:System.Drawing.Bitmap> a partir de diversos tipos de archivo y después se muestran los mapas de bits.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#12)]  
  
 La clase <xref:System.Drawing.Bitmap> proporciona un método <xref:System.Drawing.Bitmap.Clone%2A> que puede utilizarse para hacer una copia de un objeto <xref:System.Drawing.Bitmap> existente.  El método <xref:System.Drawing.Bitmap.Clone%2A> tiene un parámetro de rectángulo de origen que puede utilizarse para especificar la parte del mapa de bits original que se desea copiar.  En el ejemplo de código siguiente se muestra cómo crear un objeto <xref:System.Drawing.Bitmap> clonando la mitad superior de un objeto <xref:System.Drawing.Bitmap> existente.  Después, se dibujan ambas imágenes.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#13)]  
  
 En la siguiente ilustración se muestran las dos imágenes.  
  
 ![Recortar](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art05.png "AboutGdip03\_Art05")  
  
## Vea también  
 [Imágenes, mapas de bits y metarchivos](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [Cómo: Crear objetos Graphics para dibujar](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [Trabajar con imágenes, mapas de bits, iconos y metarchivos](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
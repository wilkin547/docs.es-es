---
title: "C&#243;mo: Codificar un objeto Visual en un archivo de imagen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "codificar formatos de imagen"
  - "archivos de imagen, codificar a partir de elementos visuales"
  - "elementos visuales, codificar en un archivo de imagen"
ms.assetid: 2036385b-ea47-4d54-8027-5797f52c8149
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# C&#243;mo: Codificar un objeto Visual en un archivo de imagen
En este ejemplo se muestra cómo codificar un objeto <xref:System.Windows.Media.Visual> en un archivo de imagen utilizando un objeto <xref:System.Windows.Media.Imaging.RenderTargetBitmap> y un objeto <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.  
  
## Ejemplo  
 <xref:System.Windows.Media.DrawingVisual> se crea utilizando los objetos <xref:System.Windows.Media.Imaging.BitmapImage> y <xref:System.Windows.Media.FormattedText>, que se representa en un objeto <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.  A continuación, el mapa de bits representado se utiliza para crear un objeto <xref:System.Windows.Media.Imaging.BitmapFrame> que se agrega a <xref:System.Windows.Media.Imaging.PngBitmapEncoder> para crear un nuevo archivo [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)].  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 En este ejemplo se ha utilizado un objeto <xref:System.Windows.Media.Imaging.PngBitmapEncoder>, pero podría utilizarse cualquiera de los objetos derivados de <xref:System.Windows.Media.Imaging.BitmapEncoder> para crear el archivo de imagen.  
  
## Vea también  
 <xref:System.Windows.Media.DrawingContext>   
 [Información general sobre imágenes](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)   
 [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [Usar objetos DrawingVisual](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)
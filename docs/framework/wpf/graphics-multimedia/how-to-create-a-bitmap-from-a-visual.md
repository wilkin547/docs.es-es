---
title: "C&#243;mo: Crear un mapa de bits desde un objeto Visual | Microsoft Docs"
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
  - "mapas de bits, representar a partir de elementos visuales"
  - "elementos visuales, representar en mapas de bits"
ms.assetid: 103fc7f5-7306-4026-9d61-2005e79959f3
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Crear un mapa de bits desde un objeto Visual
En este ejemplo se muestra cómo crear un mapa de bits a partir de un objeto <xref:System.Windows.Media.Visual>.  Un objeto <xref:System.Windows.Media.DrawingVisual> se representa con <xref:System.Windows.Media.FormattedText>.  A continuación, <xref:System.Windows.Media.Visual> se representa en <xref:System.Windows.Media.Imaging.RenderTargetBitmap>, con lo que se crea un mapa de bits del texto de que se trate.  
  
## Ejemplo  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#CreateRTBImage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample.cs#creatertbimage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#CreateRTBImage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample.vb#creatertbimage)]  
  
## Vea también  
 <xref:System.Windows.Media.DrawingContext>   
 [Información general sobre imágenes](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)   
 [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [Usar objetos DrawingVisual](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)
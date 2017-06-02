---
title: "C&#243;mo: Codificar y descodificar una imagen GIF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "descodificar imágenes GIF"
  - "descodificar formatos de imagen"
  - "codificar imágenes GIF"
  - "codificar formatos de imagen"
  - "descodificación de GIF"
  - "codificación de GIF"
ms.assetid: 9cdd9ec7-71eb-444b-b9e3-991958461163
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Codificar y descodificar una imagen GIF
En los ejemplos siguientes, se muestra cómo descodificar y codificar una imagen [!INCLUDE[TLA#tla_gif](../../../../includes/tlasharptla-gif-md.md)] mediante los objetos <xref:System.Windows.Media.Imaging.GifBitmapDecoder> y <xref:System.Windows.Media.Imaging.GifBitmapEncoder> específicos.  
  
## Ejemplo  
 En este ejemplo se muestra cómo descodificar una imagen [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] utilizando un <xref:System.Windows.Media.Imaging.GifBitmapDecoder> desde un <xref:System.IO.FileStream>.  
  
 [!code-cpp[GifBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#1)]
 [!code-csharp[GifBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#1)]
 [!code-vb[GifBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#1)]  
  
## Ejemplo  
 En este ejemplo se muestra cómo codificar un <xref:System.Windows.Media.Imaging.BitmapSource> en una imagen [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] utilizando un <xref:System.Windows.Media.Imaging.GifBitmapEncoder>.  
  
 [!code-cpp[GifBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#4)]
 [!code-csharp[GifBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#4)]
 [!code-vb[GifBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#4)]  
  
## Vea también  
 [Información general sobre imágenes](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
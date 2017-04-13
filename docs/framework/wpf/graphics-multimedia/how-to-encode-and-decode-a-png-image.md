---
title: "C&#243;mo: Codificar y descodificar una imagen PNG | Microsoft Docs"
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
  - "descodificar formatos de imagen"
  - "descodificar imágenes PNG"
  - "codificar formatos de imagen"
  - "codificar imágenes PNG"
  - "descodificación de PNG"
  - "codificación de PNG"
ms.assetid: 3d31d186-af73-47f0-b5a7-c26ae46409a6
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Codificar y descodificar una imagen PNG
En los ejemplos siguientes, se muestra cómo descodificar y codificar una imagen [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] mediante los objetos <xref:System.Windows.Media.Imaging.PngBitmapDecoder> y <xref:System.Windows.Media.Imaging.PngBitmapEncoder> específicos.  
  
## Ejemplo  
 En este ejemplo se muestra cómo descodificar una imagen [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)] utilizando un <xref:System.Windows.Media.Imaging.PngBitmapDecoder> desde un <xref:System.IO.FileStream>.  
  
 [!code-cpp[PngBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CPP/PngEncoderDecoder.cpp#1)]
 [!code-csharp[PngBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CSharp/PngEncoderDecoder.cs#1)]
 [!code-vb[PngBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PngBitmapDecoderEncoder/VB/PngEncoderDecoder.vb#1)]  
  
## Ejemplo  
 En este ejemplo se muestra cómo codificar un <xref:System.Windows.Media.Imaging.BitmapSource> en una imagen [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)] utilizando un <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.  
  
 [!code-cpp[PngBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CPP/PngEncoderDecoder.cpp#4)]
 [!code-csharp[PngBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CSharp/PngEncoderDecoder.cs#4)]
 [!code-vb[PngBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PngBitmapDecoderEncoder/VB/PngEncoderDecoder.vb#4)]  
  
## Vea también  
 [Información general sobre imágenes](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
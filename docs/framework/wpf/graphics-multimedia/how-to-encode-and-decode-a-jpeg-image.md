---
title: "C&#243;mo: Codificar y descodificar una imagen JPEG | Microsoft Docs"
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
  - "descodificar imágenes JPEG"
  - "codificar formatos de imagen"
  - "codificar imágenes JPEG"
  - "descodificación de JPEG"
  - "codificación de JPEG"
ms.assetid: b8cfde37-9f68-4911-a05e-51d8d7bdec7b
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Codificar y descodificar una imagen JPEG
En los ejemplos siguientes, se muestra cómo descodificar y codificar una imagen [!INCLUDE[TLA#tla_jpeg](../../../../includes/tlasharptla-jpeg-md.md)] mediante los objetos <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> y <xref:System.Windows.Media.Imaging.JpegBitmapEncoder> específicos.  
  
## Ejemplo  
 En este ejemplo se muestra cómo descodificar una imagen [!INCLUDE[TLA2#tla_jpeg](../../../../includes/tla2sharptla-jpeg-md.md)] utilizando un <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> desde un <xref:System.IO.FileStream>.  
  
 [!code-cpp[JpegBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CPP/jpegencoderdecoder.cpp#1)]
 [!code-csharp[JpegBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CSharp/JpegEncoderDecoder.cs#1)]
 [!code-vb[JpegBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/VB/JpegEncoderDecoder.vb#1)]  
  
## Ejemplo  
 En este ejemplo se muestra cómo codificar un <xref:System.Windows.Media.Imaging.BitmapSource> en una imagen [!INCLUDE[TLA2#tla_jpeg](../../../../includes/tla2sharptla-jpeg-md.md)] utilizando un <xref:System.Windows.Media.Imaging.JpegBitmapEncoder>.  
  
 [!code-cpp[JpegBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CPP/jpegencoderdecoder.cpp#4)]
 [!code-csharp[JpegBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CSharp/JpegEncoderDecoder.cs#4)]
 [!code-vb[JpegBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/VB/JpegEncoderDecoder.vb#4)]  
  
## Seguridad de .NET Framework  
  
## Vea también  
 [Información general sobre imágenes](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
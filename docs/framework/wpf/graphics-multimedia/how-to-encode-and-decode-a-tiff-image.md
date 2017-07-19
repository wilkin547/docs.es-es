---
title: "C&#243;mo: Codificar y descodificar una imagen TIFF | Microsoft Docs"
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
  - "descodificar imágenes TIFF"
  - "codificar formatos de imagen"
  - "codificar imágenes TIFF"
  - "descodificación de TIFF"
  - "codificación de TIFF"
ms.assetid: 1dfe3209-fc73-40e6-ad1c-71c1c58b3364
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Codificar y descodificar una imagen TIFF
En los ejemplos siguientes, se muestra cómo descodificar y codificar una imagen [!INCLUDE[TLA#tla_tiff](../../../../includes/tlasharptla-tiff-md.md)] mediante los objetos <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> y <xref:System.Windows.Media.Imaging.TiffBitmapEncoder> específicos.  
  
## Ejemplo  
 En este ejemplo se muestra cómo descodificar una imagen [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] utilizando un <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> desde un <xref:System.Uri>.  
  
 [!code-cpp[TiffBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#1)]
 [!code-csharp[TiffBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#1)]
 [!code-vb[TiffBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#1)]  
  
## Ejemplo  
 En este ejemplo se muestra cómo codificar un <xref:System.Windows.Media.Imaging.BitmapSource> en una imagen [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] utilizando un <xref:System.Windows.Media.Imaging.TiffBitmapEncoder>.  
  
 [!code-cpp[TiffBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#4)]
 [!code-csharp[TiffBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#4)]
 [!code-vb[TiffBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#4)]  
  
## Vea también  
 [Información general sobre imágenes](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
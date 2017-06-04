---
title: "C&#243;mo: Recortar una imagen | Microsoft Docs"
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
  - "clases, CroppedBitmap"
  - "CroppedBitmap (clase)"
  - "recortar imágenes"
  - "imágenes, recortar"
ms.assetid: c6bba109-c6e7-4cf8-bfe6-9cf8d01bb4fc
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Recortar una imagen
En este ejemplo se muestra cómo recortar una imagen mediante <xref:System.Windows.Media.Imaging.CroppedBitmap>.  
  
 <xref:System.Windows.Media.Imaging.CroppedBitmap> se utiliza principalmente para codificar una versión recortada de una imagen a fin de guardarla en un archivo.  Para recortar una imagen con fines de presentación, vea el tema [Create a Clip Region](http://msdn.microsoft.com/es-es/56e4bed6-78d7-4292-b917-d72d0b3e4376).  
  
## Ejemplo  
 El marcado [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] siguiente define los recursos utilizados en los ejemplos siguientes.  
  
 [!code-xml[imageelementexample#CroppedXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml1)]  
  
 En el ejemplo siguiente se crea una imagen utilizando <xref:System.Windows.Media.Imaging.CroppedBitmap> como su origen.  
  
 [!code-xml[imageelementexample#CroppedXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml2)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp1)]
 [!code-vb[imageelementexample#CroppedCSharp1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp1)]  
  
 <xref:System.Windows.Media.Imaging.CroppedBitmap> también se puede utilizar como origen de otro objeto <xref:System.Windows.Media.Imaging.CroppedBitmap>, de modo que se encadena el recorte.  Observe que <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> utiliza valores que son relativos al mapa de bits recortado de origen, no a la imagen inicial.  
  
 [!code-xml[imageelementexample#CroppedXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml3)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp2)]
 [!code-vb[imageelementexample#CroppedCSharp2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp2)]  
  
## Vea también  
 [Create a Clip Region](http://msdn.microsoft.com/es-es/56e4bed6-78d7-4292-b917-d72d0b3e4376)
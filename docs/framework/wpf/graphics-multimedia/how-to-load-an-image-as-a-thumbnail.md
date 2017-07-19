---
title: "C&#243;mo: Cargar una imagen como una miniatura | Microsoft Docs"
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
  - "imágenes, cargar como vistas en miniatura"
  - "cargar imágenes como vistas en miniatura"
  - "vistas en miniatura, cargar imágenes como"
ms.assetid: 02e055a0-54df-499a-b8b6-ab6ff7535cff
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Cargar una imagen como una miniatura
En los ejemplos siguientes se muestra cómo cargar un control <xref:System.Windows.Controls.Image> como una miniatura para conservar la memoria de la aplicación.  
  
## Ejemplo  
 En el ejemplo siguiente se establece la propiedad <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> de <xref:System.Windows.Media.Imaging.BitmapImage> en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] a fin de reducir la memoria necesaria para cargar la imagen.  
  
 [!code-xml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## Ejemplo  
 En el ejemplo siguiente se establece la propiedad <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> de un objeto <xref:System.Windows.Media.Imaging.BitmapImage> mediante código a fin de reducir la memoria necesaria para cargar la imagen.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## Vea también  
 [Información general sobre imágenes](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
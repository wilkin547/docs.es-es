---
title: "C&#243;mo: Pintar un &#225;rea con una imagen | Microsoft Docs"
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
  - "pinceles, pintar con imágenes"
  - "imágenes, pintar con"
  - "dibujar, con imágenes"
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Pintar un &#225;rea con una imagen
En este ejemplo se muestra cómo utilizar la clase <xref:System.Windows.Media.ImageBrush> para pintar una área con una imagen.  Un <xref:System.Windows.Media.ImageBrush> muestra una imagen única, que se especifica mediante su propiedad <xref:System.Windows.Media.ImageBrush.ImageSource%2A>.  
  
## Ejemplo  
 En el ejemplo siguiente se pinta el fondo \(<xref:System.Windows.Controls.Control.Background%2A>\) de un botón mediante <xref:System.Windows.Media.ImageBrush>.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 De manera predeterminada, <xref:System.Windows.Media.ImageBrush> ajusta su imagen hasta rellenar completamente el área que se está pintando.  En el ejemplo anterior, la imagen se ajusta hasta rellenar el botón, lo que puede distorsionar la imagen.  Puede controlar este comportamiento estableciendo la propiedad <xref:System.Windows.Media.TileBrush.Stretch%2A> de <xref:System.Windows.Media.TileBrush> en <xref:System.Windows.Media.Stretch> o <xref:System.Windows.Media.Stretch>, para que el pincel conserve la [relación de aspecto](GTMT) de la imagen.  
  
 Si establece las propiedades <xref:System.Windows.Media.TileBrush.Viewport%2A> y <xref:System.Windows.Media.TileBrush.TileMode%2A> de <xref:System.Windows.Media.ImageBrush>, puede crear un patrón que se repite.  En el ejemplo siguiente se pinta un botón mediante un patrón creado a partir de una imagen.  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 Para obtener más información sobre la clase <xref:System.Windows.Media.ImageBrush>, vea [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
 Este ejemplo de código forma parte de un ejemplo más extenso proporcionado para la clase <xref:System.Windows.Media.ImageBrush>.  Para obtener el ejemplo completo, vea [ImageBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160005).  
  
## Vea también  
 [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
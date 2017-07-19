---
title: "C&#243;mo: Pintar un &#225;rea con un degradado lineal | Microsoft Docs"
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
  - "pinceles, pintar con degradados lineales"
  - "degradados lineales, pintar con"
  - "dibujar, con degradados lineales"
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Pintar un &#225;rea con un degradado lineal
En este ejemplo se muestra cómo utilizar la clase <xref:System.Windows.Media.LinearGradientBrush> para pintar una área con un degradado lineal.  En el ejemplo siguiente, la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> de <xref:System.Windows.Shapes.Rectangle> se pinta con un degradado lineal diagonal que efectúa una transición del amarillo al rojo, al azul y al verde esmeralda.  
  
## Ejemplo  
 [!code-xml[GradientBrushExamples_snip#DiagonalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 En la ilustración siguiente se muestra el degradado creado en el ejemplo anterior.  
  
 ![Degradado lineal diagonal](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-diagonallgb.png "graphicsmm\_DiagonalLGB")  
  
 Para crear un degradado lineal horizontal, cambie las propiedades <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> y <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> de <xref:System.Windows.Media.LinearGradientBrush> a \(0,0.5\) y \(1,0.5\).  En el ejemplo siguiente, se pinta un objeto <xref:System.Windows.Shapes.Rectangle> con un degradado lineal horizontal.  
  
 [!code-xml[GradientBrushExamples_snip#HorizontalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 En la ilustración siguiente se muestra el degradado creado en el ejemplo anterior.  
  
 ![Degradado lineal horizontal](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-horizontallgb.png "graphicsmm\_HorizontalLGB")  
  
 Para crear un degradado lineal vertical, cambie las propiedades <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> y <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> de <xref:System.Windows.Media.LinearGradientBrush> a \(0.5,0\) y \(0.5,1\).  En el ejemplo siguiente, se pinta un objeto <xref:System.Windows.Shapes.Rectangle> con un degradado lineal vertical.  
  
 [!code-xml[GradientBrushExamples_snip#VerticalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 En la ilustración siguiente se muestra el degradado creado en el ejemplo anterior.  
  
 ![Degradado lineal vertical](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-verticallgb.png "graphicsmm\_VerticalLGB")  
  
> [!NOTE]
>  Los ejemplos de este tema utilizan el sistema de coordenadas predeterminado para establecer los puntos inicial y final.  El sistema de coordenadas predeterminado es relativo a un rectángulo de selección: 0 indica un 0 por ciento del rectángulo de selección y 1, un 100 por cien del mismo.  Puede cambiar este sistema de coordenadas estableciendo la propiedad <xref:System.Windows.Media.GradientBrush.MappingMode%2A> en el valor <xref:System.Windows.Media.BrushMappingMode?displayProperty=fullName>.  Un sistema de coordenadas absoluto no es relativo respecto a ningún rectángulo de selección.  Los valores se interpretan directamente en el espacio local.  
  
 Para obtener más ejemplos, vea [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).  Para obtener más información sobre los degradados y otros tipos de pinceles, vea [Información general sobre el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).
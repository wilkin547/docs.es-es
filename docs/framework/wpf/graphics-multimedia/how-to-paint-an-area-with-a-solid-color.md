---
title: "C&#243;mo: Pintar un &#225;rea con un color s&#243;lido | Microsoft Docs"
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
  - "pinceles, pintar colores sólidos"
  - "dibujar, con colores sólidos"
  - "colores sólidos, pintar con"
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Pintar un &#225;rea con un color s&#243;lido
Para pintar una área con un color sólido, puede utilizar un pincel predefinido del sistema, como <xref:System.Windows.Media.Brushes.Red%2A> o <xref:System.Windows.Media.Brushes.Blue%2A>o puede crear un nuevo <xref:System.Windows.Media.SolidColorBrush> y describir su propiedad <xref:System.Windows.Media.SolidColorBrush.Color%2A> mediante sus valores de alfa, rojo, verde y azul.  En XAML, puede pintar también una área con un color sólido utilizando la notación hexadecimal.  
  
 En los ejemplos siguientes se utilizan cada una de estas técnicas para pintar un objeto <xref:System.Windows.Shapes.Rectangle> de azul.  
  
## Ejemplo  
 **Utilizar un pincel predefinido**  
  
 En el ejemplo siguiente se utiliza la propiedad <xref:System.Windows.Media.Brushes.Blue%2A> del pincel predefinido para pintar un rectángulo de azul.  
  
 [!code-xml[brushsamples_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 **Utilizar la notación hexadecimal**  
  
 En el ejemplo siguiente se utiliza la notación hexadecimal de 8 dígitos para pintar un rectángulo de azul.  
  
 [!code-xml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 **Utilizar los valores ARGB**  
  
 En el ejemplo siguiente se crea un objeto <xref:System.Windows.Media.SolidColorBrush> y se describe su propiedad <xref:System.Windows.Media.SolidColorBrush.Color%2A> utilizando los valores ARGB para el color azul.  
  
 [!code-xml[brushsamples_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 Para obtener otras maneras de describir colores, vea la estructura <xref:System.Windows.Media.Color>.  
  
 **Temas relacionados**  
  
 Para obtener más información acerca de <xref:System.Windows.Media.SolidColorBrush> y más ejemplos, vea [Información general sobre el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
 Este ejemplo de código forma parte de un ejemplo más extenso referente a la clase <xref:System.Windows.Media.SolidColorBrush>.  Para obtener el ejemplo completo, vea [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).  
  
## Vea también  
 <xref:System.Windows.Media.Brushes>
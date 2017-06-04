---
title: "C&#243;mo: Pintar un &#225;rea con un degradado radial | Microsoft Docs"
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
  - "pinceles, pintar con degradados radiales"
  - "dibujar, con degradados radiales"
  - "degradados radiales, pintar con"
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Pintar un &#225;rea con un degradado radial
En este ejemplo se muestra cómo utilizar la clase <xref:System.Windows.Media.RadialGradientBrush> para pintar una área con un degradado radial.  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza <xref:System.Windows.Media.RadialGradientBrush> para pintar un rectángulo con un degradado radial que efectúa una transición del amarillo al rojo, al azul y al verde esmeralda.  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 En la ilustración siguiente, se ve el degradado del ejemplo anterior.  Se han resaltado los puntos de degradado.  
  
 ![Delimitadores de degradado en un degradado radial](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk\_graphicsmm\_4gradientstops\_rg")  
  
> [!NOTE]
>  En los ejemplos de este tema se utiliza el sistema de coordenadas predeterminado para establecer los puntos de control.  El sistema de coordenadas predeterminado es relativo a un rectángulo de selección: 0 indica un 0 por ciento del rectángulo de selección y 1, un 100 por cien del mismo.  Puede cambiar este sistema de coordenadas estableciendo la propiedad <xref:System.Windows.Media.GradientBrush.MappingMode%2A> en el valor <xref:System.Windows.Media.BrushMappingMode>.  Un sistema de coordenadas absoluto no es relativo respecto a ningún rectángulo de selección.  Los valores se interpretan directamente en el espacio local.  
  
 Para obtener más ejemplos de <xref:System.Windows.Media.RadialGradientBrush>, vea [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).  Para obtener más información sobre los degradados y otros tipos de pinceles, vea [Información general sobre el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).
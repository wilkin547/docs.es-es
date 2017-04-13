---
title: "C&#243;mo: Animar el color o la opacidad de un objeto SolidColorBrush | Microsoft Docs"
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
  - "animación, color de SolidColorBrush"
  - "animación, opacidad de SolidColorBrush"
  - "colores, animar"
  - "opacidad, animar"
  - "SolidColorBrush, animar el color de"
  - "SolidColorBrush, animar la opacidad de"
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Animar el color o la opacidad de un objeto SolidColorBrush
En este ejemplo se muestra cómo animar las propiedades <xref:System.Windows.Media.SolidColorBrush.Color%2A> y <xref:System.Windows.Media.Brush.Opacity%2A> de un objeto <xref:System.Windows.Media.SolidColorBrush>.  
  
## Ejemplo  
 En el ejemplo siguiente se utilizan tres animaciones para animar las propiedades <xref:System.Windows.Media.SolidColorBrush.Color%2A> y <xref:System.Windows.Media.Brush.Opacity%2A> de un objeto <xref:System.Windows.Media.SolidColorBrush>.  
  
-   La primera animación, <xref:System.Windows.Media.Animation.ColorAnimation>, cambia el color del pincel a <xref:System.Windows.Media.Colors.Gray%2A> cuando el mouse entra en el rectángulo.  
  
-   La animación siguiente, <xref:System.Windows.Media.Animation.ColorAnimation>, cambia el color del pincel a <xref:System.Windows.Media.Colors.Orange%2A> cuando el mouse sale del rectángulo.  
  
-   La última animación, <xref:System.Windows.Media.Animation.DoubleAnimation>, cambia la opacidad del pincel a 0.0 cuando se presiona el botón primario del mouse.  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 Para obtener un ejemplo más completo, que muestra cómo animar tipos diferentes de pinceles, vea [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).  Para obtener más información acerca de la animación, vea [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Para ofrecer coherencia con otros ejemplos de animación, en las versiones de código de este ejemplo se utiliza un objeto <xref:System.Windows.Media.Animation.Storyboard> para aplicar sus animaciones.  Sin embargo, al aplicar una animación única en código, es más fácil para utilizar el método <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> en lugar de utilizar un objeto <xref:System.Windows.Media.Animation.Storyboard>.  Para obtener un ejemplo, vea [Animar una propiedad sin utilizar un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## Vea también  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Información general sobre objetos Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)   
 [Ejemplo Brushes](http://go.microsoft.com/fwlink/?LinkID=159973)
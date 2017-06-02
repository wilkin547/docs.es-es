---
title: "C&#243;mo: Animar la posici&#243;n o color de un punto de degradado | Microsoft Docs"
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
  - "animación, color de los objetos GradientStop"
  - "animación, posición de los objetos GradientStop"
  - "colores, animar"
  - "GradientStop (objetos), animar el color de"
  - "GradientStop (objetos), animar la posición de"
  - "posición, animar"
ms.assetid: 6f5b8b47-6c32-4b8e-98ee-fdf6515ec843
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Animar la posici&#243;n o color de un punto de degradado
En este ejemplo se muestra cómo animar las propiedades <xref:System.Windows.Media.GradientStop.Color%2A> y <xref:System.Windows.Media.GradientStop.Offset%2A> de los objetos <xref:System.Windows.Media.GradientStop>.  
  
## Ejemplo  
 En el ejemplo siguiente se animan tres puntos de degradado dentro de <xref:System.Windows.Media.LinearGradientBrush>.  En el ejemplo se utilizan tres animaciones, cada una de las cuales anima un punto de degradado diferente:  
  
-   La primera animación, un objeto <xref:System.Windows.Media.Animation.DoubleAnimation>, anima la propiedad <xref:System.Windows.Media.GradientStop.Offset%2A> del primer punto de degradado desde 0.0 hasta 1.0 y de nuevo hasta 0.0.  Como resultado, el primer color del degradado cambia del lado izquierdo al derecho del rectángulo y vuelve al izquierdo.  
  
-   La segunda animación, <xref:System.Windows.Media.Animation.ColorAnimation>, anima la propiedad <xref:System.Windows.Media.GradientStop.Color%2A> del segundo punto de degradado desde <xref:System.Windows.Media.Colors.Purple%2A> hasta <xref:System.Windows.Media.Colors.Yellow%2A> y de nuevo hasta <xref:System.Windows.Media.Colors.Purple%2A>.  Como resultado, el color central del degradado cambia del púrpura al amarillo y vuelve al púrpura.  
  
-   La tercera animación, <xref:System.Windows.Media.Animation.ColorAnimation>, anima la opacidad de la propiedad <xref:System.Windows.Media.GradientStop.Color%2A> del tercer punto de degradado en \-1 y vuelve al punto inicial.  Como resultado, el tercer color del degradado se desvanece y, a continuación, se vuelve de nuevo opaco.  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 Aunque en este ejemplo se utiliza un objeto <xref:System.Windows.Media.LinearGradientBrush>, el proceso es el mismo para animar objetos <xref:System.Windows.Media.GradientStop> dentro de <xref:System.Windows.Media.RadialGradientBrush>.  
  
 Para obtener más ejemplos, vea [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).  
  
## Vea también  
 <xref:System.Windows.Media.GradientStop>   
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Información general sobre objetos Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
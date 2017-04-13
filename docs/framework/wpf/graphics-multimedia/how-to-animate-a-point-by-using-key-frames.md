---
title: "C&#243;mo: Animar un punto mediante fotogramas clave | Microsoft Docs"
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
  - "animación, puntos con fotogramas clave"
  - "fotogramas clave, animar puntos con"
  - "puntos, animar con fotogramas clave"
ms.assetid: d2e2ef10-0773-4133-856e-d41c09f60ded
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Animar un punto mediante fotogramas clave
En este ejemplo se muestra cómo utilizar la clase <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> para animar una estructura <xref:System.Windows.Point>.  
  
## Ejemplo  
 En el ejemplo siguiente se mueve una elipse a lo largo de una trayectoria triangular.  El ejemplo utiliza la clase <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> para animar la propiedad <xref:System.Windows.Media.EllipseGeometry.Center%2A> de un objeto <xref:System.Windows.Media.EllipseGeometry>.  Esta animación utiliza tres fotogramas clave de la siguiente manera:  
  
1.  Durante el primer medio segundo, utiliza una instancia de la clase <xref:System.Windows.Media.Animation.LinearPointKeyFrame> para mover la elipse a lo largo de una trayectoria a una velocidad constante desde su posición inicial.  Los cuadros clave lineales como <xref:System.Windows.Media.Animation.LinearPointKeyFrame> crean una interpolación lineal suavizada entre los valores.  
  
2.  Durante el medio segundo siguiente, utiliza una instancia de la clase <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> para mover repentinamente la elipse a lo largo de la trayectoria a la posición siguiente.  Los fotogramas clave discretos como <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> crean saltos súbitos entre los valores.  
  
3.  En los dos segundos finales, se utiliza una instancia de la clase <xref:System.Windows.Media.Animation.SplinePointKeyFrame> para devolver la elipse a su posición inicial.  Los fotogramas clave [spline](GTMT) como <xref:System.Windows.Media.Animation.SplinePointKeyFrame> crean una transición variable entre los valores según los valores de la propiedad <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A>.  En este ejemplo, la animación comienza despacio y se acelera exponencialmente hacia el final del segmento de tiempo.  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 Para obtener el ejemplo completo, vea [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
 Para ofrecer coherencia con otros ejemplos de animación, en las versiones de código de este ejemplo se usa un objeto <xref:System.Windows.Media.Animation.Storyboard> para aplicar <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>.  Sin embargo, al aplicar una animación única en código, es más fácil para utilizar el método <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> en lugar de utilizar un objeto <xref:System.Windows.Media.Animation.Storyboard>.  Para obtener un ejemplo, vea [Animar una propiedad sin utilizar un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## Vea también  
 <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>   
 <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=fullName>   
 <xref:System.Windows.Media.EllipseGeometry>   
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Temas "Cómo..." de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
---
title: "C&#243;mo: Animar un objeto Double mediante fotogramas clave | Microsoft Docs"
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
  - "animación, Double (valores) con fotogramas clave"
  - "Dobles, animar con fotogramas clave"
  - "fotogramas clave, animar valores Double con"
ms.assetid: 3a1a7dba-7694-4907-8a2f-3408baebfa82
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Animar un objeto Double mediante fotogramas clave
En este ejemplo se muestra cómo animar el valor de una propiedad que toma un objeto <xref:System.Double> mediante fotogramas clave.  
  
## Ejemplo  
 En el ejemplo siguiente se mueve un rectángulo por una pantalla.  En el ejemplo se utiliza la clase <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> para animar la propiedad <xref:System.Windows.Media.TranslateTransform.X%2A> de una clase <xref:System.Windows.Media.TranslateTransform> aplicada a <xref:System.Windows.Shapes.Rectangle>.  Esta animación, que se repite indefinidamente, utiliza tres fotogramas clave de la manera siguiente:  
  
1.  Durante los primeros tres segundos, utiliza una instancia de la clase <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> para mover el rectángulo a lo largo de un trayecto a ritmo constante desde su posición inicial hasta la posición 500.  Los fotogramas clave lineales como <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> crean una transición lineal suave entre valores.  
  
2.  Al final del cuarto segundo, utiliza una instancia de la clase <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> para mover de golpe el rectángulo a la posición siguiente.  Los fotogramas clave discretos como <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> crean saltos súbitos entre los valores.  En este ejemplo, el rectángulo está en la posición inicial y aparece de pronto en la posición 500.  
  
3.  En los dos segundos finales, se utiliza una instancia de la clase <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> para devolver el rectángulo a su posición inicial.  Los fotogramas clave [spline](GTMT) como <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> crean una transición variable entre los valores según el valor de la propiedad <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A>.  En este ejemplo, el rectángulo comienza a moverse despacio y, a continuación, se va acelerando exponencialmente hasta el final del segmento temporal.  
  
 [!code-csharp[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/AltDoubleAnimationUsingKeyFramesExample.cs#altdoubleanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/altdoubleanimationusingkeyframesexample.vb#altdoubleanimationusingkeyframeswholepage)]
 [!code-xml[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/AltDoubleAnimationUsingKeyFramesExample.xaml#altdoubleanimationusingkeyframeswholepage)]  
  
 Para obtener el ejemplo completo, vea [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
 Para ofrecer coherencia con otros ejemplos de animación, en las versiones de código de este ejemplo se utiliza un objeto <xref:System.Windows.Media.Animation.Storyboard> para aplicar <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.  Como alternativa, al aplicar una animación única en código, es más fácil utilizar el método <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> en lugar de utilizar <xref:System.Windows.Media.Animation.Storyboard>.  Para obtener un ejemplo, vea [Animar una propiedad sin utilizar un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## Vea también  
 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>   
 <xref:System.Windows.Shapes.Rectangle>   
 <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>   
 <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>   
 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>   
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Temas "Cómo..." de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
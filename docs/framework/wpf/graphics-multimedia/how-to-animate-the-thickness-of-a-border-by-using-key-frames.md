---
title: "C&#243;mo: Animar el grosor de un borde mediante fotogramas clave | Microsoft Docs"
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
  - "animación, grosor del borde con fotogramas clave"
  - "grosor del borde, animar con fotogramas clave"
  - "fotogramas clave, animar el grosor del borde con"
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Animar el grosor de un borde mediante fotogramas clave
En este ejemplo se muestra cómo animar la propiedad <xref:System.Windows.Controls.Control.BorderThickness%2A> de <xref:System.Windows.Controls.Border>.  
  
## Ejemplo  
 En el ejemplo siguiente, se utiliza la clase <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> para animar la propiedad <xref:System.Windows.Controls.Control.BorderThickness%2A> de <xref:System.Windows.Controls.Border>.  Esta animación utiliza tres fotogramas clave de la siguiente manera:  
  
1.  Durante el primer medio segundo, utiliza una instancia de la clase <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> para aumentar gradualmente el grosor del borde.  En el ejemplo se utiliza <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> para crear un aumento lineal suavizado entre los valores.  
  
2.  Al final del medio segundo siguiente, utiliza una instancia de la clase <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> para aumentar de repente el grosor del borde.  Los fotogramas clave discretos como los derivados de <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> crean saltos súbitos entre los valores, es decir, el movimiento de la animación es brusco.  
  
3.  Durante los dos últimos segundos, utiliza una instancia de la clase <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> para reducir el grosor del borde.  Los fotogramas clave [spline](GTMT) como los derivados de <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> crean una transición variable entre los valores según los valores de la propiedad <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A>.  En este fotograma clave, la animación se inicia lentamente y se va acelerando de forma exponencial hasta el final del segmento temporal.  
  
 [!code-xml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 Para obtener el ejemplo completo, vea [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## Vea también  
 <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>   
 <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>   
 <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>   
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Temas "Cómo..." de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)   
 [Animar el valor del grosor de un borde](../../../../docs/framework/wpf/controls/how-to-animate-a-borderthickness-value.md)
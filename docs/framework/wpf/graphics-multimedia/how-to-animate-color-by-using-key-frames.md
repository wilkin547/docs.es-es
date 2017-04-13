---
title: "C&#243;mo: Animar un color mediante fotogramas clave | Microsoft Docs"
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
  - "animación, colores con fotogramas clave"
  - "colores, animar con fotogramas clave"
  - "fotogramas clave, animar colores con"
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Animar un color mediante fotogramas clave
En este ejemplo se muestra cómo animar la propiedad <xref:System.Windows.Media.SolidColorBrush.Color%2A> de <xref:System.Windows.Media.SolidColorBrush> mediante fotogramas clave.  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza la clase <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> para animar la propiedad <xref:System.Windows.Media.SolidColorBrush.Color%2A> de <xref:System.Windows.Media.SolidColorBrush>.  Esta animación utiliza tres fotogramas clave de la siguiente manera:  
  
1.  Durante los primeros dos segundos, utiliza una instancia de la clase <xref:System.Windows.Media.Animation.LinearColorKeyFrame> para cambiar gradualmente el color de verde a rojo.  Los fotogramas clave lineales como <xref:System.Windows.Media.Animation.LinearColorKeyFrame> crean una transición lineal suave entre valores.  
  
2.  Mientras finaliza el siguiente medio segundo, utiliza una instancia de la clase <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> para cambiar rápidamente el color de rojo a amarillo.  Los fotogramas clave discretos como <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> crean cambios súbitos entre los valores; es decir, el cambio de color en esta parte de la animación se produce de forma rápida y brusca.  
  
3.  Durante los dos últimos segundos, utiliza una instancia de la clase <xref:System.Windows.Media.Animation.SplineColorKeyFrame> para volver a cambiar el color, esta vez de amarillo a verde.  Los fotogramas clave [spline](GTMT) como <xref:System.Windows.Media.Animation.SplineColorKeyFrame> crean una transición variable entre los valores según los valores de la propiedad <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A>.  En este ejemplo, el cambio de color comienza despacio y se acelera exponencialmente hacia el final del segmento temporal.  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 Para obtener el ejemplo completo, vea [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## Vea también  
 <xref:System.Windows.Media.SolidColorBrush.Color%2A>   
 <xref:System.Windows.Media.SolidColorBrush>   
 <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>   
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Temas "Cómo..." de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
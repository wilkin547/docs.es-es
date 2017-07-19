---
title: "C&#243;mo: Animar la geometr&#237;a de un rect&#225;ngulo mediante fotogramas clave | Microsoft Docs"
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
  - "animación, RectangleGeometry (objetos) con fotogramas clave"
  - "fotogramas clave, animar objetos RectangleGeometry con"
  - "RectangleGeometry (objetos), animar con fotogramas clave"
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Animar la geometr&#237;a de un rect&#225;ngulo mediante fotogramas clave
En este ejemplo, se muestra cómo animar la propiedad <xref:System.Windows.Media.RectangleGeometry.Rect%2A> de <xref:System.Windows.Media.RectangleGeometry> mediante fotogramas clave.  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza la clase <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> para animar la propiedad <xref:System.Windows.Media.RectangleGeometry.Rect%2A> de <xref:System.Windows.Media.RectangleGeometry>.  Esta animación utiliza tres fotogramas clave de la siguiente manera:  
  
1.  Durante los primeros dos segundos, utiliza una instancia de la clase <xref:System.Windows.Media.Animation.LinearRectKeyFrame> para animar un cambio gradual en la posición, ancho y alto de un rectángulo.  Los fotogramas clave lineales como <xref:System.Windows.Media.Animation.LinearRectKeyFrame> crean una transición lineal suave entre valores.  
  
2.  Durante el final del medio segundo siguiente, utiliza una instancia de la clase <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> para reducir de repente el alto del rectángulo.  Los fotogramas clave discretos como <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> crean cambios súbitos entre los valores; es decir, la disminución de alto se produce de forma rápida y brusca.  
  
3.  Durante los dos últimos segundos, utiliza una instancia de la clase <xref:System.Windows.Media.Animation.SplineRectKeyFrame> para volver a establecer el rectángulo a su tamaño y posición originales.  Los fotogramas clave [spline](GTMT) como <xref:System.Windows.Media.Animation.SplineRectKeyFrame> crean una transición variable entre los valores según los valores de la propiedad <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A>.  En este ejemplo, el cambio comienza despacio y se acelera exponencialmente hacia el final del segmento temporal.  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 Para obtener el ejemplo completo, vea [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## Vea también  
 <xref:System.Windows.Media.RectangleGeometry>   
 <xref:System.Windows.Media.RectangleGeometry.Rect%2A>   
 <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>   
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Temas "Cómo..." de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
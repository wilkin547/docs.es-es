---
title: "C&#243;mo: Animar los cambios de tama&#241;o mediante fotogramas clave | Microsoft Docs"
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
  - "animación, cambios de tamaño con fotogramas clave"
  - "fotogramas clave, animar cambios de tamaño con"
  - "cambios de tamaño, animar con fotogramas clave"
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Animar los cambios de tama&#241;o mediante fotogramas clave
En este ejemplo se muestra cómo animar los cambios del tamaño mediante fotogramas clave.  
  
## Ejemplo  
 En el ejemplo siguiente se usa la clase <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> para animar la propiedad <xref:System.Windows.Media.ArcSegment.Size%2A> de <xref:System.Windows.Media.ArcSegment>.  Esta animación utiliza tres fotogramas clave de la siguiente manera:  
  
1.  Durante el primer medio segundo de la animación, usa una instancia de la clase <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> para aumentar gradualmente el tamaño del arco.  Los fotogramas clave lineales como <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> crean una transición lineal suave entre valores.  
  
2.  Al final del medio segundo siguiente, usa una instancia de la clase <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> para aumentar el tamaño del arco repentinamente.  Los fotogramas clave discretos como <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> crean saltos súbitos entre los valores, es decir, los cambios de tamaño se producen de repente y no son sutiles.  
  
3.  Durante los dos últimos segundos, utiliza una instancia de la clase <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> para aumentar el tamaño del arco.  Los fotogramas clave [spline](GTMT) como <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> crean una transición variable entre los valores según los valores de la propiedad <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A>.  En este ejemplo, el tamaño del arco aumenta lentamente al principio y va aumentando exponencialmente a medida que se acerca el final del segmento temporal.  
  
 [!code-xml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 Para obtener el ejemplo completo, vea [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## Vea también  
 <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>   
 <xref:System.Windows.Media.ArcSegment.Size%2A>   
 <xref:System.Windows.Media.ArcSegment>   
 <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>   
 <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>   
 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>   
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Temas "Cómo..." de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
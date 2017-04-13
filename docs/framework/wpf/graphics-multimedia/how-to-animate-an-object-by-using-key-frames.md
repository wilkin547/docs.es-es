---
title: "C&#243;mo: Animar un objeto mediante fotogramas clave | Microsoft Docs"
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
  - "animación, objetos con fotogramas clave"
  - "fotogramas clave, animar objetos con"
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Animar un objeto mediante fotogramas clave
En este ejemplo se muestra cómo animar un objeto, que en este ejemplo es la propiedad <xref:System.Windows.Controls.Page.Background%2A> de un control <xref:System.Windows.Controls.Page>, mediante fotogramas clave.  
  
## Ejemplo  
 En el ejemplo siguiente se usa la clase <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> para animar los cambios de color para la propiedad <xref:System.Windows.Controls.Page.Background%2A> de un control <xref:System.Windows.Controls.Page>.  La animación de ejemplo cambia a un pincel de fondo diferente a intervalos regulares.  Esta animación usa la clase <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> para crear tres fotogramas clave diferentes.  La animación usa los fotogramas clave de la manera siguiente:  
  
1.  Al final del primer segundo, anima una instancia de la clase <xref:System.Windows.Media.LinearGradientBrush>.  En esta sección del ejemplo se aplica un degradado lineal al color de fondo, de manera que el color pasa de amarillo a naranja y a rojo.  
  
2.  Al final del segundo siguiente, anima una instancia de la clase <xref:System.Windows.Media.RadialGradientBrush>.  En esta sección del ejemplo se aplica un degradado radial al color de fondo, de manera que el color pasa de blanco a azul y a negro.  
  
3.  Al final del tercer segundo, anima una instancia de la clase <xref:System.Windows.Media.DrawingBrush>.  En esta sección del ejemplo se aplica un modelo de tablero al fondo.  
  
4.  La animación comienza de nuevo y se repite indefinidamente.  
  
> [!NOTE]
>  <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> es el único tipo de fotograma clave que se puede usar con la clase <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>.  Los fotogramas clave como <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> crean cambios repentinos en los valores, es decir, los cambios de color de este ejemplo se producen de repente.  
  
 [!code-xml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 Para obtener el ejemplo completo, vea [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## Vea también  
 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>   
 <xref:System.Windows.Controls.Page.Background%2A>   
 <xref:System.Windows.Controls.Page>   
 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>   
 <xref:System.Windows.Media.LinearGradientBrush>   
 <xref:System.Windows.Media.RadialGradientBrush>   
 <xref:System.Windows.Media.DrawingBrush>   
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Temas "Cómo..." de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
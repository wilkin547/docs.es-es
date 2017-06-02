---
title: "C&#243;mo: Animar un objeto Boolean mediante fotogramas clave | Microsoft Docs"
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
  - "animación, valores Boolean con fotogramas clave"
  - "Boolean (valores), animar con fotogramas clave"
  - "fotogramas clave, animar valores Boolean con"
ms.assetid: 4b0fac96-6231-4fcf-9775-4dd673ddc785
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Animar un objeto Boolean mediante fotogramas clave
En este ejemplo se muestra cómo animar el valor de propiedad de tipo Boolean de un control <xref:System.Windows.Controls.Button> mediante fotogramas clave.  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza la clase <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> para animar la propiedad <xref:System.Windows.UIElement.IsEnabled%2A> de un control <xref:System.Windows.Controls.Button>.  Todos los fotogramas clave de este ejemplo utilizan una instancia de la clase <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame>.  Los fotogramas clave discretos como <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> crean saltos súbitos entre los valores, es decir, el movimiento de la animación es brusco.  
  
 [!code-csharp[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/BooleanAnimationUsingKeyFramesExample.cs#booleananimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/booleananimationusingkeyframesexample.vb#booleananimationusingkeyframeswholepage)]
 [!code-xml[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/BooleanAnimationUsingKeyFramesExample.xaml#booleananimationusingkeyframeswholepage)]  
  
 Para obtener el ejemplo completo, vea [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## Vea también  
 <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>   
 <xref:System.Windows.UIElement.IsEnabled%2A>   
 <xref:System.Windows.Controls.Button>   
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Temas "Cómo..." de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
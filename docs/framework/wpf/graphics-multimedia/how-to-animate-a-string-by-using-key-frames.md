---
title: "C&#243;mo: Animar una cadena mediante fotogramas clave | Microsoft Docs"
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
  - "animación, cadenas con fotogramas clave"
  - "fotogramas clave, animar cadenas con"
  - "cadenas, animar con fotogramas clave"
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Animar una cadena mediante fotogramas clave
En este ejemplo se muestra cómo animar una cadena, que en este ejemplo es la propiedad <xref:System.Windows.Controls.ContentControl.Content%2A> de un control <xref:System.Windows.Controls.Button>, mediante fotogramas clave.  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza la clase <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> para animar la propiedad <xref:System.Windows.Controls.ContentControl.Content%2A> de <xref:System.Windows.Controls.Button>.  
  
 Todos los cuadros clave de este ejemplo usan una instancia de la clase <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>, porque una animación de cadena creada con cuadros clave solamente puede utilizar cuadros clave discretos.  Los cuadros clave discretos como <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> crean saltos súbitos entre valores, es decir, los cambios de la animación se producen rápidamente y no de forma sutil.  
  
 [!code-xml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 Para obtener el ejemplo completo, vea [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## Vea también  
 <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>   
 <xref:System.Windows.Controls.ContentControl.Content%2A>   
 <xref:System.Windows.Controls.Button>   
 <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>   
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Temas "Cómo..." de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
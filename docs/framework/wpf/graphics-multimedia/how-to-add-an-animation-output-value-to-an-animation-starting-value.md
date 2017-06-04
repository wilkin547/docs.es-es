---
title: "C&#243;mo: Agregar un valor de salida de animaci&#243;n a un valor inicial de animaci&#243;n | Microsoft Docs"
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
  - "animación"
  - "IsAdditive (propiedad)"
ms.assetid: b89a82be-b03d-481e-a8d3-cc513d09ca00
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Agregar un valor de salida de animaci&#243;n a un valor inicial de animaci&#243;n
Este ejemplo muestra cómo agregar un valor de salida de animación al valor inicial de una animación.  
  
## Ejemplo  
 La propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> especifica si desea que el valor de salida de una animación se agregue al valor inicial \(valor base\) de una propiedad animada.  Puede usar la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> con la mayoría de las animaciones básicas y la mayoría de las animaciones de fotogramas clave.  Para obtener más información, consulte [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) y [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
 El ejemplo siguiente muestra el efecto de utilizar la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=fullName> con <xref:System.Windows.Media.Animation.DoubleAnimation> y la propiedad <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=fullName> con <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.  
  
 [!code-xml[timingbehaviors_snip#IsAdditiveWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsAdditiveExample.xaml#isadditivewholepage)]  
  
## Vea también  
 [Acumular valores de animaciones durante la repetición de ciclos](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)   
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Animation and Timing](http://msdn.microsoft.com/es-es/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
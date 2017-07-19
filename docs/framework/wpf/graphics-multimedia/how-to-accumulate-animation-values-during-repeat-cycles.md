---
title: "C&#243;mo: Acumular valores de animaciones durante la repetici&#243;n de ciclos | Microsoft Docs"
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
  - "acumular valores de animaciones entre ciclos que se repiten"
  - "animación, acumular valores entre ciclos que se repiten"
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Acumular valores de animaciones durante la repetici&#243;n de ciclos
En este ejemplo se muestra cómo usar la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> para acumular valores de animación entre ciclos que se repiten.  
  
## Ejemplo  
 Use la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> para acumular los valores base de una animación entre ciclos que se repiten.  Por ejemplo, si establece una animación para que se repita 9 veces \(<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> \= "9x"\) y establece la propiedad que se va a animar entre 10 y 15 \(From \= 10 To \= 15\), la propiedad se anima de 10 a 15 durante el primer ciclo, de 15 a 20 durante el segundo ciclo, de 20 a 25 durante el tercer ciclo, y así sucesivamente.  Por lo tanto, cada ciclo de animación usa el valor de animación final del ciclo de animación anterior como su valor base.  
  
 Puede usar la propiedad `IsCumulative` con la mayoría de las animaciones básicas y la mayoría de las animaciones de fotogramas clave.  Para obtener más información, consulte [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) y [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
 En el ejemplo siguiente se muestra este comportamiento al animar el ancho de cuatro rectángulos.  En el ejemplo:  
  
-   Se anima el primer rectángulo con <xref:System.Windows.Media.Animation.DoubleAnimation> y se establece la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> en `true`.  
  
-   Se anima el segundo rectángulo con <xref:System.Windows.Media.Animation.DoubleAnimation> y se establece la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> en el valor predeterminado `false`.  
  
-   Se anima el tercer rectángulo con <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> y se establece la propiedad <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> en `true`.  
  
-   Se anima el último rectángulo con <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> y se establece la propiedad <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> en `false`.  
  
 [!code-xml[timingbehaviors_snip#IsCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## Vea también  
 [Agregar un valor de salida de animación a un valor inicial de animación](../../../../docs/framework/wpf/graphics-multimedia/how-to-add-an-animation-output-value-to-an-animation-starting-value.md)   
 [Repetir una animación](../../../../docs/framework/wpf/graphics-multimedia/how-to-repeat-an-animation.md)   
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
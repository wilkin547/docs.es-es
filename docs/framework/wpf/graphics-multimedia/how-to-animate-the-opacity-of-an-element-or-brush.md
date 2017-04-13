---
title: "C&#243;mo: Animar la opacidad de un elemento o pincel | Microsoft Docs"
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
  - "animación, Opacity (propiedad)"
  - "opacidad, animar"
ms.assetid: 572af23b-39dd-48d1-9db5-4bca56a4b3d3
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Animar la opacidad de un elemento o pincel
Para que un elemento de marco aparezca y se desvanezca mediante un fundido, puede animar su propiedad <xref:System.Windows.UIElement.Opacity%2A>, o bien puede animar la propiedad <xref:System.Windows.Media.Brush.Opacity%2A> del objeto o los objetos <xref:System.Windows.Media.Brush> utilizados para pintarlo.  Al animar la opacidad del elemento, éste aparece y se desvanece mediante un fundido; sin embargo, animar el pincel utilizado para pintar el elemento permite seleccionar mejor qué parte del elemento se desvanece.  Por ejemplo, podría animar la opacidad de un pincel utilizada para pintar el fondo de un botón.  Esto haría que el fondo del botón apareciese y se desvaneciese mediante un fundido, pero el texto permanecería totalmente opaco.  
  
> [!NOTE]
>  Animar la propiedad <xref:System.Windows.Media.Brush.Opacity%2A> de un objeto <xref:System.Windows.Media.Brush>, aporta ventajas de rendimiento con respecto a animar la propiedad <xref:System.Windows.UIElement.Opacity%2A> de un elemento.  
  
 En el ejemplo siguiente, se animan dos botones para que aparezcan y se desvanezcan mediante un fundido.  La opacidad del primer control <xref:System.Windows.Controls.Button> se anima desde `1.0` hasta `0.0` durante un valor de <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de cinco segundos.  El segundo botón también se anima, pero lo que se anima es la opacidad del objeto SolidColorBrush utilizado para pintar su propiedad <xref:System.Windows.Controls.Control.Background%2A>, en lugar de la opacidad del botón completo.  Al ejecutar el ejemplo, el primer botón aparece y desaparece completamente, mientras que en el segundo botón lo único que aparece y desaparece es su fondo.  Su texto y borde permanecen totalmente opacos.  
  
## Ejemplo  
 [!code-xml[timingbehaviors_snip#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/OpacityAnimationExample.xaml#10)]  
  
 Se ha omitido código en este ejemplo.  El ejemplo completo también muestra cómo animar la opacidad de un objeto <xref:System.Windows.Media.Color> dentro de <xref:System.Windows.Media.LinearGradientBrush>.  Para obtener el ejemplo completo, vea [Animating the Opacity of an Element Sample](http://go.microsoft.com/fwlink/?LinkID=159968).
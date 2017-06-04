---
title: "C&#243;mo: Controlar la temporizaci&#243;n de animaciones y fotogramas clave | Microsoft Docs"
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
  - "fotogramas clave [WPF], control de tiempo"
  - "control de tiempo de animación de fotogramas clave"
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Controlar la temporizaci&#243;n de animaciones y fotogramas clave
En este ejemplo se muestra cómo controlar la temporización de fotogramas clave dentro de una animación de fotogramas clave.  Como sucede con las demás animaciones, las animaciones de fotogramas clave tienen una propiedad <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.  Además de especificar la duración de la animación, necesita especificar qué parte de esa duración se asigna a cada uno de sus fotogramas clave.  Para la asignación del tiempo, debe especificar <xref:System.Windows.Media.Animation.KeyTime> para cada fotograma clave de la animación.  
  
 El elemento <xref:System.Windows.Media.Animation.KeyTime> de cada fotograma clave especifica cuándo finaliza \(no el tiempo durante el cual se reproduce\).  Puede especificar <xref:System.Windows.Media.Animation.KeyTime> como un valor <xref:System.TimeSpan>, como un porcentaje o como el valor especial <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> o <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>.  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> para animar un rectángulo por la pantalla.  Los tiempos clave de los fotogramas clave se establecen con valores <xref:System.TimeSpan>.  
  
 [!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
 [!code-vb[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
 [!code-xml[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]  
  
 La ilustración siguiente muestra cuándo se alcanza el valor de cada fotograma clave.  
  
 ![Los valores de clave se alcanzan a 3, 4 y 10 segundos](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm\_keyframe\_keytime1\_timespan")  
  
 En el ejemplo siguiente se muestra una animación que es idéntica; la única diferencia es que los tiempos clave de los fotogramas clave se establecen con valores de porcentaje.  
  
 [!code-csharp[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
 [!code-vb[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
 [!code-xml[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]  
  
 La ilustración siguiente muestra cuándo se alcanza el valor de cada fotograma clave.  
  
 ![Los valores de clave se alcanzan a 3, 4 y 10 segundos](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm\_keyframe\_keytime2\_percentage")  
  
 En el ejemplo siguiente se utilizan valores de tiempos clave <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>.  
  
 [!code-csharp[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
 [!code-vb[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
 [!code-xml[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]  
  
 La ilustración siguiente muestra cuándo se alcanza el valor de cada fotograma clave.  
  
 ![Los valores de clave se alcanzan a 3.3, 6.6 y 9.9 segundos](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm\_keyframe\_keytime3\_uniform")  
  
 En el último ejemplo se utilizan valores de tiempos clave <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>.  
  
 [!code-csharp[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
 [!code-vb[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
 [!code-xml[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]  
  
 La ilustración siguiente muestra cuándo se alcanza el valor de cada fotograma clave.  
  
 ![Los valores de clave se alcanzan a 0, 5 y 10 segundos](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm\_keyframe\_keytime4\_paced")  
  
 Para que no fueran tan complejas, las versiones de código de este ejemplo usan animaciones locales, no guiones gráficos, porque sólo se aplica una animación a una propiedad. Sin embargo, los ejemplos se pueden modificar para utilizar guiones gráficos.  Para obtener un ejemplo donde se muestra cómo declarar un guión gráfico en el código, vea [Animar una propiedad utilizando un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).  
  
 Para obtener el ejemplo completo, vea [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).  Para obtener más información sobre las animaciones de fotogramas clave, vea [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
## Vea también  
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
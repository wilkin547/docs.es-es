---
title: "C&#243;mo: Establecer una propiedad despu&#233;s de animarla con un gui&#243;n gr&#225;fico | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "animación, cambiar valores de propiedad después"
ms.assetid: 79466556-4dbf-40bd-9c1e-a77613b07077
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Establecer una propiedad despu&#233;s de animarla con un gui&#243;n gr&#225;fico
En algunos casos, puede parecer que no es posible cambiar el valor de una propiedad después de animarla.  
  
## Ejemplo  
 En el ejemplo siguiente, se utiliza un objeto <xref:System.Windows.Media.Animation.Storyboard> para animar el color de <xref:System.Windows.Media.SolidColorBrush>.  El guión gráfico se activa al hacer clic en el botón.  El evento <xref:System.Windows.Media.Animation.Timeline.Completed> se controla para que se notifique al programa cuando se completa <xref:System.Windows.Media.Animation.ColorAnimation>.  
  
 [!code-xml[timingbehaviors_snip#GraphicsMMButton1Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton1declaration)]  
  
## Ejemplo  
 Después de completarse <xref:System.Windows.Media.Animation.ColorAnimation>, el programa intenta cambiar el color del pincel a azul.  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton1Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton1handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton1Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton1handler)]  
  
 Parece que el código anterior no surte efecto alguno: el pincel sigue siendo amarillo, que es el valor proporcionado por el objeto <xref:System.Windows.Media.Animation.ColorAnimation> que animó el pincel.  El valor de propiedad subyacente \(el valor base\) sí se cambia a azul.  Sin embargo, el valor efectivo, o actual, sigue siendo amarillo porque <xref:System.Windows.Media.Animation.ColorAnimation> continúa invalidando el valor base.  Si desea que el valor base pase a ser de nuevo el valor efectivo, debe conseguir que la animación deje de influir en la propiedad.  Hay tres maneras de hacer esto con las animaciones de guión gráfico:  
  
-   Establecer la propiedad <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> de la animación en <xref:System.Windows.Media.Animation.FillBehavior>  
  
-   Quitar el guión gráfico completo.  
  
-   Quitar la animación de la propiedad individual.  
  
## Establecer la propiedad FillBehavior de la animación en Stop  
 Al establecer <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> en <xref:System.Windows.Media.Animation.FillBehavior>, le está indicando a la animación que deje de afectar a su propiedad de destino una vez finalice su período activo.  
  
 [!code-xml[timingbehaviors_snip#GraphicsMMButton2Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton2declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton2Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton2handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton2Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton2handler)]  
  
## Quitar el guión gráfico completo  
 Al utilizar un desencadenador de <xref:System.Windows.Media.Animation.RemoveStoryboard> o el método <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=fullName>, está indicando a las animaciones de guión gráfico que dejen de afectar a las propiedades de destino.  La diferencia entre este enfoque y establecer la propiedad <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> es que el guión gráfico se puede quitar en cualquier momento, mientras que la propiedad <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> sólo surte efecto cuando la animación llega al final de su período activo.  
  
 [!code-xml[timingbehaviors_snip#GraphicsMMButton3Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton3declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton3Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton3handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton3Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton3handler)]  
  
## Quitar una animación de una propiedad individual  
 Otra técnica para conseguir que una animación deje de afectar a una propiedad es utilizar el método <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> del objeto animado.  Especifique la propiedad animada como primer parámetro y `null`, como segundo.  
  
 [!code-xml[timingbehaviors_snip#GraphicsMMButton4Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton4declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton4Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton4handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton4Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton4handler)]  
  
 Esta técnica también funciona para animaciones que no son de guión gráfico.  
  
## Vea también  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>   
 <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=fullName>   
 <xref:System.Windows.Media.Animation.RemoveStoryboard>   
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Información general sobre técnicas de animación de propiedades](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
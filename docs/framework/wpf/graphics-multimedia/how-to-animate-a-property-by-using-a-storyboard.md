---
title: "C&#243;mo: Animar una propiedad utilizando un gui&#243;n gr&#225;fico | Microsoft Docs"
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
  - "animación, Guiones gráficos"
  - "Guiones gráficos, animación"
ms.assetid: f4a314e9-1da2-4367-85fc-1232487efa7a
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Animar una propiedad utilizando un gui&#243;n gr&#225;fico
En este ejemplo se muestra cómo utilizar un objeto <xref:System.Windows.Media.Animation.Storyboard> para animar propiedades.  Para animar una propiedad utilizando un objeto <xref:System.Windows.Media.Animation.Storyboard>, cree una animación para cada propiedad que desee animar y cree también un objeto <xref:System.Windows.Media.Animation.Storyboard> para contener las animaciones.  
  
 El tipo de propiedad determina el tipo de animación a utilizar.  Por ejemplo, para animar una propiedad que toma valores <xref:System.Double>, utilice un objeto <xref:System.Windows.Media.Animation.DoubleAnimation>.  Las [propiedades adjuntas](GTMT) <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> y <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> especifique el objeto y la propiedad a la que se aplica la animación.  
  
 Para iniciar un guión gráfico en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], utilice una acción <xref:System.Windows.Media.Animation.BeginStoryboard> y un objeto <xref:System.Windows.EventTrigger>.  El objeto <xref:System.Windows.EventTrigger> inicia la acción <xref:System.Windows.Media.Animation.BeginStoryboard> cuando se produce el evento especificado por su propiedad <xref:System.Windows.EventTrigger.RoutedEvent%2A>.  La acción <xref:System.Windows.Media.Animation.BeginStoryboard> inicia el objeto <xref:System.Windows.Media.Animation.Storyboard>.  
  
 En el ejemplo siguiente se utiliza objetos <xref:System.Windows.Media.Animation.Storyboard> para animar dos controles <xref:System.Windows.Controls.Button>.  Para realizar la primera modificación del botón en tamaño, se anima su propiedad <xref:System.Windows.FrameworkElement.Width%2A>.  Para hacer que el segundo botón cambie de color, se utiliza la propiedad <xref:System.Windows.Media.SolidColorBrush.Color%2A> del objeto  <xref:System.Windows.Media.SolidColorBrush> para establecer la propiedad <xref:System.Windows.Controls.Control.Background%2A> del botón que se anima.  
  
## Ejemplo  
 [!code-xml[AnimatePropertyStoryboards#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/StoryboardExample.xaml#1)]  
  
> [!NOTE]
>  Aunque las animaciones pueden destinarse a un objeto <xref:System.Windows.FrameworkElement>, tal como <xref:System.Windows.Controls.Control> o <xref:System.Windows.Controls.Panel>, o a un objeto <xref:System.Windows.Freezable>, tal como <xref:System.Windows.Media.Brush> o <xref:System.Windows.Media.Transform>, solamente los elementos del marco tienen una propiedad <xref:System.Windows.FrameworkElement.Name%2A>.  Para asignar un nombre a un elemento inmovilizable para que pueda servir de destino para una animación, utilice [x:Name \(Directiva\)](../../../../docs/framework/xaml-services/x-name-directive.md), como muestra el ejemplo anterior.  
  
 Si utiliza el código, debe crear un objeto <xref:System.Windows.NameScope> para un objeto <xref:System.Windows.FrameworkElement> y registrar los nombres de los objetos a animar con <xref:System.Windows.FrameworkElement>.  Para iniciar las animación en código, utilice una acción <xref:System.Windows.Media.Animation.BeginStoryboard> con un objeto <xref:System.Windows.EventTrigger>.  Opcionalmente, puede utilizar un controlador de eventos y el método <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> de un objeto <xref:System.Windows.Media.Animation.Storyboard>.  En el siguiente ejemplo, se muestra cómo utilizar el método <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>.  
  
 [!code-csharp[AnimatePropertyStoryboards#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatePropertyStoryboards/CSharp/StoryboardExample.cs#11)]
 [!code-vb[AnimatePropertyStoryboards#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AnimatePropertyStoryboards/VisualBasic/StoryboardExample.vb#11)]  
  
 Para obtener más información sobre animaciones y guiones gráficos, vea [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Si utiliza código, no estará limitado a utilizar objetos <xref:System.Windows.Media.Animation.Storyboard> para animar las propiedades.  Para obtener más información y ejemplos, vea [Animar una propiedad sin utilizar un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md) y [Animar una propiedad usando un objeto AnimationClock](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-an-animationclock.md).
---
title: 'Cómo: Animar una propiedad utilizando un guión gráfico'
description: Animar la interfaz de usuario con animaciones y guiones gráficos para las propiedades de Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], Storyboards
- Storyboards [WPF], animation
ms.assetid: f4a314e9-1da2-4367-85fc-1232487efa7a
ms.openlocfilehash: f21b606751b845905a7bde6d3a7658b214369cc6
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853747"
---
# <a name="how-to-animate-a-property-by-using-a-storyboard"></a>Cómo: Animar una propiedad utilizando un guión gráfico
En este ejemplo se muestra cómo utilizar un <xref:System.Windows.Media.Animation.Storyboard> para animar propiedades. Para animar una propiedad utilizando un <xref:System.Windows.Media.Animation.Storyboard> , cree una animación para cada propiedad que desee animar y cree también una <xref:System.Windows.Media.Animation.Storyboard> para que contenga las animaciones.  
  
 El tipo de propiedad determina el tipo de animación que se va a utilizar. Por ejemplo, para animar una propiedad que toma <xref:System.Double> valores, use <xref:System.Windows.Media.Animation.DoubleAnimation> . Las <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> propiedades adjuntas y especifican el objeto y la propiedad a la que se aplica la animación.  
  
 Para iniciar un guión gráfico en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , use una <xref:System.Windows.Media.Animation.BeginStoryboard> acción y un <xref:System.Windows.EventTrigger> . <xref:System.Windows.EventTrigger>Comienza la <xref:System.Windows.Media.Animation.BeginStoryboard> acción cuando se produce el evento especificado por su <xref:System.Windows.EventTrigger.RoutedEvent%2A> propiedad. La <xref:System.Windows.Media.Animation.BeginStoryboard> acción inicia el <xref:System.Windows.Media.Animation.Storyboard> .  
  
 En el ejemplo siguiente <xref:System.Windows.Media.Animation.Storyboard> se usan objetos para animar dos <xref:System.Windows.Controls.Button> controles. Para que el primer cambio de botón tenga el mismo tamaño, <xref:System.Windows.FrameworkElement.Width%2A> se anima. Para hacer que el segundo botón cambie de color, la <xref:System.Windows.Media.SolidColorBrush.Color%2A> propiedad de <xref:System.Windows.Media.SolidColorBrush> se utiliza para establecer el <xref:System.Windows.Controls.Control.Background%2A> del botón que está animado.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[AnimatePropertyStoryboards#1](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/StoryboardExample.xaml#1)]  
  
> [!NOTE]
> Aunque las animaciones pueden tener como destino un <xref:System.Windows.FrameworkElement> objeto, como <xref:System.Windows.Controls.Control> o <xref:System.Windows.Controls.Panel> , y un <xref:System.Windows.Freezable> objeto, como <xref:System.Windows.Media.Brush> o <xref:System.Windows.Media.Transform> , solo los elementos del marco tienen una <xref:System.Windows.FrameworkElement.Name%2A> propiedad. Para asignar un nombre a un elemento inmovilizable para que pueda servir de destino para una animación, utilice [x:Name (Directiva)](../../../desktop-wpf/xaml-services/xname-directive.md), como se muestra en el ejemplo anterior.  
  
 Si utiliza código, debe crear <xref:System.Windows.NameScope> para un <xref:System.Windows.FrameworkElement> y registrar los nombres de los objetos que se van a animar con ellos <xref:System.Windows.FrameworkElement> . Para iniciar las animaciones en el código, use una <xref:System.Windows.Media.Animation.BeginStoryboard> acción con un <xref:System.Windows.EventTrigger> . Opcionalmente, puede usar un controlador de eventos y el <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método de <xref:System.Windows.Media.Animation.Storyboard> . En el siguiente ejemplo, se muestra cómo utilizar el método <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>.  
  
 [!code-csharp[AnimatePropertyStoryboards#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatePropertyStoryboards/CSharp/StoryboardExample.cs#11)]
 [!code-vb[AnimatePropertyStoryboards#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimatePropertyStoryboards/VisualBasic/StoryboardExample.vb#11)]  
  
 Para más información sobre animaciones y guiones gráficos, vea [Información general sobre animaciones](animation-overview.md).  
  
 Si usa código, no se limita a usar objetos para <xref:System.Windows.Media.Animation.Storyboard> animar propiedades. Para más información y ejemplos, vea [Animar una propiedad sin utilizar un guión gráfico](how-to-animate-a-property-without-using-a-storyboard.md) y [Animar una propiedad usando un objeto AnimationClock](how-to-animate-a-property-by-using-an-animationclock.md).

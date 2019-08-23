---
title: Procedimiento Animar una propiedad mediante un guión gráfico
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], Storyboards
- Storyboards [WPF], animation
ms.assetid: f4a314e9-1da2-4367-85fc-1232487efa7a
ms.openlocfilehash: a7a2656d84d37d3e2726df009a07ccf29661df07
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963045"
---
# <a name="how-to-animate-a-property-by-using-a-storyboard"></a>Procedimiento Animar una propiedad mediante un guión gráfico
En este ejemplo se muestra cómo utilizar <xref:System.Windows.Media.Animation.Storyboard> un para animar propiedades. Para animar una propiedad utilizando un <xref:System.Windows.Media.Animation.Storyboard>, cree una animación para cada propiedad que desee animar y cree también una <xref:System.Windows.Media.Animation.Storyboard> para que contenga las animaciones.  
  
 El tipo de propiedad determina el tipo de animación que se va a utilizar. Por ejemplo, para animar una propiedad que <xref:System.Double> toma valores, <xref:System.Windows.Media.Animation.DoubleAnimation>use. Las <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> propiedades <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> adjuntas y especifican el objeto y la propiedad a la que se aplica la animación.  
  
 Para iniciar un guión gráfico [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]en, use <xref:System.Windows.Media.Animation.BeginStoryboard> una acción y <xref:System.Windows.EventTrigger>un. Comienza la <xref:System.Windows.Media.Animation.BeginStoryboard> acción cuando se produce el evento especificado por su <xref:System.Windows.EventTrigger.RoutedEvent%2A> propiedad. <xref:System.Windows.EventTrigger> La <xref:System.Windows.Media.Animation.BeginStoryboard> acción inicia el <xref:System.Windows.Media.Animation.Storyboard>.  
  
 En el ejemplo siguiente <xref:System.Windows.Media.Animation.Storyboard> se usan objetos para <xref:System.Windows.Controls.Button> animar dos controles. Para que el primer cambio de botón <xref:System.Windows.FrameworkElement.Width%2A> tenga el mismo tamaño, se anima. Para hacer que el segundo botón cambie de color <xref:System.Windows.Media.SolidColorBrush.Color%2A> , la propiedad <xref:System.Windows.Media.SolidColorBrush> de se utiliza para establecer <xref:System.Windows.Controls.Control.Background%2A> el del botón que está animado.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[AnimatePropertyStoryboards#1](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/StoryboardExample.xaml#1)]  
  
> [!NOTE]
> Aunque las animaciones pueden tener como <xref:System.Windows.FrameworkElement> destino un objeto, <xref:System.Windows.Controls.Control> como o <xref:System.Windows.Controls.Panel> <xref:System.Windows.Media.Brush> , y un <xref:System.Windows.Freezable> objeto, como o <xref:System.Windows.Media.Transform>, solo los elementos del marco tienen una <xref:System.Windows.FrameworkElement.Name%2A> propiedad. Para asignar un nombre a un elemento inmovilizable para que pueda servir de destino para una animación, utilice [x:Name (Directiva)](../../xaml-services/x-name-directive.md), como se muestra en el ejemplo anterior.  
  
 Si utiliza código, debe crear <xref:System.Windows.NameScope> para un <xref:System.Windows.FrameworkElement> y registrar los nombres de los <xref:System.Windows.FrameworkElement>objetos que se van a animar con ellos. Para iniciar las animaciones en el código, use <xref:System.Windows.Media.Animation.BeginStoryboard> una acción con <xref:System.Windows.EventTrigger>un. Opcionalmente, puede usar un controlador de eventos y el <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método de <xref:System.Windows.Media.Animation.Storyboard>. En el siguiente ejemplo, se muestra cómo utilizar el método <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>.  
  
 [!code-csharp[AnimatePropertyStoryboards#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatePropertyStoryboards/CSharp/StoryboardExample.cs#11)]
 [!code-vb[AnimatePropertyStoryboards#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimatePropertyStoryboards/VisualBasic/StoryboardExample.vb#11)]  
  
 Para más información sobre animaciones y guiones gráficos, vea [Información general sobre animaciones](animation-overview.md).  
  
 Si usa código, no se limita a usar <xref:System.Windows.Media.Animation.Storyboard> objetos para animar propiedades. Para más información y ejemplos, vea [Animar una propiedad sin utilizar un guión gráfico](how-to-animate-a-property-without-using-a-storyboard.md) y [Animar una propiedad usando un objeto AnimationClock](how-to-animate-a-property-by-using-an-animationclock.md).

---
title: 'Cómo: Animar una propiedad utilizando un guión gráfico'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], Storyboards
- Storyboards [WPF], animation
ms.assetid: f4a314e9-1da2-4367-85fc-1232487efa7a
ms.openlocfilehash: 7e67fb07a05d474999515a678fd72ac6b96953c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561077"
---
# <a name="how-to-animate-a-property-by-using-a-storyboard"></a>Cómo: Animar una propiedad utilizando un guión gráfico
Este ejemplo muestra cómo utilizar un <xref:System.Windows.Media.Animation.Storyboard> para animar propiedades. Para animar una propiedad usando un <xref:System.Windows.Media.Animation.Storyboard>, crear una animación para cada propiedad que se va a animar y cree también un <xref:System.Windows.Media.Animation.Storyboard> para contener las animaciones.  
  
 El tipo de propiedad determina el tipo de animación que se va a utilizar. Por ejemplo, para animar una propiedad que toma <xref:System.Double> valores, utilice un <xref:System.Windows.Media.Animation.DoubleAnimation>. El <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> y <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> propiedades adjuntas que especifican el objeto y propiedad a la que se aplica la animación.  
  
 Para iniciar un guión gráfico en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], use un <xref:System.Windows.Media.Animation.BeginStoryboard> acción y un <xref:System.Windows.EventTrigger>. El <xref:System.Windows.EventTrigger> comienza el <xref:System.Windows.Media.Animation.BeginStoryboard> acción cuando el evento es especificado por su <xref:System.Windows.EventTrigger.RoutedEvent%2A> se produce la propiedad. El <xref:System.Windows.Media.Animation.BeginStoryboard> acción inicia el <xref:System.Windows.Media.Animation.Storyboard>.  
  
 En el ejemplo siguiente se utiliza <xref:System.Windows.Media.Animation.Storyboard> objetos que se va a animar dos <xref:System.Windows.Controls.Button> controles. Para realizar el primer botón cambia de tamaño, su <xref:System.Windows.FrameworkElement.Width%2A> se anima. Para hacer que el segundo botón Cambiar el color, el <xref:System.Windows.Media.SolidColorBrush.Color%2A> propiedad de la <xref:System.Windows.Media.SolidColorBrush> se usa para establecer el <xref:System.Windows.Controls.Control.Background%2A> del botón que se anima.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[AnimatePropertyStoryboards#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/StoryboardExample.xaml#1)]  
  
> [!NOTE]
>  Aunque pueden tener como destino las animaciones tanto un <xref:System.Windows.FrameworkElement> objeto, como un <xref:System.Windows.Controls.Control> o <xref:System.Windows.Controls.Panel>y un <xref:System.Windows.Freezable> objeto, como un <xref:System.Windows.Media.Brush> o <xref:System.Windows.Media.Transform>, sólo los elementos de marco de trabajo tienen un <xref:System.Windows.FrameworkElement.Name%2A> propiedad. Para asignar un nombre a un elemento inmovilizable para que pueda servir de destino para una animación, utilice [x:Name (Directiva)](../../../../docs/framework/xaml-services/x-name-directive.md), como se muestra en el ejemplo anterior.  
  
 Si utiliza el código, debe crear un <xref:System.Windows.NameScope> para un <xref:System.Windows.FrameworkElement> y registrar los nombres de los objetos que se va a animar con ese <xref:System.Windows.FrameworkElement>. Para iniciar las animaciones en el código, use un <xref:System.Windows.Media.Animation.BeginStoryboard> acción con un <xref:System.Windows.EventTrigger>. Si lo desea, puede usar un controlador de eventos y el <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método <xref:System.Windows.Media.Animation.Storyboard>. En el siguiente ejemplo, se muestra cómo utilizar el método <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>.  
  
 [!code-csharp[AnimatePropertyStoryboards#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatePropertyStoryboards/CSharp/StoryboardExample.cs#11)]
 [!code-vb[AnimatePropertyStoryboards#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AnimatePropertyStoryboards/VisualBasic/StoryboardExample.vb#11)]  
  
 Para más información sobre animaciones y guiones gráficos, vea [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Si utiliza código, no está limitado a usar <xref:System.Windows.Media.Animation.Storyboard> objetos para animar propiedades. Para más información y ejemplos, vea [Animar una propiedad sin utilizar un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md) y [Animar una propiedad usando un objeto AnimationClock](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-an-animationclock.md).

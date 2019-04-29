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
ms.openlocfilehash: f6064368b4f5e4fa8324b4039d734d4430cd9174
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761213"
---
# <a name="how-to-animate-a-property-by-using-a-storyboard"></a>Procedimiento Animar una propiedad mediante un guión gráfico
En este ejemplo se muestra cómo usar un <xref:System.Windows.Media.Animation.Storyboard> para animar propiedades. Para animar una propiedad utilizando un <xref:System.Windows.Media.Animation.Storyboard>, crear una animación para cada propiedad que desee animar y cree también un <xref:System.Windows.Media.Animation.Storyboard> para contener las animaciones.  
  
 El tipo de propiedad determina el tipo de animación que se va a utilizar. Por ejemplo, para animar una propiedad que acepta <xref:System.Double> valores, utilice un <xref:System.Windows.Media.Animation.DoubleAnimation>. El <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> y <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> las propiedades adjuntas que especifican el objeto y propiedad a la que se aplica la animación.  
  
 Para iniciar un guión gráfico en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], utilice un <xref:System.Windows.Media.Animation.BeginStoryboard> acción y un <xref:System.Windows.EventTrigger>. El <xref:System.Windows.EventTrigger> comienza el <xref:System.Windows.Media.Animation.BeginStoryboard> acción cuando el evento que está especificado por su <xref:System.Windows.EventTrigger.RoutedEvent%2A> se produce la propiedad. El <xref:System.Windows.Media.Animation.BeginStoryboard> acción comienza el <xref:System.Windows.Media.Animation.Storyboard>.  
  
 En el ejemplo siguiente se usa <xref:System.Windows.Media.Animation.Storyboard> objetos que se va a animar dos <xref:System.Windows.Controls.Button> controles. Para realizar el primer botón cambia de tamaño, su <xref:System.Windows.FrameworkElement.Width%2A> está animada. Para realizar el segundo botón Cambiar el color, el <xref:System.Windows.Media.SolidColorBrush.Color%2A> propiedad de la <xref:System.Windows.Media.SolidColorBrush> se usa para establecer el <xref:System.Windows.Controls.Control.Background%2A> del botón que se anima.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[AnimatePropertyStoryboards#1](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/StoryboardExample.xaml#1)]  
  
> [!NOTE]
>  Aunque las animaciones pueden destinar un <xref:System.Windows.FrameworkElement> objetos, como un <xref:System.Windows.Controls.Control> o <xref:System.Windows.Controls.Panel>y un <xref:System.Windows.Freezable> objetos, como un <xref:System.Windows.Media.Brush> o <xref:System.Windows.Media.Transform>, solo los elementos de marco de trabajo tienen un <xref:System.Windows.FrameworkElement.Name%2A> propiedad. Para asignar un nombre a un elemento inmovilizable para que pueda servir de destino para una animación, utilice [x:Name (Directiva)](../../xaml-services/x-name-directive.md), como se muestra en el ejemplo anterior.  
  
 Si utiliza código, debe crear un <xref:System.Windows.NameScope> para un <xref:System.Windows.FrameworkElement> y registrar los nombres de los objetos que se va a animar con ese <xref:System.Windows.FrameworkElement>. Para iniciar las animaciones en código, use un <xref:System.Windows.Media.Animation.BeginStoryboard> acción con un <xref:System.Windows.EventTrigger>. Si lo desea, puede usar un controlador de eventos y el <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método <xref:System.Windows.Media.Animation.Storyboard>. En el siguiente ejemplo, se muestra cómo utilizar el método <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>.  
  
 [!code-csharp[AnimatePropertyStoryboards#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatePropertyStoryboards/CSharp/StoryboardExample.cs#11)]
 [!code-vb[AnimatePropertyStoryboards#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimatePropertyStoryboards/VisualBasic/StoryboardExample.vb#11)]  
  
 Para más información sobre animaciones y guiones gráficos, vea [Información general sobre animaciones](animation-overview.md).  
  
 Si utiliza código, no está limitado a usar <xref:System.Windows.Media.Animation.Storyboard> objetos para animar las propiedades. Para más información y ejemplos, vea [Animar una propiedad sin utilizar un guión gráfico](how-to-animate-a-property-without-using-a-storyboard.md) y [Animar una propiedad usando un objeto AnimationClock](how-to-animate-a-property-by-using-an-animationclock.md).

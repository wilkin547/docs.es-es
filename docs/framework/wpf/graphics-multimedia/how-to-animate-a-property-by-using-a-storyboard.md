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
ms.openlocfilehash: 6cfce9a5b070a23ed9ac03473888bf572b61393b
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559643"
---
# <a name="how-to-animate-a-property-by-using-a-storyboard"></a>Cómo: Animar una propiedad utilizando un guión gráfico
En este ejemplo se muestra cómo usar un <xref:System.Windows.Media.Animation.Storyboard> para animar propiedades. Para animar una propiedad mediante un <xref:System.Windows.Media.Animation.Storyboard>, cree una animación para cada propiedad que desee animar y cree también un <xref:System.Windows.Media.Animation.Storyboard> que contenga las animaciones.  
  
 El tipo de propiedad determina el tipo de animación que se va a utilizar. Por ejemplo, para animar una propiedad que toma <xref:System.Double> valores, utilice un <xref:System.Windows.Media.Animation.DoubleAnimation>. Las propiedades adjuntas <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> y <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> especifican el objeto y la propiedad a la que se aplica la animación.  
  
 Para iniciar un guion gráfico en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], use una acción de <xref:System.Windows.Media.Animation.BeginStoryboard> y una <xref:System.Windows.EventTrigger>. El <xref:System.Windows.EventTrigger> inicia la acción de <xref:System.Windows.Media.Animation.BeginStoryboard> cuando se produce el evento especificado por su propiedad <xref:System.Windows.EventTrigger.RoutedEvent%2A>. La acción <xref:System.Windows.Media.Animation.BeginStoryboard> inicia el <xref:System.Windows.Media.Animation.Storyboard>.  
  
 En el ejemplo siguiente se utiliza <xref:System.Windows.Media.Animation.Storyboard> objetos para animar dos controles <xref:System.Windows.Controls.Button>. Para que el primer cambio de botón tenga el mismo tamaño, se anima su <xref:System.Windows.FrameworkElement.Width%2A>. Para hacer que el segundo botón cambie de color, se usa la propiedad <xref:System.Windows.Media.SolidColorBrush.Color%2A> del <xref:System.Windows.Media.SolidColorBrush> para establecer la <xref:System.Windows.Controls.Control.Background%2A> del botón que está animado.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[AnimatePropertyStoryboards#1](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/StoryboardExample.xaml#1)]  
  
> [!NOTE]
> Aunque las animaciones pueden tener como destino un objeto <xref:System.Windows.FrameworkElement>, como un <xref:System.Windows.Controls.Control> o <xref:System.Windows.Controls.Panel>, y un objeto <xref:System.Windows.Freezable>, como un <xref:System.Windows.Media.Brush> o <xref:System.Windows.Media.Transform>, solo los elementos del marco tienen una propiedad <xref:System.Windows.FrameworkElement.Name%2A>. Para asignar un nombre a un elemento inmovilizable para que pueda servir de destino para una animación, utilice [x:Name (Directiva)](../../../desktop-wpf/xaml-services/xname-directive.md), como se muestra en el ejemplo anterior.  
  
 Si utiliza código, debe crear un <xref:System.Windows.NameScope> para un <xref:System.Windows.FrameworkElement> y registrar los nombres de los objetos que desea animar con ese <xref:System.Windows.FrameworkElement>. Para iniciar las animaciones en el código, utilice una acción de <xref:System.Windows.Media.Animation.BeginStoryboard> con un <xref:System.Windows.EventTrigger>. Opcionalmente, puede usar un controlador de eventos y el método <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> de <xref:System.Windows.Media.Animation.Storyboard>. En el siguiente ejemplo, se muestra cómo utilizar el método <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>.  
  
 [!code-csharp[AnimatePropertyStoryboards#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatePropertyStoryboards/CSharp/StoryboardExample.cs#11)]
 [!code-vb[AnimatePropertyStoryboards#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimatePropertyStoryboards/VisualBasic/StoryboardExample.vb#11)]  
  
 Para más información sobre animaciones y guiones gráficos, vea [Información general sobre animaciones](animation-overview.md).  
  
 Si utiliza código, no se limita a utilizar objetos de <xref:System.Windows.Media.Animation.Storyboard> para animar propiedades. Para más información y ejemplos, vea [Animar una propiedad sin utilizar un guión gráfico](how-to-animate-a-property-without-using-a-storyboard.md) y [Animar una propiedad usando un objeto AnimationClock](how-to-animate-a-property-by-using-an-animationclock.md).

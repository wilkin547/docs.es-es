---
title: 'Tutorial: Crear su primera aplicación táctil'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating a touch-sensitive application [WPF]
- touchscreen applications [WPF], creating
- touch-sensitive applications [WPF], creating
- creating a touchscreen application [WPF]
ms.assetid: d69e602e-9a25-4e24-950b-e89eaa2a906b
ms.openlocfilehash: d6a59d3e80e8eb3810b04e1535b72bc4b133b7df
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "56747682"
---
# <a name="walkthrough-creating-your-first-touch-application"></a>Tutorial: Crear su primera aplicación táctil
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] permite que las aplicaciones responder a la entrada táctil. Por ejemplo, puede interactuar con una aplicación mediante el uso de uno o más dedos en un dispositivo táctil, como una pantalla táctil en este tutorial se crea una aplicación que permite al usuario mover, cambiar el tamaño o girar un solo objeto mediante el uso de interacción.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   Visual Studio.  
  
-   Un dispositivo que acepta la entrada táctil, como una pantalla táctil, compatible con Windows Touch.  
  
 Además, debe tener un conocimiento básico de cómo crear una aplicación en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], especialmente cómo suscribirse a y controlar un evento. Para obtener más información, vea [Tutorial: Mi primera aplicación de escritorio de WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## <a name="creating-the-application"></a>Crear la aplicación  
  
#### <a name="to-create-the-application"></a>Para crear la aplicación  
  
1.  Cree un proyecto de aplicación de WPF en Visual Basic o Visual C# denominado `BasicManipulation`. Para obtener más información, vea [Tutorial: Mi primera aplicación de escritorio de WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
2.  Reemplace el contenido de MainWindow.xaml por el XAML siguiente.  
  
     Este marcado crea una aplicación simple que contiene una roja <xref:System.Windows.Shapes.Rectangle> en un <xref:System.Windows.Controls.Canvas>. El <xref:System.Windows.UIElement.IsManipulationEnabled%2A> propiedad de la <xref:System.Windows.Shapes.Rectangle> se establece en true para que se va a recibir eventos de manipulación. La aplicación se suscribe a la <xref:System.Windows.UIElement.ManipulationStarting>, <xref:System.Windows.UIElement.ManipulationDelta>, y <xref:System.Windows.UIElement.ManipulationInertiaStarting> eventos. Estos eventos contienen la lógica para mover el <xref:System.Windows.Shapes.Rectangle> cuando el usuario manipula.  
  
     [!code-xaml[BasicManipulation#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml#ui)]  
  
3.  Si utiliza Visual Basic, en la primera línea de MainWindow.xaml, reemplace `x:Class="BasicManipulation.MainWindow"` con `x:Class="MainWindow"`.  
  
4.  En el `MainWindow` clase, agregue las siguientes <xref:System.Windows.UIElement.ManipulationStarting> controlador de eventos.  
  
     El <xref:System.Windows.UIElement.ManipulationStarting> evento tiene lugar cuando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] detecta ese toque entrada comienza a manipular un objeto. El código especifica que la posición de la manipulación debe ser relativa a la <xref:System.Windows.Window> estableciendo el <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> propiedad.  
  
     [!code-csharp[BasicManipulation#ManipulationStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationstarting)]
     [!code-vb[BasicManipulation#ManipulationStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationstarting)]

5.  En el `MainWindow` clase, agregue las siguientes <xref:System.Windows.Input.ManipulationDelta> controlador de eventos.

     El <xref:System.Windows.Input.ManipulationDelta> evento se produce cuando cambia la posición de entrada de la entrada táctil y puede aparecer varias veces durante una manipulación. También puede producirse el evento después de que se genera un dedo. Por ejemplo, si el usuario arrastra un dedo en una pantalla, el <xref:System.Windows.Input.ManipulationDelta> evento tiene lugar varias veces como se mueve el dedo. Cuando el usuario levanta un dedo en la pantalla, el <xref:System.Windows.Input.ManipulationDelta> evento sigue produciéndose para simular la inercia.

     El código se aplica el <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> a la <xref:System.Windows.UIElement.RenderTransform%2A> de la <xref:System.Windows.Shapes.Rectangle> moverlo a medida que el usuario mueve la entrada táctil de entrada. También comprueba si el <xref:System.Windows.Shapes.Rectangle> está fuera de los límites del <xref:System.Windows.Window> cuando el evento tiene lugar durante la inercia. Si es así, la aplicación llama a la <xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=nameWithType> método para finalizar la manipulación.

     [!code-csharp[BasicManipulation#ManipulationDelta](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationdelta)]
     [!code-vb[BasicManipulation#ManipulationDelta](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationdelta)]

6.  En el `MainWindow` clase, agregue las siguientes <xref:System.Windows.UIElement.ManipulationInertiaStarting> controlador de eventos.

     El <xref:System.Windows.UIElement.ManipulationInertiaStarting> evento se produce cuando el usuario todos los dedos de la pantalla. El código establece la velocidad inicial y la desaceleración para el movimiento, expansión y rotación del rectángulo.

     [!code-csharp[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationinertiastarting)]
     [!code-vb[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationinertiastarting)]

7.  Compile y ejecute el proyecto.

     Debería ver un cuadrado rojo en la ventana.

## <a name="testing-the-application"></a>Probar la aplicación
 Para probar la aplicación, intente las siguientes manipulaciones. Tenga en cuenta que puede realizar más de una de las siguientes acciones al mismo tiempo.

-   Para mover el <xref:System.Windows.Shapes.Rectangle>, coloque un dedo en el <xref:System.Windows.Shapes.Rectangle> y mueva el dedo por la pantalla.

-   Para cambiar el tamaño de la <xref:System.Windows.Shapes.Rectangle>, coloque dos dedos en la <xref:System.Windows.Shapes.Rectangle> y acérquelos o aléjelos aparte entre sí.

-   Para girar el <xref:System.Windows.Shapes.Rectangle>, coloque dos dedos en la <xref:System.Windows.Shapes.Rectangle> y gírelos entre sí.

 Para producir inercia, generar rápidamente los dedos en la pantalla de medida que realiza las manipulaciones anteriores. El <xref:System.Windows.Shapes.Rectangle> seguirá mover, cambiar el tamaño o gire durante algunos segundos antes de detenerse.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.UIElement.ManipulationStarting?displayProperty=nameWithType>
- <xref:System.Windows.UIElement.ManipulationDelta?displayProperty=nameWithType>
- <xref:System.Windows.UIElement.ManipulationInertiaStarting?displayProperty=nameWithType>
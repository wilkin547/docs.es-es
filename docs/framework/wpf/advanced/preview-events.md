---
title: Eventos de vista previa
ms.date: 03/30/2017
helpviewer_keywords:
- Preview events [WPF]
- suppressing events [WPF]
- events [WPF], Preview
- events [WPF], suppressing
ms.assetid: b5032308-aa9c-4d02-af11-630ecec8df7e
ms.openlocfilehash: 75165df94aa8b508ef85cf970933efb98b9d62ca
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59211404"
---
# <a name="preview-events"></a>Eventos de vista previa
Eventos de vista previa, también conocidos como eventos de túnel, son eventos enrutados donde la dirección de la ruta se desplaza desde la raíz de la aplicación hacia el elemento que provocó el evento y se notifica como el origen de datos del evento. No todos los escenarios de evento admiten o requieran eventos de vista previa; en este tema describe las situaciones donde existen eventos de vista previa, cómo las aplicaciones o componentes deberían mostrarlos, y los casos donde crear eventos de vista previa en componentes personalizados o clases podría ser adecuado.  
  
## <a name="preview-events-and-input"></a>Eventos de vista previa y entrada  
 Al controlar eventos en general, tenga cuidado de vista previa marcar los eventos en el evento controla datos. Controlar un evento de vista previa en cualquier elemento que no sea el elemento que lo provocó (el elemento que se notifica como el origen de datos de evento) tiene el efecto de no proporcionar un elemento de la oportunidad de controlar el evento que se originó. A veces esto es el resultado deseado, especialmente si los elementos en cuestión existen en las relaciones dentro de la composición de un control.  
  
 Los eventos de entrada en concreto, eventos de vista previa también compartan instancias de datos de eventos con el evento de propagación equivalente. Si usa un controlador de clase de eventos de vista previa para marcar el evento de entrada controlado, no se invocará el controlador de clase de evento de entrada propagación. O bien, si utiliza un controlador de instancia de evento de vista previa para marcar el evento como controlado, controladores para el evento de propagación no se invocarán normalmente. Controladores de clase o instancia puede se registra o se adjunta con una opción que se debe invocar incluso si el evento está marcado como controlado, pero esa técnica no es frecuente.  
  
 Para obtener más información sobre el control de clases y cómo se relaciona con los eventos de vista previa, consulte [Marcar eventos enrutados como controlados y control de clases](marking-routed-events-as-handled-and-class-handling.md).  
  
### <a name="working-around-event-suppression-by-controls"></a>Solución de la supresión de eventos mediante controles  
 Es un escenario donde normalmente se usan los eventos de vista previa para el control compuesto de control de eventos de entrada. A veces, el autor del control suprime un determinado evento desde que se originan desde su control, quizás para sustituir un evento definido por el componente que lleva más información o implica un comportamiento más concreto. Por ejemplo, un [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> suprime <xref:System.Windows.UIElement.MouseLeftButtonDown> y <xref:System.Windows.UIElement.MouseRightButtonDown> propagación de los eventos generados por el <xref:System.Windows.Controls.Button> o sus elementos compuestos en favor de la captura del mouse y provocar un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento que siempre se genera mediante el <xref:System.Windows.Controls.Button> propio. El evento y sus datos continúan a lo largo de la ruta, pero dado que el <xref:System.Windows.Controls.Button> marca los datos del evento como <xref:System.Windows.RoutedEventArgs.Handled%2A>, solo los controladores para el evento que se indique específicamente actúan en el `handledEventsToo` caso se invocan.  Si otros elementos hacia la raíz de la aplicación aún deseaban una oportunidad de controlar un evento suprimido por el control, una alternativa consiste en adjuntar controladores en el código con `handledEventsToo` especificado como `true`. Pero a menudo es una técnica más sencilla cambiar la dirección de enrutamiento que controla para que sea el equivalente de vista previa de un evento de entrada. Por ejemplo, si un control suprime <xref:System.Windows.UIElement.MouseLeftButtonDown>, intente adjuntar un controlador para <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> en su lugar. Esta técnica solo funciona para los eventos de entrada de elemento base como <xref:System.Windows.UIElement.MouseLeftButtonDown>. Estos eventos de entrada de usan pares de túnel/propagación, provocan ambos eventos y compartan los datos del evento.  
  
 Cada una de estas técnicas tiene efectos secundarios o limitaciones. El efecto de controlar el evento de vista previa es que controle el evento en ese momento podría deshabilitar los controladores que esperan controlar el evento de propagación, y por lo tanto, la limitación es que normalmente no resulta una buena idea para marcar el evento como controlado mientras está todavía en el Previ Novedades de la parte la ruta. La limitación de la `handledEventsToo` técnica es que no se puede especificar un `handledEventsToo` controlador en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] como un atributo, debe registrar el controlador de eventos en el código después de obtener una referencia de objeto para el elemento donde es el controlador que se adjuntará.  
  
## <a name="see-also"></a>Vea también

- [Marcar eventos enrutados como controlados y control de clases](marking-routed-events-as-handled-and-class-handling.md)
- [Información general sobre eventos enrutados](routed-events-overview.md)

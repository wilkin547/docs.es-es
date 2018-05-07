---
title: Eventos de vista previa
ms.date: 03/30/2017
helpviewer_keywords:
- Preview events [WPF]
- suppressing events [WPF]
- events [WPF], Preview
- events [WPF], suppressing
ms.assetid: b5032308-aa9c-4d02-af11-630ecec8df7e
ms.openlocfilehash: 2d6c1ab32cb43730af2f935f4bd4405059994c12
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="preview-events"></a>Eventos de vista previa
Eventos de vista previa, también conocidos como eventos de túnel, son eventos enrutados que se pasa la dirección de la ruta desde la raíz de la aplicación hacia el elemento que provocó el evento y se notifica como el origen de datos del evento. No todos los escenarios de eventos admiten o requieren los eventos de vista previa. en este tema se describe las situaciones donde existen eventos de vista previa, cómo las aplicaciones o componentes deben controlar, y los casos donde la creación de eventos de vista previa en componentes personalizados o de clases puede ser adecuado.  
  
## <a name="preview-events-and-input"></a>Eventos de vista previa y entrada  
 Cuando se controla la vista previa de eventos en general, tenga cuidado al marcar los eventos en el evento controla datos. Controle un evento de vista previa en cualquier elemento distinto del elemento que generó (es decir, el elemento que se notifica como el origen de los datos del evento) tiene el efecto de no proporciona la oportunidad de controlar el evento que se haya originado de un elemento. A veces, esto es el resultado deseado, especialmente si los elementos en cuestión existan en relaciones dentro de la composición de un control.  
  
 Para eventos de entrada en concreto, eventos de vista previa también comparten instancias de datos de evento con el evento de propagación equivalente. Si usa un controlador de clase de eventos de vista previa para marcar el evento de entrada controlado, no se invocará el controlador de clase de evento de entrada propagación. O bien, si utiliza un controlador de instancia de evento de vista previa para marcar el evento como controlado, controladores para el evento de propagación no normalmente se invocará. Controladores de clase o instancia se registrado o asociados con una opción que se debe invocar incluso si el evento está marcado como controlado, pero esta técnica no suele utilizarse.  
  
 Para obtener más información sobre el control de clases y cómo se relaciona con los eventos de vista previa vea [Marcar eventos enrutados como Handled and Class Handling](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md).  
  
### <a name="working-around-event-suppression-by-controls"></a>Solución de la supresión de eventos mediante controles  
 Un escenario donde normalmente se utilizan los eventos de vista previa es para el control de compuestas de control de eventos de entrada. A veces, el autor del control suprime un determinado evento desde que se originan desde su control, quizás para sustituir un evento definido por el componente que contiene más información o implica un comportamiento más concreto. Por ejemplo, un [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> suprime <xref:System.Windows.UIElement.MouseLeftButtonDown> y <xref:System.Windows.UIElement.MouseLeftButtonDown> propagación de eventos generados por el <xref:System.Windows.Controls.Button> o sus elementos compuestos en favor de captura del mouse y generar un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos que siempre se generan mediante el <xref:System.Windows.Controls.Button> propio. El evento y sus datos siguen a lo largo de la ruta, sin embargo, dado el <xref:System.Windows.Controls.Button> marca los datos del evento como <xref:System.Windows.RoutedEventArgs.Handled%2A>, solo los controladores para el evento indicado específicamente que actúe en el `handledEventsToo` caso se invocan.  Si aún deseaban que otros elementos hacia la raíz de la aplicación una oportunidad para controlar un evento suprimido de control, una alternativa consiste en asociar controladores en el código con `handledEventsToo` especificado como `true`. Pero a menudo es una técnica más sencilla cambiar la dirección de enrutamiento controlar para que sea el equivalente de vista previa de un evento de entrada. Por ejemplo, si un control suprime <xref:System.Windows.UIElement.MouseLeftButtonDown>, intentar volver a adjuntar un controlador para <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> en su lugar. Esta técnica solo funciona para los eventos de entrada del elemento base como <xref:System.Windows.UIElement.MouseLeftButtonDown>. Estos eventos de entrada utilizan pares de túnel/propagación, provocan ambos eventos y compartan los datos del evento.  
  
 Cada una de estas técnicas tiene efectos secundarios o limitaciones. El efecto secundario de controlar el evento de vista previa es que controlar el evento en ese momento podría deshabilitar los controladores que esperan controlar el evento de propagación, y por lo tanto, la limitación es que normalmente no resulta una buena idea para marcar el evento como controlado mientras está conectado a la Previ parte ew de la ruta. La limitación de la `handledEventsToo` técnica es que no se puede especificar un `handledEventsToo` controlador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] como un atributo, debe registrar el controlador de eventos en código después de obtener una referencia de objeto para el elemento donde es el controlador que se adjuntará.  
  
## <a name="see-also"></a>Vea también  
 [Marcar eventos enrutados como controlados y control de clases](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)  
 [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md)

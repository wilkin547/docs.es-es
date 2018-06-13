---
title: Eventos de cambio de propiedades
ms.date: 03/30/2017
helpviewer_keywords:
- dependency properties [WPF], change events
- property value changes [WPF]
- change events [WPF], property
- events [WPF], change in property values
- creating property triggers [WPF]
- property change events [WPF], types of
- property change events [WPF]
- property triggers [WPF]
- identifying changed property events [WPF]
- property triggers [WPF], definition of
ms.assetid: 0a7989df-9674-4cc1-bc50-5d8ef5d9c055
ms.openlocfilehash: ac2a44eb92e384851bbe6ac860fd9b46d3377a06
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547656"
---
# <a name="property-change-events"></a>Eventos de cambio de propiedades
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] define varios eventos que se producen como respuesta a un cambio en el valor de una propiedad. A menudo, la propiedad es una propiedad de dependencia. A veces, el propio evento es un evento enrutado y, otras, es un evento [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] estándar. La definición del evento varía según el escenario, porque algunos cambios de propiedad deben enrutarse a través de un árbol de elementos, mientras que otros cambios de propiedad, generalmente, solo son de interés para el objeto en el que se modifica la propiedad.  
  
## <a name="identifying-a-property-change-event"></a>Identificar un evento de cambio de propiedad  
 No todos los eventos que informan de un cambio de propiedad se identifican de manera explícita como evento de cambio de propiedad mediante un patrón de signatura o de nomenclatura. Por lo general, la descripción del evento de la documentación del [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)] indica si el evento está vinculado directamente a un cambio de valor de propiedad y proporciona referencias cruzadas entre la propiedad y el evento.  
  
### <a name="routedpropertychanged-events"></a>Eventos RoutedPropertyChanged  
 Algunos eventos usan un delegado y un tipo de datos de evento que se usan explícitamente para los eventos de cambio de propiedad. El tipo de datos de evento es <xref:System.Windows.RoutedPropertyChangedEventArgs%601>, y el delegado <xref:System.Windows.RoutedPropertyChangedEventHandler%601>. El delegado y los datos del evento tienen un parámetro de tipo genérico que se usa para especificar el tipo real de la propiedad que cambia al definir el controlador. Los datos del evento contienen dos propiedades, <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A> y <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A>, que son, a continuación, pasa como el argumento de tipo en el evento datos.  
  
 La parte "Routed" del nombre indica que el evento con la propiedad cambiada se registra como evento enrutado. La ventaja de enrutar un evento con la propiedad cambiada es que el nivel superior de un control puede recibir eventos con la propiedad cambiada si las propiedades de los elementos secundarios (las partes compuestas del control) cambian de valor. Por ejemplo, podría crear un control que incorpora un <xref:System.Windows.Controls.Primitives.RangeBase> de control como un <xref:System.Windows.Controls.Slider>. Si el valor de la <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> cambios de propiedades en la parte del control deslizante, puede desear controlar este cambio en el control primario en lugar de en la parte.  
  
 Dado que tiene un valor anterior y uno nuevo, puede ser tentador usar este controlador de eventos como un validador para el valor de propiedad. Sin embargo, no es la intención de diseño de la mayoría de los eventos con la propiedad cambiada. Por lo general, los valores se proporcionan para que pueda actuar sobre esos valores en otras áreas de la lógica del código, pero no se recomienda modificar los valores desde el controlador de eventos y es posible que se cause una recursividad involuntaria según cómo se implemente el controlador.  
  
 Si la propiedad es una propiedad de dependencia personalizada, o si está trabajando con una clase derivada donde ha definido el código de creación de instancias, hay un mecanismo mucho mejor para el seguimiento de cambios de propiedad que se halla integrado en el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema de propiedad: el las devoluciones de llamada del sistema de propiedad <xref:System.Windows.CoerceValueCallback> y <xref:System.Windows.PropertyChangedCallback>. Para obtener más información acerca de cómo puede usar el sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para la validación y la coerción, consulte [Devoluciones de llamada y validación de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md) y [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).  
  
### <a name="dependencypropertychanged-events"></a>Eventos DependencyPropertyChanged  
 Otro par de tipos que forman parte de un escenario de evento de cambio de propiedad es <xref:System.Windows.DependencyPropertyChangedEventArgs> y <xref:System.Windows.DependencyPropertyChangedEventHandler>. No se enrutan los eventos para estos cambios de propiedad: son eventos [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] estándares. <xref:System.Windows.DependencyPropertyChangedEventArgs> es un tipo de informe porque no se deriva de datos de evento raro <xref:System.EventArgs>; <xref:System.Windows.DependencyPropertyChangedEventArgs> es una estructura, no una clase.  
  
 Eventos que usan <xref:System.Windows.DependencyPropertyChangedEventArgs> y <xref:System.Windows.DependencyPropertyChangedEventHandler> son ligeramente más comunes que `RoutedPropertyChanged` eventos. Un ejemplo de un evento que utiliza estos tipos es <xref:System.Windows.UIElement.IsMouseCapturedChanged>.  
  
 Al igual que <xref:System.Windows.RoutedPropertyChangedEventArgs%601>, <xref:System.Windows.DependencyPropertyChangedEventArgs> también informa de un valor antiguo y nuevo para la propiedad. Además, se aplican las mismas consideraciones sobre lo que puede hacer con los valores. Por lo general, no se recomienda que intente volver a cambiar los valores en el remitente como respuesta al evento.  
  
## <a name="property-triggers"></a>Desencadenadores de propiedad  
 Un concepto estrechamente relacionado con un evento de cambio de propiedad es un desencadenador de propiedad. Un desencadenador de propiedad se crea dentro de un estilo o una plantilla y le permite crear un comportamiento condicional basado en el valor de la propiedad donde se asigna el desencadenador de propiedad.  
  
 La propiedad de un desencadenador de propiedad debe ser una propiedad de dependencia. Puede ser (y, con frecuencia, lo es) una propiedad de dependencia de solo lectura. Un buen indicador de si una propiedad de dependencia expuesta por un control está diseñada parcialmente como un desencadenador de propiedad es si el nombre de propiedad comienza por "Is". Las propiedades que tienen este nombre suelen ser una propiedad de dependencia booleana de solo lectura en que el escenario principal para la propiedad está informando de un estado de control que puede tener consecuencias en la interfaz de usuario en tiempo real y, por lo tanto, es un candidato de desencadenador de propiedad.  
  
 Algunas de estas propiedades también tienen un evento de cambio de propiedad dedicado. Por ejemplo, la propiedad <xref:System.Windows.UIElement.IsMouseCaptured%2A> tiene un evento de cambio de propiedad <xref:System.Windows.UIElement.IsMouseCapturedChanged>. La propiedad en sí es de sólo lectura, con su valor ajustado por el sistema de entrada y genera el sistema de entrada <xref:System.Windows.UIElement.IsMouseCapturedChanged> en cada cambio en tiempo real.  
  
 En comparación con un evento de cambio de propiedad auténtico, el uso de un desencadenador de propiedad para actuar sobre un cambio de propiedad tiene algunas limitaciones.  
  
 Los desencadenadores de propiedad funcionan mediante una lógica de coincidencia exacta. Especifica una propiedad y un valor que indica el valor específico por el que el desencadenador se activa. Por ejemplo: `<Setter Property="IsMouseCaptured" Value="true"> ... </Setter>`. Debido a esta limitación, la mayoría de los usos de desencadenadores de propiedad será para propiedades booleanas o propiedades que usan un valor de enumeración dedicado, donde el intervalo de valores posibles es lo bastante administrable para definir un desencadenador para cada caso. O bien pueden existir desencadenadores de propiedad solo para valores especiales, como cuando un recuento de elementos llega a cero, y no habría ningún desencadenador que reconociera los casos en los que vuelve a cambiar el valor de la propiedad en dirección contraria a cero de nuevo (en lugar de desencadenadores para todos los casos, es posible que necesite aquí un controlador de evento de código o un comportamiento predeterminado que vuelva a alternar el estado del desencadenador cuando el valor no sea cero).  
  
 La sintaxis del desencadenador de propiedad es análoga a una instrucción "if" en programación. Si se cumple la condición del desencadenador, el valor "body" del desencadenador de propiedad será "executed". El valor "body" de un desencadenador de propiedad no es código, sino marcado. Ese marcado está limitado mediante uno o más <xref:System.Windows.Setter> elementos para establecer otras propiedades del objeto donde se aplica el estilo o la plantilla.  
  
 Para compensar la condición "if" de un desencadenador de propiedad que tiene una gran variedad de valores posibles, es normalmente se recomienda establecer ese mismo valor de propiedad a un valor predeterminado mediante una <xref:System.Windows.Setter>. De esta manera, el <xref:System.Windows.Trigger> establecedor independiente tendrá prioridad cuando es true, la condición desencadenadora y <xref:System.Windows.Setter> que no está dentro un <xref:System.Windows.Trigger> tendrá prioridad siempre que la condición desencadenadora es false.  
  
 Los desencadenadores de propiedad, por lo general, suelen ser adecuados para escenarios donde pueden cambiar una o varias propiedades de apariencia, en función del estado de otra propiedad del mismo elemento.  
  
 Para obtener más información acerca de los desencadenadores de propiedad, consulte [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)

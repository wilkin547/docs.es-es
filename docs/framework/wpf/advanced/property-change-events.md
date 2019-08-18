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
ms.openlocfilehash: 06056b492439531aa60becbb7bca250a439bfb68
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567426"
---
# <a name="property-change-events"></a>Eventos de cambio de propiedades
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] define varios eventos que se producen como respuesta a un cambio en el valor de una propiedad. A menudo, la propiedad es una propiedad de dependencia. A veces, el propio evento es un evento enrutado y, a veces, es un evento de Common Language Runtime estándar (CLR). La definición del evento varía según el escenario, porque algunos cambios de propiedad deben enrutarse a través de un árbol de elementos, mientras que otros cambios de propiedad, generalmente, solo son de interés para el objeto en el que se modifica la propiedad.  
  
## <a name="identifying-a-property-change-event"></a>Identificar un evento de cambio de propiedad  
 No todos los eventos que informan de un cambio de propiedad se identifican de manera explícita como evento de cambio de propiedad mediante un patrón de signatura o de nomenclatura. Por lo general, la descripción del evento en la documentación del SDK indica si el evento está directamente vinculado a un cambio de valor de propiedad y proporciona referencias cruzadas entre la propiedad y el evento.  
  
### <a name="routedpropertychanged-events"></a>Eventos RoutedPropertyChanged  
 Algunos eventos usan un delegado y un tipo de datos de evento que se usan explícitamente para los eventos de cambio de propiedad. El tipo de datos del <xref:System.Windows.RoutedPropertyChangedEventArgs%601>evento es y el delegado <xref:System.Windows.RoutedPropertyChangedEventHandler%601>es. El delegado y los datos del evento tienen un parámetro de tipo genérico que se usa para especificar el tipo real de la propiedad que cambia al definir el controlador. Los datos de evento contienen dos propiedades <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A> , <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A>y, que se pasan entonces como el argumento de tipo en los datos de evento.  
  
 La parte "Routed" del nombre indica que el evento con la propiedad cambiada se registra como evento enrutado. La ventaja de enrutar un evento con la propiedad cambiada es que el nivel superior de un control puede recibir eventos con la propiedad cambiada si las propiedades de los elementos secundarios (las partes compuestas del control) cambian de valor. Por ejemplo, puede crear un control que incorpore un <xref:System.Windows.Controls.Primitives.RangeBase> control como. <xref:System.Windows.Controls.Slider> Si el valor de la <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> propiedad cambia en la parte del control deslizante, puede que desee controlar ese cambio en el control primario, en lugar de en el elemento.  
  
 Dado que tiene un valor anterior y uno nuevo, puede ser tentador usar este controlador de eventos como un validador para el valor de propiedad. Sin embargo, no es la intención de diseño de la mayoría de los eventos con la propiedad cambiada. Por lo general, los valores se proporcionan para que pueda actuar sobre esos valores en otras áreas de la lógica del código, pero no se recomienda modificar los valores desde el controlador de eventos y es posible que se cause una recursividad involuntaria según cómo se implemente el controlador.  
  
 Si la propiedad es una propiedad de dependencia personalizada, o si está trabajando con una clase derivada en la que ha definido el código de creación de instancias, hay un mecanismo mucho mejor para realizar el seguimiento de los cambios de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedad que se integran en el sistema de propiedades: devoluciones <xref:System.Windows.CoerceValueCallback> de llamada <xref:System.Windows.PropertyChangedCallback>del sistema de propiedades y. Para obtener más información acerca de cómo puede usar el sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para la validación y la coerción, consulte [Devoluciones de llamada y validación de las propiedades de dependencia](dependency-property-callbacks-and-validation.md) y [Propiedades de dependencia personalizadas](custom-dependency-properties.md).  
  
### <a name="dependencypropertychanged-events"></a>Eventos DependencyPropertyChanged  
 Otro par de tipos que forman parte de un escenario de eventos de cambio <xref:System.Windows.DependencyPropertyChangedEventArgs> de <xref:System.Windows.DependencyPropertyChangedEventHandler>propiedad es y. Los eventos de estos cambios de propiedad no se enrutan; son eventos CLR estándar. <xref:System.Windows.DependencyPropertyChangedEventArgs>es un tipo de informe de datos de eventos inusual porque no se <xref:System.EventArgs>deriva de; <xref:System.Windows.DependencyPropertyChangedEventArgs> es una estructura, no una clase.  
  
 Los eventos que <xref:System.Windows.DependencyPropertyChangedEventArgs> usan <xref:System.Windows.DependencyPropertyChangedEventHandler> y son ligeramente más comunes `RoutedPropertyChanged` que los eventos. Un ejemplo de un evento que usa estos tipos es <xref:System.Windows.UIElement.IsMouseCapturedChanged>.  
  
 Como <xref:System.Windows.RoutedPropertyChangedEventArgs%601> ,<xref:System.Windows.DependencyPropertyChangedEventArgs> también informa de un valor nuevo y antiguo para la propiedad. Además, se aplican las mismas consideraciones sobre lo que puede hacer con los valores. Por lo general, no se recomienda que intente volver a cambiar los valores en el remitente como respuesta al evento.  
  
## <a name="property-triggers"></a>Desencadenadores de propiedad  
 Un concepto estrechamente relacionado con un evento de cambio de propiedad es un desencadenador de propiedad. Un desencadenador de propiedad se crea dentro de un estilo o una plantilla y le permite crear un comportamiento condicional basado en el valor de la propiedad donde se asigna el desencadenador de propiedad.  
  
 La propiedad de un desencadenador de propiedad debe ser una propiedad de dependencia. Puede ser (y, con frecuencia, lo es) una propiedad de dependencia de solo lectura. Un buen indicador de si una propiedad de dependencia expuesta por un control está diseñada parcialmente como un desencadenador de propiedad es si el nombre de propiedad comienza por "Is". Las propiedades que tienen este nombre suelen ser una propiedad de dependencia booleana de solo lectura en que el escenario principal para la propiedad está informando de un estado de control que puede tener consecuencias en la interfaz de usuario en tiempo real y, por lo tanto, es un candidato de desencadenador de propiedad.  
  
 Algunas de estas propiedades también tienen un evento de cambio de propiedad dedicado. Por ejemplo, la propiedad <xref:System.Windows.UIElement.IsMouseCaptured%2A> tiene un evento <xref:System.Windows.UIElement.IsMouseCapturedChanged>de cambio de propiedad. La propiedad es de solo lectura, con su valor ajustado por el sistema de entrada, y el sistema de entrada <xref:System.Windows.UIElement.IsMouseCapturedChanged> genera en cada cambio en tiempo real.  
  
 En comparación con un evento de cambio de propiedad auténtico, el uso de un desencadenador de propiedad para actuar sobre un cambio de propiedad tiene algunas limitaciones.  
  
 Los desencadenadores de propiedad funcionan mediante una lógica de coincidencia exacta. Especifica una propiedad y un valor que indica el valor específico por el que el desencadenador se activa. Por ejemplo: `<Setter Property="IsMouseCaptured" Value="true"> ... </Setter>`. Debido a esta limitación, la mayoría de los usos de desencadenadores de propiedad será para propiedades booleanas o propiedades que usan un valor de enumeración dedicado, donde el intervalo de valores posibles es lo bastante administrable para definir un desencadenador para cada caso. O bien pueden existir desencadenadores de propiedad solo para valores especiales, como cuando un recuento de elementos llega a cero, y no habría ningún desencadenador que reconociera los casos en los que vuelve a cambiar el valor de la propiedad en dirección contraria a cero de nuevo (en lugar de desencadenadores para todos los casos, es posible que necesite aquí un controlador de evento de código o un comportamiento predeterminado que vuelva a alternar el estado del desencadenador cuando el valor no sea cero).  
  
 La sintaxis del desencadenador de propiedad es análoga a una instrucción "if" en programación. Si se cumple la condición del desencadenador, el valor "body" del desencadenador de propiedad será "executed". El valor "body" de un desencadenador de propiedad no es código, sino marcado. Dicho marcado se limita al uso de uno o <xref:System.Windows.Setter> varios elementos para establecer otras propiedades del objeto en el que se aplica el estilo o la plantilla.  
  
 Para desplazar la condición "if" de un desencadenador de propiedad que tiene una amplia variedad de valores posibles, generalmente se recomienda establecer el mismo valor de propiedad en un valor <xref:System.Windows.Setter>predeterminado mediante. De esta manera, <xref:System.Windows.Trigger> el establecedor contenido tendrá prioridad cuando la condición del desencadenador sea true <xref:System.Windows.Setter> y el <xref:System.Windows.Trigger> que no esté dentro de tendrá prioridad siempre que la condición del desencadenador sea falsa.  
  
 Los desencadenadores de propiedad, por lo general, suelen ser adecuados para escenarios donde pueden cambiar una o varias propiedades de apariencia, en función del estado de otra propiedad del mismo elemento.  
  
 Para obtener más información acerca de los desencadenadores de propiedad, consulte [Aplicar estilos y plantillas](../controls/styling-and-templating.md).  
  
## <a name="see-also"></a>Vea también

- [Información general sobre eventos enrutados](routed-events-overview.md)
- [Información general sobre las propiedades de dependencia](dependency-properties-overview.md)

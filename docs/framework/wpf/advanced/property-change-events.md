---
title: "Eventos de cambio de propiedades | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "eventos de cambio [WPF], propiedad"
  - "crear desencadenadores de propiedad [WPF]"
  - "propiedades de dependencia [WPF], eventos de cambio"
  - "eventos [WPF], cambio en los valores de propiedad"
  - "identificar eventos de cambio de propiedad [WPF]"
  - "eventos de cambio de propiedad [WPF]"
  - "eventos de cambio de propiedad [WPF], tipos de"
  - "desencadenadores de propiedad [WPF]"
  - "desencadenadores de propiedad [WPF], definición de"
  - "cambios en el valor de propiedad [WPF]"
ms.assetid: 0a7989df-9674-4cc1-bc50-5d8ef5d9c055
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Eventos de cambio de propiedades
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] define varios eventos que se provocan en respuesta a un cambio en el valor de una propiedad.  A menudo, la propiedad es una [propiedad de dependencia](GTMT).  A veces, el propio evento es un [evento enrutado](GTMT) y, otras, un evento [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] estándar.  La definición del evento varía, dependiendo del escenario, porque algunos cambios de propiedad deben enrutarse preferentemente a través de un árbol de elementos, mientras que otros cambios de propiedad afectan tan sólo al objeto cuya propiedad se modifica.  
  
## Identificar un evento de cambio de propiedad  
 No todos los eventos que comunican un cambio de propiedad se identifican de manera explícita, ya sea mediante un modelo de firma o de denominación.  En general, en la descripción del evento de la documentación del [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)] se indica si el evento está vinculado directamente a un cambio en el valor de una propiedad y se proporcionan referencias cruzadas entre esta última y el evento.  
  
### Eventos RoutedPropertyChanged  
 Algunos eventos utilizan un delegado y un tipo de datos de evento que se usan explícitamente para los eventos de cambio de propiedad.  El tipo de datos de evento es <xref:System.Windows.RoutedPropertyChangedEventArgs%601> y el delegado es <xref:System.Windows.RoutedPropertyChangedEventHandler%601>.  Tanto los datos como el delegado del evento tienen un parámetro de tipo genérico que se utiliza para especificar, al definir el controlador, el tipo real de la propiedad que cambia.  Los datos del evento contienen dos propiedades, <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A> y <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A>, que se pasan como argumento de tipo en los datos de evento.  
  
 El elemento "Routed" del nombre indica que el evento de cambio de propiedad se registra como un evento enrutado.  La ventaja de enrutar un evento de cambio de propiedad es que el nivel superior de un control puede recibir este tipo de eventos cuando se modifica el valor de las propiedades de los elementos secundarios \(elementos compuestos del control\).  Por ejemplo, se puede crear un control que incorpore un control <xref:System.Windows.Controls.Primitives.RangeBase>, como <xref:System.Windows.Controls.Slider>.  Si cambia el valor de la propiedad <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> en el elemento de control deslizante, puede ser conveniente controlar este cambio en el control primario, en lugar de en dicho elemento.  
  
 Al haber un valor anterior y otro nuevo, podría caerse en la tentación de utilizar este controlador de eventos como un validador del valor de propiedad.  Sin embargo, no es esta la intención del diseño de la mayoría de los eventos de cambio de propiedad.  En general, se proporcionan los valores para permitir actuar con ellos en otras áreas lógicas del código, pero no se recomienda modificar valores desde el interior del controlador de eventos, ya que podría provocar una recursividad involuntaria según cómo se implemente este último.  
  
 Si la propiedad es una propiedad de dependencia personalizada, o si trabaja con una clase derivada donde ha definido el código de creación de instancias, existe un mecanismo mucho mejor para realizar el seguimiento de los cambios de las propiedades integrado en el sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: las devoluciones de llamada <xref:System.Windows.CoerceValueCallback> y <xref:System.Windows.PropertyChangedCallback> a las propiedades del sistema.  Para obtener más detalles sobre cómo usar el sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para validar y convertir valores, vea [Devoluciones de llamada y validación de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md) y [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).  
  
### Eventos DependencyPropertyChanged  
 Otros dos tipos que forman parte de un escenario de evento de cambio de propiedad son <xref:System.Windows.DependencyPropertyChangedEventArgs> y <xref:System.Windows.DependencyPropertyChangedEventHandler>.  No se enrutan los eventos para estos cambios de propiedad; son los eventos de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] estándar.  <xref:System.Windows.DependencyPropertyChangedEventArgs> es un tipo de informes de datos de eventos inusual, porque no se deriva de <xref:System.EventArgs>; <xref:System.Windows.DependencyPropertyChangedEventArgs> es una estructura, no una clase.  
  
 Los eventos que utilizan <xref:System.Windows.DependencyPropertyChangedEventArgs> y <xref:System.Windows.DependencyPropertyChangedEventHandler> son ligeramente más comunes que los eventos `RoutedPropertyChanged`.  Un ejemplo de un evento que utiliza estos tipos es <xref:System.Windows.UIElement.IsMouseCapturedChanged>.  
  
 Al igual que <xref:System.Windows.RoutedPropertyChangedEventArgs%601>, <xref:System.Windows.DependencyPropertyChangedEventArgs> también comunica un valor anterior y un valor nuevo para la propiedad.  Asimismo, son aplicables las mismas consideraciones sobre lo que se puede hacer con los valores; en general no se recomienda que se intente cambiar de nuevo los valores en el remitente en respuesta al evento.  
  
## Desencadenadores de propiedades  
 Un concepto estrechamente relacionado con los eventos de cambio de propiedad son los desencadenadores de propiedad.  Un desencadenador de propiedad se crea dentro de un estilo o plantilla, y permite crear un comportamiento condicional basado en el valor de la propiedad a la que se asigna el desencadenador de propiedad.  
  
 La propiedad correspondiente a un desencadenador de propiedad debe ser de dependencia.  Puede ser \(y suele ser\) una propiedad de dependencia de sólo lectura.  Un indicador adecuado para saber cuándo una propiedad de dependencia expuesta por un control está diseñada \(al menos en parte\) para actuar como desencadenador de propiedad, es que su nombre empiece por "Is".  Las propiedades que tienen este nombre suelen ser propiedades de dependencia de tipo Boolean de sólo lectura cuyo principal escenario consiste en informar sobre un estado del control que pueda afectar a la interfaz de usuario en tiempo real y, por consiguiente, es probable que sea un desencadenador de propiedad.  
  
 Algunas de estas propiedades también tienen un evento de cambio de propiedad dedicado.  Por ejemplo, la propiedad <xref:System.Windows.UIElement.IsMouseCaptured%2A> tiene un evento de cambio de propiedad <xref:System.Windows.UIElement.IsMouseCapturedChanged>.  La propiedad en sí es de sólo lectura, y su valor lo ajusta el sistema de entrada, que provoca el evento <xref:System.Windows.UIElement.IsMouseCapturedChanged> cada vez que se produce un cambio en tiempo real.  
  
 En comparación con un evento de cambio propiedad auténtico, el uso de un desencadenador de propiedad que actúe en caso de cambio de propiedad tiene algunas limitaciones.  
  
 Los desencadenadores de propiedad funcionan aplicando una lógica de coincidencia exacta.  Es preciso especificar una propiedad y un valor que indique el valor concreto que provocará que el desencadenador se active.  Por ejemplo: `<Setter Property="IsMouseCaptured" Value="true"> ... </Setter>`.  Debido a esta limitación, la mayoría de los usos de los desencadenadores de propiedad se centran en las propiedades de tipo Boolean o en aquéllas que toman un valor de enumeración dedicado, cuyo intervalo de valores posibles es lo bastante manejable para definir un desencadenador para cada caso.  O bien, puede que para algunos valores especiales únicamente haya desencadenadores de propiedad, por ejemplo, cuando un recuento de elementos llega a cero, y que no haya ningún desencadenador para los casos en que el valor de propiedad vuelva a cambiar y deje de ser cero \(en lugar de desencadenadores para todos los casos, en esta situación podría necesitar un controlador de eventos mediante código, o bien un comportamiento predeterminado que cambie al estado anterior cuando el valor sea distinto de cero\).  
  
 La sintaxis de los desencadenadores de propiedad es análoga a las instrucciones "if" de programación.  Si la condición de activación se cumple, entonces se "ejecuta" el "cuerpo" del desencadenador de propiedad.  El "cuerpo" de un desencadenador de propiedad no es código, sino marcado.  Ese marcado está limitado al uso de uno o más elementos <xref:System.Windows.Setter> para establecer otras propiedades del objeto donde se aplica el estilo o la plantilla.  
  
 Para compensar la condición "if" de un desencadenador de propiedad que posee gran variedad de valores posibles, suele ser aconsejable establecer ese mismo valor de propiedad en un valor predeterminado mediante <xref:System.Windows.Setter>.  De esta manera, el establecedor contenido en <xref:System.Windows.Trigger> tendrá la prioridad cuando se cumpla la condición de activación, y el objeto <xref:System.Windows.Setter> que no esté contenido en <xref:System.Windows.Trigger> tendrá prioridad siempre que no se cumpla la condición de activación.  
  
 Los desencadenadores de propiedad suelen ser adecuados para escenarios en que deben cambiar una o varias propiedades de aspecto basándose en el estado de otra propiedad del mismo elemento.  
  
 Para obtener más información sobre las desencadenadores de propiedad, vea [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
## Vea también  
 [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
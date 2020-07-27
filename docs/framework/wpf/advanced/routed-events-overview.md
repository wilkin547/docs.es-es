---
title: Información general sobre eventos enrutados
description: Obtenga información sobre los eventos enrutados en Windows Presentation Foundation, incluido cómo se enrutan a través de un árbol de elementos y cómo crear eventos enrutados personalizados.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- attached events [WPF]
- grouped button set [WPF]
- routed events [WPF]
- events [WPF], routed
- tunneling [WPF]
- events [WPF], attached
- routing strategies for events [WPF]
- button set [WPF], grouped
- bubbling [WPF]
ms.assetid: 1a2189ae-13b4-45b0-b12c-8de2e49c29d2
ms.openlocfilehash: d18b511a4886c68922cccac14942eb54e5735a71
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164810"
---
# <a name="routed-events-overview"></a>Información general sobre eventos enrutados

En este tema se describe el concepto de eventos enrutados en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. En el tema se define la terminología de los eventos enrutados, se describe cómo se enrutan a través de un árbol de elementos, se resume cómo controlar los eventos enrutados y se explica cómo crear sus propios eventos enrutados personalizados.

<a name="prerequisites"></a>

## <a name="prerequisites"></a>Requisitos previos

En este tema se da por supuesto que tiene conocimientos básicos del Common Language Runtime (CLR) y la programación orientada a objetos, así como el concepto de cómo se pueden distinguir las relaciones entre los [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elementos como un árbol. Para seguir los ejemplos de este tema, también debe comprender [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y saber cómo escribir páginas o aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] muy básicas. Para obtener más información, vea [Tutorial: mi primera aplicación de escritorio WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md) e [información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md).

<a name="routing"></a>

## <a name="what-is-a-routed-event"></a>¿Qué es un evento enrutado?

Los eventos enrutados se pueden considerar desde dos perspectivas: funcional y de implementación. Aquí se presentan ambas definiciones, dado que algunas personas encuentran que una es más útil que la otra.

Definición funcional: un evento enrutado es un tipo de evento que puede invocar controladores en varios agentes de escucha en un árbol de elementos, en lugar de simplemente en el objeto que ha generado el evento.

Definición de implementación: un evento enrutado es un evento CLR respaldado por una instancia de la <xref:System.Windows.RoutedEvent> clase y se procesa mediante el [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] sistema de eventos.

Una aplicación típica de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contiene muchos elementos. Tanto si se crean en código como si se declaran en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], estos elementos se relacionan entre sí a través de un árbol de elementos. En función de la definición del evento, la ruta de eventos puede viajar en cualquiera de las dos direcciones, pero generalmente viaja desde el elemento de origen y, después, "se propaga" en sentido ascendente por el árbol de elementos hasta que llega a la raíz (normalmente una página o una ventana). Es posible que este concepto de propagación le resulte familiar si ha trabajado previamente con el modelo de objetos DHTML.

Considere el siguiente árbol de elementos simple:

[!code-xaml[EventOvwSupport#GroupButton](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml#groupbutton)]

Este árbol de elementos genera algo parecido a lo siguiente:

![Botones sí, no y cancelar](./media/routedevent-ovw-1.gif "RoutedEvent_ovw_1")

En este árbol de elementos simplificado, el origen de un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento es uno de los <xref:System.Windows.Controls.Button> elementos, y lo <xref:System.Windows.Controls.Button> que se hizo clic es el primer elemento que tiene la oportunidad de controlar el evento. Pero si ningún controlador asociado a <xref:System.Windows.Controls.Button> actúa en el evento, el evento se propagará hacia arriba hasta el <xref:System.Windows.Controls.Button> elemento primario en el árbol de elementos, que es <xref:System.Windows.Controls.StackPanel> . Potencialmente, el evento se propaga a <xref:System.Windows.Controls.Border> y después más allá de la raíz de la página del árbol de elementos (no se muestra).

En otras palabras, la ruta de eventos para este <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento es:

Botón-->StackPanel-->Borde-->...

### <a name="top-level-scenarios-for-routed-events"></a>Escenarios de nivel superior para los eventos enrutados

A continuación se encuentra un breve resumen de los escenarios que motivaron el concepto de evento enrutado y por qué un evento CLR típico no era adecuado para estos escenarios:

**Encapsulación y composición de controles:** varios controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tienen un modelo de contenido enriquecido. Por ejemplo, puede colocar una imagen dentro de un <xref:System.Windows.Controls.Button> , lo que extiende eficazmente el árbol visual del botón. Sin embargo, la imagen agregada no debe interrumpir el comportamiento de la prueba de posicionamiento que hace que un botón responda a un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> de su contenido, incluso si el usuario hace clic en píxeles que técnicamente forman parte de la imagen.

**Puntos de datos adjuntos de controlador singular:** En Windows Forms, tendría que adjuntar varias veces el mismo controlador para procesar los eventos que podrían generarse desde varios elementos. Los eventos enrutados le permiten asociar ese controlador una sola vez, tal como se ha mostrado en el ejemplo anterior, y usar la lógica del controlador para determinar el origen del evento si fuera necesario. Por ejemplo, este podría ser el controlador para el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] mostrado anteriormente:

[!code-csharp[EventOvwSupport#GroupButtonCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml.cs#groupbuttoncodebehind)]
[!code-vb[EventOvwSupport#GroupButtonCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EventOvwSupport/visualbasic/default.xaml.vb#groupbuttoncodebehind)]

**Control de clases:** los eventos enrutados permiten un controlador estático definido por la clase. Este controlador de clase tiene la oportunidad de controlar un evento antes de que pueda hacerlo cualquiera de los controladores de instancia asociados.

**Hacer referencia a un evento sin reflexión:** determinadas técnicas de código y de marcado requieren una manera de identificar un evento concreto. Un evento enrutado crea un <xref:System.Windows.RoutedEvent> campo como identificador, lo que proporciona una técnica de identificación de eventos sólida que no requiere reflexión estática o en tiempo de ejecución.

### <a name="how-routed-events-are-implemented"></a>Cómo se implementan los eventos enrutados

Un evento enrutado es un evento CLR respaldado por una instancia de la <xref:System.Windows.RoutedEvent> clase y registrado con el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema de eventos. <xref:System.Windows.RoutedEvent>Normalmente, la instancia obtenida del registro se conserva como un `public` `static` `readonly` miembro de campo de la clase que registra y, por lo tanto, "posee" el evento enrutado. La conexión al evento CLR con el mismo nombre (que a veces se denomina el evento "contenedor") se logra invalidando las `add` `remove` implementaciones y para el evento CLR. Normalmente, `add` y `remove` se dejan como un valor predeterminado implícito que usa la sintaxis de eventos específica del lenguaje adecuada para agregar y quitar controladores de ese evento. El mecanismo de respaldo y conexión de eventos enrutados es conceptualmente similar a la forma en que una propiedad de dependencia es una propiedad de CLR respaldada por la <xref:System.Windows.DependencyProperty> clase y registrada con el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema de propiedades.

En el ejemplo siguiente se muestra la declaración de un `Tap` evento enrutado personalizado, incluido el registro y la exposición del <xref:System.Windows.RoutedEvent> campo identificador y las `add` `remove` implementaciones y para el `Tap` evento CLR.

[!code-csharp[RoutedEventCustom#AddRemoveHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#addremovehandler)]
[!code-vb[RoutedEventCustom#AddRemoveHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#addremovehandler)]

### <a name="routed-event-handlers-and-xaml"></a>Controladores de eventos enrutados y XAML

Para agregar un controlador para un evento mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], declare el nombre del evento como un atributo en el elemento que actúa como agente de escucha de eventos. El valor del atributo es el nombre de su método de controlador implementado, que debe existir en la clase parcial del archivo de código subyacente.

[!code-xaml[EventOvwSupport#SimplestSyntax](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml#simplestsyntax)]

La [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sintaxis para agregar controladores de eventos CLR estándar es la misma para agregar controladores de eventos enrutados, ya que en realidad se agregan controladores al contenedor de eventos de CLR, que tiene una implementación de eventos enrutados debajo. Para más información sobre cómo agregar controladores de eventos en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], vea [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md).

<a name="routing_strategies"></a>

## <a name="routing-strategies"></a>Estrategias de enrutamiento

Los eventos enrutados usan una de estas tres estrategias de enrutamiento:

- **Propagación:** se invocan los controladores de eventos en el origen del evento. Después, el evento enrutado va pasando por los elementos primarios sucesivos hasta alcanzar la raíz del árbol de elementos. La mayoría de los eventos enrutados usan la estrategia del enrutamiento de propagación. Los eventos con enrutamiento de propagación generalmente se usan para informar sobre cambios de entrada o de estado procedentes de controles distintos u otros elementos de la interfaz de usuario.

- **Directo:** solo el propio elemento de origen tiene la oportunidad de invocar controladores como respuesta. Es análogo al "enrutamiento" que Windows Forms usa para los eventos. Sin embargo, a diferencia de un evento CLR estándar, los eventos enrutados directos admiten el control de clases (el control de clases se explica en una próxima sección) y se pueden usar con <xref:System.Windows.EventSetter> y <xref:System.Windows.EventTrigger> .

- **Tunelización:** inicialmente, se invocan los controladores de eventos en la raíz del árbol de elementos. Después, el evento enrutado viaja a través de los elementos secundarios sucesivos a lo largo de la ruta, hacia el elemento de nodo que es el origen del evento enrutado (el elemento que ha desencadenado el evento enrutado). Los eventos con enrutamiento de tunelización se suelen usar o controlar como parte de la composición de un control, de forma que los eventos de las partes compuestas se puedan suprimir o reemplazar deliberadamente por eventos que son específicos del control completo. Los eventos de entrada proporcionados en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se suelen implementar como un par de tunelización-propagación. Los eventos de tunelización también se conocen a veces como eventos de vista previa, debido a una convención de nomenclatura que se usa para los pares.

<a name="why_use"></a>

## <a name="why-use-routed-events"></a>¿Por qué usar eventos enrutados?

Como desarrollador de aplicaciones, no siempre necesita saber ni preocuparse de si el evento que está controlando se implementa como un evento enrutado. Los eventos enrutados tienen un comportamiento especial, pero ese comportamiento es prácticamente invisible si está controlando un evento en el elemento donde se desencadena.

Los eventos enrutados demuestran su eficacia cuando se usa cualquiera de los escenarios sugeridos: definir los controladores comunes en una raíz común, componer un control personalizado o definir una clase de controles personalizada.

Los agentes de escucha y los orígenes de los eventos enrutados no necesitan compartir un evento común en su jerarquía. Any <xref:System.Windows.UIElement> o <xref:System.Windows.ContentElement> puede ser un agente de escucha de eventos para cualquier evento enrutado. Por lo tanto, puede usar el conjunto completo de eventos enrutados disponibles en el conjunto de API de trabajo como una "interfaz" conceptual en la que los elementos dispares de la aplicación pueden intercambiar información de eventos. Este concepto de "interfaz" para los eventos enrutados es especialmente aplicable a los eventos de entrada.

Los eventos enrutados también se pueden usar para comunicar datos a través del árbol de elementos, porque los datos de evento para cada evento se perpetúan en cada elemento de la ruta. Un elemento podría cambiar algo en los datos del evento, y ese cambio estaría disponible para el elemento siguiente de la ruta.

Aparte del aspecto de enrutamiento, hay otras dos razones por las que cualquier [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] evento determinado podría implementarse como un evento enrutado en lugar de un evento CLR estándar. Si está implementando sus propios eventos, también podría considerar estos principios:

- Ciertas [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] características de estilo y plantillas como <xref:System.Windows.EventSetter> y <xref:System.Windows.EventTrigger> requieren que el evento al que se hace referencia sea un evento enrutado. Este es el escenario del identificador de eventos mencionado anteriormente.

- Los eventos enrutados admiten un mecanismo de control de clases en el que la clase puede especificar métodos estáticos que tienen la oportunidad de controlar eventos enrutados antes de que cualquier controlador de instancias registrado tenga acceso a ellos. Esto es muy útil en el diseño de controles, porque una clase puede exigir comportamientos de clase orientados a eventos que no se puedan suprimir accidentalmente controlando un evento en una instancia.

Cada una de las consideraciones anteriores se explica en una sección independiente de este tema.

<a name="event_handing"></a>

## <a name="adding-and-implementing-an-event-handler-for-a-routed-event"></a>Agregar e implementar un controlador de eventos para un evento enrutado

Para agregar un controlador de eventos en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], simplemente agregue el nombre del evento a un elemento como un atributo y establezca el valor del atributo como el nombre del controlador de eventos que implementa un delegado adecuado, como en el ejemplo siguiente.

[!code-xaml[EventOvwSupport#SimplestSyntax](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml#simplestsyntax)]

`b1SetColor`es el nombre del controlador implementado que contiene el código que controla el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento. `b1SetColor`debe tener la misma firma que el <xref:System.Windows.RoutedEventHandler> delegado, que es el delegado de controlador de eventos para el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento. El primer parámetro de todos los delegados de controlador de eventos enrutados especifica el elemento al que se agrega el controlador de eventos y el segundo parámetro especifica los datos para el evento.

[!code-csharp[EventOvwSupport#SimpleHandlerA](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml.cs#simplehandlera)]
[!code-vb[EventOvwSupport#SimpleHandlerA](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EventOvwSupport/visualbasic/default.xaml.vb#simplehandlera)]

<xref:System.Windows.RoutedEventHandler>es el delegado de controlador de eventos enrutados básico. Para los eventos enrutados especializados para ciertos controles o escenarios, los delegados que deben usarse para los controladores de eventos enrutados también podrían volverse más especializados, de forma que puedan transmitir datos de evento especializados. Por ejemplo, en un escenario de entrada común, podría controlar un <xref:System.Windows.UIElement.DragEnter> evento enrutado. El controlador debe implementar el <xref:System.Windows.DragEventHandler> delegado. Mediante el uso del delegado más específico, puede procesar el <xref:System.Windows.DragEventArgs> en el controlador y leer la <xref:System.Windows.DragEventArgs.Data%2A> propiedad, que contiene la carga del portapapeles de la operación de arrastre.

Para obtener un ejemplo completo de cómo agregar un controlador de eventos a un elemento mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], vea [Cómo: Controlar un evento enrutado](how-to-handle-a-routed-event.md).

Resulta sencillo agregar un controlador para un evento enrutado en una aplicación que se crea en el código. Los controladores de eventos enrutados siempre se pueden agregar a través de un método auxiliar <xref:System.Windows.UIElement.AddHandler%2A> (que es el mismo método para el que las llamadas de respaldo existentes `add` ). Sin embargo, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] los eventos enrutados existentes generalmente tienen implementaciones de respaldo de `add` `remove` la lógica y que permiten agregar los controladores para los eventos enrutados mediante una sintaxis de eventos específica del lenguaje, que es una sintaxis más intuitiva que el método auxiliar. A continuación se muestra un ejemplo de uso del método del asistente:

[!code-csharp[EventOvwSupport#AddHandlerCode](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml.cs#addhandlercode)]
[!code-vb[EventOvwSupport#AddHandlerCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EventOvwSupport/visualbasic/default.xaml.vb#addhandlercode)]

En el ejemplo siguiente se muestra la sintaxis del operador de C# (Visual Basic tiene una sintaxis de operador ligeramente diferente debido a su control de desreferenciación):

[!code-csharp[EventOvwSupport#AddHandlerPlusEquals](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml.cs#addhandlerplusequals)]
[!code-vb[EventOvwSupport#AddHandlerPlusEquals](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EventOvwSupport/visualbasic/default.xaml.vb#addhandlerplusequals)]

Para obtener un ejemplo de cómo agregar un controlador de eventos en el código, vea [Agregar un controlador de eventos mediante código](how-to-add-an-event-handler-using-code.md).

Si usa Visual Basic, también puede usar la `Handles` palabra clave para agregar controladores como parte de las declaraciones del controlador. Para más información, vea [Control de eventos en Visual Basic y WPF](visual-basic-and-wpf-event-handling.md).

<a name="concept_handled"></a>

### <a name="the-concept-of-handled"></a>El concepto de controlado

Todos los eventos enrutados comparten una clase base de datos de eventos comunes, <xref:System.Windows.RoutedEventArgs> . <xref:System.Windows.RoutedEventArgs>define la <xref:System.Windows.RoutedEventArgs.Handled%2A> propiedad, que toma un valor booleano. El propósito de la <xref:System.Windows.RoutedEventArgs.Handled%2A> propiedad es permitir que cualquier controlador de eventos a lo largo de la ruta Marque el evento enrutado como *controlado*, estableciendo el valor de <xref:System.Windows.RoutedEventArgs.Handled%2A> en `true` . Una vez procesados por el controlador de un elemento a lo largo de la ruta, se informa de nuevo sobre los datos de evento compartidos a cada agente de escucha a lo largo de la ruta.

El valor de <xref:System.Windows.RoutedEventArgs.Handled%2A> afecta al modo en que se envía o se procesa un evento enrutado a medida que se recorre la ruta. Si <xref:System.Windows.RoutedEventArgs.Handled%2A> está `true` en los datos de evento de un evento enrutado, los controladores que escuchan el evento enrutado en otros elementos normalmente ya no se invocan para esa instancia de evento concreta. Esto se cumple tanto para los controladores adjuntos en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] como para los controladores agregados mediante sintaxis de adjuntar controladores de eventos específicas del lenguaje como `+=` o `Handles`. En el caso de los escenarios de controlador más comunes, si se marca un evento como controlado, <xref:System.Windows.RoutedEventArgs.Handled%2A> se establece en `true` "detener" el enrutamiento para una ruta de tunelización o una ruta de propagación, y también para cualquier evento que se controle en un punto de la ruta mediante un controlador de clase.

Sin embargo, hay un mecanismo de "handledEventsToo" por el que los agentes de escucha pueden seguir ejecutando controladores en respuesta a los eventos enrutados <xref:System.Windows.RoutedEventArgs.Handled%2A> `true` en los datos de evento. Es decir, la ruta de eventos no se detiene realmente al marcar los datos de evento como controlados. Solo se puede usar el mecanismo handledEventsToo en el código o en <xref:System.Windows.EventSetter> :

- En el código, en lugar de usar una sintaxis de eventos específica del lenguaje que funcione para eventos CLR generales, llame al [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] método <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> para agregar el controlador. Especifique el valor de `handledEventsToo` como `true`.

- En <xref:System.Windows.EventSetter> , establezca el <xref:System.Windows.EventSetter.HandledEventsToo%2A> atributo en `true` .

Además del comportamiento que el <xref:System.Windows.RoutedEventArgs.Handled%2A> Estado produce en los eventos enrutados, el concepto de <xref:System.Windows.RoutedEventArgs.Handled%2A> tiene implicaciones sobre cómo diseñar la aplicación y escribir el código del controlador de eventos. Puede conceptualizar <xref:System.Windows.RoutedEventArgs.Handled%2A> como un protocolo simple que exponen los eventos enrutados. El uso exacto de este protocolo depende de usted, pero el diseño conceptual de cómo se debe usar el valor de es el <xref:System.Windows.RoutedEventArgs.Handled%2A> siguiente:

- Si un evento enrutado está marcado como controlado, no es necesario que los demás elementos a lo largo de esa ruta lo controlen de nuevo.

- Si un evento enrutado no está marcado como controlado, otros agentes de escucha que se encontraban antes de la ruta han elegido no registrar un controlador o los controladores que se han registrado deciden no manipular los datos del evento y establecen <xref:System.Windows.RoutedEventArgs.Handled%2A> en `true` . (O bien, es posible que el agente de escucha actual sea el primer punto de la ruta). Los controladores del agente de escucha actual ahora tienen tres posibles cursos de acción:

  - No realizar ninguna acción; el evento sigue estando sin controlar y se enruta al agente de escucha siguiente.

  - Ejecutar código en respuesta al evento, pero tomar la determinación de que la acción realizada no ha sido lo suficientemente sustancial como para marcar el evento como controlado. El evento se enruta al agente de escucha siguiente.

  - Ejecutar código en respuesta al evento. Marcar el evento como controlado en los datos de evento pasados al controlador, porque la acción realizada se ha considerado lo suficientemente sustancial como para marcarlo como controlado. El evento sigue enrutando al siguiente agente de escucha, pero con <xref:System.Windows.RoutedEventArgs.Handled%2A> = `true` en sus datos de evento, solo `handledEventsToo` los agentes de escucha tienen la oportunidad de invocar más controladores.

Este diseño conceptual se refuerza mediante el comportamiento de enrutamiento mencionado anteriormente: es más difícil (aunque aún posible en código o estilos) adjuntar controladores para eventos enrutados que se invocan incluso si un controlador anterior a lo largo de la ruta ya está establecido <xref:System.Windows.RoutedEventArgs.Handled%2A> en `true` .

Para obtener más información sobre <xref:System.Windows.RoutedEventArgs.Handled%2A> , el control de clases de eventos enrutados y recomendaciones sobre Cuándo es adecuado marcar un evento enrutado como <xref:System.Windows.RoutedEventArgs.Handled%2A> , vea [marcar eventos enrutados como controlados y control de clases](marking-routed-events-as-handled-and-class-handling.md).

En las aplicaciones, es bastante habitual controlar un evento enrutado de propagación solamente en el objeto que lo ha desencadenado, y no preocuparse en absoluto por las características de enrutado del evento. Pero es una buena práctica marcar el evento enrutado como controlado en los datos de evento para evitar efectos secundarios imprevistos en caso de que un elemento situado más arriba en el árbol de elementos también tenga un controlador asociado para ese mismo evento enrutado.

<a name="class_handlers"></a>

## <a name="class-handlers"></a>Controladores de clase

Si está definiendo una clase que deriva de alguna manera de <xref:System.Windows.DependencyObject> , también puede definir y adjuntar un controlador de clase para un evento enrutado que sea un miembro de evento declarado o heredado de la clase. Los controladores de clase se invocan antes que cualquier controlador de agente de escucha de instancia que esté asociado a una instancia de esa clase, cada vez que un evento enrutado alcanza una instancia de elemento en su ruta.

Algunos controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tienen el control de clase inherente para ciertos eventos enrutados. Esto podría dar la impresión de que el evento enrutado nunca se genera, pero en realidad está sujeto al control de clase y sus controladores de instancia todavía pueden controlar el evento enrutado si emplea ciertas técnicas. Además, muchas clases y controles base exponen métodos virtuales que se pueden usar para invalidar el comportamiento del control de clase. Para más información sobre cómo evitar el control de clase no deseado y cómo definir su propio control de clase en una clase personalizada, vea [Marcar eventos enrutados como controlados y control de clases](marking-routed-events-as-handled-and-class-handling.md).

<a name="attached_events"></a>

## <a name="attached-events-in-wpf"></a>Evento adjuntos en WPF

El lenguaje [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] también define un tipo especial de evento denominado *evento adjunto*. Un evento adjunto permite agregar un controlador para un evento determinado a un elemento arbitrario. No es necesario que el elemento que controla el evento defina o herede el evento adjunto, y ni el objeto que genera potencialmente el evento ni la instancia que controla el destino deben definir o ser "propietarios" de ese evento como miembro de clase.

El sistema de entrada de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] emplea mucho los eventos adjuntos. Pero casi todos estos eventos adjuntos se reenvían a través de elementos base. Los eventos de entrada aparecen como eventos enrutados no adjuntos equivalentes que son miembros de la clase de elemento base. Por ejemplo, el evento adjunto subyacente <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> se puede controlar más fácilmente en cualquier determinado mediante <xref:System.Windows.UIElement> <xref:System.Windows.UIElement.MouseDown> en, en <xref:System.Windows.UIElement> lugar de tratar con la sintaxis de eventos adjuntos en o en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] código.

Para más información sobre los eventos adjuntos en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vea [Información general sobre eventos adjuntos](attached-events-overview.md).

<a name="Qualifying_Event_Names_in_XAML_for_Anticipated_Routing"></a>

## <a name="qualified-event-names-in-xaml"></a>Nombres de evento completos en XAML

Otro uso de una sintaxis similar a la sintaxis de eventos adjuntos *nombreDeTipo*.*nombreDeEvento* pero que no es en sentido estricto un uso de eventos adjuntos se produce al adjuntar controladores para eventos enrutados que son desencadenados por elementos secundarios. Los controladores se adjuntan a un elemento primario común, para aprovecharse del enrutamiento de eventos, aunque el evento enrutado pertinente no sea miembro del elemento primario común. Considere este ejemplo de nuevo:

[!code-xaml[EventOvwSupport#GroupButton](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml#groupbutton)]

Aquí, el agente de escucha del elemento primario donde se agrega el controlador es <xref:System.Windows.Controls.StackPanel> . Sin embargo, está agregando un controlador para un evento enrutado que se declaró y lo generará la <xref:System.Windows.Controls.Button> clase ( <xref:System.Windows.Controls.Primitives.ButtonBase> en realidad, pero disponible para a través de la <xref:System.Windows.Controls.Button> herencia). <xref:System.Windows.Controls.Button>"posee" el evento, pero el sistema de eventos enrutados permite que los controladores de cualquier evento enrutado se adjunten a cualquier <xref:System.Windows.UIElement> <xref:System.Windows.ContentElement> agente de escucha de instancia o que, de lo contrario, podría adjuntar agentes de escucha para un evento de Common Language Runtime (CLR). El espacio de nombres xmlns predeterminado para estos nombres de atributo de evento calificados suele ser el espacio de nombres xmlns de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] predeterminado, pero también se pueden especificar espacios de nombres con prefijos para los eventos enrutados personalizados. Para más información sobre xmlns, vea [Espacios de nombres y asignación de espacios de nombres XAML para WPF](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).

<a name="how_event_processing_works"></a>

## <a name="wpf-input-events"></a>Eventos de entrada de WPF

En la plataforma [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], con frecuencia se emplean los eventos enrutados como eventos de entrada. En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], a los nombres de los eventos enrutados con tunelización se les antepone la palabra "Preview" por convención. Los eventos de entrada suelen presentarse en parejas, donde uno es el evento de propagación y el otro es el evento de tunelización. Por ejemplo, el evento <xref:System.Windows.ContentElement.KeyDown> y el <xref:System.Windows.ContentElement.PreviewKeyDown> evento tienen la misma firma, donde el primero es el evento de entrada de propagación y el último es el evento de entrada de tunelización. En ocasiones, los eventos de entrada solo tienen una versión de propagación o quizás solo una versión enrutada directa. En la documentación, los temas sobre eventos enrutados contienen referencias cruzadas a los temas relativos a los eventos enrutados similares con estrategias de enrutamiento alternativas, si existen dichos eventos enrutados, y las secciones de las páginas de referencia administradas clarifican la estrategia de enrutamiento de cada evento enrutado.

Los eventos de entrada de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que se presentan en parejas se implementan de forma que una única acción del usuario desde la entrada, como presionar un botón del mouse, desencadenará los dos eventos enrutados de la pareja secuencialmente. En primer lugar, se desencadena el evento de tunelización, que viaja por su ruta. Después se desencadena el evento de propagación y este viaja por su ruta. Los dos eventos comparten literalmente la misma instancia de datos de evento, porque la <xref:System.Windows.UIElement.RaiseEvent%2A> llamada al método en la clase de implementación que genera el evento de propagación realiza escuchas para los datos de evento desde el evento de tunelización y lo vuelve a utilizar en el nuevo evento generado. Los agentes de escucha con controladores para el evento de tunelización tienen la primera oportunidad de marcar el evento enrutado como controlado (en primer lugar los controladores de clase y después los controladores de instancia). Si un elemento a lo largo de la ruta de tunelización ha marcado el evento enrutado como controlado, los datos del evento ya controlado se envían para el evento de propagación y no se invocarán los controladores adjuntos típicos para los eventos de entrada de propagación equivalentes. Externamente dará la impresión de que el evento de propagación controlado ni siquiera se ha desencadenado. Este comportamiento de control es útil para la composición de controles, donde podría ser conveniente que fuera el control final y no sus partes compuestas el que informara de todos los eventos de entrada basados en pruebas de posicionamiento o de los eventos de entrada basados en el foco. El elemento del control final está más próximo a la raíz en la composición y, por tanto, tiene la oportunidad de controlar desde la clase el evento de tunelización en primer lugar y posiblemente "reemplazar" dicho evento enrutado por un evento más específico del control, como parte del código que respalda la clase del control.

Para ilustrar cómo funciona el procesamiento de eventos de entrada, observe el ejemplo de evento de entrada siguiente. En la ilustración de árbol siguiente, `leaf element #2` es el origen de `PreviewMouseDown` y, a continuación, un `MouseDown` evento:

![Diagrama de enrutamiento de eventos](./media/routed-events-overview/input-event-routing.png)

El orden de procesamiento de los eventos es el siguiente:

1. `PreviewMouseDown` (túnel) en el elemento raíz.

2. `PreviewMouseDown` (túnel) en el elemento intermedio n.º 1.

3. `PreviewMouseDown` (túnel) en el elemento de origen n.º 2.

4. `MouseDown` (propagación) en el elemento de origen n.º 2.

5. `MouseDown` (propagación) en el elemento intermedio n.º 1.

6. `MouseDown` (propagación) en el elemento raíz.

Un delegado de controlador de eventos enrutados proporciona referencias a dos objetos: el objeto que ha desencadenado el evento y el objeto en el que se ha invocado el controlador. El objeto en el que se ha invocado el controlador es el objeto sobre el que informa el parámetro `sender`. La <xref:System.Windows.RoutedEventArgs.Source%2A> propiedad de los datos de evento detecta el objeto en el que se generó el evento por primera vez. Un evento enrutado todavía puede ser generado y controlado por el mismo objeto, en cuyo caso `sender` y <xref:System.Windows.RoutedEventArgs.Source%2A> son idénticos (este es el caso de los pasos 3 y 4 en la lista de ejemplo de procesamiento de eventos).

Debido a la tunelización y a la propagación, los elementos primarios reciben eventos de entrada donde <xref:System.Windows.RoutedEventArgs.Source%2A> es uno de sus elementos secundarios. Cuando es importante saber cuál es el elemento de origen, puede identificar el elemento de origen mediante el acceso a la <xref:System.Windows.RoutedEventArgs.Source%2A> propiedad.

Normalmente, una vez que se marca el evento de entrada <xref:System.Windows.RoutedEventArgs.Handled%2A> , no se invocan controladores adicionales. Lo habitual es marcar los eventos de entrada como controlados en cuanto se invoca un controlador que se ocupa del control lógico específico de la aplicación relacionado con el significado del evento de entrada.

La excepción a esta instrucción general sobre <xref:System.Windows.RoutedEventArgs.Handled%2A> el estado es que los controladores de eventos de entrada que se registran para omitir deliberadamente <xref:System.Windows.RoutedEventArgs.Handled%2A> el estado de los datos de evento se pueden invocar a lo largo de una ruta. Para más información, vea [Eventos de vista previa](preview-events.md) o [Marcar eventos enrutados como controlados y control de clases](marking-routed-events-as-handled-and-class-handling.md).

El modelo de datos de evento compartido entre los eventos de tunelización y de propagación, y el desencadenamiento secuencial primero de los eventos de tunelización y después de los de propagación, no es un concepto que se cumpla de forma general para todos los eventos enrutados. Ese comportamiento se implementa específicamente según el modo en que los dispositivos de entrada de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] deciden generar y conectar los pares de eventos de entrada. Implementar sus propios eventos de entrada es un escenario avanzado, pero también podría decidir seguir ese modelo para sus propios eventos de entrada.

Algunas clases eligen controlar ciertos eventos de entrada mediante clases, normalmente con la intención de volver a definir lo que significa un determinado evento de entrada controlado por el usuario dentro de ese control y de desencadenar un nuevo evento. Para más información, vea [Marcar eventos enrutados como controlados y control de clases](marking-routed-events-as-handled-and-class-handling.md).

Para más información sobre la entrada y cómo interactúa con los eventos en escenarios de aplicación típicos, vea [Información general sobre acciones del usuario](input-overview.md).

<a name="events_styles"></a>

## <a name="eventsetters-and-eventtriggers"></a>EventSetters y EventTriggers

En los estilos, puede incluir alguna sintaxis de control de eventos declarada previamente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en el marcado mediante <xref:System.Windows.EventSetter> . Cuando se aplica el estilo, el controlador al que se hace referencia se agrega a la instancia que recibe el estilo. Puede declarar un <xref:System.Windows.EventSetter> solo para un evento enrutado. A continuación se muestra un ejemplo. Tenga en cuenta que el método `b1SetColor` al que se hace referencia aquí está en un archivo de código subyacente.

[!code-xaml[EventOvwSupport#XAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/page2.xaml#xaml2)]

La ventaja que se obtiene aquí es que es probable que el estilo contenga una gran cantidad de información que se pueda aplicar a cualquier botón de la aplicación, y que la <xref:System.Windows.EventSetter> forma de formar parte de ese estilo promocione la reutilización de código, incluso en el nivel de marcado. Además, <xref:System.Windows.EventSetter> abstrae los nombres de método para los controladores un paso más allá de la aplicación general y el marcado de página.

Otra sintaxis especializada que combina las características de animación y eventos enrutados de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es un <xref:System.Windows.EventTrigger> . Al igual que con <xref:System.Windows.EventSetter> , solo se pueden usar eventos enrutados para <xref:System.Windows.EventTrigger> . Normalmente, <xref:System.Windows.EventTrigger> se declara como parte de un estilo, pero <xref:System.Windows.EventTrigger> también se puede declarar en elementos de nivel de página como parte de la <xref:System.Windows.FrameworkElement.Triggers%2A> colección o en <xref:System.Windows.Controls.ControlTemplate> . <xref:System.Windows.EventTrigger>Permite especificar un <xref:System.Windows.Media.Animation.Storyboard> que se ejecuta cada vez que un evento enrutado alcanza un elemento en su ruta que declara un <xref:System.Windows.EventTrigger> para ese evento. La ventaja de un control <xref:System.Windows.EventTrigger> sobre simplemente controlar el evento y hacer que se inicie un guion gráfico existente es que <xref:System.Windows.EventTrigger> proporciona un mejor control sobre el guión gráfico y su comportamiento en tiempo de ejecución. Para más información, vea [Cómo: Utilizar desencadenadores de eventos para controlar un guión gráfico después de su inicio](../graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).

<a name="more_about"></a>

## <a name="more-about-routed-events"></a>Más información sobre los eventos enrutados

En este tema se explican principalmente los eventos enrutados desde la perspectiva de describir los conceptos básicos y proporcionar orientación sobre cómo y cuándo responder a los eventos enrutados que ya existen en los distintos elementos y controles base. Pero puede crear sus propios eventos enrutados en su clase personalizada junto con toda la compatibilidad necesaria, como clases y delegados de datos de evento especializados. El propietario del evento enrutado puede ser cualquier clase, pero los eventos enrutados se deben generar y controlar mediante <xref:System.Windows.UIElement> o <xref:System.Windows.ContentElement> clases derivadas para ser útiles. Para más información sobre los eventos personalizados, vea [Crear un evento enrutado personalizado](how-to-create-a-custom-routed-event.md).

## <a name="see-also"></a>Vea también

- <xref:System.Windows.EventManager>
- <xref:System.Windows.RoutedEvent>
- <xref:System.Windows.RoutedEventArgs>
- [Marcar eventos enrutados como controlados y control de clases](marking-routed-events-as-handled-and-class-handling.md)
- [Información general sobre acciones del usuario](input-overview.md)
- [Información general sobre comandos](commanding-overview.md)
- [Propiedades de dependencia personalizadas](custom-dependency-properties.md)
- [Árboles en WPF](trees-in-wpf.md)
- [Modelos de evento débil](weak-event-patterns.md)

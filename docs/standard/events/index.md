---
title: Controlar y provocar eventos
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- delegate model for events
- application development [.NET], events
- application development [.NET Framework], events
- application development [.NET Core], events
- events [.NET]
- events [.NET Core]
- events [.NET Framework]
ms.assetid: b6f65241-e0ad-4590-a99f-200ce741bb1f
ms.openlocfilehash: b8ed028bc1edabf14d7b2dd67d94b28d574d2eb4
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159629"
---
# <a name="handling-and-raising-events"></a>Controlar y provocar eventos

Los eventos de .NET se basan en el modelo de delegado. El modelo de delegado sigue el [patrón de diseño del observador](observer-design-pattern.md), que permite que un suscriptor se registre con un proveedor y reciba notificaciones de él. El emisor de un evento inserta una notificación de que se ha producido un evento, y un receptor de eventos recibe la notificación y define una respuesta a la misma. En este artículo se describen los componentes principales del modelo de delegado, cómo consumir eventos en las aplicaciones y cómo implementar eventos en el código.  
  
 Para obtener información sobre el control de eventos en las aplicaciones de la Tienda de Windows 8.x, vea [Introducción a eventos y eventos enrutados](https://docs.microsoft.com/previous-versions/windows/apps/hh758286(v=win.10)).  
  
## <a name="events"></a>Events

Un evento es un mensaje que envía un objeto cuando ocurre una acción. La acción podría deberse a la interacción del usuario, como hacer clic en un botón, o podría derivarse de cualquier otra lógica del programa, como el cambio del valor de una propiedad. El objeto que provoca el evento se conoce como *emisor del evento*. El emisor del evento no sabe qué objeto o método recibirá (controlará) los eventos que genera. El evento normalmente es un miembro del emisor del evento; por ejemplo, el evento <xref:System.Web.UI.WebControls.Button.Click> es un miembro de la clase <xref:System.Web.UI.WebControls.Button>, y el evento <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> es un miembro de la clase que implementa la interfaz <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
Para definir un evento, se utiliza la palabra clave [`event`](../../csharp/language-reference/keywords/event.md) de C# o [`Event`](../../visual-basic/language-reference/statements/event-statement.md) de Visual Basic en la signatura de la clase de eventos y se especifica el tipo de delegado para el evento. Los delegados se describen en la sección siguiente.  
  
Normalmente, para generar un evento, se agrega un método marcado como `protected` y `virtual` (en C#) o `Protected` y `Overridable` (en Visual Basic). Asigne a este método el nombre `On`*EventName*; por ejemplo, `OnDataReceived`. El método debe tomar un parámetro que especifica un objeto de datos de evento, que es un objeto de tipo <xref:System.EventArgs> o un tipo derivado. Este método se proporciona para permitir que las clases derivadas reemplacen la lógica para generar el evento. Una clase derivada siempre debería llamar al método `On`*EventName* de la clase base para asegurarse de que los delegados registrados reciben el evento.  

En el ejemplo siguiente se muestra cómo declarar un evento denominado `ThresholdReached`. El evento está asociado al delegado <xref:System.EventHandler> y se genera en un método denominado `OnThresholdReached`.  
  
 [!code-csharp[EventsOverview#1](~/samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programtruncated.cs#1)]
 [!code-vb[EventsOverview#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1truncated.vb#1)]  
  
## <a name="delegates"></a>Delegados

Un delegado es un tipo que tiene una referencia a un método. Un delegado se declara con una signatura que muestra el tipo de valor devuelto y los parámetros para los métodos a los que hace referencia, y únicamente puede contener referencias a los métodos que coinciden con su signatura. Por lo tanto, un delegado equivale a un puntero a función con seguridad o a una devolución de llamada. Una declaración de delegado es suficiente para definir una clase de delegado.  
  
Los delegados tienen muchos usos en .NET. En el contexto de los eventos, un delegado es un intermediario (o un mecanismo de puntero) entre el origen del evento y el código que lo controla. Para asociar un delegado a un evento se incluye el tipo de delegado en la declaración del evento, como se muestra en el ejemplo de la sección anterior. Para obtener más información sobre los delegados, vea la clase <xref:System.Delegate>.  
  
.NET proporciona los delegados <xref:System.EventHandler> y <xref:System.EventHandler%601> que admiten la mayoría de los escenarios de eventos. Use el delegado <xref:System.EventHandler> para todos los eventos que no incluyen datos de evento. Use el delegado <xref:System.EventHandler%601> para los eventos que incluyen datos sobre el evento. Estos delegados no tienen ningún valor de tipo devuelto y toman dos parámetros (un objeto para el origen del evento y un objeto para los datos del evento).  
  
Los delegados son de [multidifusión](xref:System.MulticastDelegate), lo que significa que pueden guardar referencias a más de un método de control de eventos. Para obtener información detallada, vea la página de referencia de <xref:System.Delegate>. Los delegados permiten realizar un control de eventos más flexible y detallado. Un delegado actúa como remitente de eventos de la clase que genera el evento y mantiene una lista de los controladores registrados para el evento.  
  
Para los escenarios en que no funcionan los delegados <xref:System.EventHandler> y <xref:System.EventHandler%601>, puede definir un delegado. Los escenarios para los es necesario definir un delegado son poco habituales, como cuando se debe ejecutar código que no reconoce genéricos. Los delegados se marcan con la palabra clave [`delegate`](../../csharp/language-reference/builtin-types/reference-types.md#the-delegate-type) de C# y [`Delegate`](../../visual-basic/language-reference/statements/delegate-statement.md) de Visual Basic en la declaración. En el ejemplo siguiente se muestra cómo declarar un delegado denominado `ThresholdReachedEventHandler`.  
  
[!code-csharp[EventsOverview#4](~/samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programtruncated.cs#4)]
[!code-vb[EventsOverview#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1truncated.vb#4)]  
  
## <a name="event-data"></a>Datos de evento

Los datos asociados a un evento se pueden proporcionar a través de una clase de datos de evento. .NET proporciona muchas clases de datos de evento que puede utilizar en las aplicaciones. Por ejemplo, la clase <xref:System.IO.Ports.SerialDataReceivedEventArgs> es la clase de datos de evento del evento <xref:System.IO.Ports.SerialPort.DataReceived?displayProperty=nameWithType>. En .NET se sigue un patrón de nombres que consiste en finalizar todas las clases de datos de evento con `EventArgs`. Para determinar qué clase de datos de evento está asociada a un evento, basta con examinar el delegado del evento. Por ejemplo, el delegado <xref:System.IO.Ports.SerialDataReceivedEventHandler> incluye entre sus parámetros la clase <xref:System.IO.Ports.SerialDataReceivedEventArgs>.  
  
La clase <xref:System.EventArgs> es el tipo base para todas las clases de datos de evento. <xref:System.EventArgs> también es la clase que se usa cuando un evento no tiene datos asociados. Cuando cree un evento que solo sirva para notificar a otras clases que algo ha sucedido y que no necesite pasar ningún dato, incluya la clase <xref:System.EventArgs> como segundo parámetro del delegado. Puede pasar el valor <xref:System.EventArgs.Empty?displayProperty=nameWithType> cuando no se proporciona ningún dato. El delegado <xref:System.EventHandler> incluye la clase <xref:System.EventArgs> como parámetro.  
  
Si desea crear una clase de datos de evento personalizada, cree una clase que se derive de <xref:System.EventArgs> y, a continuación, especifique los miembros que sean necesarios para pasar los datos relacionados con el evento. Normalmente, debe usar el mismo patrón de asignación de nombres que se usa en .NET y finalizar el nombre de la clase de los datos de evento con `EventArgs`.  
  
En el ejemplo siguiente se muestra una clase de datos de evento denominada `ThresholdReachedEventArgs`. Contiene propiedades específicas del evento que se genera.  
  
[!code-csharp[EventsOverview#3](~/samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programtruncated.cs#3)]
[!code-vb[EventsOverview#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1truncated.vb#3)]  
  
## <a name="event-handlers"></a>Controladores de eventos

Para responder a un evento, se define un método controlador de eventos en el receptor de eventos. Este método debe coincidir con la signatura del delegado del evento que se está controlando. En el controlador de eventos, se realizan las acciones que es necesario llevar a cabo cuando se genera el evento, como recopilar los datos proporcionados por el usuario cuando este hace clic en un botón. Para recibir notificaciones cuando se genera el evento, el método controlador de eventos debe suscribirse al evento.  
  
En el ejemplo siguiente se muestra un método de control de eventos denominado `c_ThresholdReached` que coincide con la signatura del delegado <xref:System.EventHandler>. El método se suscribe al evento `ThresholdReached`.  
  
[!code-csharp[EventsOverview#2](~/samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programtruncated.cs#2)]
[!code-vb[EventsOverview#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1truncated.vb#2)]  
  
## <a name="static-and-dynamic-event-handlers"></a>Controladores de eventos estáticos y dinámicos  

.NET permite a los suscriptores registrarse para las notificaciones de eventos estática o dinámicamente. Los controladores de eventos estáticos son efectivos durante toda la vida de la clase cuyos eventos controlan. Los controladores de eventos dinámicos se activan y desactivan explícitamente durante la ejecución de un programa, normalmente en respuesta a alguna lógica condicional del programa. Por ejemplo, pueden utilizarse si las notificaciones de eventos solo son necesarias en condiciones específicas o si una aplicación proporciona varios controladores de eventos y las condiciones en tiempo de ejecución determinan cuál es el que debe utilizarse. En el ejemplo de la sección anterior se muestra cómo agregar dinámicamente un controlador de eventos. Para obtener más información, vea [Eventos](../../visual-basic/programming-guide/language-features/events/index.md) (en Visual Basic) y [Eventos](../../csharp/programming-guide/events/index.md) (en C#).  
  
## <a name="raising-multiple-events"></a>Generar múltiples eventos  
 Si la clase genera varios eventos, el compilador genera un campo por cada instancia de delegado de eventos. Si el número de eventos es alto, es posible que el costo de almacenamiento de un campo por delegado no sea aceptable. Para estos casos, .NET dispone de propiedades de evento que se pueden usar con otra estructura de datos (de elección propia) para almacenar los delegados de eventos.  
  
 Las propiedades de evento están compuestas de declaraciones de evento acompañadas de descriptores de acceso de evento. Los descriptores de acceso de eventos son métodos que se definen para agregar o quitar instancias de delegados de eventos de la estructura de datos de almacenamiento. Hay que tener en cuenta que las propiedades de evento son más lentas que los campos de evento, ya que se debe recuperar cada delegado de evento antes de poder invocarlo. La memoria y la velocidad se ven afectadas. Si la clase define muchos eventos que no se provocan con frecuencia, es posible que desee implementar propiedades de evento. Para obtener más información, vea [Cómo: Controlar varios eventos mediante las propiedades de evento](how-to-handle-multiple-events-using-event-properties.md).  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Title|Descripción|  
|-----------|-----------------|  
|[Cómo: Provocar y utilizar eventos](how-to-raise-and-consume-events.md)|Contiene ejemplos de cómo generar y consumir eventos.|  
|[Cómo: Controlar varios eventos mediante las propiedades de evento](how-to-handle-multiple-events-using-event-properties.md)|Muestra cómo utilizar propiedades de evento para controlar varios eventos.|  
|[Modelo de diseño de observador](observer-design-pattern.md)|Describe el patrón de diseño que permite que un suscriptor se registre con un proveedor y reciba notificaciones de dicho proveedor.|  
|[Cómo: Consumir eventos en una aplicación de formularios Web Forms](how-to-consume-events-in-a-web-forms-application.md)|Muestra cómo controlar un evento generado por un control de formularios Web Forms.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.EventHandler>
- <xref:System.EventHandler%601>
- <xref:System.EventArgs>
- <xref:System.Delegate>
- [Eventos (Visual Basic)](../../visual-basic/programming-guide/language-features/events/index.md)
- [Eventos (Guía de programación de C#)](../../csharp/programming-guide/events/index.md)
- [Introducción a eventos y eventos enrutados (aplicaciones de UWP)](/windows/uwp/xaml-platform/events-and-routed-events-overview)

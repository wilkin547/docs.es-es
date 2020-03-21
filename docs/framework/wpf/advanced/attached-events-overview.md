---
title: Información general sobre eventos adjuntos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- handling attached events [WPF]
- defining attached events as routed events [WPF]
- attached events [WPF], scenarios for
- attached events vs. routed events [WPF]
- backing attached events with routed events [WPF]
- attached events [WPF], definition
ms.assetid: 2c40eae3-80e4-4a45-ae09-df6c9ab4d91e
ms.openlocfilehash: e125c9a57090049f4319da96c7004f06606d0147
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141567"
---
# <a name="attached-events-overview"></a>Información general sobre eventos adjuntos

Lenguaje XAML (Extensible Application Markup Language) define un componente de lenguaje y un tipo de evento denominado *evento adjunto.* El concepto de un evento adjunto permite agregar un controlador de un evento determinado a un elemento arbitrario, en lugar de agregarlo a un elemento que realmente define o hereda el evento. En este caso, ni el objeto que genera potencialmente el evento ni la instancia de control del destino definen ni "poseen" de otro modo el evento.  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>Requisitos previos  
 En este tema se da por supuesto que ha leído [Información general sobre eventos enrutados](routed-events-overview.md) e [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md).  
  
<a name="Syntax"></a>
## <a name="attached-event-syntax"></a>Sintaxis de los eventos adjuntos  
 Los eventos adjuntos tienen una sintaxis XAML y un patrón de codificación que debe usar el código de respaldo para admitir el uso del evento adjunto.  
  
 En la sintaxis XAML, el evento adjunto se especifica no solo por su nombre de evento, sino también por su tipo propietario más el nombre del evento, separado por un punto (.). Dado que el nombre del evento está calificado con el nombre de su tipo de propiedad, la sintaxis del evento adjunto permite que cualquier evento adjunto se adjunte a cualquier elemento del que se pueda crear una instancia.  
  
 Por ejemplo, la siguiente es la sintaxis XAML `NeedsCleaning` para adjuntar un controlador para un evento adjunto personalizado:  
  
 [!code-xaml[WPFAquariumSln#AE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquarium/Window1.xaml#ae)]  
  
 Observe el prefijo `aqua:`, que, en este caso, es necesario porque el evento adjunto es un evento personalizado que procede de un atributo xmlns asignado personalizado.  
  
<a name="WPFImplements"></a>
## <a name="how-wpf-implements-attached-events"></a>Cómo implementa WPF los eventos adjuntos

En WPFWPF, los eventos <xref:System.Windows.RoutedEvent> adjuntos están respaldados por un campo y se enrutan a través del árbol después de que se generan. Normalmente, el origen del evento adjunto (el objeto que genera el evento) es un origen del sistema o del servicio y, por tanto, el objeto que ejecuta el código que genera el evento no forma parte directamente del árbol de elementos.  
  
<a name="Scenarios"></a>
## <a name="scenarios-for-attached-events"></a>Escenarios de eventos adjuntos  
 En WPFWPF, los eventos adjuntos están presentes en ciertas áreas de características donde <xref:System.Windows.Input.Mouse> hay abstracción de nivel de servicio, como para los eventos habilitados por la clase estática o la <xref:System.Windows.Controls.Validation> clase. Las clases que interactúan con el servicio o lo usan pueden emplear el evento de la sintaxis del evento adjunto, o bien pueden optar por exponer el evento adjunto como un evento enrutado que forme parte de cómo la clase integra las capacidades del servicio.  
  
 Aunque WPFWPF define una serie de eventos adjuntos, los escenarios en los que usará o controlará el evento adjunto directamente son muy limitados. Por lo general, el evento adjunto tiene un propósito de arquitectura, pero luego se reenvía a un evento enrutado no asociado (respaldado con un evento CLR "wrapper").  
  
 Por ejemplo, el evento <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> adjunto subyacente se puede <xref:System.Windows.UIElement> controlar <xref:System.Windows.UIElement.MouseDown> más <xref:System.Windows.UIElement> fácilmente en cualquier detalle mediante el uso en eso en lugar de tratar con la sintaxis de evento adjunta en XAML o código. El evento adjunto cumple un propósito de la arquitectura porque permite la expansión futura de los dispositivos de entrada. El dispositivo hipotético sólo tendría <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> que subir para simular la entrada del <xref:System.Windows.Input.Mouse> ratón, y no tendría que derivar de hacerlo. Sin embargo, este escenario implica el control de código de los eventos y el control XAML del evento adjunto no es relevante para este escenario.  
  
<a name="Handling"></a>
## <a name="handling-an-attached-event-in-wpf"></a>Control de un evento adjunto en WPF  
 El proceso para controlar un evento adjunto y el código del controlador que se va a escribir son, básicamente, los mismos que para un evento enrutado.  
  
 En general, un WPFWPF evento adjunto no es muy diferente de un WPFWPF enrutado eventos. Las diferencias son cómo se origina el evento y cómo lo expone una clase como miembro (lo que también afecta a la sintaxis del controlador XAML).  
  
 Sin embargo, como se indicó anteriormente, los eventos adjuntos WPFWPF existentes no están especialmente diseñados para controlar en WPFWPF. Más a menudo, el propósito del evento es habilitar un elemento compuesto para notificar un estado a un elemento primario en la composición, en cuyo caso el evento se genera normalmente en el código y también se basa en el control de clases de la clase primaria pertinente. Por ejemplo, se <xref:System.Windows.Controls.Primitives.Selector> espera que los <xref:System.Windows.Controls.Primitives.Selector.Selected> elementos dentro de a <xref:System.Windows.Controls.Primitives.Selector> generen el evento adjunto, que, a continuación, es clase controlada por la clase y, a continuación, potencialmente convertidos por la <xref:System.Windows.Controls.Primitives.Selector> clase en un evento enrutado diferente, <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>. Para obtener más información, consulte [Marcar eventos enrutados como controlados y control de clases](marking-routed-events-as-handled-and-class-handling.md).  
  
<a name="Custom"></a>
## <a name="defining-your-own-attached-events-as-routed-events"></a>Definición de eventos adjuntos propios como eventos enrutados  
 Si se deriva de clases base comunes de WPFWPF, puede implementar sus propios eventos adjuntos mediante la inclusión de determinados métodos de patrón en la clase y mediante el uso de métodos de utilidad que ya están presentes en las clases base.  
  
 El patrón es el siguiente:  
  
- Un método __Add*EventName*Handler__ con dos parámetros. El primer parámetro es la instancia a la que se agrega el controlador de eventos. El segundo parámetro es el controlador de eventos que se va a agregar. El método `public` debe `static`ser y , sin ningún valor devuelto.  
  
- Un método __Remove*EventName*Handler__ con dos parámetros. El primer parámetro es la instancia de la que se quita el controlador de eventos. El segundo parámetro es el controlador de eventos que se va a quitar. El método `public` debe `static`ser y , sin ningún valor devuelto.  
  
 El método de descriptor de acceso __Add*EventName*Handler__ facilita el procesamiento XAML cuando se declaran atributos de controlador de eventos adjuntos en un elemento. Los métodos __Add*EventName*Handler__ y __Remove*EventName*Handler__ también permiten el acceso de código al almacén del controlador de eventos para el evento adjunto.  
  
 Este patrón general aún no es lo suficientemente preciso para la implementación práctica en un marco de trabajo, porque cualquier implementación de lector XAML determinada podría tener esquemas diferentes para identificar eventos subyacentes en el lenguaje y la arquitectura de soporte. Esta es una de las razones por las que WPFWPF implementa eventos adjuntos como eventos enrutados; el identificador que se<xref:System.Windows.RoutedEvent>va a usar para un evento ( ) ya está definido por el sistema de eventos WPFWPF. Además, el enrutamiento de un evento es una extensión de implementación natural en el concepto de nivel de lenguaje XAML de un evento adjunto.  
  
 El __Add*EventName*Handler__ implementación para un <xref:System.Windows.UIElement.AddHandler%2A> WPFWPF evento adjunto consiste en llamar a la con el evento enrutado y controlador como argumentos.  
  
 Esta estrategia de implementación y el sistema de <xref:System.Windows.UIElement> eventos enrutados en general restringen el control de los eventos adjuntos a clases derivadas o <xref:System.Windows.ContentElement> clases derivadas, porque solo esas clases tienen <xref:System.Windows.UIElement.AddHandler%2A> implementaciones.  
  
 Por ejemplo, el código `NeedsCleaning` siguiente define el `Aquarium`evento adjunto en la clase owner , mediante la estrategia de eventos adjuntos WPFWPF de declarar el evento adjunto como un evento enrutado.  
  
 [!code-csharp[WPFAquariumSln#AECode](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#aecode)]
 [!code-vb[WPFAquariumSln#AECode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#aecode)]  
  
 Tenga en cuenta que el método utilizado <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>para establecer el campo de identificador de evento adjunto, , es en realidad el mismo método que se utiliza para registrar un evento enrutado no asociado. Todos los eventos adjuntos y eventos enrutados se registran en un almacén interno centralizado. Esta implementación del almacén de eventos permite la consideración conceptual de "eventos como una interfaz" que se describe en [Información general sobre eventos enrutados](routed-events-overview.md).  
  
<a name="Raising"></a>
## <a name="raising-a-wpf-attached-event"></a>Generación de un evento adjunto de WPF  
 Normalmente no es necesario generar eventos adjuntos definidos por WPF existentes desde el código. Estos eventos siguen el modelo conceptual general de <xref:System.Windows.Input.InputManager> "servicio" y las clases de servicio, como son responsables de generar los eventos.  
  
 Sin embargo, si está definiendo un evento adjunto personalizado basado <xref:System.Windows.RoutedEvent>en el <xref:System.Windows.UIElement.RaiseEvent%2A> modelo WPFWPF de <xref:System.Windows.UIElement> <xref:System.Windows.ContentElement>basar eventos adjuntos en , puede usar para generar un evento adjunto desde cualquier o . Generar un evento enrutado (adjunto o no) requiere que se declare un elemento determinado en el árbol de elementos como origen de eventos; ese origen se <xref:System.Windows.UIElement.RaiseEvent%2A> notifica como el autor de la llamada. Determinar qué elemento se notifica como el origen del árbol es responsabilidad del servicio.  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre eventos enrutados](routed-events-overview.md)
- [Detalles de la sintaxis XAML](xaml-syntax-in-detail.md)
- [Clases XAML y personalizadas para WPF](xaml-and-custom-classes-for-wpf.md)

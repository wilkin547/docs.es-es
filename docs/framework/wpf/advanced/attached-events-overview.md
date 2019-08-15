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
ms.openlocfilehash: 40e7bd34388bec06cd8a7c3610599d814aef101f
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038156"
---
# <a name="attached-events-overview"></a>Información general sobre eventos adjuntos

Lenguaje XAML (XAML) define un componente de lenguaje y el tipo de evento denominado *evento adjunto*. El concepto de un evento adjunto permite agregar un controlador de un evento determinado a un elemento arbitrario, en lugar de agregarlo a un elemento que realmente define o hereda el evento. En este caso, ni el objeto que genera potencialmente el evento ni la instancia de control del destino definen ni "poseen" de otro modo el evento.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 En este tema se da por supuesto que ha leído [Información general sobre eventos enrutados](routed-events-overview.md) e [Información general sobre XAML (WPF)](xaml-overview-wpf.md).  
  
<a name="Syntax"></a>   
## <a name="attached-event-syntax"></a>Sintaxis de los eventos adjuntos  
 Los eventos adjuntos tienen una sintaxis XAML y un patrón de codificación que debe usar el código de respaldo para admitir el uso de eventos adjuntos.  
  
 En la sintaxis XAML, el evento adjunto se especifica no solo por su nombre de evento, sino por su tipo propietario más el nombre del evento, separado por un punto (.). Dado que el nombre del evento está calificado con el nombre de su tipo de propiedad, la sintaxis del evento adjunto permite que cualquier evento adjunto se adjunte a cualquier elemento del que se pueda crear una instancia.  
  
 Por ejemplo, la siguiente es la sintaxis XAML para adjuntar un controlador para un `NeedsCleaning` evento adjunto personalizado:  
  
 [!code-xaml[WPFAquariumSln#AE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquarium/Window1.xaml#ae)]  
  
 Observe el prefijo `aqua:`, que, en este caso, es necesario porque el evento adjunto es un evento personalizado que procede de un atributo xmlns asignado personalizado.  
  
<a name="WPFImplements"></a>   
## <a name="how-wpf-implements-attached-events"></a>Cómo implementa WPF los eventos adjuntos

En WPF, los eventos adjuntos están respaldados por un <xref:System.Windows.RoutedEvent> campo y se enrutan a través del árbol una vez que se generan. Normalmente, el origen del evento adjunto (el objeto que genera el evento) es un origen del sistema o del servicio y, por tanto, el objeto que ejecuta el código que genera el evento no forma parte directamente del árbol de elementos.  
  
<a name="Scenarios"></a>   
## <a name="scenarios-for-attached-events"></a>Escenarios de eventos adjuntos  
 En WPF, los eventos adjuntos están presentes en algunas áreas de características en las que hay abstracción de nivel de servicio, como los eventos <xref:System.Windows.Input.Mouse> habilitados por <xref:System.Windows.Controls.Validation> la clase estática o la clase. Las clases que interactúan con el servicio o lo usan pueden emplear el evento de la sintaxis del evento adjunto, o bien pueden optar por exponer el evento adjunto como un evento enrutado que forme parte de cómo la clase integra las capacidades del servicio.  
  
 Aunque WPF define una serie de eventos adjuntos, los escenarios en los que va a usar o controlar el evento adjunto directamente están muy limitados. Por lo general, el evento adjunto sirve de arquitectura, pero se reenvía a un evento enrutado no adjunto (respaldado con un "contenedor" de eventos CLR).  
  
 Por ejemplo, el <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> evento adjunto subyacente se puede controlar más fácilmente en cualquier determinado <xref:System.Windows.UIElement> <xref:System.Windows.UIElement.MouseDown> mediante en <xref:System.Windows.UIElement> , en lugar de trabajar con la sintaxis de eventos adjuntos en XAML o código. El evento adjunto cumple un propósito de la arquitectura porque permite la expansión futura de los dispositivos de entrada. El dispositivo hipotético solo tendría que generarse <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> para simular la entrada del mouse y no tendría que derivar de <xref:System.Windows.Input.Mouse> para hacerlo. Sin embargo, este escenario implica el control de código de los eventos y el control de XAML del evento adjunto no es relevante para este escenario.  
  
<a name="Handling"></a>   
## <a name="handling-an-attached-event-in-wpf"></a>Control de un evento adjunto en WPF  
 El proceso para controlar un evento adjunto y el código del controlador que se va a escribir son, básicamente, los mismos que para un evento enrutado.  
  
 En general, los eventos adjuntos de WPF no son muy diferentes de los eventos enrutados de WPF. Las diferencias son cómo se produce el origen del evento y cómo lo expone una clase como miembro (lo que también afecta a la sintaxis del controlador XAML).  
  
 Sin embargo, como se indicó anteriormente, los eventos adjuntos de WPF existentes no se han diseñado especialmente para el control en WPF. Más a menudo, el propósito del evento es habilitar un elemento compuesto para notificar un estado a un elemento primario en la composición, en cuyo caso el evento se genera normalmente en el código y también se basa en el control de clases de la clase primaria pertinente. Por ejemplo, los elementos de <xref:System.Windows.Controls.Primitives.Selector> un se espera que generen <xref:System.Windows.Controls.Primitives.Selector.Selected> el evento adjunto, que es la clase controlada <xref:System.Windows.Controls.Primitives.Selector> por la clase y que, a <xref:System.Windows.Controls.Primitives.Selector> continuación, la clase puede convertir en un <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> evento enrutado diferente. . Para obtener más información, consulte [Marcar eventos enrutados como controlados y control de clases](marking-routed-events-as-handled-and-class-handling.md).  
  
<a name="Custom"></a>   
## <a name="defining-your-own-attached-events-as-routed-events"></a>Definición de eventos adjuntos propios como eventos enrutados  
 Si deriva de clases base de WPF comunes, puede implementar sus propios eventos adjuntos incluyendo ciertos métodos de patrón en la clase y usando métodos de utilidad que ya están presentes en las clases base.  
  
 El patrón es el siguiente:  
  
- Un __controlador Add*eventName*handler__ con dos parámetros. El primer parámetro es la instancia de a la que se agrega el controlador de eventos. El segundo parámetro es el controlador de eventos que se va a agregar. El método debe ser `public` y `static`, sin ningún valor devuelto.  
  
- Un método __Remove*eventName*handler__ con dos parámetros. El primer parámetro es la instancia de la que se quita el controlador de eventos. El segundo parámetro es el controlador de eventos que se va a quitar. El método debe ser `public` y `static`, sin ningún valor devuelto.  
  
 El método de descriptor de acceso __Add*eventName*handler__ facilita el procesamiento de XAML cuando los atributos de controlador de eventos adjuntos se declaran en un elemento. Los métodos __Add*eventName*handler__ y __Remove*eventName*handler__ también permiten el acceso de código al almacén de controladores de eventos para el evento adjunto.  
  
 Este patrón general no es lo suficientemente preciso para la implementación práctica en un marco de trabajo, ya que cualquier implementación de lector XAML puede tener esquemas diferentes para identificar eventos subyacentes en el lenguaje y la arquitectura admitidos. Esta es una de las razones por las que WPF implementa los eventos adjuntos como eventos enrutados; el identificador que se va a usar para un<xref:System.Windows.RoutedEvent>evento () ya está definido por el sistema de eventos de WPF. Además, el enrutamiento de un evento es una extensión de implementación natural en el concepto de nivel de lenguaje XAML de un evento adjunto.  
  
 La implementación del __controlador Add*eventName*__ para un evento adjunto de WPF consiste en <xref:System.Windows.UIElement.AddHandler%2A> llamar a con el evento enrutado y el controlador como argumentos.  
  
 Esta estrategia de implementación y el sistema de eventos enrutados en general restringen el control de <xref:System.Windows.UIElement> eventos adjuntos a clases derivadas o <xref:System.Windows.ContentElement> clases derivadas, ya que solo esas clases tienen <xref:System.Windows.UIElement.AddHandler%2A> implementaciones.  
  
 Por ejemplo, el código siguiente define el `NeedsCleaning` evento adjunto en la clase `Aquarium`Owner, utilizando la estrategia de eventos adjuntos de WPF para declarar el evento adjunto como un evento enrutado.  
  
 [!code-csharp[WPFAquariumSln#AECode](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#aecode)]
 [!code-vb[WPFAquariumSln#AECode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#aecode)]  
  
 Tenga en cuenta que el método utilizado para establecer el campo Identificador de evento <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>adjunto,, es en realidad el mismo método que se usa para registrar un evento enrutado no adjunto. Todos los eventos adjuntos y eventos enrutados se registran en un almacén interno centralizado. Esta implementación del almacén de eventos permite la consideración conceptual de "eventos como una interfaz" que se describe en [Información general sobre eventos enrutados](routed-events-overview.md).  
  
<a name="Raising"></a>   
## <a name="raising-a-wpf-attached-event"></a>Generación de un evento adjunto de WPF  
 Normalmente no es necesario generar eventos adjuntos definidos por WPF existentes desde el código. Estos eventos siguen el modelo conceptual general "servicio" y las clases de servicio como <xref:System.Windows.Input.InputManager> son responsables de generar los eventos.  
  
 Sin embargo, si define un evento adjunto personalizado basado en el modelo <xref:System.Windows.RoutedEvent>de WPF de basar eventos adjuntos en, puede utilizar <xref:System.Windows.UIElement.RaiseEvent%2A> para generar un evento adjunto desde <xref:System.Windows.ContentElement>cualquier <xref:System.Windows.UIElement> o. La generación de un evento enrutado (asociado o no) requiere que se declare un elemento determinado en el árbol de elementos como el origen del evento. ese origen se registra como el <xref:System.Windows.UIElement.RaiseEvent%2A> autor de la llamada. Determinar qué elemento se notifica como el origen del árbol es responsabilidad del servicio.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre eventos enrutados](routed-events-overview.md)
- [Detalles de la sintaxis XAML](xaml-syntax-in-detail.md)
- [Clases XAML y personalizadas para WPF](xaml-and-custom-classes-for-wpf.md)

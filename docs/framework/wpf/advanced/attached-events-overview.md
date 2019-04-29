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
ms.openlocfilehash: 7b7b0fcc9612994803bb23e985f44c483e708857
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777148"
---
# <a name="attached-events-overview"></a>Información general sobre eventos adjuntos
[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] define un componente de lenguaje y un tipo de evento denominado *evento adjunto*. El concepto de un evento adjunto permite agregar un controlador de un evento determinado a un elemento arbitrario, en lugar de agregarlo a un elemento que realmente define o hereda el evento. En este caso, ni el objeto que genera potencialmente el evento ni la instancia de control del destino definen ni "poseen" de otro modo el evento.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 En este tema se da por supuesto que ha leído [Información general sobre eventos enrutados](routed-events-overview.md) e [Información general sobre XAML (WPF)](xaml-overview-wpf.md).  
  
<a name="Syntax"></a>   
## <a name="attached-event-syntax"></a>Sintaxis de los eventos adjuntos  
 Los eventos adjuntos tienen un modelo de codificación y una sintaxis [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que el código de respaldo debe usar para admitir el uso de eventos adjuntos.  
  
 En la sintaxis [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], se especifica el evento adjunto no solo por su nombre de evento, sino por su tipo de propiedad y el nombre de evento, separados por un punto (.). Dado que el nombre del evento está calificado con el nombre de su tipo de propiedad, la sintaxis del evento adjunto permite que cualquier evento adjunto se adjunte a cualquier elemento del que se pueda crear una instancia.  
  
 Por ejemplo, la siguiente es la sintaxis de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para adjuntar un controlador a un evento adjunto `NeedsCleaning` personalizado:  
  
 [!code-xaml[WPFAquariumSln#AE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquarium/Window1.xaml#ae)]  
  
 Observe el prefijo `aqua:`, que, en este caso, es necesario porque el evento adjunto es un evento personalizado que procede de un atributo xmlns asignado personalizado.  
  
<a name="WPFImplements"></a>   
## <a name="how-wpf-implements-attached-events"></a>Cómo implementa WPF los eventos adjuntos  
 En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], adjunta los eventos están respaldados por un <xref:System.Windows.RoutedEvent> campo y se enrutan a través del árbol después de generarse. Normalmente, el origen del evento adjunto (el objeto que genera el evento) es un origen del sistema o del servicio y, por tanto, el objeto que ejecuta el código que genera el evento no forma parte directamente del árbol de elementos.  
  
<a name="Scenarios"></a>   
## <a name="scenarios-for-attached-events"></a>Escenarios de eventos adjuntos  
 En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], adjunta los eventos están presentes en determinadas áreas de características donde hay abstracción de nivel de servicio, como para los eventos que habilita la estática <xref:System.Windows.Input.Mouse> clase o el <xref:System.Windows.Controls.Validation> clase. Las clases que interactúan con el servicio o lo usan pueden emplear el evento de la sintaxis del evento adjunto, o bien pueden optar por exponer el evento adjunto como un evento enrutado que forme parte de cómo la clase integra las capacidades del servicio.  
  
 Aunque [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] define varios eventos adjuntos, los escenarios donde usará o controlará el evento adjunto directamente son muy limitados. Generalmente, el evento adjunto cumple un propósito de arquitectura, pero se reenvía posteriormente a un evento enrutado no adjunto (respaldado por un "contenedor" de eventos de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]).  
  
 Por ejemplo, subyacente evento adjunto <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> más fácilmente se pueden controlar en cualquier <xref:System.Windows.UIElement> utilizando <xref:System.Windows.UIElement.MouseDown> en que <xref:System.Windows.UIElement> en lugar de tratar con la sintaxis del evento adjunto, ya sea en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] o código. El evento adjunto cumple un propósito de la arquitectura porque permite la expansión futura de los dispositivos de entrada. El dispositivo hipotético solo tendría que generar <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> para simular la entrada del mouse y no necesitaría derivar <xref:System.Windows.Input.Mouse> para hacerlo. No obstante, este escenario implica el control de código de los eventos, y el control de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] del evento adjunto no es importante para este escenario.  
  
<a name="Handling"></a>   
## <a name="handling-an-attached-event-in-wpf"></a>Control de un evento adjunto en WPF  
 El proceso para controlar un evento adjunto y el código del controlador que se va a escribir son, básicamente, los mismos que para un evento enrutado.  
  
 En general, un evento adjunto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no es muy diferente de un evento enrutado de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Las diferencias se encuentran en cómo se origina el evento y en cómo lo expone una clase como un miembro (lo que también afecta a la sintaxis del controlador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]).  
  
 Sin embargo, como se indicó anteriormente, los eventos adjuntos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] existentes no están diseñados especialmente para el control en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Más a menudo, el propósito del evento es habilitar un elemento compuesto para notificar un estado a un elemento primario en la composición, en cuyo caso el evento se genera normalmente en el código y también se basa en el control de clases de la clase primaria pertinente. Por ejemplo, los elementos de un <xref:System.Windows.Controls.Primitives.Selector> se espera que genere el archivo adjunto <xref:System.Windows.Controls.Primitives.Selector.Selected> controlando el evento, que es, a continuación, la clase el <xref:System.Windows.Controls.Primitives.Selector> clase y, a continuación, convierte potencialmente por la <xref:System.Windows.Controls.Primitives.Selector> clase en un evento enrutado diferente, <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> . Para obtener más información, consulte [Marcar eventos enrutados como controlados y control de clases](marking-routed-events-as-handled-and-class-handling.md).  
  
<a name="Custom"></a>   
## <a name="defining-your-own-attached-events-as-routed-events"></a>Definición de eventos adjuntos propios como eventos enrutados  
 Si realiza la derivación de clases base de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] comunes, puede implementar sus propios eventos adjuntos incluyendo determinados métodos de patrón en la clase y usando métodos de utilidad que ya están presentes en las clases base.  
  
 El patrón es el siguiente:  
  
- Un método **agregar*EventName*controlador** con dos parámetros. El primer parámetro es la instancia a la que se agrega el controlador de eventos. El segundo parámetro es el controlador de eventos para agregar. El método debe ser `public` y `static`, sin ningún valor devuelto.  
  
- Un método **quitar*EventName*controlador** con dos parámetros. El primer parámetro es la instancia desde la que se quita el controlador de eventos. El segundo parámetro es el controlador de eventos para quitar. El método debe ser `public` y `static`, sin ningún valor devuelto.  
  
 El **agregar*EventName*controlador** facilita el método de descriptor de acceso del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesos cuando adjunta el controlador de eventos, los atributos se declaran en un elemento. El **agregar*EventName*controlador** y **quitar*EventName*controlador** métodos también habilitar el acceso de código para el almacén del controlador de eventos para el evento adjunto.  
  
 Este patrón general no es aún lo suficientemente preciso para la implementación práctica en un marco, ya que cualquier implementación determinada del lector de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] puede tener esquemas diferentes para identificar eventos subyacentes en el lenguaje y la arquitectura secundarios. Esta es una de las razones que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementa adjuntada eventos como eventos enrutados; el identificador que se utiliza para un evento (<xref:System.Windows.RoutedEvent>) ya está definido por el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema de eventos. Además, el enrutamiento de un evento es una extensión natural de la implementación en el concepto de nivel de lenguaje de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de un evento adjunto.  
  
 El **agregar*EventName*controlador** implementación para un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] evento adjunto consiste en llamar a la <xref:System.Windows.UIElement.AddHandler%2A> con el evento enrutado y el controlador como argumentos.  
  
 Esta estrategia de implementación y el sistema de eventos enrutados en general restringen el control de eventos adjuntos como <xref:System.Windows.UIElement> las clases derivadas o <xref:System.Windows.ContentElement> clases derivadas, porque solo esas clases tienen <xref:System.Windows.UIElement.AddHandler%2A> implementaciones.  
  
 Por ejemplo, el código siguiente define el evento adjunto de `NeedsCleaning` en la clase propietaria `Aquarium`, mediante la estrategia de declarar un evento adjunto como un evento enrutado que ofrecen los eventos adjuntos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 [!code-csharp[WPFAquariumSln#AECode](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#aecode)]
 [!code-vb[WPFAquariumSln#AECode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#aecode)]  
  
 Tenga en cuenta que el método usado para establecer el campo de identificador de evento adjunto, <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>, es realmente el mismo método que se usa para registrar un evento enrutado no adjunto. Todos los eventos adjuntos y eventos enrutados se registran en un almacén interno centralizado. Esta implementación del almacén de eventos permite la consideración conceptual de "eventos como una interfaz" que se describe en [Información general sobre eventos enrutados](routed-events-overview.md).  
  
<a name="Raising"></a>   
## <a name="raising-a-wpf-attached-event"></a>Generación de un evento adjunto de WPF  
 Normalmente, no es necesario generar eventos adjuntos definidos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a partir del código. Estos eventos siguen el modelo conceptual general "servicio" así como las clases del servicio <xref:System.Windows.Input.InputManager> son responsables de generar los eventos.  
  
 Sin embargo, si va a definir un evento adjunto personalizado basado en la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] modelo de basar los eventos adjuntos en <xref:System.Windows.RoutedEvent>, puede usar <xref:System.Windows.UIElement.RaiseEvent%2A> para generar un evento adjunto desde cualquier <xref:System.Windows.UIElement> o <xref:System.Windows.ContentElement>. Generar un evento enrutado (adjunto o no) requiere que se declare un elemento determinado en el árbol de elementos como el origen del evento; se notifica ese origen como el <xref:System.Windows.UIElement.RaiseEvent%2A> llamador. Determinar qué elemento se notifica como el origen del árbol es responsabilidad del servicio.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre eventos enrutados](routed-events-overview.md)
- [Detalles de la sintaxis XAML](xaml-syntax-in-detail.md)
- [Clases XAML y personalizadas para WPF](xaml-and-custom-classes-for-wpf.md)

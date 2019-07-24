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
ms.openlocfilehash: a3a2f711840ad7f6e28443dac3c18501cd4400e0
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401404"
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
 En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], los eventos adjuntos están respaldados por un <xref:System.Windows.RoutedEvent> campo y se enrutan a través del árbol una vez que se generan. Normalmente, el origen del evento adjunto (el objeto que genera el evento) es un origen del sistema o del servicio y, por tanto, el objeto que ejecuta el código que genera el evento no forma parte directamente del árbol de elementos.  
  
<a name="Scenarios"></a>   
## <a name="scenarios-for-attached-events"></a>Escenarios de eventos adjuntos  
 En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], los eventos adjuntos están presentes en algunas áreas de características en las que hay abstracción de nivel de servicio, como los eventos <xref:System.Windows.Input.Mouse> habilitados por <xref:System.Windows.Controls.Validation> la clase estática o la clase. Las clases que interactúan con el servicio o lo usan pueden emplear el evento de la sintaxis del evento adjunto, o bien pueden optar por exponer el evento adjunto como un evento enrutado que forme parte de cómo la clase integra las capacidades del servicio.  
  
 Aunque [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] define varios eventos adjuntos, los escenarios donde usará o controlará el evento adjunto directamente son muy limitados. Por lo general, el evento adjunto sirve de arquitectura, pero se reenvía a un evento enrutado no adjunto (respaldado con un "contenedor" de eventos CLR).  
  
 Por ejemplo, <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> el evento adjunto subyacente se puede controlar más fácilmente en cualquier determinado <xref:System.Windows.UIElement> <xref:System.Windows.UIElement.MouseDown> mediante en <xref:System.Windows.UIElement> , en lugar de tratar con la sintaxis de eventos adjuntos en o en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] el código. El evento adjunto cumple un propósito de la arquitectura porque permite la expansión futura de los dispositivos de entrada. El dispositivo hipotético solo tendría que generarse <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> para simular la entrada del mouse y no tendría que derivar de <xref:System.Windows.Input.Mouse> para hacerlo. No obstante, este escenario implica el control de código de los eventos, y el control de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] del evento adjunto no es importante para este escenario.  
  
<a name="Handling"></a>   
## <a name="handling-an-attached-event-in-wpf"></a>Control de un evento adjunto en WPF  
 El proceso para controlar un evento adjunto y el código del controlador que se va a escribir son, básicamente, los mismos que para un evento enrutado.  
  
 En general, un evento adjunto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no es muy diferente de un evento enrutado de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Las diferencias se encuentran en cómo se origina el evento y en cómo lo expone una clase como un miembro (lo que también afecta a la sintaxis del controlador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]).  
  
 Sin embargo, como se indicó anteriormente, los eventos adjuntos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] existentes no están diseñados especialmente para el control en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Más a menudo, el propósito del evento es habilitar un elemento compuesto para notificar un estado a un elemento primario en la composición, en cuyo caso el evento se genera normalmente en el código y también se basa en el control de clases de la clase primaria pertinente. Por ejemplo, los elementos de <xref:System.Windows.Controls.Primitives.Selector> un se espera que generen <xref:System.Windows.Controls.Primitives.Selector.Selected> el evento adjunto, que es la clase controlada <xref:System.Windows.Controls.Primitives.Selector> por la clase y que, a <xref:System.Windows.Controls.Primitives.Selector> continuación, la clase puede convertir en un <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> evento enrutado diferente. . Para obtener más información, consulte [Marcar eventos enrutados como controlados y control de clases](marking-routed-events-as-handled-and-class-handling.md).  
  
<a name="Custom"></a>   
## <a name="defining-your-own-attached-events-as-routed-events"></a>Definición de eventos adjuntos propios como eventos enrutados  
 Si realiza la derivación de clases base de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] comunes, puede implementar sus propios eventos adjuntos incluyendo determinados métodos de patrón en la clase y usando métodos de utilidad que ya están presentes en las clases base.  
  
 El patrón es el siguiente:  
  
- Un **controlador Add*eventName*handler** con dos parámetros. El primer parámetro es la instancia de a la que se agrega el controlador de eventos. El segundo parámetro es el controlador de eventos que se va a agregar. El método debe ser `public` y `static`, sin ningún valor devuelto.  
  
- Un método **Remove*eventName*handler** con dos parámetros. El primer parámetro es la instancia de la que se quita el controlador de eventos. El segundo parámetro es el controlador de eventos que se va a quitar. El método debe ser `public` y `static`, sin ningún valor devuelto.  
  
 El método de descriptor de acceso **Add*eventName*handler** facilita el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesamiento cuando los atributos de controlador de eventos adjuntos se declaran en un elemento. Los métodos **Add*eventName*handler** y **Remove*eventName*handler** también permiten el acceso de código al almacén de controladores de eventos para el evento adjunto.  
  
 Este patrón general no es aún lo suficientemente preciso para la implementación práctica en un marco, ya que cualquier implementación determinada del lector de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] puede tener esquemas diferentes para identificar eventos subyacentes en el lenguaje y la arquitectura secundarios. Esta es una de las razones por [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] las que implementa eventos adjuntos como eventos enrutados; el identificador que se va<xref:System.Windows.RoutedEvent>a usar para un evento ( [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ) ya está definido por el sistema de eventos. Además, el enrutamiento de un evento es una extensión natural de la implementación en el concepto de nivel de lenguaje de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de un evento adjunto.  
  
 La implementación del **controlador Add*eventName*** para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un evento <xref:System.Windows.UIElement.AddHandler%2A> adjunto consiste en llamar a con el evento enrutado y el controlador como argumentos.  
  
 Esta estrategia de implementación y el sistema de eventos enrutados en general restringen el control de <xref:System.Windows.UIElement> eventos adjuntos a clases derivadas o <xref:System.Windows.ContentElement> clases derivadas, ya que solo esas clases tienen <xref:System.Windows.UIElement.AddHandler%2A> implementaciones.  
  
 Por ejemplo, el código siguiente define el evento adjunto de `NeedsCleaning` en la clase propietaria `Aquarium`, mediante la estrategia de declarar un evento adjunto como un evento enrutado que ofrecen los eventos adjuntos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 [!code-csharp[WPFAquariumSln#AECode](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#aecode)]
 [!code-vb[WPFAquariumSln#AECode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#aecode)]  
  
 Tenga en cuenta que el método utilizado para establecer el campo Identificador de evento <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>adjunto,, es en realidad el mismo método que se usa para registrar un evento enrutado no adjunto. Todos los eventos adjuntos y eventos enrutados se registran en un almacén interno centralizado. Esta implementación del almacén de eventos permite la consideración conceptual de "eventos como una interfaz" que se describe en [Información general sobre eventos enrutados](routed-events-overview.md).  
  
<a name="Raising"></a>   
## <a name="raising-a-wpf-attached-event"></a>Generación de un evento adjunto de WPF  
 Normalmente, no es necesario generar eventos adjuntos definidos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a partir del código. Estos eventos siguen el modelo conceptual general "servicio" y las clases de servicio como <xref:System.Windows.Input.InputManager> son responsables de generar los eventos.  
  
 Sin embargo, si define un evento adjunto personalizado basado [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en el modelo de basar eventos adjuntos en <xref:System.Windows.RoutedEvent>, puede <xref:System.Windows.UIElement.RaiseEvent%2A> utilizar para generar un evento adjunto desde <xref:System.Windows.UIElement> cualquier <xref:System.Windows.ContentElement>o. La generación de un evento enrutado (asociado o no) requiere que se declare un elemento determinado en el árbol de elementos como el origen del evento. ese origen se registra como el <xref:System.Windows.UIElement.RaiseEvent%2A> autor de la llamada. Determinar qué elemento se notifica como el origen del árbol es responsabilidad del servicio.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre eventos enrutados](routed-events-overview.md)
- [Detalles de la sintaxis XAML](xaml-syntax-in-detail.md)
- [Clases XAML y personalizadas para WPF](xaml-and-custom-classes-for-wpf.md)

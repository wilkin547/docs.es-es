---
title: Control de eventos en Visual Basic y WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Visual Basic [WPF], event handlers
- event handlers [WPF], Visual Basic
ms.assetid: ad4eb9aa-3afc-4a71-8cf6-add3fbea54a1
ms.openlocfilehash: c6e1863850ebf04408c7ffc7b784e9ca3ca12cf5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078029"
---
# <a name="visual-basic-and-wpf-event-handling"></a>Control de eventos en Visual Basic y WPF
Para el idioma de Microsoft Visual Basic .NET en concreto, puede usar específico del lenguaje `Handles` palabra clave para asociar controladores de eventos con instancias, en lugar de asociar controladores de eventos con atributos o utilizando el <xref:System.Windows.UIElement.AddHandler%2A> método. Pero la técnica de `Handles` para adjuntar controladores a instancias tiene algunas limitaciones, ya que la sintaxis de `Handles` no es compatible con algunas de las características específicas de eventos enrutados del sistema de eventos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
## <a name="using-handles-in-a-wpf-application"></a>Usar "Handles" en una aplicación WPF  
 Los controladores de eventos que se conectan a instancias y eventos con `Handles` deben definirse dentro de la declaración de clase parcial de la instancia, algo que también es un requisito para los controladores de eventos que se asignan a través de valores de atributo en los elementos. Solo se puede especificar `Handles` para un elemento en la página que tiene un <xref:System.Windows.FrameworkContentElement.Name%2A> valor de propiedad (o [x: Name Directive](../../xaml-services/x-name-directive.md) declarado). Esto es porque el <xref:System.Windows.FrameworkContentElement.Name%2A> en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] crea la referencia de instancia que es necesaria para admitir la *instancia.evento* formato de referencia que requiere la `Handles` sintaxis. El único elemento que se puede usar para `Handles` sin un <xref:System.Windows.FrameworkContentElement.Name%2A> referencia es la instancia de elemento raíz que define la clase parcial.  
  
 Puede asignar el mismo controlador a varios elementos. Para ello, separe con comas las referencias *Instancia.Evento* después de `Handles`.  
  
 Puede usar `Handles` para asignar más de un controlador a la misma referencia *Instancia.Evento*. No dé importancia al orden en el que se proporcionan los controladores en la referencia `Handles`, ya que se supone que los controladores que controlan el mismo evento se pueden invocar en cualquier orden.  
  
 Para quitar un controlador que se ha agregado con `Handles` en la declaración, puede llamar a <xref:System.Windows.UIElement.RemoveHandler%2A>.  
  
 Puede usar `Handles` para asociar controladores para eventos enrutados, siempre y cuando asocie los controladores a instancias que definen el evento que se está controlando en sus tablas de miembros. Los eventos enrutados, los controladores asociados con `Handles` siguen las mismas reglas de enrutamientos como hacen los controladores asociados como [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] atributos, o con la firma común de <xref:System.Windows.UIElement.AddHandler%2A>. Esto significa que si el evento ya está marcado como controlado (la <xref:System.Windows.RoutedEventArgs.Handled%2A> es propiedad de los datos del evento `True`), los controladores asociados con `Handles` no se invocan en respuesta a esa instancia de evento. El evento lo pueden marcar como controlado los controladores de instancia de otro elemento de la ruta o la clase que controla en el elemento actual o en elementos anteriores de la ruta. En el caso de los eventos de entrada que admiten eventos emparejados de túnel/propagación, la ruta de tunelización puede haber marcado como controlado el par de eventos. Para obtener más información sobre los eventos enrutados, vea [Información general sobre eventos enrutados](routed-events-overview.md).  
  
## <a name="limitations-of-handles-for-adding-handlers"></a>Limitaciones de "Handles" para agregar controladores  
 `Handles` no puede hacer referencia a controladores para eventos adjuntos. Debe usar el método de descriptor de acceso `add` para ese evento adjunto o atributos de evento *nombreDeTipo.nombreDeEvento* en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Para obtener más información, vea [Información general sobre eventos enrutados](routed-events-overview.md).  
  
 En el caso de los eventos enrutados, solo se puede usar `Handles` para asignar controladores a las instancias en las que ese evento existe en la tabla de miembros de instancia. Pero, en los eventos enrutados en general, un elemento primario puede ser un agente de escucha de un evento de elementos secundarios, incluso si el elemento primario no contiene ese evento en su tabla de miembros. En la sintaxis de atributo, puede especificar esto mediante un formato de atributo *nombreDeTipo.nombreDeMiembro* que califica el tipo que realmente define el evento que quiere controlar. Por ejemplo, un elemento primario `Page` (sin ningún `Click` evento definido) puede escuchar eventos de clic de botón, se asigna un controlador de atributo en el formulario `Button.Click`. Pero `Handles` no es compatible con el formato *nombreDeTipo.nombreDeMiembro*, porque debe admitir un formato *Instancia.Evento* que entra en conflicto. Para obtener más información, vea [Información general sobre eventos enrutados](routed-events-overview.md).  
  
 `Handles` no puede adjuntar los controladores que se invocan para eventos que ya están marcados como controlados. En su lugar, debe usar código y llamar a la `handledEventsToo` sobrecarga de <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29>.  
  
> [!NOTE]
>  No utilice el `Handles` sintaxis en el código de Visual Basic cuando se especifica un controlador de eventos para el mismo evento en XAML. En ese caso, se llama al controlador de eventos dos veces.  
  
## <a name="how-wpf-implements-handles-functionality"></a>Cómo implementa WPF la funcionalidad "Handles"  
 Cuando un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] se compila la página, el archivo intermedio declara `Friend` `WithEvents` referencias a todos los elementos en la página que tiene un <xref:System.Windows.FrameworkContentElement.Name%2A> conjunto de propiedades (o [x: Name Directive](../../xaml-services/x-name-directive.md) declarado). Cada instancia con nombre es potencialmente un elemento que se puede asignar a un controlador mediante `Handles`.  
  
> [!NOTE]
>  En [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], [!INCLUDE[TLA2#tla_intellisense](../../../../includes/tla2sharptla-intellisense-md.md)] puede mostrar la finalización de los elementos que están disponibles para una referencia `Handles` en una página. Sin embargo, esto podría ocupar un paso de compilación para que el archivo intermedio pueda rellenar todas las referencias `Friends`.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.UIElement.AddHandler%2A>
- [Marcar eventos enrutados como controlados y control de clases](marking-routed-events-as-handled-and-class-handling.md)
- [Información general sobre eventos enrutados](routed-events-overview.md)
- [Información general sobre XAML (WPF)](xaml-overview-wpf.md)

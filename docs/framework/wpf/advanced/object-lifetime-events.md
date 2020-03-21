---
title: Eventos de duración de objetos
ms.date: 03/30/2017
helpviewer_keywords:
- events [WPF], ContentRendered
- events [WPF], Deactivated
- events [WPF], Unloaded
- Activated events [WPF]
- events [WPF], Loaded
- Application objects [WPF], lifetime events
- events [WPF], Activated
- ContentRendered events [WPF]
- Deactivated events [WPF]
- events [WPF], Initialized
- events [WPF], Closing
- Unloaded events [WPF]
- exit events [WPF]
- objects' lifetime events [WPF]
- Loaded events [WPF]
- Closing events [WPF]
- events [WPF], Closed
- Initialized events [WPF]
- Closed events [WPF]
- startup events [WPF]
- lifetime events of objects [WPF]
ms.assetid: face6fc7-465b-4502-bfe5-e88d2e729a78
ms.openlocfilehash: 3b761674bd2464ee87e07d9299c805431f8fdeb7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141112"
---
# <a name="object-lifetime-events"></a>Eventos de duración de objetos
En este tema se describen los eventos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] específicos que indican las fases de duración de la creación, el uso y la destrucción de objetos.  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>Requisitos previos  
 En este tema, se supone que entiende las propiedades de dependencia desde la perspectiva de un consumidor de propiedades de dependencia existentes en las clases [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] y que ha leído el tema [Información general sobre las propiedades de dependencia](dependency-properties-overview.md). Para seguir los ejemplos de este tema, también debe comprender [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] (consulte [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)) y saber cómo escribir aplicaciones [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="intro"></a>
## <a name="object-lifetime-events"></a>Eventos de duración de objetos  
 Todos los objetos del código administrado de Microsoft .NET Framework pasan por un conjunto similar de fases de vida, creación, uso y destrucción. Además, muchos objetos tienen una fase de finalización de duración que se produce como parte de la fase de destrucción. Los objetos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], concretamente los objetos visuales que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] identifica como elementos, también tienen un conjunto de fases comunes de duración de objeto. Los modelos de programación y aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] exponen estas fases como una serie de eventos. Hay cuatro tipos principales de objetos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con respecto a los eventos de duración: elementos en general, elementos de ventana, hosts de navegación y objetos de aplicación. Las ventanas y los hosts de navegación también se encuentran dentro de un grupo más grande de objetos visuales (elementos). En este tema se describen los eventos de duración que son comunes para todos los elementos y se indican los más específicos que se aplican a las definiciones de aplicación, las ventanas o los hosts de navegación.  
  
<a name="common_events"></a>
## <a name="common-lifetime-events-for-elements"></a>Eventos de duración comunes para elementos  
 Cualquier elemento de nivel de marco de <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement>WPF (esos objetos <xref:System.Windows.FrameworkElement.Initialized> <xref:System.Windows.FrameworkElement.Loaded>derivados <xref:System.Windows.FrameworkElement.Unloaded>de o ) tiene tres eventos de duración comunes: , , y .  
  
### <a name="initialized"></a>Inicializado  
 <xref:System.Windows.FrameworkElement.Initialized>se genera primero, y corresponde aproximadamente a la inicialización del objeto mediante la llamada a su constructor. Dado que el evento se produce en respuesta a la inicialización, se garantiza que se establecen todas las propiedades del objeto. (Una excepción son los usos de expresiones como recursos dinámicos o enlaces; serán expresiones no evaluadas.) Como consecuencia del requisito de que se establecen todas las propiedades, la secuencia de <xref:System.Windows.FrameworkElement.Initialized> ser provocado por elementos anidados que se definen en el marcado parece ocurrir en orden de los elementos más profundos en el árbol de elementos primero, a continuación, los elementos primarios hacia la raíz. Este orden se debe a que las relaciones entre elementos primarios y secundarios y las inclusiones son propiedades y, por tanto, el elemento primario no puede informar de la inicialización hasta que los elementos secundarios que rellenan la propiedad estén inicializados completamente.  
  
 Al escribir controladores en respuesta <xref:System.Windows.FrameworkElement.Initialized> al evento, debe tener en cuenta que no hay ninguna garantía de que se hayan creado todos los demás elementos del árbol de elementos (árbol lógico o árbol visual) alrededor de donde está asociado el controlador, especialmente los elementos primarios. Es posible que las variables de miembro sean nulas o que el enlace subyacente no haya rellenado todavía los orígenes de datos (incluso en el nivel de expresión).  
  
### <a name="loaded"></a>Cargado  
 <xref:System.Windows.FrameworkElement.Loaded>se plantea a continuación. El <xref:System.Windows.FrameworkElement.Loaded> evento se genera antes de la representación final, pero después de que el sistema de diseño haya calculado todos los valores necesarios para la representación. <xref:System.Windows.FrameworkElement.Loaded>implica que el árbol lógico en el que se encuentra un elemento está completo y se conecta a un origen de presentación que proporciona el HWND y la superficie de representación. El enlace de datos estándar (enlace a orígenes locales, como <xref:System.Windows.FrameworkElement.Loaded>otras propiedades o orígenes de datos definidos directamente) se habrá producido antes de . Es posible que el enlace de datos asincrónico (orígenes externos o dinámicos) se haya producido, pero, por definición de su naturaleza asincrónica, no se puede garantizar que realmente se haya producido.  
  
 El mecanismo por <xref:System.Windows.FrameworkElement.Loaded> el que se <xref:System.Windows.FrameworkElement.Initialized>genera el evento es diferente de . El <xref:System.Windows.FrameworkElement.Initialized> evento se genera elemento por elemento, sin una coordinación directa por un árbol de elementos completado. Por el <xref:System.Windows.FrameworkElement.Loaded> contrario, el evento se genera como un esfuerzo coordinado en todo el árbol de elementos (específicamente, el árbol lógico). Cuando todos los elementos del árbol están en <xref:System.Windows.FrameworkElement.Loaded> un estado en el que se consideran cargados, el evento se genera primero en el elemento raíz. A <xref:System.Windows.FrameworkElement.Loaded> continuación, el evento se genera sucesivamente en cada elemento secundario.  
  
> [!NOTE]
> Este comportamiento puede parecerse a primera vista a una tunelización para un evento enrutado. Sin embargo, no se desplaza información de un evento a otro. Cada elemento siempre tiene la <xref:System.Windows.FrameworkElement.Loaded> oportunidad de controlar su evento y marcar los datos de evento como controlados no tiene ningún efecto más allá de ese elemento.  
  
### <a name="unloaded"></a>Descargado  
 <xref:System.Windows.FrameworkElement.Unloaded>se genera en último lugar y se inicia mediante el origen de la presentación o el elemento primario visual que se va a quitar. Cuando <xref:System.Windows.FrameworkElement.Unloaded> se genera y controla, el elemento que es <xref:System.Windows.FrameworkElement.Parent%2A> el elemento primario del origen del evento (según lo determinado por la propiedad) o cualquier elemento dado hacia arriba en los árboles lógicos o visuales puede que ya se haya desestablecido, lo que significa que el enlace de datos, las referencias de recursos y los estilos no se pueden establecer en su valor de tiempo de ejecución normal o el último conocido.  
  
<a name="application_model_elements"></a>
## <a name="lifetime-events-application-model-elements"></a>Elementos del modelo de aplicación de eventos de duración  
 Basándose en los eventos de duración comunes <xref:System.Windows.Application>para <xref:System.Windows.Window> <xref:System.Windows.Controls.Page>los <xref:System.Windows.Navigation.NavigationWindow>elementos son los siguientes elementos del modelo de aplicación: , , , , y <xref:System.Windows.Controls.Frame>. Extienden los eventos de duración comunes con eventos adicionales que son pertinentes para su finalidad específica. Esto se trata detalladamente en las siguientes ubicaciones:  
  
- <xref:System.Windows.Application>: [Descripción general de](../app-development/application-management-overview.md)la gestión de aplicaciones .  
  
- <xref:System.Windows.Window>: [Descripción general de WPF Windows](../app-development/wpf-windows-overview.md).  
  
- <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>y : [Descripción general de la navegación](../app-development/navigation-overview.md).  
  
## <a name="see-also"></a>Consulte también

- [Precedencia del valor de la propiedad de dependencia](dependency-property-value-precedence.md)
- [Información general sobre eventos enrutados](routed-events-overview.md)

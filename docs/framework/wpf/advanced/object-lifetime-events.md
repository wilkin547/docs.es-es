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
ms.openlocfilehash: dd2e116c4241a44786af3a56b931b0c3c0571814
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933489"
---
# <a name="object-lifetime-events"></a>Eventos de duración de objetos
En este tema se describen los eventos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] específicos que indican las fases de duración de la creación, el uso y la destrucción de objetos.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 En este tema, se supone que entiende las propiedades de dependencia desde la perspectiva de un consumidor de propiedades de dependencia existentes en las clases [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] y que ha leído el tema [Información general sobre las propiedades de dependencia](dependency-properties-overview.md). Para seguir los ejemplos de este tema, también debe comprender [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] (consulte [Información general sobre XAML (WPF)](xaml-overview-wpf.md)) y saber cómo escribir aplicaciones [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="intro"></a>   
## <a name="object-lifetime-events"></a>Eventos de duración de objetos  
 Todos los objetos de código administrado de Microsoft .NET Framework pasan por un conjunto similar de fases de vida, creación, uso y destrucción. Además, muchos objetos tienen una fase de finalización de duración que se produce como parte de la fase de destrucción. Los objetos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], concretamente los objetos visuales que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] identifica como elementos, también tienen un conjunto de fases comunes de duración de objeto. Los modelos de programación y aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] exponen estas fases como una serie de eventos. Hay cuatro tipos principales de objetos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con respecto a los eventos de duración: elementos en general, elementos de ventana, hosts de navegación y objetos de aplicación. Las ventanas y los hosts de navegación también se encuentran dentro de un grupo más grande de objetos visuales (elementos). En este tema se describen los eventos de duración que son comunes para todos los elementos y se indican los más específicos que se aplican a las definiciones de aplicación, las ventanas o los hosts de navegación.  
  
<a name="common_events"></a>   
## <a name="common-lifetime-events-for-elements"></a>Eventos de duración comunes para elementos  
 Cualquier elemento de nivel de marco de WPF (los objetos derivados de <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>) tiene tres eventos de duración comunes <xref:System.Windows.FrameworkElement.Initialized>: <xref:System.Windows.FrameworkElement.Loaded>, y <xref:System.Windows.FrameworkElement.Unloaded>.  
  
### <a name="initialized"></a>Inicializado  
 <xref:System.Windows.FrameworkElement.Initialized>se genera primero y, aproximadamente, corresponde a la inicialización del objeto por la llamada a su constructor. Dado que el evento se produce en respuesta a la inicialización, se garantiza que se establecen todas las propiedades del objeto. (Las excepciones son los usos de la expresión, como recursos dinámicos o enlaces, que son expresiones no evaluadas). Como consecuencia del requisito de que se establezcan todas las propiedades, la secuencia <xref:System.Windows.FrameworkElement.Initialized> de los elementos anidados que se definen en el marcado parece aparecer en orden de los elementos más profundos primero en el árbol de elementos y, a continuación, los elementos primarios hacia la raíz. Este orden se debe a que las relaciones entre elementos primarios y secundarios y las inclusiones son propiedades y, por tanto, el elemento primario no puede informar de la inicialización hasta que los elementos secundarios que rellenan la propiedad estén inicializados completamente.  
  
 Al escribir controladores en respuesta al <xref:System.Windows.FrameworkElement.Initialized> evento, debe tener en cuenta que no hay ninguna garantía de que se hayan creado todos los demás elementos del árbol de elementos (ya sea árbol lógico o árbol visual) en torno al punto en el que está asociado el controlador, especialmente elementos primarios. Es posible que las variables de miembro sean nulas o que el enlace subyacente no haya rellenado todavía los orígenes de datos (incluso en el nivel de expresión).  
  
### <a name="loaded"></a>Cargado  
 <xref:System.Windows.FrameworkElement.Loaded>se genera a continuación. El <xref:System.Windows.FrameworkElement.Loaded> evento se genera antes de la representación final, pero después de que el sistema de diseño haya calculado todos los valores necesarios para la representación. <xref:System.Windows.FrameworkElement.Loaded>implica que el árbol lógico en el que se encuentra un elemento está completo y se conecta a un origen de presentación que proporciona el HWND y la superficie de representación. El enlace de datos estándar (enlace a orígenes locales, como otras propiedades o orígenes de datos definidos directamente) se habrá producido <xref:System.Windows.FrameworkElement.Loaded>antes de. Es posible que el enlace de datos asincrónico (orígenes externos o dinámicos) se haya producido, pero, por definición de su naturaleza asincrónica, no se puede garantizar que realmente se haya producido.  
  
 El mecanismo por el que <xref:System.Windows.FrameworkElement.Loaded> se genera el evento es diferente <xref:System.Windows.FrameworkElement.Initialized>de. El <xref:System.Windows.FrameworkElement.Initialized> evento se genera elemento por elemento, sin una coordinación directa mediante un árbol de elementos completado. Por el contrario, <xref:System.Windows.FrameworkElement.Loaded> el evento se genera como un esfuerzo coordinado en todo el árbol de elementos (específicamente, el árbol lógico). Cuando todos los elementos del árbol se encuentran en un estado en el que se consideran cargados, el <xref:System.Windows.FrameworkElement.Loaded> evento se genera primero en el elemento raíz. Después <xref:System.Windows.FrameworkElement.Loaded> , el evento se genera sucesivamente en cada elemento secundario.  
  
> [!NOTE]
> Este comportamiento puede parecerse a primera vista a una tunelización para un evento enrutado. Sin embargo, no se desplaza información de un evento a otro. Cada elemento tiene siempre la oportunidad de controlar su <xref:System.Windows.FrameworkElement.Loaded> evento y marcar los datos de evento como controlados no tiene ningún efecto más allá de ese elemento.  
  
### <a name="unloaded"></a>Descargado  
 <xref:System.Windows.FrameworkElement.Unloaded>se genera en último lugar y lo inicia el origen de presentación o el elemento primario visual que se va a quitar. Cuando <xref:System.Windows.FrameworkElement.Unloaded> se genera y se controla, el elemento que es el elemento primario del origen del evento <xref:System.Windows.FrameworkElement.Parent%2A> (determinado por la propiedad) o cualquier elemento determinado que se encuentre en los árboles lógicos o visuales, puede que ya se haya desactivado, lo que significa que el enlace de datos, las referencias de recursos los estilos y no pueden establecerse en su valor de tiempo de ejecución normal o último conocido.  
  
<a name="application_model_elements"></a>   
## <a name="lifetime-events-application-model-elements"></a>Elementos del modelo de aplicación de eventos de duración  
 La compilación de los eventos de duración comunes para los elementos son los siguientes elementos <xref:System.Windows.Application>del modelo <xref:System.Windows.Controls.Page>de aplicación: <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Window>,, <xref:System.Windows.Navigation.NavigationWindow>y. Extienden los eventos de duración comunes con eventos adicionales que son pertinentes para su finalidad específica. Esto se trata detalladamente en las siguientes ubicaciones:  
  
- <xref:System.Windows.Application>: [Información general sobre la administración de aplicaciones](../app-development/application-management-overview.md).  
  
- <xref:System.Windows.Window>: [Información general sobre ventanas de WPF](../app-development/wpf-windows-overview.md).  
  
- <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>y :<xref:System.Windows.Controls.Frame> [Información general sobre navegación](../app-development/navigation-overview.md).  
  
## <a name="see-also"></a>Vea también

- [Prioridad de los valores de propiedades de dependencia](dependency-property-value-precedence.md)
- [Información general sobre eventos enrutados](routed-events-overview.md)

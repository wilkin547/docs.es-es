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
ms.openlocfilehash: 02a6736fe54be4683044f648e9d5ed5e8a3d95dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="object-lifetime-events"></a>Eventos de duración de objetos
En este tema se describen los eventos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] específicos que indican las fases de duración de la creación, el uso y la destrucción de objetos.  
  

  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 En este tema, se supone que entiende las propiedades de dependencia desde la perspectiva de un consumidor de propiedades de dependencia existentes en las clases [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] y que ha leído el tema [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md). Para seguir los ejemplos de este tema, también debe comprender [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] (consulte [Información general sobre XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)) y saber cómo escribir aplicaciones [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="intro"></a>   
## <a name="object-lifetime-events"></a>Eventos de duración de objetos  
 Todos los objetos en el código administrado de Microsoft .NET Framework que se van a través de un conjunto similar de fases de vida, creación, uso y destrucción. Además, muchos objetos tienen una fase de finalización de duración que se produce como parte de la fase de destrucción. Los objetos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], concretamente los objetos visuales que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] identifica como elementos, también tienen un conjunto de fases comunes de duración de objeto. Los modelos de programación y aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] exponen estas fases como una serie de eventos. Hay cuatro tipos principales de objetos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con respecto a los eventos de duración: elementos en general, elementos de ventana, hosts de navegación y objetos de aplicación. Las ventanas y los hosts de navegación también se encuentran dentro de un grupo más grande de objetos visuales (elementos). En este tema se describen los eventos de duración que son comunes para todos los elementos y se indican los más específicos que se aplican a las definiciones de aplicación, las ventanas o los hosts de navegación.  
  
<a name="common_events"></a>   
## <a name="common-lifetime-events-for-elements"></a>Eventos de duración comunes para elementos  
 Cualquier elemento de nivel de marco WPF (esos objetos derivar desde <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>) tiene tres eventos de duración comunes: <xref:System.Windows.FrameworkElement.Initialized>, <xref:System.Windows.FrameworkElement.Loaded>, y <xref:System.Windows.FrameworkElement.Unloaded>.  
  
### <a name="initialized"></a>Inicializado  
 <xref:System.Windows.FrameworkElement.Initialized> se produce en primer lugar y corresponden aproximadamente a la inicialización del objeto mediante la llamada a su constructor. Dado que el evento se produce en respuesta a la inicialización, se garantiza que se establecen todas las propiedades del objeto. (Las excepciones son los usos de la expresión, como recursos dinámicos o enlaces, que son expresiones no evaluadas). Por consiguiente el requisito de que se establecen todas las propiedades, la secuencia de <xref:System.Windows.FrameworkElement.Initialized> provocados por elementos anidados que se definen en el marcado parece que se producen en el orden de los elementos más profundo en el árbol de elementos en primer lugar, después elementos hasta la raíz de la principal. Este orden se debe a que las relaciones entre elementos primarios y secundarios y las inclusiones son propiedades y, por tanto, el elemento primario no puede informar de la inicialización hasta que los elementos secundarios que rellenan la propiedad estén inicializados completamente.  
  
 Cuando se escribe controladores en respuesta a la <xref:System.Windows.FrameworkElement.Initialized> evento, debe tener en cuenta que no hay ninguna garantía de que todos los demás elementos en el árbol de elementos (árbol lógico o árbol visual) alrededor de la que está asociado el controlador se han creado, especialmente elementos primarios. Es posible que las variables de miembro sean nulas o que el enlace subyacente no haya rellenado todavía los orígenes de datos (incluso en el nivel de expresión).  
  
### <a name="loaded"></a>Cargado  
 <xref:System.Windows.FrameworkElement.Loaded> se produce a continuación. El <xref:System.Windows.FrameworkElement.Loaded> evento se desencadena antes de la presentación final, pero después de que el sistema de diseño ha calculado todos los valores necesarios para la representación. <xref:System.Windows.FrameworkElement.Loaded> implica que el árbol lógico que está dentro de un elemento se ha completado y se conecta a un origen de presentación que proporciona el HWND y la superficie de representación. Enlace de datos estándar (enlaces a orígenes locales, como otras propiedades u orígenes de datos definidos directamente) se habrá producido antes <xref:System.Windows.FrameworkElement.Loaded>. Es posible que el enlace de datos asincrónico (orígenes externos o dinámicos) se haya producido, pero, por definición de su naturaleza asincrónica, no se puede garantizar que realmente se haya producido.  
  
 El mecanismo mediante el cual el <xref:System.Windows.FrameworkElement.Loaded> evento se desencadena es diferente de <xref:System.Windows.FrameworkElement.Initialized>. El <xref:System.Windows.FrameworkElement.Initialized> evento es provoca de elemento en elemento, sin la coordinación directa de un árbol de elementos completado. Por el contrario, el <xref:System.Windows.FrameworkElement.Loaded> evento se desencadena como un esfuerzo coordinado a lo largo del árbol de elementos completa (específicamente, el árbol lógico). Cuando todos los elementos del árbol están en un estado en que se consideran cargados, el <xref:System.Windows.FrameworkElement.Loaded> en primer lugar se provoca el evento en el elemento raíz. El <xref:System.Windows.FrameworkElement.Loaded> eventos, a continuación, se generan consecutivamente en cada elemento secundario.  
  
> [!NOTE]
>  Este comportamiento puede parecerse a primera vista a una tunelización para un evento enrutado. Sin embargo, no se desplaza información de un evento a otro. Cada elemento siempre tiene la oportunidad de controlar sus <xref:System.Windows.FrameworkElement.Loaded> eventos y marcar los datos del evento como controlado no tiene ningún efecto más allá de ese elemento.  
  
### <a name="unloaded"></a>Descargado  
 <xref:System.Windows.FrameworkElement.Unloaded> se provoca en último lugar y se inicia el origen de presentación o el elemento primario visual que se va a quitar. Cuando <xref:System.Windows.FrameworkElement.Unloaded> genera y controlada, el elemento que es el primario de origen del evento (según lo determinado por <xref:System.Windows.FrameworkElement.Parent%2A> propiedad) o cualquier elemento hacia arriba en los árboles lógicos o visuales puede haber ya no se establece, lo que significa que ese enlace de datos, las referencias de recursos , y no se pueden establecer estilos en sus valores de tiempo de ejecución normal o el último conocido.  
  
<a name="application_model_elements"></a>   
## <a name="lifetime-events-application-model-elements"></a>Elementos del modelo de aplicación de eventos de duración  
 A partir de los eventos de duración comunes para elementos son los siguientes elementos de modelo de aplicación: <xref:System.Windows.Application>, <xref:System.Windows.Window>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, y <xref:System.Windows.Controls.Frame>. Extienden los eventos de duración comunes con eventos adicionales que son pertinentes para su finalidad específica. Esto se trata detalladamente en las siguientes ubicaciones:  
  
-   <xref:System.Windows.Application>: [Información general sobre la administración de aplicaciones](../../../../docs/framework/wpf/app-development/application-management-overview.md).  
  
-   <xref:System.Windows.Window>: [Introducción a WPF Windows](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md).  
  
-   <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, y <xref:System.Windows.Controls.Frame>: [información general de navegación](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
## <a name="see-also"></a>Vea también  
 [Prioridad de los valores de propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md)  
 [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md)

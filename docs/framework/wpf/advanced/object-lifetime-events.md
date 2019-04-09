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
ms.openlocfilehash: 8ecc3f716061dfd08ac95652d1a9d8e06e26d949
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175799"
---
# <a name="object-lifetime-events"></a>Eventos de duración de objetos
En este tema se describen los eventos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] específicos que indican las fases de duración de la creación, el uso y la destrucción de objetos.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 En este tema, se supone que entiende las propiedades de dependencia desde la perspectiva de un consumidor de propiedades de dependencia existentes en las clases [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] y que ha leído el tema [Información general sobre las propiedades de dependencia](dependency-properties-overview.md). Para seguir los ejemplos de este tema, también debe comprender [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] (consulte [Información general sobre XAML (WPF)](xaml-overview-wpf.md)) y saber cómo escribir aplicaciones [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="intro"></a>   
## <a name="object-lifetime-events"></a>Eventos de duración de objetos  
 Todos los objetos en el código administrado de Microsoft .NET Framework que se van a través de un conjunto similar de fases de la vida, la creación, uso y destrucción. Además, muchos objetos tienen una fase de finalización de duración que se produce como parte de la fase de destrucción. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] objetos, más concretamente los objetos visuales que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] identifica como elementos, también tienen un conjunto de fases comunes del ciclo de vida del objeto. Los modelos de programación y aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] exponen estas fases como una serie de eventos. Hay cuatro tipos principales de objetos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con respecto a los eventos de duración: elementos en general, elementos de ventana, hosts de navegación y objetos de aplicación. Las ventanas y los hosts de navegación también se encuentran dentro de un grupo más grande de objetos visuales (elementos). En este tema se describen los eventos de duración que son comunes para todos los elementos y se indican los más específicos que se aplican a las definiciones de aplicación, las ventanas o los hosts de navegación.  
  
<a name="common_events"></a>   
## <a name="common-lifetime-events-for-elements"></a>Eventos de duración comunes para elementos  
 Cualquier elemento de nivel de marco WPF (los objetos derivados de cualquiera <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>) tiene tres eventos de duración comunes: <xref:System.Windows.FrameworkElement.Initialized>, <xref:System.Windows.FrameworkElement.Loaded>, y <xref:System.Windows.FrameworkElement.Unloaded>.  
  
### <a name="initialized"></a>Inicializado  
 <xref:System.Windows.FrameworkElement.Initialized> se genera primero y corresponde aproximadamente a la inicialización del objeto mediante la llamada a su constructor. Dado que el evento se produce en respuesta a la inicialización, se garantiza que se establecen todas las propiedades del objeto. (Las excepciones son los usos de la expresión, como recursos dinámicos o enlaces, que son expresiones no evaluadas). Como consecuencia el requisito de que se establecen todas las propiedades, la secuencia de <xref:System.Windows.FrameworkElement.Initialized> que se generan elementos anidados que se definen en la marcación parece que ocurre en orden de los elementos más profundo en el árbol de elementos en primer lugar, elementos primarios hasta la raíz. Este orden se debe a que las relaciones entre elementos primarios y secundarios y las inclusiones son propiedades y, por tanto, el elemento primario no puede informar de la inicialización hasta que los elementos secundarios que rellenan la propiedad estén inicializados completamente.  
  
 Cuando se escribe controladores en respuesta a la <xref:System.Windows.FrameworkElement.Initialized> eventos, debe tener en cuenta que no hay ninguna garantía de que todos los demás elementos del árbol de elementos (árbol visual o árbol lógico) en torno a la que está asociado el controlador se han creado, especialmente elementos primarios. Es posible que las variables de miembro sean nulas o que el enlace subyacente no haya rellenado todavía los orígenes de datos (incluso en el nivel de expresión).  
  
### <a name="loaded"></a>Cargado  
 <xref:System.Windows.FrameworkElement.Loaded> se genera a continuación. El <xref:System.Windows.FrameworkElement.Loaded> evento se genera antes de la representación final, pero después de que el sistema de diseño haya calculado todos los valores necesarios para la representación. <xref:System.Windows.FrameworkElement.Loaded> implica que el árbol lógico que está dentro de un elemento está completado y se conecta a un origen de presentación que proporciona el HWND y la superficie de representación. Enlace de datos estándar (enlace a orígenes locales, como otras propiedades u orígenes de datos definidos directamente) se habrán producido antes <xref:System.Windows.FrameworkElement.Loaded>. Es posible que el enlace de datos asincrónico (orígenes externos o dinámicos) se haya producido, pero, por definición de su naturaleza asincrónica, no se puede garantizar que realmente se haya producido.  
  
 Mecanismo por el cual el <xref:System.Windows.FrameworkElement.Loaded> provoca el evento es diferente de <xref:System.Windows.FrameworkElement.Initialized>. El <xref:System.Windows.FrameworkElement.Initialized> evento es genera elemento por elemento, sin la coordinación directa de un árbol de elementos completado. Por el contrario, el <xref:System.Windows.FrameworkElement.Loaded> se provoca el evento como un esfuerzo coordinado en todo el árbol de elementos completo (en concreto, el árbol lógico). Cuando todos los elementos del árbol están en un estado en que se consideran cargado, el <xref:System.Windows.FrameworkElement.Loaded> en primer lugar se provoca el evento en el elemento raíz. El <xref:System.Windows.FrameworkElement.Loaded> , a continuación, se genera correctamente el evento en cada elemento secundario.  
  
> [!NOTE]
>  Este comportamiento puede parecerse a primera vista a una tunelización para un evento enrutado. Sin embargo, no se desplaza información de un evento a otro. Cada elemento siempre tiene la oportunidad de controlar su <xref:System.Windows.FrameworkElement.Loaded> eventos y marcar los datos de evento como controlados no tiene ningún efecto más allá de ese elemento.  
  
### <a name="unloaded"></a>Descargado  
 <xref:System.Windows.FrameworkElement.Unloaded> se genera en último lugar y se inicia cuando el origen de presentación o el elemento primario visual que se va a quitar. Cuando <xref:System.Windows.FrameworkElement.Unloaded> se genera y se controla, el elemento que es el elemento primario de origen de eventos (según lo determinado por <xref:System.Windows.FrameworkElement.Parent%2A> propiedad) o cualquier elemento hacia arriba en los árboles lógicos o visuales puede haber estado sin establecer, lo que significa que enlace de datos, las referencias de recursos , y no se pueden establecer los estilos a su valor de tiempo de ejecución normal o último conocido.  
  
<a name="application_model_elements"></a>   
## <a name="lifetime-events-application-model-elements"></a>Elementos del modelo de aplicación de eventos de duración  
 A partir de los eventos de duración comunes para los elementos son los siguientes elementos de modelo de aplicación: <xref:System.Windows.Application>, <xref:System.Windows.Window>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, y <xref:System.Windows.Controls.Frame>. Extienden los eventos de duración comunes con eventos adicionales que son pertinentes para su finalidad específica. Esto se trata detalladamente en las siguientes ubicaciones:  
  
-   <xref:System.Windows.Application>: [Información general sobre la administración de aplicaciones](../app-development/application-management-overview.md).  
  
-   <xref:System.Windows.Window>: [Información general de Windows WPF](../app-development/wpf-windows-overview.md).  
  
-   <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, y <xref:System.Windows.Controls.Frame>: [Información general sobre navegación](../app-development/navigation-overview.md).  
  
## <a name="see-also"></a>Vea también

- [Prioridad de los valores de propiedades de dependencia](dependency-property-value-precedence.md)
- [Información general sobre eventos enrutados](routed-events-overview.md)

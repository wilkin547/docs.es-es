---
title: "Eventos de duraci&#243;n de objetos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Activated (eventos)"
  - "Application (objetos), eventos de duración"
  - "clases, Fotograma"
  - "clases, NavigationWindow"
  - "Closed (eventos)"
  - "Closing (eventos)"
  - "ContentRendered (eventos)"
  - "Deactivated (eventos)"
  - "eventos, Activated"
  - "eventos, Cerrado"
  - "eventos, Closing"
  - "eventos, ContentRendered"
  - "eventos, Deactivated"
  - "eventos, Inicializado"
  - "eventos, Cargado"
  - "eventos, Descargado"
  - "eventos de salida"
  - "Frame (clase)"
  - "Initialized (eventos)"
  - "eventos de duración de objetos"
  - "Loaded (eventos)"
  - "NavigationWindow (clase)"
  - "eventos de duración de objetos"
  - "Startup (eventos)"
  - "Unloaded (eventos)"
ms.assetid: face6fc7-465b-4502-bfe5-e88d2e729a78
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Eventos de duraci&#243;n de objetos
En este tema se describen los eventos específicos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que representan las fases de la duración de un objeto, a saber, creación, uso y destrucción.  
  
   
  
<a name="prerequisites"></a>   
## Requisitos previos  
 En este tema se da por sentado que el lector entiende las [propiedades de dependencia](GTMT) desde la perspectiva de un consumidor de propiedades de dependencia existentes en las clases de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], y que ha leído el tema [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  Para seguir los ejemplos de este tema, también debe entender [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] \(vea [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)\) y saber escribir aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="intro"></a>   
## Eventos de duración de objetos  
 Todos los objetos de código administrado de [!INCLUDE[TLA#tla_netframewk](../../../../includes/tlasharptla-netframewk-md.md)] pasan por un conjunto similar de fases de duración: creación, uso y destrucción.  Además, muchos objetos tienen una fase de finalización de su duración que tiene lugar como parte de la fase de destrucción.  Los objetos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , y más concretamente los objetos visuales que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] identifica como elementos, también tienen un conjunto de fases comunes de duración de objeto.  Los modelos de programación y de aplicación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] exponen estas fases como una serie de eventos.  Hay cuatro tipos principales de objetos en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con respecto a los eventos de duración; los elementos en general, los elementos de ventana, los hosts de navegación y los objetos de aplicación.  Las ventanas y los hosts de navegación también pertenecen al grupo mayor de objetos visuales \(elementos\).  En este tema se describen los eventos de duración comunes a todos los elementos y, a continuación, se presentan los más concretos que se aplican a las definiciones de aplicación, ventanas u hosts de navegación.  
  
<a name="common_events"></a>   
## Eventos de duración comunes para elementos  
 Cualquier elemento de [nivel de marco de trabajo de WPF](GTMT) \(aquellos objetos que se derivan de <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>\) tiene tres eventos de duración comunes: <xref:System.Windows.FrameworkElement.Initialized>, <xref:System.Windows.FrameworkElement.Loaded> y <xref:System.Windows.FrameworkElement.Unloaded>.  
  
### Initialized  
 <xref:System.Windows.FrameworkElement.Initialized> se provoca primero y corresponde aproximadamente a la inicialización del objeto mediante la llamada a su constructor.  Dado que el evento se produce en respuesta a la inicialización, es seguro que se establecen todas las propiedades del objeto.  \(Una excepción de ello son los usos de expresiones del tipo de recursos dinámicos o enlaces; estas expresiones no se evaluarán.\) Como consecuencia del requisito de que se establezcan todas las propiedades, la secuencia del elemento <xref:System.Windows.FrameworkElement.Initialized> provocado por elementos anidados definidos en marcado parece suceder por orden desde los elementos más profundos del árbol de elementos hasta los elementos primarios cercanos a la raíz.  Este orden se debe a que las relaciones entre elementos primarios y secundarios y de contención son propiedades, y por consiguiente el elemento primario no puede comunicar la inicialización hasta que se han inicializado completamente también los elementos secundarios que rellenan la propiedad.  
  
 Cuando escriba controladores en respuesta al evento <xref:System.Windows.FrameworkElement.Initialized>, debe tener en cuenta que no existe ninguna garantía de que se hayan creado todos los demás elementos del árbol de elementos \([árbol lógico](GTMT) o [el árbol visual](GTMT)\) en torno al punto donde se asocie el controlador, en particular los elementos primarios.  Puede que haya variables de miembro que sean null, o que algunos orígenes de datos no se hayan rellenado aún por el enlace subyacente \(incluso en el nivel de expresión\).  
  
### Loaded  
 El evento <xref:System.Windows.FrameworkElement.Loaded> se provoca a continuación.  El evento <xref:System.Windows.FrameworkElement.Loaded> se provoca antes de la presentación final, pero después de que el sistema de diseño haya calculado todos los valores necesarios para presentar.  <xref:System.Windows.FrameworkElement.Loaded> implica que el árbol lógico en el que está contenido un elemento está completo, y se conecta a un origen de presentación que proporciona el HWND y la superficie de presentación.  El enlace de datos estándar \(enlaces a orígenes locales, como otras propiedades u orígenes de datos definidos directamente\) se habrá producido antes de <xref:System.Windows.FrameworkElement.Loaded>.  El enlace de datos asincrónico \(orígenes externos o dinámicos\) podría haberse producido, pero por definición de su naturaleza asincrónica no se puede garantizar que así sea.  
  
 El mecanismo por el que se provoca el evento <xref:System.Windows.FrameworkElement.Loaded> es diferente que el de <xref:System.Windows.FrameworkElement.Initialized>.  El evento <xref:System.Windows.FrameworkElement.Initialized> se provoca de elemento en elemento, sin la coordinación directa de un árbol de elementos completado.  En cambio, el evento <xref:System.Windows.FrameworkElement.Loaded> se provoca como un esfuerzo coordinado en todo el árbol de elementos \(en concreto, en el [árbol lógico](GTMT)\).  Cuando todos los elementos del árbol están en un estado en que se consideran cargados, el evento <xref:System.Windows.FrameworkElement.Loaded> se provoca en primer lugar en el elemento raíz.  El evento <xref:System.Windows.FrameworkElement.Loaded> se provoca a continuación consecutivamente en cada elemento secundario.  
  
> [!NOTE]
>  A primera vista, este comportamiento podría parecerse a la tunelización de los [eventos enrutados](GTMT).  Sin embargo, no se lleva ninguna información de un evento a otro.  Cada elemento siempre tiene la oportunidad de controlar su evento <xref:System.Windows.FrameworkElement.Loaded>, de manera que marcar los datos de evento como controlados no surte ningún efecto más allá de ese elemento.  
  
### Unloaded  
 <xref:System.Windows.FrameworkElement.Unloaded> se provoca en último lugar y lo inicia el origen de presentación o bien el elemento visual primario que se quita.  Al provocar y controlar el evento <xref:System.Windows.FrameworkElement.Unloaded>, puede suceder que elemento primario de origen del evento \(según lo determina la propiedad <xref:System.Windows.FrameworkElement.Parent%2A>\) o cualquier elemento dado que se encuentre más arriba en los árboles lógico o visual, ya no esté establecido, lo que significa que el enlace de datos, las referencias de recursos y los estilos podrían no estar establecidos en su valor normal o en su último valor conocido en tiempo de ejecución.  
  
<a name="application_model_elements"></a>   
## Elementos de modelos de aplicación de eventos de duración  
 Los siguientes elementos de modelos de aplicación se basan en los eventos de duración comunes para los elementos: <xref:System.Windows.Application>, <xref:System.Windows.Window>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow> y <xref:System.Windows.Controls.Frame>.  Éstos extienden los eventos de duración comunes con eventos adicionales que son pertinentes a su finalidad específica.  Se explican con detalle en las ubicaciones siguientes:  
  
-   <xref:System.Windows.Application>: [Información general sobre la administración de aplicaciones](../../../../docs/framework/wpf/app-development/application-management-overview.md).  
  
-   <xref:System.Windows.Window>: [Información general sobre ventanas de WPF](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md).  
  
-   <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow> y <xref:System.Windows.Controls.Frame>: [Información general sobre navegación](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
## Vea también  
 [Prioridad de los valores de propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md)   
 [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
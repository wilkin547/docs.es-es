---
title: Información general sobre navegación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- loose XAML files [WPF]
- windows [WPF]
- Start page [WPF]
- HTML files [WPF]
- structured navigation [WPF]
- fragment navigation [WPF]
- URIs (Uniform Resource Identifiers)
- custom objects [WPF]
- Uniform Resource Identifiers (URIs)
- pages [WPF]
- frames [WPF]
- navigation hosts [WPF]
- journals [WPF]
- lifetimes [WPF]
- retaining content state [WPF]
- content state [WPF]
- programmatic navigation [WPF]
- hyperlinks [WPF]
ms.assetid: 86ad2143-606a-4e34-bf7e-51a2594248b8
ms.openlocfilehash: 574449f95ee9632d37f277d61806802457494df0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964588"
---
# <a name="navigation-overview"></a>Información general sobre navegación

Windows Presentation Foundation (WPF) admite la navegación de estilo explorador que se puede usar en dos tipos de aplicaciones: aplicaciones independientes [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]y. Para empaquetar el contenido para [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] la navegación <xref:System.Windows.Controls.Page> , proporciona la clase. Puede desplazarse de <xref:System.Windows.Controls.Page> uno a otro mediante declaración, <xref:System.Windows.Documents.Hyperlink>mediante, o mediante programación, mediante el uso de <xref:System.Windows.Navigation.NavigationService>. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] usa el diario para recordar las páginas desde las que se navegó o para volver a ellas.

<xref:System.Windows.Controls.Page>,, y el diario forman el núcleo de la compatibilidad de navegación que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]ofrece. <xref:System.Windows.Documents.Hyperlink> <xref:System.Windows.Navigation.NavigationService> En esta información general se exploran estas características en detalle antes de cubrir la compatibilidad con la [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] navegación avanzada, que incluye la navegación a archivos sueltos, archivos HTML y objetos.

> [!NOTE]
> En este tema, el término "explorador" solo se refiere a los exploradores [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] que pueden hospedar aplicaciones, que actualmente incluye Microsoft Internet Explorer y Firefox. Cuando solo [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] un explorador determinado admite características específicas, se hace referencia a la versión del explorador.

## <a name="navigation-in-wpf-applications"></a>Navegación a aplicaciones para WPF

En este tema se proporciona información general sobre las capacidades de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]navegación clave de. Estas capacidades están disponibles para las aplicaciones independientes y [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], aunque en este tema se presentan en el contexto [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]de.

> [!NOTE]
> En este tema no se explica cómo compilar e implementar [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]. Para obtener más información [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]sobre, vea [información general sobre las aplicaciones de explorador XAML de WPF](wpf-xaml-browser-applications-overview.md).

En esta sección se describen y se muestran los siguientes aspectos de navegación:

- [Implementación de una página](#CreatingAXAMLPage)

- [Configuración de una página de inicio](#Configuring_a_Start_Page)

- [Configuración del título, el ancho y el alto de la ventana host](#ConfiguringAXAMLPage)

- [Navegación por hipervínculos](#NavigatingBetweenXAMLPages)

- [Navegación por fragmentos](#FragmentNavigation)

- [Servicio de navegación](#NavigationService)

- [Navegación programática con el servicio de navegación](#Programmatic_Navigation_with_the_Navigation_Service)

- [Duración de la navegación](#Navigation_Lifetime)

- [Registro de la navegación con el diario](#NavigationHistory)

- [Duración de la página y el diario](#PageLifetime)

- [Conservación del estado del contenido con el historial de navegación](#RetainingContentStateWithNavigationHistory)

- [Cookies](#Cookies)

- [Navegación estructurada](#Structured_Navigation)

<a name="CreatingAXAMLPage"></a>

### <a name="implementing-a-page"></a>Implementación de una página

En [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], puede navegar a varios tipos de contenido que incluyen objetos de .NET Framework, objetos personalizados, valores de enumeración, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] controles de usuario, archivos y archivos HTML. Sin embargo, descubrirá que la manera más común y cómoda de empaquetar el contenido <xref:System.Windows.Controls.Page>es mediante. Además, <xref:System.Windows.Controls.Page> implementa características específicas de la navegación para mejorar su apariencia y simplificar el desarrollo.

Con <xref:System.Windows.Controls.Page>, puede implementar mediante declaración una página de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] contenido navegable mediante el uso de marcado como el siguiente.

[!code-xaml[NavigationOverviewSnippets#Page1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page1.xaml#page1xaml)]

Un <xref:System.Windows.Controls.Page> que se implementa en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] el marcado `Page` tiene como elemento raíz y requiere la [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] declaración del espacio de [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] nombres. El `Page` elemento incluye el contenido al que desea desplazarse y mostrarse. El contenido se agrega estableciendo el `Page.Content` elemento de propiedad, como se muestra en el marcado siguiente.

[!code-xaml[NavigationOverviewSnippets#Page2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page2.xaml#page2xaml)]

`Page.Content` solo puede contener un elemento secundario; en el ejemplo anterior, el contenido es una sola cadena, "Hello, Page!". En la práctica, normalmente usará un control de diseño como el elemento secundario (vea [diseño](../advanced/layout.md)) para contener y componer el contenido.

Los elementos secundarios de un `Page` elemento se consideran el contenido <xref:System.Windows.Controls.Page> de y, por consiguiente, no es necesario utilizar la declaración explícita `Page.Content` . La marcación siguiente es el equivalente declarativo del ejemplo anterior.

[!code-xaml[NavigationOverviewSnippets#Page3XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page3.xaml#page3xaml)]

En este caso, `Page.Content` se establece automáticamente con los elementos secundarios `Page` del elemento. Para obtener más información, consulte [Modelo de contenido de WPF](../controls/wpf-content-model.md).

Un marcado solo <xref:System.Windows.Controls.Page> es útil para mostrar el contenido. Sin embargo, <xref:System.Windows.Controls.Page> también puede mostrar controles que permiten a los usuarios interactuar con la página, y pueden responder a la interacción del usuario controlando los eventos y llamando a la lógica de la aplicación. Un interactivo <xref:System.Windows.Controls.Page> se implementa mediante una combinación de marcado y código subyacente, como se muestra en el ejemplo siguiente.

[!code-xaml[XBAPAppDefSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml#homepagemarkup)]

[!code-csharp[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml.cs#homepagecodebehind)]
[!code-vb[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/HomePage.xaml.vb#homepagecodebehind)]

Para permitir que un archivo de marcación y un archivo de código subyacente funcionen juntos, se necesita la configuración siguiente:

- En el marcado, `Page` el elemento debe incluir `x:Class` el atributo. Cuando se compila la aplicación, la existencia de `x:Class` en el archivo de marcado hace que el motor de compilación de Microsoft ( `partial` MSBuild) cree una clase <xref:System.Windows.Controls.Page> que deriva de y tiene el nombre especificado por `x:Class` el atributo. Esto requiere la adición de una [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] declaración de espacio de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] nombres para `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` el esquema (). La clase `partial` generada `InitializeComponent`implementa, a la que se llama para registrar los eventos y establecer las propiedades que se implementan en el marcado.

- En el código subyacente, la clase debe ser una `partial` clase con el mismo nombre especificado por el atributo en `x:Class` el marcado y debe derivar de <xref:System.Windows.Controls.Page>. Esto permite asociar el archivo de código subyacente con la `partial` clase que se genera para el archivo de marcado cuando se compila la aplicación (consulte compilar [una aplicación de WPF](building-a-wpf-application-wpf.md)).

- En el código subyacente, la <xref:System.Windows.Controls.Page> clase debe implementar un constructor que llame al `InitializeComponent` método. `InitializeComponent`se implementa mediante la clase generada `partial` por el archivo de marcado para registrar eventos y establecer las propiedades que se definen en el marcado.

> [!NOTE]
> Cuando se agrega un nuevo <xref:System.Windows.Controls.Page> a un proyecto mediante [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], <xref:System.Windows.Controls.Page> se implementa mediante el marcado y el código subyacente, e incluye la configuración necesaria para crear la asociación entre el marcado y los archivos de código subyacente como se describe aquí.

Una vez que tenga <xref:System.Windows.Controls.Page>un, puede desplazarse hasta él. Para especificar la primera <xref:System.Windows.Controls.Page> a la que se desplaza una aplicación, debe configurar el inicio. <xref:System.Windows.Controls.Page>

<a name="Configuring_a_Start_Page"></a>

### <a name="configuring-a-start-page"></a>Configuración de una página de inicio

[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] requieren que se hospede una determinada cantidad de infraestructuras de aplicaciones en un explorador. En [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], la <xref:System.Windows.Application> clase forma parte de una definición de aplicación que establece la infraestructura de aplicación necesaria (consulte [información general sobre la administración de aplicaciones](application-management-overview.md)).

Normalmente, una definición de aplicación se implementa mediante el marcado y el código subyacente, con el archivo de marcado configurado`ApplicationDefinition` como un elemento de MSBuild. La siguiente es una definición de aplicación para [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]un.

[!code-xaml[XBAPAppDefSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]

[!code-csharp[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml.cs#xbapapplicationdefinitioncodebehind)]
[!code-vb[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/Application.xaml.vb#xbapapplicationdefinitioncodebehind)]

Puede utilizar su definición de aplicación para especificar un inicio <xref:System.Windows.Controls.Page>, que es el <xref:System.Windows.Controls.Page> que se carga automáticamente cuando [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] se inicia. [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] Para ello, establezca la <xref:System.Windows.Application.StartupUri%2A> propiedad <xref:System.Windows.Controls.Page>con para el deseado. [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]

> [!NOTE]
> En la mayoría de los <xref:System.Windows.Controls.Page> casos, se compila en o se implementa con una aplicación. En estos casos, el [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que <xref:System.Windows.Controls.Page> identifica a es un módulo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], que es un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que se ajusta al esquema de *Pack* . El [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] módulo se describe con más detalle en [pack uri en WPF](pack-uris-in-wpf.md). También puede navegar al contenido con el esquema HTTP, que se describe a continuación.

Puede establecer <xref:System.Windows.Application.StartupUri%2A> mediante declaración en el marcado, tal y como se muestra en el ejemplo siguiente.

[!code-xaml[NavigationOverviewSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]

En este ejemplo, el `StartupUri` atributo se establece con un pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] relativo que identifica homepage. Xaml. [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] Cuando se inicia, se navega a homepage. XAML y se muestra automáticamente. Esto se muestra en la siguiente ilustración, que muestra un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] que se inició desde un servidor Web.

![Página de XBAP](./media/navigation-overview/xbap-launched-from-a-web-server.png "Esto muestra una aplicación XBAP iniciada desde un servidor Web.")

> [!NOTE]
> Para obtener más información sobre el desarrollo y la [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]implementación de, vea [información general sobre las aplicaciones de explorador XAML de WPF](wpf-xaml-browser-applications-overview.md) e [implementar una aplicación de WPF](deploying-a-wpf-application-wpf.md).

<a name="ConfiguringAXAMLPage"></a>

### <a name="configuring-the-host-windows-title-width-and-height"></a>Configuración del título, el ancho y el alto de la ventana host

Una cosa que puede haber observado en la ilustración anterior es que el título del explorador y del panel [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]de pestañas es para. Además de largo, el título no es atractivo ni informativo. Por esta razón, <xref:System.Windows.Controls.Page> ofrece una forma de cambiar el título estableciendo la <xref:System.Windows.Controls.Page.WindowTitle%2A> propiedad. Además, puede configurar el ancho y el alto de la ventana del explorador mediante <xref:System.Windows.Controls.Page.WindowWidth%2A> el <xref:System.Windows.Controls.Page.WindowHeight%2A>establecimiento de y, respectivamente.

<xref:System.Windows.Controls.Page.WindowTitle%2A>, <xref:System.Windows.Controls.Page.WindowWidth%2A>y se <xref:System.Windows.Controls.Page.WindowHeight%2A> pueden establecer mediante declaración en el marcado, tal y como se muestra en el ejemplo siguiente.

[!code-xaml[NavigationOverviewSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/HomePage.xaml#homepagemarkup)]

El resultado se muestra en la ilustración siguiente.

![Título, alto y ancho de la ventana](./media/navigation-overview/window-title-width-height.png "Esto muestra el título, el alto y el ancho de la ventana que puede configurar.")

<a name="NavigatingBetweenXAMLPages"></a>

### <a name="hyperlink-navigation"></a>Navegación por hipervínculos

Un típico [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] consta de varias páginas. La manera más sencilla de desplazarse de una página a otra es usar <xref:System.Windows.Documents.Hyperlink>. Puede agregar mediante declaración un <xref:System.Windows.Documents.Hyperlink> <xref:System.Windows.Controls.Page> a mediante el `Hyperlink` elemento, que se muestra en el marcado siguiente.

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

Un `Hyperlink` elemento requiere lo siguiente:

- Paquete [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] `NavigateUri` del al que se va a desplazar, tal y como se especifica en el atributo. <xref:System.Windows.Controls.Page>

- Contenido en el que un usuario puede hacer clic para iniciar la navegación, como texto e imágenes (para el contenido `Hyperlink` que el elemento puede contener <xref:System.Windows.Documents.Hyperlink>, vea).

En la ilustración siguiente se [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] muestra un <xref:System.Windows.Controls.Page> con un que <xref:System.Windows.Documents.Hyperlink>tiene un.

![Página con hipervínculo](./media/navigation-overview/xbap-with-a-page-with-a-hyperlink.png "Esto muestra una aplicación XBAP con una página con un hipervínculo.")

Como cabría esperar, al hacer clic <xref:System.Windows.Documents.Hyperlink> en el [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] se hace que navegue <xref:System.Windows.Controls.Page> hasta el que se identifica `NavigateUri` mediante el atributo. Además, [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] agrega una entrada para la lista de <xref:System.Windows.Controls.Page> páginas anteriores en Internet Explorer. Esto se muestra en la siguiente ilustración.

![Botones atrás y adelante](./media/navigation-overview/back-and-forward-navigation.png "Navegue con los botones atrás y adelante.")

Además de admitir la navegación de un <xref:System.Windows.Controls.Page> a otro, <xref:System.Windows.Documents.Hyperlink> también admite la navegación por fragmentos.

<a name="FragmentNavigation"></a>

### <a name="fragment-navigation"></a>Navegación por fragmentos

La *navegación por fragmentos* es la navegación a un fragmento de contenido en <xref:System.Windows.Controls.Page> el actual <xref:System.Windows.Controls.Page>o en otro. En [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], un fragmento de contenido es el contenido incluido en un elemento con nombre. Un elemento con nombre es un elemento que tiene `Name` su conjunto de atributos. En el marcado siguiente se muestra `TextBlock` un elemento con nombre que contiene un fragmento de contenido.

[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup1)]
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup2)]
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup3)]

Para que <xref:System.Windows.Documents.Hyperlink> una navegue a un fragmento de contenido, `NavigateUri` el atributo debe incluir lo siguiente:

- [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Delconelfragmentodecontenidoalque<xref:System.Windows.Controls.Page> se va a navegar.

- Un carácter "#".

- Nombre del elemento de <xref:System.Windows.Controls.Page> que contiene el fragmento de contenido.

Un fragmento [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] tiene el formato siguiente.

*PageURI* `#` *ElementName*

A continuación se muestra un ejemplo de `Hyperlink` un que está configurado para navegar a un fragmento de contenido.

[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml1)]
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml2)]
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml3)]

> [!NOTE]
> En esta sección se describe la implementación de navegación [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]por fragmentos predeterminada en. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]también le permite implementar su propio esquema de navegación por fragmentos, que, en parte, requiere <xref:System.Windows.Navigation.NavigationService.FragmentNavigation?displayProperty=nameWithType> controlar el evento.

> [!IMPORTANT]
> Puede navegar a fragmentos en páginas sueltas [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (solo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivos de marcado con `Page` como el elemento raíz) si las páginas se pueden examinar a través de http.
>
> Sin embargo, una [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] página suelta puede desplazarse a sus propios fragmentos.

<a name="NavigationService"></a>

### <a name="navigation-service"></a>Servicio de navegación

Aunque <xref:System.Windows.Documents.Hyperlink> permite que un usuario inicie la navegación a un <xref:System.Windows.Controls.Page>determinado, la <xref:System.Windows.Navigation.NavigationService> clase realiza el trabajo de búsqueda y descarga de la página. Esencialmente, <xref:System.Windows.Navigation.NavigationService> proporciona la capacidad de procesar una solicitud de navegación en nombre del código de cliente, <xref:System.Windows.Documents.Hyperlink>como. Además, <xref:System.Windows.Navigation.NavigationService> implementa compatibilidad de nivel superior para realizar el seguimiento e influir en una solicitud de navegación.

<xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.Page> [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]Cuando se hace clic en, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] llama a para buscar y descargar en el paquete especificado. <xref:System.Windows.Documents.Hyperlink> El descargado <xref:System.Windows.Controls.Page> se convierte en un árbol de objetos cuyo objeto raíz es una instancia del <xref:System.Windows.Controls.Page>descargado. Una referencia al objeto raíz <xref:System.Windows.Controls.Page> se almacena en la <xref:System.Windows.Navigation.NavigationService.Content%2A?displayProperty=nameWithType> propiedad. El paquete [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para el contenido al que se navegó se almacena en la <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType> propiedad, mientras <xref:System.Windows.Navigation.NavigationService.CurrentSource%2A?displayProperty=nameWithType> que almacena el paquete [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] de la última página a la que se navegó.

> [!NOTE]
> Es posible que una [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicación tenga más de una actualmente activa. <xref:System.Windows.Navigation.NavigationService> Para obtener más información, vea hosts de [navegación](#Navigation_Hosts) más adelante en este tema.

<a name="Programmatic_Navigation_with_the_Navigation_Service"></a>

### <a name="programmatic-navigation-with-the-navigation-service"></a>Navegación programática con el servicio de navegación

No <xref:System.Windows.Navigation.NavigationService> es necesario saber si la <xref:System.Windows.Documents.Hyperlink> <xref:System.Windows.Navigation.NavigationService> navegación se implementa mediante declaración en el marcado mediante, ya <xref:System.Windows.Documents.Hyperlink> que utiliza en su nombre. Esto significa que, siempre que el elemento primario directo o indirecto de un <xref:System.Windows.Documents.Hyperlink> sea un host de navegación (consulte hosts de <xref:System.Windows.Documents.Hyperlink> [navegación](#Navigation_Hosts)), podrá encontrar y usar el servicio de navegación del host de navegación para procesar una solicitud de navegación.

Sin embargo, hay situaciones en las que es necesario <xref:System.Windows.Navigation.NavigationService> usar directamente, entre las que se incluyen las siguientes:

- Cuando es necesario crear una instancia de <xref:System.Windows.Controls.Page> mediante un constructor sin parámetros.

- Cuando sea necesario establecer propiedades en el <xref:System.Windows.Controls.Page> antes de navegar a él.

- Cuando el <xref:System.Windows.Controls.Page> al que debe navegarse solo se puede determinar en tiempo de ejecución.

En estas situaciones, debe escribir código para iniciar la navegación mediante programación llamando al <xref:System.Windows.Navigation.NavigationService.Navigate%2A> método <xref:System.Windows.Navigation.NavigationService> del objeto. Esto requiere obtener una referencia a un <xref:System.Windows.Navigation.NavigationService>.

#### <a name="getting-a-reference-to-the-navigationservice"></a>Obtención de una referencia a NavigationService

Por motivos que se describen en la sección [Hosts de navegación](#Navigation_Hosts), una aplicación [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] puede tener más de una <xref:System.Windows.Navigation.NavigationService>. Esto significa que el código necesita una manera de buscar un <xref:System.Windows.Navigation.NavigationService>, que suele ser el <xref:System.Windows.Navigation.NavigationService> que navegó al actual <xref:System.Windows.Controls.Page>. Puede obtener una referencia a un <xref:System.Windows.Navigation.NavigationService> `static` <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A?displayProperty=nameWithType> llamando al método. Para obtener el <xref:System.Windows.Navigation.NavigationService> que navegó a un determinado <xref:System.Windows.Controls.Page>, se <xref:System.Windows.Controls.Page> pasa una referencia a como argumento del <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A> método. En el código siguiente se muestra cómo obtener <xref:System.Windows.Navigation.NavigationService> el de la <xref:System.Windows.Controls.Page>actual.

[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind1)]
[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPage.xaml.vb#getnscodebehind2)]

Como método abreviado para buscar <xref:System.Windows.Navigation.NavigationService> <xref:System.Windows.Controls.Page>para, <xref:System.Windows.Controls.Page> implementa la <xref:System.Windows.Controls.Page.NavigationService%2A> propiedad. Esta implementación se muestra en el ejemplo siguiente.

[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind1)]
[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPageShortCut.xaml.vb#getnsshortcutcodebehind2)]

> [!NOTE]
> Un <xref:System.Windows.Controls.Page> solo puede obtener una referencia a su <xref:System.Windows.Navigation.NavigationService> cuando <xref:System.Windows.Controls.Page> genera el <xref:System.Windows.FrameworkElement.Loaded> evento.

#### <a name="programmatic-navigation-to-a-page-object"></a>Navegación programática a un objeto de página

En el ejemplo siguiente se muestra cómo utilizar <xref:System.Windows.Navigation.NavigationService> para desplazarse a un <xref:System.Windows.Controls.Page>mediante programación. La navegación mediante programación es necesaria <xref:System.Windows.Controls.Page> porque solo se puede crear una instancia del al que se navega a través de un único constructor sin parámetros. El <xref:System.Windows.Controls.Page> con el constructor sin parámetros se muestra en el marcado y el código siguientes.

[!code-xaml[NavigationOverviewSnippets#PageWithNonDefaultConstructorXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml#pagewithnondefaultconstructorxaml)]

[!code-csharp[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml.cs#pagewithnondefaultconstructorcodebehind)]
[!code-vb[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithNonDefaultConstructor.xaml.vb#pagewithnondefaultconstructorcodebehind)]

El <xref:System.Windows.Controls.Page> que navega <xref:System.Windows.Controls.Page> al con el constructor sin parámetros se muestra en el marcado y el código siguientes.

[!code-xaml[NavigationOverviewSnippets#NSNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml#nsnavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml.cs#nsnavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSNavigationPage.xaml.vb#nsnavigationpagecodebehind)]

Cuando <xref:System.Windows.Controls.Page> se <xref:System.Windows.Documents.Hyperlink> hace clic en, la navegación se inicia creando una instancia de <xref:System.Windows.Controls.Page> para navegar a utilizando el constructor sin parámetros y llamando al <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> método. <xref:System.Windows.Navigation.NavigationService.Navigate%2A>acepta una referencia al objeto al que <xref:System.Windows.Navigation.NavigationService> navegará, en lugar de un Pack. [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]

#### <a name="programmatic-navigation-with-a-pack-uri"></a>Navegación programática con Pack URI

Si necesita crear un paquete [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] mediante programación (cuando solo puede determinar el pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] en tiempo de ejecución, por ejemplo), puede usar el <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> método. Esta implementación se muestra en el ejemplo siguiente.

[!code-xaml[NavigationOverviewSnippets#NSUriNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml#nsurinavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml.cs#nsurinavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSUriNavigationPage.xaml.vb#nsurinavigationpagecodebehind)]

#### <a name="refreshing-the-current-page"></a>Actualización de la página actual

No <xref:System.Windows.Controls.Page> se descarga un si tiene el mismo paquete [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que el pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] almacenado en la <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType> propiedad. Para forzar [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] a que descargue la página actual de nuevo, puede <xref:System.Windows.Navigation.NavigationService.Refresh%2A?displayProperty=nameWithType> llamar al método, como se muestra en el ejemplo siguiente.

[!code-xaml[NavigationOverviewSnippets#NSRefreshNavigationPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml#nsrefreshnavigationpagexaml1)]

[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind1)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind1)]
[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind2)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind2)]

<a name="Navigation_Lifetime"></a>

### <a name="navigation-lifetime"></a>Duración de la navegación

Hay muchas maneras de iniciar la navegación, tal como ha podido ver. Cuando se inicia la navegación y mientras la navegación está en curso, puede realizar un seguimiento e influir en la navegación mediante los siguientes eventos <xref:System.Windows.Navigation.NavigationService>implementados por:

- <xref:System.Windows.Navigation.NavigationService.Navigating> Se produce cuando se solicita una nueva navegación. Puede utilizarse para cancelar la navegación.

- <xref:System.Windows.Navigation.NavigationService.NavigationProgress> Se produce periódicamente durante una descarga y ofrece información sobre el progreso de la exploración.

- <xref:System.Windows.Navigation.NavigationService.Navigated> Se produce cuando se ha encontrado la página y se ha descargado.

- <xref:System.Windows.Navigation.NavigationService.NavigationStopped>. Se produce cuando se detiene la navegación (llamando <xref:System.Windows.Navigation.NavigationService.StopLoading%2A>a) o cuando se solicita una nueva navegación mientras está en curso una navegación actual.

- <xref:System.Windows.Navigation.NavigationService.NavigationFailed>. Se produce cuando se genera un error mientras se navega por el contenido solicitado.

- <xref:System.Windows.Navigation.NavigationService.LoadCompleted> Se produce cuando el contenido al que se navegó se carga y se analiza, y empieza a representarse.

- <xref:System.Windows.Navigation.NavigationService.FragmentNavigation>. Se produce cuando se inicia la navegación a un fragmento de contenido, cosa que tiene lugar:

  - Inmediatamente, si el fragmento deseado está en el contenido actual.

  - Una vez se ha cargado el contenido de origen, si el fragmento deseado está en otro contenido.

Los eventos de navegación se generan en el orden que se muestra en la ilustración siguiente.

![Diagrama de flujo de navegación de páginas](./media/navigation-overview/order-of-navigation-events.png "Diagrama de flujo de eventos de navegación de páginas")

En general, <xref:System.Windows.Controls.Page> no se preocupa de estos eventos. Es más probable que una aplicación esté relacionada con ellos y, por ese motivo, los eventos también se generan mediante la <xref:System.Windows.Application> clase:

- <xref:System.Windows.Application.Navigating?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationProgress?displayProperty=nameWithType>

- <xref:System.Windows.Application.Navigated?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationFailed?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationStopped?displayProperty=nameWithType>

- <xref:System.Windows.Application.LoadCompleted?displayProperty=nameWithType>

- <xref:System.Windows.Application.FragmentNavigation?displayProperty=nameWithType>

Cada vez <xref:System.Windows.Navigation.NavigationService> que genera un evento, <xref:System.Windows.Application> la clase genera el evento correspondiente. <xref:System.Windows.Controls.Frame>y <xref:System.Windows.Navigation.NavigationWindow> ofrecen los mismos eventos para detectar la navegación dentro de sus respectivos ámbitos.

En algunos casos, <xref:System.Windows.Controls.Page> podría estar interesado en estos eventos. Por ejemplo, un <xref:System.Windows.Controls.Page> puede controlar el <xref:System.Windows.Navigation.NavigationService.Navigating?displayProperty=nameWithType> evento para determinar si se debe cancelar o no la navegación fuera de sí mismo. Esta implementación se muestra en el ejemplo siguiente.

[!code-xaml[NavigationOverviewSnippets#CancelNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml#cancelnavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml.cs#cancelnavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/CancelNavigationPage.xaml.vb#cancelnavigationpagecodebehind)]

Si registra un controlador con un evento de navegación de <xref:System.Windows.Controls.Page>, como en el ejemplo anterior, también debe anular el registro del controlador de eventos. Si no lo hace, puede haber efectos secundarios con respecto a cómo [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] la navegación <xref:System.Windows.Controls.Page> recuerda la navegación con el diario.

<a name="NavigationHistory"></a>

### <a name="remembering-navigation-with-the-journal"></a>Registro de la navegación con el diario

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] usa dos pilas para recordar las páginas desde las que ha navegado: una pila de retroceso y una pila de avance. Al navegar <xref:System.Windows.Controls.Page> desde el actual a un nuevo <xref:System.Windows.Controls.Page> o reenviar a un existente <xref:System.Windows.Controls.Page>, el actual <xref:System.Windows.Controls.Page> se agrega a la *pila de retroceso*. Cuando <xref:System.Windows.Controls.Page> navega desde el actual hasta el anterior <xref:System.Windows.Controls.Page>, el actual <xref:System.Windows.Controls.Page> se agrega a la pila de *avance*. La pila de retroceso, la pila de avance y la funcionalidad para administrarlas se conocen en conjunto como el diario. Cada elemento de la pila de retroceso y la pila de avance es una instancia <xref:System.Windows.Navigation.JournalEntry> de la clase y se conoce como una *entrada de diario*.

#### <a name="navigating-the-journal-from-internet-explorer"></a>Navegación por el diario desde Internet Explorer

Conceptualmente, el diario funciona de la misma manera que los botones **atrás** y **adelante** de Internet Explorer. Esto se muestra en la siguiente ilustración.

![Botones atrás y adelante](./media/navigation-overview/back-and-forward-navigation.png "Navegue con los botones atrás y adelante.")

Para [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] hospedado en Internet Explorer, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] integra el diario en la navegación [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de Internet Explorer. Esto permite a los usuarios navegar por las [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] páginas de una mediante los botones de página **atrás**, **adelante**y **reciente** de Internet Explorer.

> [!IMPORTANT]
> En Internet Explorer, cuando un usuario navega y vuelve a un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], solo se conservan en el diario las entradas del diario de las páginas que no se mantuvieron activas. Para obtener información sobre cómo mantener las páginas activas, vea [duración de la página y el diario](#PageLifetime) más adelante en este tema.

De forma predeterminada, el texto de <xref:System.Windows.Controls.Page> cada uno de los elementos que aparecen en la lista de **páginas recientes** [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] de <xref:System.Windows.Controls.Page>Internet Explorer es para. En muchos casos, esto no es especialmente significativo para el usuario. Afortunadamente, puede cambiar el texto mediante una de las siguientes opciones:

1. Valor del `JournalEntry.Name` atributo adjunto.

2. Valor `Page.Title` del atributo.

3. Valor `Page.WindowTitle` del atributo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] y para el actual <xref:System.Windows.Controls.Page>.

4. [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] de la <xref:System.Windows.Controls.Page> actual. (Predeterminado)

El orden en que se enumeran las opciones coincide con el orden de prioridad para buscar el texto. Por ejemplo, si `JournalEntry.Name` se establece, se omiten los demás valores.

En el ejemplo siguiente se `Page.Title` usa el atributo para cambiar el texto que aparece para una entrada del diario.

[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup1)]
[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup2)]

[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind1)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind1)]
[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind2)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind2)]

#### <a name="navigating-the-journal-using-wpf"></a>Navegación por el diario mediante WPF

Aunque un usuario puede navegar por el diario mediante las páginas **atrás**, **adelante**y **recientes** de Internet Explorer, también puede navegar por el diario utilizando los mecanismos declarativos y de programación [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]proporcionados por. Una razón para ello es proporcionar una navegación [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] personalizada en las páginas.

Puede agregar mediante declaración la compatibilidad de navegación del diario mediante los comandos de navegación <xref:System.Windows.Input.NavigationCommands>expuestos por. En el ejemplo siguiente se muestra cómo utilizar `BrowseBack` el comando de navegación.

[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml1)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml2)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml3)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML4](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml4)]

Puede navegar por el diario mediante programación con uno de los siguientes miembros de la <xref:System.Windows.Navigation.NavigationService> clase:

- <xref:System.Windows.Navigation.NavigationService.GoBack%2A>

- <xref:System.Windows.Navigation.NavigationService.GoForward%2A>

- <xref:System.Windows.Navigation.NavigationService.CanGoBack%2A>

- <xref:System.Windows.Navigation.NavigationService.CanGoForward%2A>

El diario también se puede manipular mediante programación, como se describe en [retener el estado del contenido con el historial de navegación](#RetainingContentStateWithNavigationHistory) , más adelante en este tema.

<a name="PageLifetime"></a>

### <a name="page-lifetime-and-the-journal"></a>Duración de la página y el diario

Considere una [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] con varias páginas que contienen contenido enriquecido, como gráficos, animaciones y elementos multimedia. La superficie de memoria de este tipo de páginas podría ser bastante grande, especialmente si se usan elementos multimedia de audio y vídeo. Dado que el diario "recuerda" las páginas a las que se ha navegado, tal [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] vez podría consumir rápidamente una cantidad de memoria grande y notable.

Por esta razón, el comportamiento predeterminado del diario es almacenar <xref:System.Windows.Controls.Page> los metadatos en cada entrada del diario en lugar de una referencia a un <xref:System.Windows.Controls.Page> objeto. Cuando se navega a una entrada del diario, sus <xref:System.Windows.Controls.Page> metadatos se utilizan para crear una nueva instancia del especificado <xref:System.Windows.Controls.Page>. Como consecuencia, cada <xref:System.Windows.Controls.Page> que se navega tiene la duración que se muestra en la ilustración siguiente.

![Duración] de la página (./media/navigation-overview/navigated-page-lifetime.png "Esto muestra la duración cuando se navega a una página.")

Aunque el uso del comportamiento de diario predeterminado puede ahorrar en el consumo de memoria, el rendimiento de la representación por página podría reducirse; la creación de instancias <xref:System.Windows.Controls.Page> de puede llevar mucho tiempo, especialmente si tiene una gran cantidad de contenido. Si necesita conservar una <xref:System.Windows.Controls.Page> instancia en el diario, puede dibujar dos técnicas para hacerlo. En primer lugar, puede navegar mediante programación a <xref:System.Windows.Controls.Page> un objeto llamando al <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> método.

<xref:System.Windows.Controls.Page> En segundo lugar, puede especificar [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] que conserve una instancia de en el diario estableciendo la <xref:System.Windows.Controls.Page.KeepAlive%2A> propiedad en `true` (el valor predeterminado `false`es). Como se muestra en el ejemplo siguiente, se puede <xref:System.Windows.Controls.Page.KeepAlive%2A> establecer mediante declaración en el marcado.

[!code-xaml[NavigationOverviewSnippets#KeepAlivePageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/KeepAlivePage.xaml#keepalivepagexaml)]

La duración de un <xref:System.Windows.Controls.Page> que se mantiene activo es ligeramente diferente de una que no lo es. La primera vez que <xref:System.Windows.Controls.Page> se navega a un al que se mantiene activo, se crea una instancia de tal <xref:System.Windows.Controls.Page> como un que no se mantiene activo. Sin embargo, dado que una instancia <xref:System.Windows.Controls.Page> de se conserva en el diario, nunca se vuelve a crear una instancia de, siempre y cuando permanezca en el diario. Por consiguiente, si una <xref:System.Windows.Controls.Page> tiene lógica de inicialización que debe llamarse cada <xref:System.Windows.Controls.Page> vez que se navega a, debe moverla del constructor a un controlador para el <xref:System.Windows.FrameworkElement.Loaded> evento. Como se muestra en la siguiente ilustración, <xref:System.Windows.FrameworkElement.Loaded> los <xref:System.Windows.FrameworkElement.Unloaded> eventos y se generan cada vez <xref:System.Windows.Controls.Page> que se navega a y desde, respectivamente.

![Cuando se producen los eventos Loaded y] Unloaded (./media/navigation-overview/loaded-and-unloaded-events.png "Los eventos cargados y descargados se producen cuando una página se navega hacia y desde.")

Cuando no <xref:System.Windows.Controls.Page> se mantiene activo, no se debe realizar una de las siguientes acciones:

- Almacenar una referencia a la base de datos ni ninguna parte de esta.

- Registrar controladores de eventos con eventos que no haya implementado.

<xref:System.Windows.Controls.Page> Al realizar cualquiera de estas acciones se crearán referencias que obligan a que se retenga en la memoria, incluso después de que se haya quitado del diario.

En general, debe preferir el comportamiento <xref:System.Windows.Controls.Page> predeterminado de no mantener un <xref:System.Windows.Controls.Page> activo. Sin embargo, esto conlleva implicaciones de estado que se describen en la sección siguiente.

<a name="RetainingContentStateWithNavigationHistory"></a>

### <a name="retaining-content-state-with-navigation-history"></a>Conservación del estado del contenido con el historial de navegación

Si un <xref:System.Windows.Controls.Page> no se mantiene activo y tiene controles que recopilan datos del usuario, ¿qué ocurre con los datos si un usuario se desplaza fuera de y vuelve <xref:System.Windows.Controls.Page>al? Desde la perspectiva de una experiencia de usuario, el usuario debería ver los datos que especificó anteriormente. Desafortunadamente, dado que <xref:System.Windows.Controls.Page> se crea una nueva instancia de con cada navegación, se vuelve a crear una instancia de los controles que recopilaron los datos y se pierden los datos.

Afortunadamente, el diario proporciona compatibilidad para recordar datos entre <xref:System.Windows.Controls.Page> navegaciones, incluidos los datos de control. En concreto, la entrada del diario <xref:System.Windows.Controls.Page> para cada una de ellas actúa como un <xref:System.Windows.Controls.Page> contenedor temporal para el estado asociado. En los pasos siguientes se describe cómo se usa esta compatibilidad <xref:System.Windows.Controls.Page> cuando se navega desde:

1. Una entrada para el actual <xref:System.Windows.Controls.Page> se agrega al diario.

2. El estado de <xref:System.Windows.Controls.Page> se almacena con la entrada de diario de esa página, que se agrega a la pila de retroceso.

3. Se navega <xref:System.Windows.Controls.Page> a la nueva.

Cuando se vuelve <xref:System.Windows.Controls.Page> a navegar a la página, con el diario, se llevan a cabo los siguientes pasos:

1. Se crea una instancia de (laentradadediariosuperiorenlapiladeretroceso).<xref:System.Windows.Controls.Page>

2. Se actualiza con el estado que se almacenó con la entrada <xref:System.Windows.Controls.Page>de diario para. <xref:System.Windows.Controls.Page>

3. <xref:System.Windows.Controls.Page> Se vuelve a navegar a.

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]usa automáticamente esta compatibilidad cuando se utilizan los siguientes controles en un <xref:System.Windows.Controls.Page>:

- <xref:System.Windows.Controls.CheckBox>

- <xref:System.Windows.Controls.ComboBox>

- <xref:System.Windows.Controls.Expander>

- <xref:System.Windows.Controls.Frame>

- <xref:System.Windows.Controls.ListBox>

- <xref:System.Windows.Controls.ListBoxItem>

- <xref:System.Windows.Controls.MenuItem>

- <xref:System.Windows.Controls.ProgressBar>

- <xref:System.Windows.Controls.RadioButton>

- <xref:System.Windows.Controls.Slider>

- <xref:System.Windows.Controls.TabControl>

- <xref:System.Windows.Controls.TabItem>

- <xref:System.Windows.Controls.TextBox>

Si usa estos controles, los datos que se escriben en ellos <xref:System.Windows.Controls.Page> se recuerdan entre las navegaciones, como muestra el **color** <xref:System.Windows.Controls.ListBox> favorito de la ilustración siguiente. <xref:System.Windows.Controls.Page>

![Página con controles que recuerdan el estado] Los (./media/navigation-overview/data-remembered-across-page-navigations.png "datos especificados se recuerdan en las navegaciones de páginas.")

Cuando un <xref:System.Windows.Controls.Page> tiene controles distintos de los de la lista anterior, o cuando el estado se almacena en objetos personalizados, debe escribir código para hacer que el diario recuerde el estado entre <xref:System.Windows.Controls.Page> las navegaciones.

Si necesita recordar pequeños fragmentos de estado a través <xref:System.Windows.Controls.Page> de las navegaciones, puede utilizar las propiedades de dependencia (vea <xref:System.Windows.DependencyProperty>) que están configuradas con la marca de <xref:System.Windows.FrameworkPropertyMetadata.Journal%2A?displayProperty=nameWithType> metadatos.

Si el estado que necesita <xref:System.Windows.Controls.Page> recordar entre las navegaciones consta de varios fragmentos de datos, es posible que se encuentre con menos código para encapsular el estado en una sola clase e implementar <xref:System.Windows.Navigation.IProvideCustomContentState> la interfaz.

Si necesita navegar por varios Estados <xref:System.Windows.Controls.Page>de una sola, sin navegar por el <xref:System.Windows.Controls.Page> mismo, puede usar <xref:System.Windows.Navigation.IProvideCustomContentState> y <xref:System.Windows.Navigation.NavigationService.AddBackEntry%2A?displayProperty=nameWithType>.

<a name="Cookies"></a>

### <a name="cookies"></a>Cookies

Otra forma en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] que las aplicaciones pueden almacenar datos es con las cookies, que se crean, actualizan y <xref:System.Windows.Application.SetCookie%2A> eliminan mediante los métodos y <xref:System.Windows.Application.GetCookie%2A> . Las cookies que se pueden crear [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] en son las mismas cookies que usan otros tipos de aplicaciones web; las cookies son fragmentos arbitrarios de datos almacenados por una aplicación en un equipo cliente durante o a través de sesiones de aplicación. Los datos de las cookies normalmente adoptan la forma de un par de nombre-valor en el formato siguiente.

*Name* `=` *Value*

Cuando los datos se pasan a <xref:System.Windows.Application.SetCookie%2A>, junto con el <xref:System.Uri> de la ubicación para la que se debe establecer la cookie, se crea una cookie en memoria y solo está disponible mientras dure la sesión de aplicación actual. Este tipo de cookie se conoce como cookie de *sesión*.

Para almacenar una cookie mediante sesiones de la aplicación, debe agregarse una fecha de expiración para la cookie, con el formato siguiente.

*NAME* `=` *VALUE* `; expires=DAY, DD-MMM-YYYY HH:MM:SS GMT`

Una cookie con una fecha de expiración se almacena en la carpeta de archivos temporales de Internet de la instalación actual de Windows hasta que expire la cookie. Este tipo de cookie se conoce como *cookie persistente* porque se conserva entre las sesiones de la aplicación.

Puede recuperar las cookies de sesión y persistentes <xref:System.Windows.Application.GetCookie%2A> llamando al método, <xref:System.Uri> pasando el de la ubicación donde se estableció la cookie <xref:System.Windows.Application.SetCookie%2A> con el método.

A continuación se muestran algunas de las formas en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]las que se admiten las cookies:

- [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]aplicaciones independientes y [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] pueden crear y administrar cookies.

- Se [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] puede tener acceso a las cookies creadas por desde el explorador.

- [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] del mismo dominio puede crear y compartir cookies.

- [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]y las páginas HTML del mismo dominio pueden crear y compartir cookies.

- Las cookies se envían cuando [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] y las [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] páginas sueltas realizan solicitudes Web.

- Tanto el nivel [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] superior como [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] el hospedado en los iframes pueden tener acceso a las cookies.

- La compatibilidad con [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] cookies en es la misma para todos los exploradores compatibles.

- En Internet Explorer, se respeta [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]la Directiva de P3P que pertenece a las cookies, especialmente con respecto a la primera entidad y a terceros. [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]

<a name="Structured_Navigation"></a>

### <a name="structured-navigation"></a>Navegación estructurada

Si necesita pasar datos de uno <xref:System.Windows.Controls.Page> a otro, puede pasar los datos como argumentos a un constructor sin parámetros <xref:System.Windows.Controls.Page>de. Tenga en cuenta que si utiliza esta técnica, debe mantener la <xref:System.Windows.Controls.Page> conexión activa; si no, la próxima vez que navegue a <xref:System.Windows.Controls.Page>la [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] , creará una <xref:System.Windows.Controls.Page> nueva instancia de mediante el constructor sin parámetros.

Como alternativa, <xref:System.Windows.Controls.Page> puede implementar propiedades que se establecen con los datos que es necesario pasar. Sin embargo, las cosas son complicadas, <xref:System.Windows.Controls.Page> cuando es necesario devolver los <xref:System.Windows.Controls.Page> datos al que se navegó a él. El problema es que la navegación no admite de <xref:System.Windows.Controls.Page> forma nativa mecanismos para garantizar que se devolverá a después de que se navegue desde. Esencialmente, la navegación no admite la semántica de llamada/devolución. Para solucionar este problema, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] proporciona la <xref:System.Windows.Navigation.PageFunction%601> clase que se puede utilizar para asegurarse de que <xref:System.Windows.Controls.Page> se devuelve un en un modo predecible y estructurado. Para obtener más información, vea [información general sobre la navegación estructurada](structured-navigation-overview.md).

<a name="The_NavigationWindow_Class"></a>

## <a name="the-navigationwindow-class"></a>Clase NavigationWindow

En este punto, ha visto la gama de servicios de navegación que probablemente usará para compilar aplicaciones con contenido navegable. Estos servicios se trataron en el contexto [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]de, aunque no se limitan [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]a. Los sistemas operativos modernos y las aplicaciones de Windows aprovechan la experiencia del explorador de los usuarios modernos para incorporar la navegación de estilo Explorador en aplicaciones independientes. Estos son algunos ejemplos comunes:

- **Diccionario de sinónimos de Word**: Navegar por las opciones de Word.

- **Explorador de archivos**: Navegue por los archivos y las carpetas.

- **Asistentes**: Dividir una tarea compleja en varias páginas a las que se puede navegar. Un ejemplo es el Asistente para componentes de Windows que controla la adición y eliminación de características de Windows.

Para incorporar la navegación de estilo explorador a las aplicaciones independientes, puede utilizar la <xref:System.Windows.Navigation.NavigationWindow> clase. <xref:System.Windows.Navigation.NavigationWindow>deriva de <xref:System.Windows.Window> y lo extiende con la misma compatibilidad para la navegación que [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] proporciona. Puede usar <xref:System.Windows.Navigation.NavigationWindow> como la ventana principal de la aplicación independiente o como una ventana secundaria, como un cuadro de diálogo.

Para implementar un <xref:System.Windows.Navigation.NavigationWindow>, al igual que con la mayoría de las [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] clases de <xref:System.Windows.Controls.Page>nivel superior de (<xref:System.Windows.Window>,, etc.), se usa una combinación de marcado y código subyacente. Esta implementación se muestra en el ejemplo siguiente.

[!code-xaml[IntroToNavNavigationWindowSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml#navigationwindowmarkup)]

[!code-csharp[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml.cs#navigationwindowcodebehind)]
[!code-vb[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/MainWindow.xaml.vb#navigationwindowcodebehind)]

Este código crea un <xref:System.Windows.Navigation.NavigationWindow> que navega automáticamente a un <xref:System.Windows.Controls.Page> (homepage <xref:System.Windows.Navigation.NavigationWindow> . xaml) cuando se abre. Si es la ventana principal de la aplicación, puede usar el `StartupUri` atributo para iniciarla. <xref:System.Windows.Navigation.NavigationWindow> Esto se muestra en la marcación siguiente.

[!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchNavWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/App.xaml#applaunchnavwindow)]

<xref:System.Windows.Navigation.NavigationWindow> En la ilustración siguiente se muestra como la ventana principal de una aplicación independiente.

![Una ventana principal](./media/navigation-overview/navigation-window-as-main-window.png "Ventana de navegación como ventana principal")

En la ilustración, puede ver que <xref:System.Windows.Navigation.NavigationWindow> tiene un título, aunque no se haya establecido en el <xref:System.Windows.Navigation.NavigationWindow> código de implementación del ejemplo anterior. En su lugar, el título se establece mediante <xref:System.Windows.Controls.Page.WindowTitle%2A> la propiedad, que se muestra en el código siguiente.

[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup1)]
[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup2)]

El establecimiento <xref:System.Windows.Controls.Page.WindowWidth%2A> de <xref:System.Windows.Controls.Page.WindowHeight%2A> las propiedades y también <xref:System.Windows.Navigation.NavigationWindow>afecta a.

Normalmente, se implementa el suyo <xref:System.Windows.Navigation.NavigationWindow> propio cuando sea necesario personalizar su comportamiento o su apariencia. Si no realiza nada, puede usar un acceso directo. Si especifica [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] el paquete <xref:System.Windows.Controls.Page> de como <xref:System.Windows.Application.StartupUri%2A> en una aplicación independiente, <xref:System.Windows.Application> crea automáticamente un <xref:System.Windows.Navigation.NavigationWindow> para hospedar el <xref:System.Windows.Controls.Page>. En la marcación siguiente se muestra cómo habilitar esta opción.

[!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchPage](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/AnotherApp.xaml#applaunchpage)]

Si desea que una ventana de aplicación secundaria, como un cuadro de diálogo, <xref:System.Windows.Navigation.NavigationWindow>sea una, puede usar el código del ejemplo siguiente para abrirla.

[!code-csharp[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/DialogOwnerWindow.xaml.cs#createnwdialogbox)]
[!code-vb[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/DialogOwnerWindow.xaml.vb#createnwdialogbox)]

En la siguiente ilustración se muestra el resultado.

![Un cuadro de diálogo](./media/navigation-overview/navigation-window-as-dialog-box.png "Ventana de navegación como un cuadro de diálogo")

Como puede ver, <xref:System.Windows.Navigation.NavigationWindow> muestra los botones **atrás** y **adelante** de estilo de Internet Explorer que permiten a los usuarios navegar por el diario. Estos botones proporcionan la misma experiencia de usuario, como se muestra en la ilustración siguiente.

![Botones atrás y adelante en NavigationWindow](./media/navigation-overview/back-and-forward-buttons-in-navigation-window.png "Botones atrás y adelante en una ventana de navegación")

Si las páginas proporcionan su propia compatibilidad y interfaz de usuario de navegación de diario, puede ocultar los <xref:System.Windows.Navigation.NavigationWindow> botones **atrás** y adelante que se muestran al establecer <xref:System.Windows.Navigation.NavigationWindow.ShowsNavigationUI%2A> el valor `false`de la propiedad en.

Como alternativa, puede usar la compatibilidad con la personalización en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] para reemplazar el <xref:System.Windows.Navigation.NavigationWindow> [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] del propio.

<a name="Frame_in_Standalone_Applications"></a>

## <a name="the-frame-class"></a>Clase Frame

Tanto el explorador como <xref:System.Windows.Navigation.NavigationWindow> las ventanas que hospedan contenido navegable. En algunos casos, las aplicaciones tienen contenido que no hace falta que los hospede una ventana completa. En su lugar, dicho contenido se hospeda dentro de otro contenido. Puede insertar contenido navegable en otro contenido mediante la <xref:System.Windows.Controls.Frame> clase. <xref:System.Windows.Controls.Frame>proporciona la misma compatibilidad que <xref:System.Windows.Navigation.NavigationWindow> y [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].

En el ejemplo siguiente se muestra cómo agregar <xref:System.Windows.Controls.Frame> un <xref:System.Windows.Controls.Page> a mediante declaración mediante el `Frame` elemento.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml3)]

Este marcado establece el `Source` atributo `Frame` del elemento con un <xref:System.Windows.Controls.Frame> Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para el <xref:System.Windows.Controls.Page> al que debe navegar inicialmente. En la ilustración siguiente se [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] muestra un <xref:System.Windows.Controls.Page> con un que <xref:System.Windows.Controls.Frame> tiene un que ha navegado entre varias páginas.

![Marco que ha navegado entre varias páginas](./media/navigation-overview/frame-navigation-between-multiple-pages.png "Esto muestra una navegación de fotogramas entre varias páginas.")

No solo tiene que usar <xref:System.Windows.Controls.Frame> dentro del contenido <xref:System.Windows.Controls.Page>de. También es común hospedar un <xref:System.Windows.Controls.Frame> dentro del contenido <xref:System.Windows.Window>de.

De forma predeterminada <xref:System.Windows.Controls.Frame> , solo utiliza su propio diario en ausencia de otro diario. Si una <xref:System.Windows.Controls.Frame> forma parte del contenido que se hospeda en <xref:System.Windows.Navigation.NavigationWindow> o [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]en <xref:System.Windows.Navigation.NavigationWindow> , <xref:System.Windows.Controls.Frame> utiliza el diario que pertenece a o [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. A veces, sin embargo <xref:System.Windows.Controls.Frame> , es posible que deba ser responsable de su propio diario. Una razón para hacerlo es permitir la navegación del diario dentro de las páginas hospedadas por <xref:System.Windows.Controls.Frame>. Esto se muestra en la ilustración siguiente.

![Diagrama de marco y de página](./media/navigation-overview/journal-navigation-within-pages-hosted-by-a-frame.png "Esto muestra la navegación del diario dentro de las páginas hospedadas por un marco.")

En este caso <xref:System.Windows.Controls.Frame> , puede configurar para que use su propio diario estableciendo la <xref:System.Windows.Controls.Frame.JournalOwnership%2A> propiedad de <xref:System.Windows.Controls.Frame> en <xref:System.Windows.Navigation.JournalOwnership.OwnsJournal>. Esto se muestra en la marcación siguiente.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml3)]

En la ilustración siguiente se muestra el efecto de navegar dentro de <xref:System.Windows.Controls.Frame> un que usa su propio diario.

![Marco que usa su propio diario](./media/navigation-overview/frame-uses-its-own-journal.png "Esto muestra el efecto de navegar dentro de un marco que usa su propio diario.")

[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Tenga<xref:System.Windows.Controls.Frame>en cuenta que las entradas del diario se muestran en la navegación en, en lugar de en Internet Explorer.

> [!NOTE]
> Si una <xref:System.Windows.Controls.Frame> forma parte del contenido que se hospeda en un <xref:System.Windows.Window>, <xref:System.Windows.Controls.Frame> utiliza su propio diario y, por consiguiente, muestra su propia navegación [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].

Si la experiencia del usuario requiere <xref:System.Windows.Controls.Frame> un para proporcionar su propio diario sin mostrar la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]navegación, puede ocultar la navegación [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] estableciendo el <xref:System.Windows.Controls.Frame.NavigationUIVisibility%2A> en <xref:System.Windows.Visibility.Hidden>. Esto se muestra en la marcación siguiente.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml3)]

<a name="Navigation_Hosts"></a>

## <a name="navigation-hosts"></a>Hosts de navegación

<xref:System.Windows.Controls.Frame>y <xref:System.Windows.Navigation.NavigationWindow> son clases que se conocen como hosts de navegación. Un *host de navegación* es una clase que puede navegar y mostrar el contenido. Para ello, cada host de navegación utiliza su propio <xref:System.Windows.Navigation.NavigationService> y Journal. La construcción de un host de navegación básica se muestra en la ilustración siguiente.

![Diagramas de navegador](./media/navigation-overview/navigation-host-construction.png "Construcción básica de un host de navegación")

En esencia, esto <xref:System.Windows.Navigation.NavigationWindow> permite <xref:System.Windows.Controls.Frame> que y proporcionen la [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] misma compatibilidad de navegación que proporciona cuando se hospeda en el explorador.

Además de <xref:System.Windows.Navigation.NavigationService> usar y un diario, los hosts de navegación implementan los mismos miembros que <xref:System.Windows.Navigation.NavigationService> implementan. Esto se muestra en la ilustración siguiente.

![Un diario en un marco y en NavigationWindow](./media/navigation-overview/navigation-window-and-frame.png "Ventana de navegación y marco")

Esto le permite programar la compatibilidad con la navegación directamente con ellos. Puede considerar esto si necesita proporcionar una navegación [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] personalizada para un <xref:System.Windows.Controls.Frame> <xref:System.Windows.Window>que se hospeda en. Además, ambos tipos implementan miembros adicionales relacionados con la navegación, `BackStack` incluidos<xref:System.Windows.Navigation.NavigationWindow.BackStack%2A?displayProperty=nameWithType>( <xref:System.Windows.Controls.Frame.BackStack%2A?displayProperty=nameWithType>,) `ForwardStack` y<xref:System.Windows.Navigation.NavigationWindow.ForwardStack%2A?displayProperty=nameWithType>( <xref:System.Windows.Controls.Frame.ForwardStack%2A?displayProperty=nameWithType>,), que le permiten enumerar las entradas del diario en la parte posterior. pila y pila de reenvío, respectivamente.

Como se mencionó anteriormente, pueden haber varios diarios dentro de una aplicación. En la siguiente ilustración se muestra un ejemplo de cuándo ocurre esto.

![Varios diarios dentro de una aplicación](./media/navigation-overview/multiple-journals-in-one-application.png "Este es un ejemplo de más de un diario en una aplicación.")

<a name="Navigating_to_Content_Other_than_Pages"></a>

## <a name="navigating-to-content-other-than-xaml-pages"></a>Navegar a contenido distinto de páginas XAML

En este tema, <xref:System.Windows.Controls.Page> y pack [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] se han utilizado para mostrar las diversas capacidades de navegación [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]de. Sin embargo, <xref:System.Windows.Controls.Page> un que se compila en una aplicación no es el único tipo de contenido al que se puede navegar y el módulo [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] no es la única manera de identificar el contenido.

Como se muestra en esta sección, también puede navegar a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivos dinámicos, archivos HTML y objetos.

<a name="Navigating_to_Loose_XAML_Files"></a>

### <a name="navigating-to-loose-xaml-files"></a>Navegación por archivos XAML dinámicos

Un archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dinámico es un archivo con las siguientes características:

- Solo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] contiene (es decir, ningún código).

- Tiene una declaración de espacio de nombres adecuada.

- Tiene la extensión de nombre de archivo .xaml.

Por ejemplo, considere el siguiente contenido que se almacena como un archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] suelto, Person. Xaml.

[!code-xaml[NavigationOverviewSnippets#LooseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Person.xaml#loosexaml)]

Al hacer doble clic en el archivo, el explorador se abre y se desplaza al contenido y lo muestra. Esto se muestra en la siguiente ilustración.

![Presentación del contenido en el archivo person. Xaml](./media/navigation-overview/contents-of-person-xaml-file.png "Muestra el contenido del archivo person. Xaml.")

Puede mostrar un archivo suelto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] a partir de lo siguiente:

- Un sitio web en la máquina local, la intranet o Internet.

- Un [!INCLUDE[TLA#tla_unc](../../../../includes/tlasharptla-unc-md.md)] recurso compartido de archivos.

- El disco local.

Se puede [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] agregar un archivo dinámico a los favoritos del explorador o ser la Página principal del explorador.

> [!NOTE]
> Para obtener más información sobre la publicación y [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] el inicio de páginas sueltas, vea [implementar una aplicación de WPF](deploying-a-wpf-application-wpf.md).

Una limitación en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] lo que se refiere a la imparcialidad es que solo se puede hospedar contenido seguro para ejecutarse en confianza parcial. Por ejemplo, `Window` no puede ser el elemento raíz de un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo dinámico. Para obtener más información, vea [Seguridad de confianza parcial de WPF](../wpf-partial-trust-security.md).

<a name="Navigating_to_HTML_Files_Using_Frame"></a>

### <a name="navigating-to-html-files-by-using-frame"></a>Navegación a archivos HTML mediante Frame

Como cabría esperar, también puede navegar a HTML. Solo tiene que proporcionar un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que use el esquema http. Por ejemplo, a continuación [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se muestra <xref:System.Windows.Controls.Frame> un que navega a una página HTML.

[!code-xaml[NavigationOverviewSnippets#FrameHtmlNavMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHTMLNavPage.xaml#framehtmlnavmarkup)]

La navegación a HTML requiere permisos especiales. Por ejemplo, no se puede navegar desde [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] un que se ejecuta en el espacio aislado de seguridad de confianza parcial de zona de Internet. Para obtener más información, vea [Seguridad de confianza parcial de WPF](../wpf-partial-trust-security.md).

<a name="Navigating_to_HTML_Files_Using_WebBrowser"></a>

### <a name="navigating-to-html-files-by-using-the-webbrowser-control"></a>Navegación a archivos HTML mediante el Control WebBrowser

El <xref:System.Windows.Controls.WebBrowser> control admite la interoperabilidad de hospedaje de documentos HTML, navegación y script/código administrado. Para obtener información detallada sobre <xref:System.Windows.Controls.WebBrowser> el control, <xref:System.Windows.Controls.WebBrowser>vea.

Al <xref:System.Windows.Controls.Frame>igual que, desplazarse <xref:System.Windows.Controls.WebBrowser> a HTML usando requiere permisos especiales. Por ejemplo, desde una aplicación de confianza parcial, solo puede navegar a HTML ubicado en el sitio de origen. Para obtener más información, vea [Seguridad de confianza parcial de WPF](../wpf-partial-trust-security.md).

<a name="Navigating_to_Objects"></a>

### <a name="navigating-to-custom-objects"></a>Navegación por objetos personalizados

Si tiene datos que se almacenan como objetos personalizados, una manera de mostrar los datos consiste en crear un <xref:System.Windows.Controls.Page> objeto con el contenido que está enlazado a esos objetos (consulte [información general sobre el enlace de datos](../data/data-binding-overview.md)). Si no necesita la sobrecarga de la creación de una página completa para mostrar los objetos, puede navegar directamente a ellos en su lugar.

Considere la `Person` clase que se implementa en el código siguiente.

[!code-csharp[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/Person.cs#personclasscode)]
[!code-vb[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/Person.vb#personclasscode)]

Para ir a ella, llame al <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A?displayProperty=nameWithType> método, tal y como se muestra en el código siguiente.

[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject1)]
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject2)]
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject3)]

[!code-csharp[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml.cs#pagethatnavstoobjectcodebehind)]
[!code-vb[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/HomePage.xaml.vb#pagethatnavstoobjectcodebehind)]

En la siguiente ilustración se muestra el resultado.

![Página que navega a una clase](./media/navigation-overview/page-navigates-to-an-object.png "Este es un ejemplo de una página que navega a un objeto.")

En esta ilustración, puede ver que no se muestra nada útil. De hecho, el valor que se muestra es el valor devuelto del `ToString` método para el objeto **Person** ; de forma predeterminada, este es el único valor [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] que puede usar para representar el objeto. Podría invalidar el `ToString` método para devolver información más significativa, aunque seguirá siendo solo un valor de cadena. Una técnica que se puede usar que aprovecha las capacidades de presentación de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] es usar una plantilla de datos. Puede implementar una plantilla de datos que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] se puede asociar a un objeto de un tipo determinado. En el código siguiente se muestra una plantilla de `Person` datos para el objeto.

[!code-xaml[NavigateToObjectSnippets#DataTemplateMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/App.xaml#datatemplatemarkup)]

En este caso, la plantilla de datos se `Person` asocia al tipo mediante `x:Type` la extensión de marcado `DataType` en el atributo. A continuación, la plantilla de `TextBlock` datos enlaza elementos <xref:System.Windows.Controls.TextBlock>(vea) a las propiedades `Person` de la clase. En la siguiente ilustración se muestra la apariencia actualizada `Person` del objeto.

![Desplazarse a una clase que tiene una plantilla de datos](./media/navigation-overview/navigating-to-a-class.png "Desplazarse a una clase que tiene una plantilla de datos.")

Una ventaja de esta técnica es la coherencia que obtiene al poder volver a usar la plantilla de datos para mostrar los objetos de forma coherente en cualquier parte de la aplicación.

Para obtener más información sobre las plantillas de datos, vea [información general sobre plantillas de datos](../data/data-templating-overview.md).

<a name="Security"></a>

## <a name="security"></a>Seguridad

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]la compatibilidad con [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] la navegación permite navegar a través de Internet y permite a las aplicaciones hospedar contenido de terceros. Para proteger tanto las aplicaciones como los usuarios del comportamiento [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] perjudicial, proporciona una variedad de características de seguridad que se describen en [seguridad](../security-wpf.md) y [seguridad de confianza parcial de WPF](../wpf-partial-trust-security.md).

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Application.SetCookie%2A>
- <xref:System.Windows.Application.GetCookie%2A>
- [Información general sobre la administración de aplicaciones](application-management-overview.md)
- [Identificadores URI de paquete en WPF](pack-uris-in-wpf.md)
- [Información general sobre la navegación estructurada](structured-navigation-overview.md)
- [Información general sobre topologías de navegación](navigation-topologies-overview.md)
- [Temas "Cómo..."](navigation-how-to-topics.md)
- [Implementar una aplicación WPF](deploying-a-wpf-application-wpf.md)

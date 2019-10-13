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
ms.openlocfilehash: 874bc0b1b0ac38210569632dc3d21ed727ae26e4
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291651"
---
# <a name="navigation-overview"></a>Información general sobre navegación

Windows Presentation Foundation (WPF) admite la navegación de estilo explorador que se puede usar en dos tipos de aplicaciones: aplicaciones independientes y [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]. Para empaquetar el contenido para la navegación, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] proporciona la clase <xref:System.Windows.Controls.Page>. Puede desplazarse de un <xref:System.Windows.Controls.Page> a otro mediante declaración, mediante el uso de un <xref:System.Windows.Documents.Hyperlink> o mediante programación, utilizando el <xref:System.Windows.Navigation.NavigationService>. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] usa el diario para recordar las páginas desde las que se navegó o para volver a ellas.

<xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Navigation.NavigationService> y el diario forman el núcleo de la compatibilidad de navegación que ofrece [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. En esta información general se exploran estas características en detalle antes de cubrir la compatibilidad con la navegación avanzada que incluye la navegación a archivos [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] sueltos, archivos HTML y objetos.

> [!NOTE]
> En este tema, el término "explorador" solo se refiere a los exploradores que pueden hospedar aplicaciones [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], que actualmente incluye Microsoft Internet Explorer y Firefox. Cuando solo un explorador determinado admite características específicas de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], se hace referencia a la versión del explorador.

## <a name="navigation-in-wpf-applications"></a>Navegación a aplicaciones para WPF

En este tema se proporciona información general sobre las funcionalidades de navegación clave en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Estas capacidades están disponibles para las aplicaciones independientes y [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], aunque en este tema se presentan en el contexto de un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].

> [!NOTE]
> En este tema no se explica cómo compilar e implementar [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]. Para obtener más información sobre [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], vea [información general sobre las aplicaciones de explorador XAML de WPF](wpf-xaml-browser-applications-overview.md).

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

En [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], puede desplazarse a varios tipos de contenido que incluyen objetos .NET Framework, objetos personalizados, valores de enumeración, controles de usuario, archivos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y archivos HTML. Sin embargo, descubrirá que la manera más común y cómoda de empaquetar el contenido es mediante <xref:System.Windows.Controls.Page>. Además, <xref:System.Windows.Controls.Page> implementa características específicas de la navegación para mejorar su apariencia y simplificar el desarrollo.

Con <xref:System.Windows.Controls.Page>, puede implementar mediante declaración una página navegable de contenido [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] mediante el uso de marcado como el siguiente.

[!code-xaml[NavigationOverviewSnippets#Page1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page1.xaml#page1xaml)]

Un <xref:System.Windows.Controls.Page> que se implementa en el marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] tiene @no__t 2 como su elemento raíz y requiere la declaración de espacio de nombres [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] @ no__t-4. El elemento `Page` incluye el contenido al que desea desplazarse y mostrarse. El contenido se agrega estableciendo el elemento de propiedad `Page.Content`, como se muestra en el marcado siguiente.

[!code-xaml[NavigationOverviewSnippets#Page2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page2.xaml#page2xaml)]

`Page.Content` solo puede contener un elemento secundario; en el ejemplo anterior, el contenido es una sola cadena, "Hello, Page!". En la práctica, normalmente usará un control de diseño como el elemento secundario (vea [diseño](../advanced/layout.md)) para contener y componer el contenido.

Los elementos secundarios de un elemento `Page` se consideran el contenido de un <xref:System.Windows.Controls.Page> y, por consiguiente, no es necesario utilizar la declaración explícita de @no__t 2. La marcación siguiente es el equivalente declarativo del ejemplo anterior.

[!code-xaml[NavigationOverviewSnippets#Page3XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page3.xaml#page3xaml)]

En este caso, `Page.Content` se establece automáticamente con los elementos secundarios del elemento `Page`. Para obtener más información, consulte [Modelo de contenido de WPF](../controls/wpf-content-model.md).

Un <xref:System.Windows.Controls.Page> de solo marcado es útil para mostrar el contenido. Sin embargo, un <xref:System.Windows.Controls.Page> también puede mostrar controles que permiten a los usuarios interactuar con la página, y pueden responder a la interacción del usuario controlando los eventos y llamando a la lógica de la aplicación. Un @no__t interactivo-0 se implementa mediante una combinación de marcado y código subyacente, como se muestra en el ejemplo siguiente.

[!code-xaml[XBAPAppDefSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml#homepagemarkup)]

[!code-csharp[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml.cs#homepagecodebehind)]
[!code-vb[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/HomePage.xaml.vb#homepagecodebehind)]

Para permitir que un archivo de marcación y un archivo de código subyacente funcionen juntos, se necesita la configuración siguiente:

- En el marcado, el elemento `Page` debe incluir el atributo `x:Class`. Cuando se compila la aplicación, la existencia de `x:Class` en el archivo de marcado hace que el motor de compilación de Microsoft (MSBuild) cree una clase `partial` que deriva de <xref:System.Windows.Controls.Page> y tiene el nombre especificado por el atributo `x:Class`. Esto requiere la adición de una declaración de espacio de nombres [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] para el esquema [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`). La clase `partial` generada implementa `InitializeComponent`, a la que se llama para registrar los eventos y establecer las propiedades que se implementan en el marcado.

- En el código subyacente, la clase debe ser una clase `partial` con el mismo nombre especificado por el atributo `x:Class` en el marcado y debe derivar de <xref:System.Windows.Controls.Page>. Esto permite asociar el archivo de código subyacente a la clase `partial` que se genera para el archivo de marcado cuando se compila la aplicación (consulte [compilar una aplicación de WPF](building-a-wpf-application-wpf.md)).

- En el código subyacente, la clase <xref:System.Windows.Controls.Page> debe implementar un constructor que llame al método `InitializeComponent`. `InitializeComponent` se implementa mediante la clase `partial` generada por el archivo de marcado para registrar eventos y establecer las propiedades que se definen en el marcado.

> [!NOTE]
> Cuando se agrega un nuevo <xref:System.Windows.Controls.Page> al proyecto con [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], el @no__t 2 se implementa mediante marcado y código subyacente, e incluye la configuración necesaria para crear la asociación entre el marcado y los archivos de código subyacente, como se describe aquí.

Una vez que tenga un <xref:System.Windows.Controls.Page>, puede desplazarse hasta él. Para especificar el primer <xref:System.Windows.Controls.Page> al que navega una aplicación, debe configurar el inicio <xref:System.Windows.Controls.Page>.

<a name="Configuring_a_Start_Page"></a>

### <a name="configuring-a-start-page"></a>Configuración de una página de inicio

[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] requieren que se hospede una determinada cantidad de infraestructuras de aplicaciones en un explorador. En [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], la clase <xref:System.Windows.Application> forma parte de una definición de aplicación que establece la infraestructura de aplicación necesaria (consulte [información general sobre la administración de aplicaciones](application-management-overview.md)).

Una definición de aplicación normalmente se implementa mediante el marcado y el código subyacente, con el archivo de marcado configurado como un elemento MSBuild @ no__t-0. La siguiente es una definición de aplicación para un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].

[!code-xaml[XBAPAppDefSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]

[!code-csharp[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml.cs#xbapapplicationdefinitioncodebehind)]
[!code-vb[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/Application.xaml.vb#xbapapplicationdefinitioncodebehind)]

Un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] puede utilizar su definición de aplicación para especificar un inicio <xref:System.Windows.Controls.Page>, que es el @no__t 2 que se carga automáticamente cuando se inicia el [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. Para ello, establezca la propiedad <xref:System.Windows.Application.StartupUri%2A> con el [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] para el @no__t deseado.

> [!NOTE]
> En la mayoría de los casos, el <xref:System.Windows.Controls.Page> se compila en una aplicación o se implementa con ella. En estos casos, el [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que identifica un <xref:System.Windows.Controls.Page> es un Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], que es un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que se ajusta al esquema del *paquete* . Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] se describen con más detalle en [pack uri en WPF](pack-uris-in-wpf.md). También puede navegar al contenido con el esquema HTTP, que se describe a continuación.

Puede establecer <xref:System.Windows.Application.StartupUri%2A> mediante declaración en el marcado, tal como se muestra en el ejemplo siguiente.

[!code-xaml[NavigationOverviewSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]

En este ejemplo, el atributo `StartupUri` se establece con un Pack relativo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que identifica HomePage. Xaml. Cuando se inicia el [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], HomePage. XAML se visita y se muestra automáticamente. Esto se muestra en la siguiente ilustración, que muestra un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] que se inició desde un servidor Web.

![Página XBAP](./media/navigation-overview/xbap-launched-from-a-web-server.png "se muestra una aplicación XBAP iniciada desde un servidor Web.")

> [!NOTE]
> Para obtener más información sobre el desarrollo y la implementación de [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], vea [información general sobre las aplicaciones de explorador XAML de WPF](wpf-xaml-browser-applications-overview.md) e [implementar una aplicación de WPF](deploying-a-wpf-application-wpf.md).

<a name="ConfiguringAXAMLPage"></a>

### <a name="configuring-the-host-windows-title-width-and-height"></a>Configuración del título, el ancho y el alto de la ventana host

Una cosa que puede haber observado en la ilustración anterior es que el título del explorador y del panel de pestañas sea el [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para el [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. Además de largo, el título no es atractivo ni informativo. Por esta razón, <xref:System.Windows.Controls.Page> ofrece una forma de cambiar el título estableciendo la propiedad <xref:System.Windows.Controls.Page.WindowTitle%2A>. Además, puede configurar el ancho y el alto de la ventana del explorador estableciendo <xref:System.Windows.Controls.Page.WindowWidth%2A> y <xref:System.Windows.Controls.Page.WindowHeight%2A>, respectivamente.

<xref:System.Windows.Controls.Page.WindowTitle%2A>, <xref:System.Windows.Controls.Page.WindowWidth%2A> y <xref:System.Windows.Controls.Page.WindowHeight%2A> se pueden establecer mediante declaración en el marcado, tal y como se muestra en el ejemplo siguiente.

[!code-xaml[NavigationOverviewSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/HomePage.xaml#homepagemarkup)]

El resultado se muestra en la ilustración siguiente.

![Título de la ventana, alto y ancho](./media/navigation-overview/window-title-width-height.png "muestra el título, el alto y el ancho de la ventana que puede configurar.")

<a name="NavigatingBetweenXAMLPages"></a>

### <a name="hyperlink-navigation"></a>Navegación por hipervínculos

Un @no__t típico-0 consta de varias páginas. La manera más sencilla de desplazarse de una página a otra consiste en usar un <xref:System.Windows.Documents.Hyperlink>. Puede agregar mediante declaración un <xref:System.Windows.Documents.Hyperlink> a un <xref:System.Windows.Controls.Page> mediante el uso del elemento `Hyperlink`, que se muestra en el marcado siguiente.

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

Un elemento `Hyperlink` requiere lo siguiente:

- Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] del <xref:System.Windows.Controls.Page> al que desplazarse, según especifica el atributo `NavigateUri`.

- Contenido en el que un usuario puede hacer clic para iniciar la navegación, como texto e imágenes (para el contenido que puede contener el elemento `Hyperlink`, consulte <xref:System.Windows.Documents.Hyperlink>).

En la ilustración siguiente se muestra un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] con un <xref:System.Windows.Controls.Page> que tiene <xref:System.Windows.Documents.Hyperlink>.

![Página con hipervínculo](./media/navigation-overview/xbap-with-a-page-with-a-hyperlink.png "muestra una aplicación XBAP con una página con un hipervínculo.")

Como cabría esperar, al hacer clic en el <xref:System.Windows.Documents.Hyperlink>, el [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] se desplaza hasta el @no__t 2 que se identifica mediante el atributo `NavigateUri`. Además, el [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] agrega una entrada para el <xref:System.Windows.Controls.Page> anterior a la lista de páginas recientes en Internet Explorer. Esto se muestra en la siguiente ilustración.

![Botones atrás y adelante](./media/navigation-overview/back-and-forward-navigation.png "navegue con los botones atrás y adelante.")

Además de admitir la navegación de un <xref:System.Windows.Controls.Page> a otro, <xref:System.Windows.Documents.Hyperlink> también admite la navegación por fragmentos.

<a name="FragmentNavigation"></a>

### <a name="fragment-navigation"></a>Navegación por fragmentos

La *navegación por fragmentos* es la navegación a un fragmento de contenido en el @no__t actual-1 u otro <xref:System.Windows.Controls.Page>. En [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], un fragmento de contenido es el contenido incluido en un elemento con nombre. Un elemento con nombre es un elemento que tiene el conjunto de atributos `Name`. En el marcado siguiente se muestra un elemento con nombre `TextBlock` que contiene un fragmento de contenido.

[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup1)]
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup2)]
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup3)]

Para que un <xref:System.Windows.Documents.Hyperlink> navegue a un fragmento de contenido, el atributo `NavigateUri` debe incluir lo siguiente:

- @No__t-0 del <xref:System.Windows.Controls.Page> con el fragmento de contenido al que se va a navegar.

- Un carácter "#".

- Nombre del elemento del <xref:System.Windows.Controls.Page> que contiene el fragmento de contenido.

Un fragmento [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] tiene el formato siguiente.

*PageURI* `#` *ElementName*

A continuación se muestra un ejemplo de una `Hyperlink` que está configurada para desplazarse a un fragmento de contenido.

[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml1)]
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml2)]
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml3)]

> [!NOTE]
> En esta sección se describe la implementación de navegación por fragmentos predeterminada en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] también le permite implementar su propio esquema de navegación por fragmentos, que, en parte, requiere el control del evento <xref:System.Windows.Navigation.NavigationService.FragmentNavigation?displayProperty=nameWithType>.

> [!IMPORTANT]
> Puede desplazarse a los fragmentos en páginas [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sueltos (archivos de solo marcado [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] con `Page` como elemento raíz) solo si las páginas se pueden examinar a través de HTTP.
>
> Sin embargo, una página suelta [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] puede desplazarse a sus propios fragmentos.

<a name="NavigationService"></a>

### <a name="navigation-service"></a>Servicio de navegación

Aunque <xref:System.Windows.Documents.Hyperlink> permite que un usuario inicie la navegación a un @no__t determinado-1, la clase <xref:System.Windows.Navigation.NavigationService> realiza el trabajo de búsqueda y descarga de la página. Esencialmente, <xref:System.Windows.Navigation.NavigationService> proporciona la capacidad de procesar una solicitud de navegación en nombre del código de cliente, como el <xref:System.Windows.Documents.Hyperlink>. Además, <xref:System.Windows.Navigation.NavigationService> implementa una compatibilidad de nivel superior para realizar el seguimiento e influir en una solicitud de navegación.

Cuando se hace clic en <xref:System.Windows.Documents.Hyperlink>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] llama a @no__t 2 para buscar y descargar <xref:System.Windows.Controls.Page> en el paquete especificado [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]. El @no__t descargado-0 se convierte en un árbol de objetos cuyo objeto raíz es una instancia del @no__t descargado-1. Una referencia al objeto raíz <xref:System.Windows.Controls.Page> se almacena en la propiedad <xref:System.Windows.Navigation.NavigationService.Content%2A?displayProperty=nameWithType>. El Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para el contenido al que se navegó se almacena en la propiedad <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType>, mientras que el @no__t 2 almacena el paquete [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para la última página a la que se navegó.

> [!NOTE]
> Es posible que una aplicación [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] tenga más de una actualmente activa <xref:System.Windows.Navigation.NavigationService>. Para obtener más información, vea [hosts de navegación](#Navigation_Hosts) más adelante en este tema.

<a name="Programmatic_Navigation_with_the_Navigation_Service"></a>

### <a name="programmatic-navigation-with-the-navigation-service"></a>Navegación programática con el servicio de navegación

No es necesario conocer <xref:System.Windows.Navigation.NavigationService> si la navegación se implementa mediante declaración en el marcado mediante <xref:System.Windows.Documents.Hyperlink>, ya que <xref:System.Windows.Documents.Hyperlink> usa el <xref:System.Windows.Navigation.NavigationService> en su nombre. Esto significa que, siempre que el elemento primario directo o indirecto de un <xref:System.Windows.Documents.Hyperlink> sea un host de navegación (consulte [hosts de navegación](#Navigation_Hosts)), <xref:System.Windows.Documents.Hyperlink> podrá encontrar y usar el servicio de navegación del host de navegación para procesar una solicitud de navegación.

Sin embargo, hay situaciones en las que es necesario usar <xref:System.Windows.Navigation.NavigationService> directamente, entre las que se incluyen las siguientes:

- Cuando necesite crear una instancia de un <xref:System.Windows.Controls.Page> mediante un constructor sin parámetros.

- Cuando necesite establecer propiedades en el <xref:System.Windows.Controls.Page> antes de navegar a ella.

- Cuando el <xref:System.Windows.Controls.Page> al que es necesario navegar hasta solo se puede determinar en tiempo de ejecución.

En estas situaciones, debe escribir código para iniciar la navegación mediante programación llamando al método <xref:System.Windows.Navigation.NavigationService.Navigate%2A> del objeto <xref:System.Windows.Navigation.NavigationService>. Esto requiere obtener una referencia a un <xref:System.Windows.Navigation.NavigationService>.

#### <a name="getting-a-reference-to-the-navigationservice"></a>Obtención de una referencia a NavigationService

Por motivos que se describen en la sección [Hosts de navegación](#Navigation_Hosts), una aplicación [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] puede tener más de una <xref:System.Windows.Navigation.NavigationService>. Esto significa que el código necesita una manera de buscar un <xref:System.Windows.Navigation.NavigationService>, que suele ser el <xref:System.Windows.Navigation.NavigationService> que navegó al @no__t actual-2. Puede obtener una referencia a un <xref:System.Windows.Navigation.NavigationService> llamando al método `static` @ no__t-2. Para obtener el <xref:System.Windows.Navigation.NavigationService> que ha navegado a un @no__t determinado-1, debe pasar una referencia a <xref:System.Windows.Controls.Page> como argumento del método <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A>. En el código siguiente se muestra cómo obtener el <xref:System.Windows.Navigation.NavigationService> para el @no__t actual-1.

[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind1)]
[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPage.xaml.vb#getnscodebehind2)]

Como método abreviado para buscar el <xref:System.Windows.Navigation.NavigationService> para un <xref:System.Windows.Controls.Page>, <xref:System.Windows.Controls.Page> implementa la propiedad <xref:System.Windows.Controls.Page.NavigationService%2A>. Esta implementación se muestra en el ejemplo siguiente.

[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind1)]
[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPageShortCut.xaml.vb#getnsshortcutcodebehind2)]

> [!NOTE]
> Un <xref:System.Windows.Controls.Page> solo puede obtener una referencia a su <xref:System.Windows.Navigation.NavigationService> cuando <xref:System.Windows.Controls.Page> provoca el evento <xref:System.Windows.FrameworkElement.Loaded>.

#### <a name="programmatic-navigation-to-a-page-object"></a>Navegación programática a un objeto de página

En el ejemplo siguiente se muestra cómo utilizar el <xref:System.Windows.Navigation.NavigationService> para navegar mediante programación a un <xref:System.Windows.Controls.Page>. La navegación mediante programación es necesaria porque solo se puede crear una instancia de la <xref:System.Windows.Controls.Page> a la que se navega mediante un solo constructor sin parámetros. El <xref:System.Windows.Controls.Page> con el constructor sin parámetros se muestra en el marcado y el código siguientes.

[!code-xaml[NavigationOverviewSnippets#PageWithNonDefaultConstructorXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml#pagewithnondefaultconstructorxaml)]

[!code-csharp[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml.cs#pagewithnondefaultconstructorcodebehind)]
[!code-vb[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithNonDefaultConstructor.xaml.vb#pagewithnondefaultconstructorcodebehind)]

El <xref:System.Windows.Controls.Page> que navega al <xref:System.Windows.Controls.Page> con el constructor sin parámetros se muestra en el marcado y el código siguientes.

[!code-xaml[NavigationOverviewSnippets#NSNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml#nsnavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml.cs#nsnavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSNavigationPage.xaml.vb#nsnavigationpagecodebehind)]

Cuando se hace clic en <xref:System.Windows.Documents.Hyperlink> en este <xref:System.Windows.Controls.Page>, la navegación se inicia creando una instancia de la <xref:System.Windows.Controls.Page> para navegar hasta usar el constructor sin parámetros y llamar al método <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType>. <xref:System.Windows.Navigation.NavigationService.Navigate%2A> acepta una referencia al objeto al que se va a desplazar el <xref:System.Windows.Navigation.NavigationService>, en lugar de un Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].

#### <a name="programmatic-navigation-with-a-pack-uri"></a>Navegación programática con Pack URI

Si necesita crear un paquete [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] mediante programación (cuando solo puede determinar el Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] en tiempo de ejecución, por ejemplo), puede usar el método <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType>. Esta implementación se muestra en el ejemplo siguiente.

[!code-xaml[NavigationOverviewSnippets#NSUriNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml#nsurinavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml.cs#nsurinavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSUriNavigationPage.xaml.vb#nsurinavigationpagecodebehind)]

#### <a name="refreshing-the-current-page"></a>Actualización de la página actual

No se descarga <xref:System.Windows.Controls.Page> si tiene el mismo Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que el Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que se almacena en la propiedad <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType>. Para forzar que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Descargue la página actual de nuevo, puede llamar al método <xref:System.Windows.Navigation.NavigationService.Refresh%2A?displayProperty=nameWithType>, como se muestra en el ejemplo siguiente.

[!code-xaml[NavigationOverviewSnippets#NSRefreshNavigationPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml#nsrefreshnavigationpagexaml1)]

[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind1)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind1)]
[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind2)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind2)]

<a name="Navigation_Lifetime"></a>

### <a name="navigation-lifetime"></a>Duración de la navegación

Hay muchas maneras de iniciar la navegación, tal como ha podido ver. Cuando se inicia la navegación y mientras la navegación está en curso, puede realizar un seguimiento e influir en la navegación usando los siguientes eventos implementados por <xref:System.Windows.Navigation.NavigationService>:

- <xref:System.Windows.Navigation.NavigationService.Navigating> Se produce cuando se solicita una nueva navegación. Puede utilizarse para cancelar la navegación.

- <xref:System.Windows.Navigation.NavigationService.NavigationProgress> Se produce periódicamente durante una descarga y ofrece información sobre el progreso de la exploración.

- <xref:System.Windows.Navigation.NavigationService.Navigated> Se produce cuando se ha encontrado la página y se ha descargado.

- <xref:System.Windows.Navigation.NavigationService.NavigationStopped> Se produce cuando se detiene la navegación (llamando a <xref:System.Windows.Navigation.NavigationService.StopLoading%2A>) o cuando se solicita una nueva navegación mientras está en curso una navegación actual.

- <xref:System.Windows.Navigation.NavigationService.NavigationFailed> Se produce cuando se genera un error mientras se navega por el contenido solicitado.

- <xref:System.Windows.Navigation.NavigationService.LoadCompleted> Se produce cuando el contenido al que se navegó se carga y se analiza, y empieza a representarse.

- <xref:System.Windows.Navigation.NavigationService.FragmentNavigation> Se produce cuando se inicia la navegación a un fragmento de contenido, cosa que tiene lugar:

  - Inmediatamente, si el fragmento deseado está en el contenido actual.

  - Una vez se ha cargado el contenido de origen, si el fragmento deseado está en otro contenido.

Los eventos de navegación se generan en el orden que se muestra en la ilustración siguiente.

(./media/navigation-overview/order-of-navigation-events.png "Gráfico de flujo de eventos de navegación") de página del gráfico de flujo de navegación de ![páginas]

En general, un <xref:System.Windows.Controls.Page> no se preocupa de estos eventos. Es más probable que una aplicación esté relacionada con ellos y, por ese motivo, estos eventos también se generan mediante la clase <xref:System.Windows.Application>:

- <xref:System.Windows.Application.Navigating?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationProgress?displayProperty=nameWithType>

- <xref:System.Windows.Application.Navigated?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationFailed?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationStopped?displayProperty=nameWithType>

- <xref:System.Windows.Application.LoadCompleted?displayProperty=nameWithType>

- <xref:System.Windows.Application.FragmentNavigation?displayProperty=nameWithType>

Cada vez que <xref:System.Windows.Navigation.NavigationService> genera un evento, la clase <xref:System.Windows.Application> genera el evento correspondiente. <xref:System.Windows.Controls.Frame> y <xref:System.Windows.Navigation.NavigationWindow> ofrecen los mismos eventos para detectar la navegación dentro de sus respectivos ámbitos.

En algunos casos, un <xref:System.Windows.Controls.Page> podría estar interesado en estos eventos. Por ejemplo, un <xref:System.Windows.Controls.Page> podría controlar el evento <xref:System.Windows.Navigation.NavigationService.Navigating?displayProperty=nameWithType> para determinar si cancelar o no la navegación fuera de sí mismo. Esta implementación se muestra en el ejemplo siguiente.

[!code-xaml[NavigationOverviewSnippets#CancelNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml#cancelnavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml.cs#cancelnavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/CancelNavigationPage.xaml.vb#cancelnavigationpagecodebehind)]

Si registra un controlador con un evento de navegación de un <xref:System.Windows.Controls.Page>, como en el ejemplo anterior, también debe anular el registro del controlador de eventos. Si no lo hace, puede haber efectos secundarios con respecto a cómo la navegación [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] recuerda la navegación <xref:System.Windows.Controls.Page> mediante el diario.

<a name="NavigationHistory"></a>

### <a name="remembering-navigation-with-the-journal"></a>Registro de la navegación con el diario

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] usa dos pilas para recordar las páginas desde las que ha navegado: una pila de retroceso y una pila de avance. Al navegar desde el @no__t actual-0 a un nuevo <xref:System.Windows.Controls.Page> o reenviar a un @no__t 2 existente, el <xref:System.Windows.Controls.Page> actual se agrega a la *pila de retroceso*. Al navegar desde el @no__t actual-0 hasta el @no__t anterior-1, se agrega el @no__t 2 actual a la *pila de avance*. La pila de retroceso, la pila de avance y la funcionalidad para administrarlas se conocen en conjunto como el diario. Cada elemento de la pila de retroceso y la pila de avance es una instancia de la clase <xref:System.Windows.Navigation.JournalEntry> y se conoce como una *entrada de diario*.

#### <a name="navigating-the-journal-from-internet-explorer"></a>Navegación por el diario desde Internet Explorer

Conceptualmente, el diario funciona de la misma manera que los botones **atrás** y **adelante** de Internet Explorer. Esto se muestra en la siguiente ilustración.

![Botones atrás y adelante](./media/navigation-overview/back-and-forward-navigation.png "navegue con los botones atrás y adelante.")

En el caso de [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] que se hospedan en Internet Explorer, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] integra el diario en el @no__t de navegación 2 de Internet Explorer. Esto permite a los usuarios navegar por las páginas de un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] mediante los botones de páginas **atrás**, **adelante**y **recientes** de Internet Explorer.

> [!IMPORTANT]
> En Internet Explorer, cuando un usuario navega y vuelve a un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], solo se conservan en el diario las entradas de diario de las páginas que no se mantuvieron activas. Para obtener información sobre cómo mantener las páginas activas, vea [duración de la página y el diario](#PageLifetime) más adelante en este tema.

De forma predeterminada, el texto de cada <xref:System.Windows.Controls.Page> que aparece en la lista de **páginas recientes** de Internet Explorer es el [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para <xref:System.Windows.Controls.Page>. En muchos casos, esto no es especialmente significativo para el usuario. Afortunadamente, puede cambiar el texto mediante una de las siguientes opciones:

1. Valor del atributo `JournalEntry.Name` adjunto.

2. Valor del atributo `Page.Title`.

3. El valor del atributo `Page.WindowTitle` y el [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para el @no__t actual-2.

4. [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] de la <xref:System.Windows.Controls.Page> actual. (Predeterminado)

El orden en que se enumeran las opciones coincide con el orden de prioridad para buscar el texto. Por ejemplo, si se establece `JournalEntry.Name`, se omiten los demás valores.

En el ejemplo siguiente se usa el atributo `Page.Title` para cambiar el texto que aparece para una entrada del diario.

[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup1)]
[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup2)]

[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind1)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind1)]
[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind2)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind2)]

#### <a name="navigating-the-journal-using-wpf"></a>Navegación por el diario mediante WPF

Aunque un usuario puede navegar por el diario mediante las páginas **atrás**, **adelante**y **recientes** de Internet Explorer, también puede navegar por el diario utilizando los mecanismos declarativos y de programación proporcionados por [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Una razón para ello es proporcionar interfaces de IU de navegación personalizadas en las páginas.

Puede agregar mediante declaración la compatibilidad de navegación del diario mediante los comandos de navegación expuestos por <xref:System.Windows.Input.NavigationCommands>. En el ejemplo siguiente se muestra cómo usar el comando de navegación `BrowseBack`.

[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml1)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml2)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml3)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML4](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml4)]

Puede navegar por el diario mediante programación con uno de los siguientes miembros de la clase <xref:System.Windows.Navigation.NavigationService>:

- <xref:System.Windows.Navigation.NavigationService.GoBack%2A>

- <xref:System.Windows.Navigation.NavigationService.GoForward%2A>

- <xref:System.Windows.Navigation.NavigationService.CanGoBack%2A>

- <xref:System.Windows.Navigation.NavigationService.CanGoForward%2A>

El diario también se puede manipular mediante programación, como se describe en [retener el estado del contenido con el historial de navegación](#RetainingContentStateWithNavigationHistory) , más adelante en este tema.

<a name="PageLifetime"></a>

### <a name="page-lifetime-and-the-journal"></a>Duración de la página y el diario

Considere un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] con varias páginas que contienen contenido enriquecido, como gráficos, animaciones y elementos multimedia. La superficie de memoria de este tipo de páginas podría ser bastante grande, especialmente si se usan elementos multimedia de audio y vídeo. Dado que el diario "recuerda" las páginas a las que se ha navegado, este tipo de [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] podría consumir rápidamente una cantidad de memoria grande y notable.

Por esta razón, el comportamiento predeterminado del diario es almacenar los metadatos <xref:System.Windows.Controls.Page> en cada entrada del diario en lugar de una referencia a un objeto <xref:System.Windows.Controls.Page>. Cuando se navega a una entrada del diario, se usan sus metadatos <xref:System.Windows.Controls.Page> para crear una nueva instancia del <xref:System.Windows.Controls.Page> especificado. Como consecuencia, cada <xref:System.Windows.Controls.Page> a la que se navega tiene la duración que se muestra en la ilustración siguiente.

![Duración](./media/navigation-overview/navigated-page-lifetime.png "de la página muestra la duración cuando se navega a una página.")

Aunque el uso del comportamiento de diario predeterminado puede ahorrar en el consumo de memoria, el rendimiento de la representación por página podría reducirse; la creación de instancias de un <xref:System.Windows.Controls.Page> puede llevar mucho tiempo, especialmente si tiene una gran cantidad de contenido. Si necesita conservar una instancia de <xref:System.Windows.Controls.Page> en el diario, puede dibujar dos técnicas para hacerlo. En primer lugar, puede navegar mediante programación a un objeto <xref:System.Windows.Controls.Page> llamando al método <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType>.

En segundo lugar, puede especificar que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] conserve una instancia de <xref:System.Windows.Controls.Page> en el diario estableciendo la propiedad @no__t 2 en `true` (el valor predeterminado es `false`). Como se muestra en el ejemplo siguiente, puede establecer <xref:System.Windows.Controls.Page.KeepAlive%2A> mediante declaración en el marcado.

[!code-xaml[NavigationOverviewSnippets#KeepAlivePageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/KeepAlivePage.xaml#keepalivepagexaml)]

La duración de un <xref:System.Windows.Controls.Page> que se mantiene activo es ligeramente diferente de una que no lo es. La primera vez que se navega a un <xref:System.Windows.Controls.Page> que se mantiene activo, se crea una instancia como un <xref:System.Windows.Controls.Page> que no se mantiene activa. Sin embargo, dado que una instancia de <xref:System.Windows.Controls.Page> se conserva en el diario, nunca se vuelve a crear una instancia de, siempre y cuando permanezca en el diario. Por consiguiente, si un <xref:System.Windows.Controls.Page> tiene una lógica de inicialización que debe llamarse cada vez que se navega a <xref:System.Windows.Controls.Page>, debe moverla del constructor a un controlador para el evento <xref:System.Windows.FrameworkElement.Loaded>. Como se muestra en la ilustración siguiente, los eventos <xref:System.Windows.FrameworkElement.Loaded> y <xref:System.Windows.FrameworkElement.Unloaded> se siguen generando cada vez que se navega a un @no__t 2 y desde, respectivamente.

![Cuando se generan eventos cargados y descargados](./media/navigation-overview/loaded-and-unloaded-events.png ", y se generan eventos descargados cuando una página se navega hacia y desde.")

Cuando un <xref:System.Windows.Controls.Page> no se mantiene activo, no debe realizar ninguna de las siguientes acciones:

- Almacenar una referencia a la base de datos ni ninguna parte de esta.

- Registrar controladores de eventos con eventos que no haya implementado.

Al realizar cualquiera de estas acciones se crearán referencias que obligan a que el <xref:System.Windows.Controls.Page> se conserve en la memoria, incluso después de que se haya quitado del diario.

En general, se debe preferir el comportamiento predeterminado <xref:System.Windows.Controls.Page> de no mantener un <xref:System.Windows.Controls.Page> activo. Sin embargo, esto conlleva implicaciones de estado que se describen en la sección siguiente.

<a name="RetainingContentStateWithNavigationHistory"></a>

### <a name="retaining-content-state-with-navigation-history"></a>Conservación del estado del contenido con el historial de navegación

Si un <xref:System.Windows.Controls.Page> no se mantiene activo y tiene controles que recopilan datos del usuario, ¿qué ocurre con los datos si un usuario navega fuera de y vuelve al <xref:System.Windows.Controls.Page>? Desde la perspectiva de una experiencia de usuario, el usuario debería ver los datos que especificó anteriormente. Desafortunadamente, dado que se crea una nueva instancia del <xref:System.Windows.Controls.Page> con cada navegación, se vuelve a crear una instancia de los controles que recopilaron los datos y se pierden los datos.

Afortunadamente, el diario proporciona compatibilidad para recordar datos a través de las navegaciones de <xref:System.Windows.Controls.Page>, incluidos los datos de control. En concreto, la entrada de diario para cada <xref:System.Windows.Controls.Page> actúa como un contenedor temporal para el estado <xref:System.Windows.Controls.Page> asociado. En los pasos siguientes se describe cómo se usa esta compatibilidad cuando se navega desde <xref:System.Windows.Controls.Page>:

1. Se agrega una entrada para el @no__t actual-0 al diario.

2. El estado de la <xref:System.Windows.Controls.Page> se almacena con la entrada de diario de esa página, que se agrega a la pila de retroceso.

3. Se navega a la nueva <xref:System.Windows.Controls.Page>.

Cuando se vuelve a navegar a la página <xref:System.Windows.Controls.Page>, con el diario, se llevan a cabo los siguientes pasos:

1. Se crea una instancia del <xref:System.Windows.Controls.Page> (la entrada del diario superior en la pila de retroceso).

2. El <xref:System.Windows.Controls.Page> se actualiza con el estado que se almacenó con la entrada de diario para el <xref:System.Windows.Controls.Page>.

3. El <xref:System.Windows.Controls.Page> se vuelve a navegar a.

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] usa automáticamente esta compatibilidad cuando se utilizan los siguientes controles en un <xref:System.Windows.Controls.Page>:

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

Si un <xref:System.Windows.Controls.Page> usa estos controles, los datos que se escriben en ellos se recuerdan entre las navegaciones de <xref:System.Windows.Controls.Page>, tal y como se muestra en el **color favorito**<xref:System.Windows.Controls.ListBox> en la siguiente ilustración.

![Página con controles que recuerdan que los](./media/navigation-overview/data-remembered-across-page-navigations.png "datos de estado especificados se recuerdan en las navegaciones de páginas.")

Cuando un <xref:System.Windows.Controls.Page> tiene controles distintos de los de la lista anterior, o cuando el estado se almacena en objetos personalizados, debe escribir código para hacer que el diario recuerde el estado en las navegaciones de <xref:System.Windows.Controls.Page>.

Si necesita recordar pequeños fragmentos de estado a través de las navegaciones de <xref:System.Windows.Controls.Page>, puede usar las propiedades de dependencia (consulte <xref:System.Windows.DependencyProperty>) que están configuradas con la marca de metadatos <xref:System.Windows.FrameworkPropertyMetadata.Journal%2A?displayProperty=nameWithType>.

Si el estado que el <xref:System.Windows.Controls.Page> debe recordar entre las navegaciones consta de varios fragmentos de datos, puede que le resulte menos código para encapsular el estado en una sola clase e implementar la interfaz <xref:System.Windows.Navigation.IProvideCustomContentState>.

Si necesita navegar por varios Estados de un solo <xref:System.Windows.Controls.Page>, sin navegar por el <xref:System.Windows.Controls.Page>, puede usar <xref:System.Windows.Navigation.IProvideCustomContentState> y <xref:System.Windows.Navigation.NavigationService.AddBackEntry%2A?displayProperty=nameWithType>.

<a name="Cookies"></a>

### <a name="cookies"></a>Cookies

Otra forma en que las aplicaciones [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] pueden almacenar datos es con las cookies, que se crean, actualizan y eliminan mediante los métodos <xref:System.Windows.Application.SetCookie%2A> y <xref:System.Windows.Application.GetCookie%2A>. Las cookies que se pueden crear en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] son las mismas cookies que usan otros tipos de aplicaciones Web. las cookies son fragmentos arbitrarios de datos que se almacenan en una aplicación en un equipo cliente durante o a través de sesiones de aplicación. Los datos de las cookies normalmente adoptan la forma de un par de nombre-valor en el formato siguiente.

*Name* `=` *Value*

Cuando los datos se pasan a <xref:System.Windows.Application.SetCookie%2A>, junto con el <xref:System.Uri> de la ubicación para la que se debe establecer la cookie, se crea una cookie en memoria y solo está disponible mientras dure la sesión de aplicación actual. Este tipo de cookie se conoce como cookie de *sesión*.

Para almacenar una cookie mediante sesiones de la aplicación, debe agregarse una fecha de expiración para la cookie, con el formato siguiente.

*NAME* `=` *VALUE* `; expires=DAY, DD-MMM-YYYY HH:MM:SS GMT`

Una cookie con una fecha de expiración se almacena en la carpeta de archivos temporales de Internet de la instalación actual de Windows hasta que expire la cookie. Este tipo de cookie se conoce como *cookie persistente* porque se conserva entre las sesiones de la aplicación.

Puede recuperar las cookies de sesión y persistentes llamando al método <xref:System.Windows.Application.GetCookie%2A>, pasando el <xref:System.Uri> de la ubicación en la que se estableció la cookie con el método <xref:System.Windows.Application.SetCookie%2A>.

A continuación se muestran algunas de las formas en las que se admiten las cookies en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]:

- las aplicaciones independientes [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] y [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] pueden crear y administrar cookies.

- Se puede tener acceso a las cookies creadas por [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] desde el explorador.

- [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] del mismo dominio puede crear y compartir cookies.

- [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] y las páginas HTML del mismo dominio pueden crear y compartir cookies.

- Las cookies se envían cuando [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] y las páginas @no__t menos sueltas realizan solicitudes Web.

- Tanto @no__t de nivel superior-0 como [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] hospedados en IFRAMEs pueden tener acceso a las cookies.

- La compatibilidad con cookies en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] es la misma para todos los exploradores compatibles.

- En Internet Explorer, la Directiva de P3P que pertenece a las cookies se respeta en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], especialmente en lo que respecta a la primera entidad y a la de terceros [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].

<a name="Structured_Navigation"></a>

### <a name="structured-navigation"></a>Navegación estructurada

Si necesita pasar datos de un <xref:System.Windows.Controls.Page> a otro, puede pasar los datos como argumentos a un constructor sin parámetros del <xref:System.Windows.Controls.Page>. Tenga en cuenta que si utiliza esta técnica, debe mantener el <xref:System.Windows.Controls.Page> activo; Si no es así, la próxima vez que navegue al <xref:System.Windows.Controls.Page>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] vuelve a crear una instancia del <xref:System.Windows.Controls.Page> mediante el constructor sin parámetros.

Como alternativa, el <xref:System.Windows.Controls.Page> puede implementar propiedades que se establecen con los datos que es necesario pasar. Sin embargo, las cosas son complicadas cuando un <xref:System.Windows.Controls.Page> necesita devolver los datos al <xref:System.Windows.Controls.Page> que ha navegado a él. El problema es que la navegación no admite de forma nativa mecanismos para garantizar que se devolverá un <xref:System.Windows.Controls.Page> después de navegar desde. Esencialmente, la navegación no admite la semántica de llamada/devolución. Para solucionar este problema, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] proporciona la clase <xref:System.Windows.Navigation.PageFunction%601> que puede usar para asegurarse de que se devuelva un @no__t 2 a de un modo predecible y estructurado. Para obtener más información, vea [información general sobre la navegación estructurada](structured-navigation-overview.md).

<a name="The_NavigationWindow_Class"></a>

## <a name="the-navigationwindow-class"></a>Clase NavigationWindow

En este punto, ha visto la gama de servicios de navegación que probablemente usará para compilar aplicaciones con contenido navegable. Estos servicios se trataron en el contexto de [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], aunque no se limitan a [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]. Los sistemas operativos modernos y las aplicaciones de Windows aprovechan la experiencia del explorador de los usuarios modernos para incorporar la navegación de estilo Explorador en aplicaciones independientes. Estos son algunos ejemplos comunes:

- **Diccionario de sinónimos de Word**: Navegar por las opciones de Word.

- **Explorador de archivos**: Navegue por los archivos y las carpetas.

- **Asistentes**: Dividir una tarea compleja en varias páginas a las que se puede navegar. Un ejemplo es el Asistente para componentes de Windows que controla la adición y eliminación de características de Windows.

Para incorporar la navegación de estilo explorador a las aplicaciones independientes, puede usar la clase <xref:System.Windows.Navigation.NavigationWindow>. <xref:System.Windows.Navigation.NavigationWindow> deriva de <xref:System.Windows.Window> y lo extiende con la misma compatibilidad para la navegación que proporcionan [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]. Puede usar <xref:System.Windows.Navigation.NavigationWindow> como ventana principal de la aplicación independiente o como una ventana secundaria, como un cuadro de diálogo.

Para implementar un <xref:System.Windows.Navigation.NavigationWindow>, al igual que con la mayoría de las clases de nivel superior de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] (@no__t 2, <xref:System.Windows.Controls.Page>, etc.), se usa una combinación de marcado y código subyacente. Esta implementación se muestra en el ejemplo siguiente.

[!code-xaml[IntroToNavNavigationWindowSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml#navigationwindowmarkup)]

[!code-csharp[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml.cs#navigationwindowcodebehind)]
[!code-vb[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/MainWindow.xaml.vb#navigationwindowcodebehind)]

Este código crea un <xref:System.Windows.Navigation.NavigationWindow> que navega automáticamente a un <xref:System.Windows.Controls.Page> (HomePage. xaml) cuando se abre la <xref:System.Windows.Navigation.NavigationWindow>. Si el <xref:System.Windows.Navigation.NavigationWindow> es la ventana principal de la aplicación, puede usar el atributo `StartupUri` para iniciarla. Esto se muestra en la marcación siguiente.

[!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchNavWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/App.xaml#applaunchnavwindow)]

En la ilustración siguiente se muestra el <xref:System.Windows.Navigation.NavigationWindow> como la ventana principal de una aplicación independiente.

Ventana de navegación de la ![ventana principal](./media/navigation-overview/navigation-window-as-main-window.png "como ventana principal")

En la ilustración, puede ver que el <xref:System.Windows.Navigation.NavigationWindow> tiene un título, aunque no se haya establecido en el código de implementación de <xref:System.Windows.Navigation.NavigationWindow> del ejemplo anterior. En su lugar, el título se establece mediante la propiedad <xref:System.Windows.Controls.Page.WindowTitle%2A>, que se muestra en el código siguiente.

[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup1)]
[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup2)]

El establecimiento de las propiedades <xref:System.Windows.Controls.Page.WindowWidth%2A> y <xref:System.Windows.Controls.Page.WindowHeight%2A> también afecta al @no__t 2.

Normalmente, implemente su propio <xref:System.Windows.Navigation.NavigationWindow> cuando necesite personalizar su comportamiento o su apariencia. Si no realiza nada, puede usar un acceso directo. Si especifica el Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] de un <xref:System.Windows.Controls.Page> como @no__t 2 en una aplicación independiente, <xref:System.Windows.Application> crea automáticamente un <xref:System.Windows.Navigation.NavigationWindow> para hospedar el <xref:System.Windows.Controls.Page>. En la marcación siguiente se muestra cómo habilitar esta opción.

[!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchPage](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/AnotherApp.xaml#applaunchpage)]

Si desea que una ventana de la aplicación secundaria, como un cuadro de diálogo, sea una <xref:System.Windows.Navigation.NavigationWindow>, puede usar el código del ejemplo siguiente para abrirla.

[!code-csharp[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/DialogOwnerWindow.xaml.cs#createnwdialogbox)]
[!code-vb[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/DialogOwnerWindow.xaml.vb#createnwdialogbox)]

En la siguiente ilustración se muestra el resultado.

Ventana de navegación de ![un cuadro de diálogo](./media/navigation-overview/navigation-window-as-dialog-box.png "como un cuadro de diálogo")

Como puede ver, <xref:System.Windows.Navigation.NavigationWindow> muestra los botones **atrás** y **adelante** de estilo de Internet Explorer que permiten a los usuarios navegar por el diario. Estos botones proporcionan la misma experiencia de usuario, como se muestra en la ilustración siguiente.

![Botones atrás y adelante de un](./media/navigation-overview/back-and-forward-buttons-in-navigation-window.png "botón atrás y adelante de NavigationWindow en una ventana de navegación")

Si las páginas proporcionan su propia compatibilidad de navegación del diario y la interfaz de usuario, puede ocultar los botones **atrás** y **adelante** que se muestran en @no__t 2 estableciendo el valor de la propiedad <xref:System.Windows.Navigation.NavigationWindow.ShowsNavigationUI%2A> en `false`.

Como alternativa, puede usar la compatibilidad con la personalización en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] para reemplazar el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] del <xref:System.Windows.Navigation.NavigationWindow>.

<a name="Frame_in_Standalone_Applications"></a>

## <a name="the-frame-class"></a>Clase Frame

Tanto el explorador como el <xref:System.Windows.Navigation.NavigationWindow> son ventanas que hospedan contenido navegable. En algunos casos, las aplicaciones tienen contenido que no hace falta que los hospede una ventana completa. En su lugar, dicho contenido se hospeda dentro de otro contenido. Puede insertar contenido navegable en otro contenido mediante la clase <xref:System.Windows.Controls.Frame>. <xref:System.Windows.Controls.Frame> proporciona la misma compatibilidad que <xref:System.Windows.Navigation.NavigationWindow> y [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].

En el ejemplo siguiente se muestra cómo agregar un <xref:System.Windows.Controls.Frame> a un <xref:System.Windows.Controls.Page> mediante declaración con el elemento `Frame`.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml3)]

Este marcado establece el atributo `Source` del elemento `Frame` con un Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para el <xref:System.Windows.Controls.Page> al que se debe desplazar el <xref:System.Windows.Controls.Frame> inicialmente. En la ilustración siguiente se muestra un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] con un <xref:System.Windows.Controls.Page> que tiene un @no__t 2 que ha navegado entre varias páginas.

![Marco que ha navegado entre varias páginas](./media/navigation-overview/frame-navigation-between-multiple-pages.png ". muestra una navegación de fotogramas entre varias páginas.")

No solo tiene que usar <xref:System.Windows.Controls.Frame> dentro del contenido de un <xref:System.Windows.Controls.Page>. También es común hospedar un <xref:System.Windows.Controls.Frame> dentro del contenido de un <xref:System.Windows.Window>.

De forma predeterminada, <xref:System.Windows.Controls.Frame> solo usa su propio diario en ausencia de otro diario. Si un <xref:System.Windows.Controls.Frame> forma parte del contenido que se hospeda en un <xref:System.Windows.Navigation.NavigationWindow> o en un @no__t 2, <xref:System.Windows.Controls.Frame> usa el diario que pertenece a <xref:System.Windows.Navigation.NavigationWindow> o [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. A veces, sin embargo, un <xref:System.Windows.Controls.Frame> podría necesitar ser responsable de su propio diario. Una razón para ello es permitir la navegación del diario dentro de las páginas hospedadas por un <xref:System.Windows.Controls.Frame>. Esto se muestra en la ilustración siguiente.

![Diagrama de marco y de página](./media/navigation-overview/journal-navigation-within-pages-hosted-by-a-frame.png "muestra la navegación del diario dentro de las páginas hospedadas por un marco.")

En este caso, puede configurar el <xref:System.Windows.Controls.Frame> para usar su propio diario estableciendo la propiedad <xref:System.Windows.Controls.Frame.JournalOwnership%2A> del <xref:System.Windows.Controls.Frame> en <xref:System.Windows.Navigation.JournalOwnership.OwnsJournal>. Esto se muestra en la marcación siguiente.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml3)]

En la ilustración siguiente se muestra el efecto de navegar en un <xref:System.Windows.Controls.Frame> que usa su propio diario.

![Un marco que usa su propio diario](./media/navigation-overview/frame-uses-its-own-journal.png "muestra el efecto de navegar dentro de un marco que usa su propio diario.")

Tenga en cuenta que las entradas del diario se muestran en el @no__t de navegación-0 en el <xref:System.Windows.Controls.Frame>, en lugar de en Internet Explorer.

> [!NOTE]
> Si un <xref:System.Windows.Controls.Frame> forma parte del contenido que se hospeda en un <xref:System.Windows.Window>, @no__t 2 utiliza su propio diario y, por consiguiente, muestra su propia navegación [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].

Si la experiencia del usuario requiere que <xref:System.Windows.Controls.Frame> proporcione su propio diario sin mostrar el @no__t de navegación-1, puede ocultar el @no__t de navegación 2 estableciendo el <xref:System.Windows.Controls.Frame.NavigationUIVisibility%2A> en <xref:System.Windows.Visibility.Hidden>. Esto se muestra en la marcación siguiente.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml3)]

<a name="Navigation_Hosts"></a>

## <a name="navigation-hosts"></a>Hosts de navegación

<xref:System.Windows.Controls.Frame> y <xref:System.Windows.Navigation.NavigationWindow> son clases conocidas como hosts de navegación. Un *host de navegación* es una clase que puede navegar y mostrar el contenido. Para ello, cada host de navegación usa sus propios <xref:System.Windows.Navigation.NavigationService> y Journal. La construcción de un host de navegación básica se muestra en la ilustración siguiente.

![Diagramas de navegador](./media/navigation-overview/navigation-host-construction.png "creación básica de un host de navegación")

En esencia, esto permite que <xref:System.Windows.Navigation.NavigationWindow> y <xref:System.Windows.Controls.Frame> proporcionen la misma compatibilidad de navegación que proporciona un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] cuando se hospeda en el explorador.

Además de usar <xref:System.Windows.Navigation.NavigationService> y un diario, los hosts de navegación implementan los mismos miembros que implementa <xref:System.Windows.Navigation.NavigationService>. Esto se muestra en la ilustración siguiente.

![Un diario en un marco y en una](./media/navigation-overview/navigation-window-and-frame.png "ventana y marco de navegación") NavigationWindow

Esto le permite programar la compatibilidad con la navegación directamente con ellos. Puede tener esto en cuenta si necesita proporcionar una navegación personalizada [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] para un <xref:System.Windows.Controls.Frame> que se hospede en un @no__t 2. Además, ambos tipos implementan miembros adicionales relacionados con la navegación, como `BackStack` (<xref:System.Windows.Navigation.NavigationWindow.BackStack%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Frame.BackStack%2A?displayProperty=nameWithType>) y `ForwardStack` (<xref:System.Windows.Navigation.NavigationWindow.ForwardStack%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Frame.ForwardStack%2A?displayProperty=nameWithType>), que permiten enumerar las entradas del diario en la pila de retroceso y la pila de reenvío, respectivamente.

Como se mencionó anteriormente, pueden haber varios diarios dentro de una aplicación. En la siguiente ilustración se muestra un ejemplo de cuándo ocurre esto.

![Varios diarios dentro de una aplicación](./media/navigation-overview/multiple-journals-in-one-application.png "es un ejemplo de más de un diario en una aplicación.")

<a name="Navigating_to_Content_Other_than_Pages"></a>

## <a name="navigating-to-content-other-than-xaml-pages"></a>Navegar a contenido distinto de páginas XAML

En este tema, se han usado <xref:System.Windows.Controls.Page> y Pack [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] para mostrar las diversas funciones de navegación de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Sin embargo, un <xref:System.Windows.Controls.Page> que se compila en una aplicación no es el único tipo de contenido al que se puede navegar y Pack [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] no es la única manera de identificar el contenido.

Como se muestra en esta sección, también puede navegar a archivos sueltos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], archivos HTML y objetos.

<a name="Navigating_to_Loose_XAML_Files"></a>

### <a name="navigating-to-loose-xaml-files"></a>Navegación por archivos XAML dinámicos

Un archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] suelto es un archivo con las siguientes características:

- Solo contiene [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (es decir, ningún código).

- Tiene una declaración de espacio de nombres adecuada.

- Tiene la extensión de nombre de archivo .xaml.

Por ejemplo, considere el siguiente contenido almacenado como un archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] suelto, Person. Xaml.

[!code-xaml[NavigationOverviewSnippets#LooseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Person.xaml#loosexaml)]

Al hacer doble clic en el archivo, el explorador se abre y se desplaza al contenido y lo muestra. Esto se muestra en la siguiente ilustración.

La ![presentación del contenido en el archivo person. Xaml](./media/navigation-overview/contents-of-person-xaml-file.png "muestra el contenido del archivo person. Xaml.")

Puede mostrar un archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] suelto desde lo siguiente:

- Un sitio web en la máquina local, la intranet o Internet.

- Un recurso compartido de archivos UNC (Convención de nomenclatura universal).

- El disco local.

Se puede Agregar un archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] suelto a los favoritos del explorador o ser la Página principal del explorador.

> [!NOTE]
> Para obtener más información sobre la publicación y el inicio de páginas sueltas [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], consulte [implementar una aplicación de WPF](deploying-a-wpf-application-wpf.md).

Una limitación con respecto al @no__t dinámico es que solo se puede hospedar contenido que es seguro para ejecutarse en confianza parcial. Por ejemplo, `Window` no puede ser el elemento raíz de un archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] suelto. Para obtener más información, vea [Seguridad de confianza parcial de WPF](../wpf-partial-trust-security.md).

<a name="Navigating_to_HTML_Files_Using_Frame"></a>

### <a name="navigating-to-html-files-by-using-frame"></a>Navegación a archivos HTML mediante Frame

Como cabría esperar, también puede navegar a HTML. Solo tiene que proporcionar un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que use el esquema http. Por ejemplo, el siguiente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] muestra un <xref:System.Windows.Controls.Frame> que navega a una página HTML.

[!code-xaml[NavigationOverviewSnippets#FrameHtmlNavMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHTMLNavPage.xaml#framehtmlnavmarkup)]

La navegación a HTML requiere permisos especiales. Por ejemplo, no se puede navegar desde un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] que se ejecuta en el espacio aislado de seguridad de confianza parcial de zona de Internet. Para obtener más información, vea [Seguridad de confianza parcial de WPF](../wpf-partial-trust-security.md).

<a name="Navigating_to_HTML_Files_Using_WebBrowser"></a>

### <a name="navigating-to-html-files-by-using-the-webbrowser-control"></a>Navegación a archivos HTML mediante el Control WebBrowser

El control <xref:System.Windows.Controls.WebBrowser> admite el hospedaje de documentos HTML, la navegación y la interoperabilidad de código administrado o script. Para obtener información detallada sobre el control <xref:System.Windows.Controls.WebBrowser>, consulte <xref:System.Windows.Controls.WebBrowser>.

Como <xref:System.Windows.Controls.Frame>, la navegación a HTML con <xref:System.Windows.Controls.WebBrowser> requiere permisos especiales. Por ejemplo, desde una aplicación de confianza parcial, solo puede navegar a HTML ubicado en el sitio de origen. Para obtener más información, vea [Seguridad de confianza parcial de WPF](../wpf-partial-trust-security.md).

<a name="Navigating_to_Objects"></a>

### <a name="navigating-to-custom-objects"></a>Navegación por objetos personalizados

Si tiene datos que se almacenan como objetos personalizados, una manera de mostrar los datos consiste en crear un <xref:System.Windows.Controls.Page> con contenido enlazado a esos objetos (consulte [información general sobre el enlace de datos](../data/data-binding-overview.md)). Si no necesita la sobrecarga de la creación de una página completa para mostrar los objetos, puede navegar directamente a ellos en su lugar.

Considere la clase `Person` que se implementa en el código siguiente.

[!code-csharp[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/Person.cs#personclasscode)]
[!code-vb[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/Person.vb#personclasscode)]

Para ir a ella, llame al método <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A?displayProperty=nameWithType>, tal y como se muestra en el código siguiente.

[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject1)]
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject2)]
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject3)]

[!code-csharp[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml.cs#pagethatnavstoobjectcodebehind)]
[!code-vb[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/HomePage.xaml.vb#pagethatnavstoobjectcodebehind)]

En la siguiente ilustración se muestra el resultado.

![Página que navega a una clase](./media/navigation-overview/page-navigates-to-an-object.png ". este es un ejemplo de una página que navega a un objeto.")

En esta ilustración, puede ver que no se muestra nada útil. De hecho, el valor que se muestra es el valor devuelto del método `ToString` para el objeto **Person** ; de forma predeterminada, este es el único valor que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] puede usar para representar el objeto. Puede invalidar el método `ToString` para devolver información más significativa, aunque seguirá siendo solo un valor de cadena. Una técnica que se puede usar que aprovecha las funcionalidades de presentación de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] es usar una plantilla de datos. Puede implementar una plantilla de datos que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] puede asociar a un objeto de un tipo determinado. En el código siguiente se muestra una plantilla de datos para el objeto `Person`.

[!code-xaml[NavigateToObjectSnippets#DataTemplateMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/App.xaml#datatemplatemarkup)]

En este caso, la plantilla de datos se asocia al tipo `Person` mediante la extensión de marcado `x:Type` en el atributo `DataType`. A continuación, la plantilla de datos enlaza los elementos `TextBlock` (vea <xref:System.Windows.Controls.TextBlock>) a las propiedades de la clase `Person`. En la siguiente ilustración se muestra la apariencia actualizada del objeto `Person`.

![Desplazarse a una clase que tiene una plantilla de datos]que(./media/navigation-overview/navigating-to-a-class.png "navega a una clase que tiene una plantilla de datos.")

Una ventaja de esta técnica es la coherencia que obtiene al poder volver a usar la plantilla de datos para mostrar los objetos de forma coherente en cualquier parte de la aplicación.

Para obtener más información sobre las plantillas de datos, vea [información general sobre plantillas de datos](../data/data-templating-overview.md).

<a name="Security"></a>

## <a name="security"></a>Seguridad

la compatibilidad con la navegación [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] permite a [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] navegar a través de Internet y permite a las aplicaciones hospedar contenido de terceros. Para proteger tanto las aplicaciones como los usuarios del comportamiento perjudicial, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] proporciona una variedad de características de seguridad que se describen en [seguridad](../security-wpf.md) y [seguridad de confianza parcial de WPF](../wpf-partial-trust-security.md).

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Application.SetCookie%2A>
- <xref:System.Windows.Application.GetCookie%2A>
- [Información general sobre la administración de aplicaciones](application-management-overview.md)
- [Identificadores URI de paquete en WPF](pack-uris-in-wpf.md)
- [Información general sobre la navegación estructurada](structured-navigation-overview.md)
- [Información general sobre topologías de navegación](navigation-topologies-overview.md)
- [Temas "Cómo..."](navigation-how-to-topics.md)
- [Implementar una aplicación WPF](deploying-a-wpf-application-wpf.md)

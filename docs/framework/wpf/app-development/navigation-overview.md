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
ms.openlocfilehash: 8afda2a314bd04e91c6686fb254a1bd9e773913d
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636294"
---
# <a name="navigation-overview"></a>Información general sobre navegación

Windows Presentation Foundation (WPF) admite la navegación de estilo explorador que se puede usar en dos tipos de aplicaciones: aplicaciones independientes y aplicaciones de explorador XAML (XBAP). Para empaquetar el contenido para la navegación, WPF proporciona la clase <xref:System.Windows.Controls.Page>. Puede desplazarse de un <xref:System.Windows.Controls.Page> a otro mediante declaración, mediante un <xref:System.Windows.Documents.Hyperlink>o mediante programación, mediante el uso de la <xref:System.Windows.Navigation.NavigationService>. WPF usa el diario para recordar las páginas a las que se ha navegado y para volver a ellas.

<xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Navigation.NavigationService>y el diario forman el núcleo de la compatibilidad de navegación que proporciona WPF. En esta información general se exploran estas características en detalle antes de cubrir la compatibilidad con la navegación avanzada, que incluye la navegación a archivos de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] sueltos, archivos HTML y objetos.

> [!NOTE]
> En este tema, el término "explorador" solo se refiere a los exploradores que pueden hospedar aplicaciones WPF, que actualmente incluye Microsoft Internet Explorer y Firefox. Cuando solo se admiten características específicas de WPF en un explorador determinado, se hace referencia a la versión del explorador.

## <a name="navigation-in-wpf-applications"></a>Navegación a aplicaciones para WPF

En este tema se proporciona información general sobre las funcionalidades de navegación clave en WPF. Estas funcionalidades están disponibles tanto para aplicaciones independientes como para XBAP, aunque en este tema se presentan en el contexto de una aplicación XBAP.

> [!NOTE]
> En este tema no se explica cómo compilar e implementar XBAP. Para obtener más información sobre las XBAP, consulte [información general sobre las aplicaciones de explorador XAML de WPF](wpf-xaml-browser-applications-overview.md).

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

En WPF, puede navegar a varios tipos de contenido que incluyen objetos de .NET Framework, objetos personalizados, valores de enumeración, controles de usuario, archivos de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y archivos HTML. Sin embargo, descubrirá que la manera más común y cómoda de empaquetar el contenido es mediante <xref:System.Windows.Controls.Page>. Además, <xref:System.Windows.Controls.Page> implementa características específicas de la navegación para mejorar su apariencia y simplificar el desarrollo.

Con <xref:System.Windows.Controls.Page>, puede implementar mediante declaración una página navegable de contenido de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] mediante un marcado como el siguiente.

[!code-xaml[NavigationOverviewSnippets#Page1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page1.xaml#page1xaml)]

Un <xref:System.Windows.Controls.Page> que se implementa en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] marcado tiene `Page` como su elemento raíz y requiere la declaración del espacio de nombres XML de WPF. El elemento `Page` contiene el contenido al que desea desplazarse y mostrarse. El contenido se agrega estableciendo el elemento de propiedad `Page.Content`, como se muestra en el marcado siguiente.

[!code-xaml[NavigationOverviewSnippets#Page2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page2.xaml#page2xaml)]

`Page.Content` solo puede contener un elemento secundario; en el ejemplo anterior, el contenido es una sola cadena, "Hello, Page!". En la práctica, normalmente usará un control de diseño como el elemento secundario (vea [diseño](../advanced/layout.md)) para contener y componer el contenido.

Los elementos secundarios de un elemento `Page` se consideran el contenido de un <xref:System.Windows.Controls.Page> y, por consiguiente, no es necesario utilizar la declaración de `Page.Content` explícita. La marcación siguiente es el equivalente declarativo del ejemplo anterior.

[!code-xaml[NavigationOverviewSnippets#Page3XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page3.xaml#page3xaml)]

En este caso, `Page.Content` se establece automáticamente con los elementos secundarios del elemento `Page`. Para obtener más información, consulte [Modelo de contenido de WPF](../controls/wpf-content-model.md).

Un <xref:System.Windows.Controls.Page> de solo marcado es útil para mostrar el contenido. Sin embargo, un <xref:System.Windows.Controls.Page> también puede mostrar controles que permiten a los usuarios interactuar con la página, y pueden responder a la interacción del usuario controlando los eventos y llamando a la lógica de la aplicación. Un <xref:System.Windows.Controls.Page> interactivo se implementa mediante una combinación de marcado y código subyacente, como se muestra en el ejemplo siguiente.

[!code-xaml[XBAPAppDefSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml#homepagemarkup)]

[!code-csharp[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml.cs#homepagecodebehind)]
[!code-vb[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/HomePage.xaml.vb#homepagecodebehind)]

Para permitir que un archivo de marcación y un archivo de código subyacente funcionen juntos, se necesita la configuración siguiente:

- En el marcado, el elemento `Page` debe incluir el atributo `x:Class`. Cuando se compila la aplicación, la existencia de `x:Class` en el archivo de marcado hace que el motor de compilación de Microsoft (MSBuild) cree una `partial` clase que deriva de <xref:System.Windows.Controls.Page> y tiene el nombre especificado por el atributo `x:Class`. Esto requiere la adición de una declaración de espacio de nombres XML para el esquema de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`). La clase `partial` generada implementa `InitializeComponent`, a la que se llama para registrar los eventos y establecer las propiedades que se implementan en el marcado.

- En el código subyacente, la clase debe ser una `partial` clase con el mismo nombre especificado por el atributo `x:Class` en el marcado y debe derivar de <xref:System.Windows.Controls.Page>. Esto permite asociar el archivo de código subyacente a la clase `partial` que se genera para el archivo de marcado cuando se compila la aplicación (consulte [compilar una aplicación WPF](building-a-wpf-application-wpf.md)).

- En el código subyacente, la clase <xref:System.Windows.Controls.Page> debe implementar un constructor que llame al método `InitializeComponent`. la clase `partial` generada por el archivo de marcado implementa `InitializeComponent` para registrar eventos y establecer las propiedades que se definen en el marcado.

> [!NOTE]
> Al agregar un nuevo <xref:System.Windows.Controls.Page> al proyecto mediante Visual Studio, el <xref:System.Windows.Controls.Page> se implementa mediante marcado y código subyacente, e incluye la configuración necesaria para crear la asociación entre el marcado y los archivos de código subyacente, como se describe aquí.

Una vez que tenga un <xref:System.Windows.Controls.Page>, puede desplazarse hasta él. Para especificar el primer <xref:System.Windows.Controls.Page> al que navega una aplicación, debe configurar el <xref:System.Windows.Controls.Page>de inicio.

<a name="Configuring_a_Start_Page"></a>

### <a name="configuring-a-start-page"></a>Configuración de una página de inicio

Las XBAP requieren que se hospede una determinada cantidad de infraestructura de aplicación en un explorador. En WPF, la clase <xref:System.Windows.Application> forma parte de una definición de aplicación que establece la infraestructura de aplicación necesaria (consulte [información general sobre la administración de aplicaciones](application-management-overview.md)).

Normalmente, una definición de aplicación se implementa mediante el marcado y el código subyacente, con el archivo de marcado configurado como un elemento de`ApplicationDefinition` de MSBuild. La siguiente es una definición de aplicación para un XBAP.

[!code-xaml[XBAPAppDefSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]

[!code-csharp[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml.cs#xbapapplicationdefinitioncodebehind)]
[!code-vb[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/Application.xaml.vb#xbapapplicationdefinitioncodebehind)]

Un XBAP puede usar su definición de aplicación para especificar una <xref:System.Windows.Controls.Page>de inicio, que es el <xref:System.Windows.Controls.Page> que se carga automáticamente cuando se inicia la aplicación XBAP. Para ello, establezca la propiedad <xref:System.Windows.Application.StartupUri%2A> con el identificador uniforme de recursos (URI) para el <xref:System.Windows.Controls.Page>deseado.

> [!NOTE]
> En la mayoría de los casos, los <xref:System.Windows.Controls.Page> se compilan o se implementan con una aplicación. En estos casos, el URI que identifica una <xref:System.Windows.Controls.Page> es un Pack URI, que es un URI que se ajusta al esquema del *paquete* . Los URI de los paquetes se describen con más detalle en [pack uri en WPF](pack-uris-in-wpf.md). También puede navegar al contenido con el esquema HTTP, que se describe a continuación.

Puede establecer <xref:System.Windows.Application.StartupUri%2A> mediante declaración en el marcado, tal como se muestra en el ejemplo siguiente.

[!code-xaml[NavigationOverviewSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]

En este ejemplo, el atributo `StartupUri` se establece con un Pack URI relativo que identifica HomePage. Xaml. Cuando se inicia la aplicación XBAP, se navega a HomePage. XAML y se muestra automáticamente. Esto se muestra en la siguiente ilustración, que muestra una aplicación XBAP iniciada desde un servidor Web.

![Página de XBAP](./media/navigation-overview/xbap-launched-from-a-web-server.png "Esto muestra una aplicación XBAP iniciada desde un servidor Web.")

> [!NOTE]
> Para obtener más información sobre el desarrollo y la implementación de XBAP, vea [información general sobre las aplicaciones de explorador XAML de WPF](wpf-xaml-browser-applications-overview.md) e [implementar una aplicación de WPF](deploying-a-wpf-application-wpf.md).

<a name="ConfiguringAXAMLPage"></a>

### <a name="configuring-the-host-windows-title-width-and-height"></a>Configuración del título, el ancho y el alto de la ventana host

Una cosa que puede haber observado en la ilustración anterior es que el título del explorador y del panel de pestañas es el URI de la aplicación XBAP. Además de largo, el título no es atractivo ni informativo. Por esta razón, <xref:System.Windows.Controls.Page> ofrece una forma de cambiar el título estableciendo la propiedad <xref:System.Windows.Controls.Page.WindowTitle%2A>. Además, puede configurar el ancho y el alto de la ventana del explorador estableciendo <xref:System.Windows.Controls.Page.WindowWidth%2A> y <xref:System.Windows.Controls.Page.WindowHeight%2A>, respectivamente.

<xref:System.Windows.Controls.Page.WindowTitle%2A>, <xref:System.Windows.Controls.Page.WindowWidth%2A>y <xref:System.Windows.Controls.Page.WindowHeight%2A> se pueden establecer mediante declaración en el marcado, tal y como se muestra en el ejemplo siguiente.

[!code-xaml[NavigationOverviewSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/HomePage.xaml#homepagemarkup)]

El resultado se muestra en la ilustración siguiente.

![Título, alto y ancho de la ventana](./media/navigation-overview/window-title-width-height.png "Esto muestra el título, el alto y el ancho de la ventana que puede configurar.")

<a name="NavigatingBetweenXAMLPages"></a>

### <a name="hyperlink-navigation"></a>Navegación por hipervínculos

Una aplicación XBAP típica consta de varias páginas. La manera más sencilla de desplazarse de una página a otra consiste en usar una <xref:System.Windows.Documents.Hyperlink>. Puede agregar mediante declaración una <xref:System.Windows.Documents.Hyperlink> a una <xref:System.Windows.Controls.Page> mediante el elemento `Hyperlink`, que se muestra en el marcado siguiente.

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

Un elemento `Hyperlink` requiere lo siguiente:

- Pack URI del <xref:System.Windows.Controls.Page> al que se va a desplazar, tal y como especifica el atributo `NavigateUri`.

- Contenido en el que un usuario puede hacer clic para iniciar la navegación, como texto e imágenes (para el contenido que puede contener el elemento `Hyperlink`, vea <xref:System.Windows.Documents.Hyperlink>).

En la ilustración siguiente se muestra una aplicación XBAP con un <xref:System.Windows.Controls.Page> que tiene un <xref:System.Windows.Documents.Hyperlink>.

![Página con hipervínculo](./media/navigation-overview/xbap-with-a-page-with-a-hyperlink.png "Esto muestra una aplicación XBAP con una página con un hipervínculo.")

Como cabría esperar, al hacer clic en el <xref:System.Windows.Documents.Hyperlink> hace que la aplicación XBAP navegue hasta el <xref:System.Windows.Controls.Page> identificado por el atributo `NavigateUri`. Además, la aplicación XBAP agrega una entrada para el <xref:System.Windows.Controls.Page> anterior a la lista de páginas recientes en Internet Explorer. Esto se muestra en la siguiente ilustración.

![Botones atrás y adelante](./media/navigation-overview/back-and-forward-navigation.png "Navegue con los botones atrás y adelante.")

Además de permitir la navegación de un <xref:System.Windows.Controls.Page> a otro, <xref:System.Windows.Documents.Hyperlink> también admite la navegación por fragmentos.

<a name="FragmentNavigation"></a>

### <a name="fragment-navigation"></a>Navegación por fragmentos

La *navegación por fragmentos* es la navegación a un fragmento de contenido en el <xref:System.Windows.Controls.Page> actual u otro <xref:System.Windows.Controls.Page>. En WPF, un fragmento de contenido es el contenido incluido en un elemento con nombre. Un elemento con nombre es un elemento que tiene su conjunto de atributos `Name`. En el marcado siguiente se muestra un elemento de `TextBlock` con nombre que contiene un fragmento de contenido.

[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup1)]
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup2)]
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup3)]

Para una <xref:System.Windows.Documents.Hyperlink> para navegar a un fragmento de contenido, el atributo `NavigateUri` debe incluir lo siguiente:

- URI del <xref:System.Windows.Controls.Page> con el fragmento de contenido al que se va a navegar.

- Un carácter "#".

- Nombre del elemento en el <xref:System.Windows.Controls.Page> que contiene el fragmento de contenido.

Un identificador URI de fragmento tiene el formato siguiente.

*PageURI* `#` *ElementName*

A continuación se muestra un ejemplo de una `Hyperlink` que está configurada para navegar a un fragmento de contenido.

[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml1)]
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml2)]
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml3)]

> [!NOTE]
> En esta sección se describe la implementación de navegación por fragmentos predeterminada en WPF. WPF también le permite implementar su propio esquema de navegación por fragmentos, que, en parte, requiere controlar el evento <xref:System.Windows.Navigation.NavigationService.FragmentNavigation?displayProperty=nameWithType>.

> [!IMPORTANT]
> Puede desplazarse hasta fragmentos en páginas de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sueltos (solo archivos de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de marcado con `Page` como elemento raíz) si las páginas se pueden examinar a través de HTTP.
>
> Sin embargo, una página [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] floja puede desplazarse a sus propios fragmentos.

<a name="NavigationService"></a>

### <a name="navigation-service"></a>Servicio de navegación

Aunque <xref:System.Windows.Documents.Hyperlink> permite a un usuario iniciar la navegación a un <xref:System.Windows.Controls.Page>determinado, la clase <xref:System.Windows.Navigation.NavigationService> realiza el trabajo de buscar y descargar la página. Esencialmente, <xref:System.Windows.Navigation.NavigationService> proporciona la capacidad de procesar una solicitud de navegación en nombre del código de cliente, como el <xref:System.Windows.Documents.Hyperlink>. Además, <xref:System.Windows.Navigation.NavigationService> implementa compatibilidad de nivel superior para realizar el seguimiento e influir en una solicitud de navegación.

Cuando se hace clic en un <xref:System.Windows.Documents.Hyperlink>, WPF llama <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> para buscar y descargar el <xref:System.Windows.Controls.Page> en el Pack URI especificado. El <xref:System.Windows.Controls.Page> descargado se convierte en un árbol de objetos cuyo objeto raíz es una instancia del <xref:System.Windows.Controls.Page>descargado. Una referencia al objeto <xref:System.Windows.Controls.Page> raíz se almacena en la propiedad <xref:System.Windows.Navigation.NavigationService.Content%2A?displayProperty=nameWithType>. El URI del paquete para el contenido al que se navegó se almacena en la propiedad <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType>, mientras que la <xref:System.Windows.Navigation.NavigationService.CurrentSource%2A?displayProperty=nameWithType> almacena el Pack URI de la última página a la que se navegó.

> [!NOTE]
> Es posible que una aplicación WPF tenga más de una <xref:System.Windows.Navigation.NavigationService>activa actualmente. Para obtener más información, vea [hosts de navegación](#Navigation_Hosts) más adelante en este tema.

<a name="Programmatic_Navigation_with_the_Navigation_Service"></a>

### <a name="programmatic-navigation-with-the-navigation-service"></a>Navegación programática con el servicio de navegación

No es necesario saber <xref:System.Windows.Navigation.NavigationService> si la navegación se implementa mediante declaración en el marcado mediante <xref:System.Windows.Documents.Hyperlink>, porque <xref:System.Windows.Documents.Hyperlink> usa el <xref:System.Windows.Navigation.NavigationService> en su nombre. Esto significa que, siempre que el elemento primario directo o indirecto de un <xref:System.Windows.Documents.Hyperlink> sea un host de navegación (consulte [hosts de navegación](#Navigation_Hosts)), <xref:System.Windows.Documents.Hyperlink> podrá encontrar y usar el servicio de navegación del host de navegación para procesar una solicitud de navegación.

Sin embargo, hay situaciones en las que es necesario usar <xref:System.Windows.Navigation.NavigationService> directamente, entre las que se incluyen las siguientes:

- Cuando necesite crear una instancia de un <xref:System.Windows.Controls.Page> mediante un constructor sin parámetros.

- Cuando necesite establecer propiedades en el <xref:System.Windows.Controls.Page> antes de navegar a él.

- Cuando el <xref:System.Windows.Controls.Page> al que debe navegarse solo se puede determinar en tiempo de ejecución.

En estas situaciones, debe escribir código para iniciar la navegación mediante programación llamando al método <xref:System.Windows.Navigation.NavigationService.Navigate%2A> del objeto <xref:System.Windows.Navigation.NavigationService>. Esto requiere obtener una referencia a un <xref:System.Windows.Navigation.NavigationService>.

#### <a name="getting-a-reference-to-the-navigationservice"></a>Obtención de una referencia a NavigationService

Por motivos que se describen en la sección [hosts de navegación](#Navigation_Hosts) , una aplicación WPF puede tener más de un <xref:System.Windows.Navigation.NavigationService>. Esto significa que el código necesita una manera de buscar un <xref:System.Windows.Navigation.NavigationService>, que suele ser el <xref:System.Windows.Navigation.NavigationService> que navega hasta el <xref:System.Windows.Controls.Page>actual. Puede obtener una referencia a un <xref:System.Windows.Navigation.NavigationService> llamando al método <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A?displayProperty=nameWithType> `static`. Para obtener el <xref:System.Windows.Navigation.NavigationService> que navegó a un <xref:System.Windows.Controls.Page>determinado, se pasa una referencia a la <xref:System.Windows.Controls.Page> como el argumento del método <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A>. En el código siguiente se muestra cómo obtener el <xref:System.Windows.Navigation.NavigationService> para la <xref:System.Windows.Controls.Page>actual.

[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind1)]
[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPage.xaml.vb#getnscodebehind2)]

Como método abreviado para buscar el <xref:System.Windows.Navigation.NavigationService> para un <xref:System.Windows.Controls.Page>, <xref:System.Windows.Controls.Page> implementa la propiedad <xref:System.Windows.Controls.Page.NavigationService%2A>. Esta implementación se muestra en el ejemplo siguiente.

[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind1)]
[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPageShortCut.xaml.vb#getnsshortcutcodebehind2)]

> [!NOTE]
> Un <xref:System.Windows.Controls.Page> solo puede obtener una referencia a su <xref:System.Windows.Navigation.NavigationService> cuando <xref:System.Windows.Controls.Page> provoca el evento de <xref:System.Windows.FrameworkElement.Loaded>.

#### <a name="programmatic-navigation-to-a-page-object"></a>Navegación programática a un objeto de página

En el ejemplo siguiente se muestra cómo utilizar el <xref:System.Windows.Navigation.NavigationService> para desplazarse a un <xref:System.Windows.Controls.Page>mediante programación. La navegación mediante programación es necesaria porque solo se puede crear una instancia de la <xref:System.Windows.Controls.Page> a la que se está navegando mediante un solo constructor sin parámetros. El <xref:System.Windows.Controls.Page> con el constructor sin parámetros se muestra en el marcado y el código siguientes.

[!code-xaml[NavigationOverviewSnippets#PageWithNonDefaultConstructorXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml#pagewithnondefaultconstructorxaml)]

[!code-csharp[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml.cs#pagewithnondefaultconstructorcodebehind)]
[!code-vb[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithNonDefaultConstructor.xaml.vb#pagewithnondefaultconstructorcodebehind)]

El <xref:System.Windows.Controls.Page> que navega al <xref:System.Windows.Controls.Page> con el constructor sin parámetros se muestra en el marcado y el código siguientes.

[!code-xaml[NavigationOverviewSnippets#NSNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml#nsnavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml.cs#nsnavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSNavigationPage.xaml.vb#nsnavigationpagecodebehind)]

Cuando se hace clic en el <xref:System.Windows.Documents.Hyperlink> de este <xref:System.Windows.Controls.Page>, la navegación se inicia creando una instancia de la <xref:System.Windows.Controls.Page> para navegar hasta usar el constructor sin parámetros y llamar al método <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType>. <xref:System.Windows.Navigation.NavigationService.Navigate%2A> acepta una referencia al objeto al que se va a desplazar el <xref:System.Windows.Navigation.NavigationService>, en lugar de un Pack URI.

#### <a name="programmatic-navigation-with-a-pack-uri"></a>Navegación programática con Pack URI

Si necesita crear un Pack URI mediante programación (cuando solo puede determinar el URI del paquete en tiempo de ejecución, por ejemplo), puede usar el método <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType>. Esta implementación se muestra en el ejemplo siguiente.

[!code-xaml[NavigationOverviewSnippets#NSUriNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml#nsurinavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml.cs#nsurinavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSUriNavigationPage.xaml.vb#nsurinavigationpagecodebehind)]

#### <a name="refreshing-the-current-page"></a>Actualización de la página actual

No se descarga un <xref:System.Windows.Controls.Page> si tiene el mismo Pack URI que el URI del paquete que se almacena en la propiedad <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType>. Para forzar a WPF a descargar la página actual de nuevo, puede llamar al método <xref:System.Windows.Navigation.NavigationService.Refresh%2A?displayProperty=nameWithType>, como se muestra en el ejemplo siguiente.

[!code-xaml[NavigationOverviewSnippets#NSRefreshNavigationPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml#nsrefreshnavigationpagexaml1)]

[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind1)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind1)]
[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind2)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind2)]

<a name="Navigation_Lifetime"></a>

### <a name="navigation-lifetime"></a>Duración de la navegación

Hay muchas maneras de iniciar la navegación, tal como ha podido ver. Cuando se inicia la navegación y mientras la navegación está en curso, puede realizar un seguimiento e influir en la navegación mediante los siguientes eventos implementados por <xref:System.Windows.Navigation.NavigationService>:

- <xref:System.Windows.Navigation.NavigationService.Navigating>. Se produce cuando se solicita una nueva navegación. Puede utilizarse para cancelar la navegación.

- <xref:System.Windows.Navigation.NavigationService.NavigationProgress>. Se produce periódicamente durante una descarga y ofrece información sobre el progreso de la exploración.

- <xref:System.Windows.Navigation.NavigationService.Navigated>. Se produce cuando se ha encontrado la página y se ha descargado.

- <xref:System.Windows.Navigation.NavigationService.NavigationStopped>. Se produce cuando se detiene la navegación (llamando a <xref:System.Windows.Navigation.NavigationService.StopLoading%2A>) o cuando se solicita una nueva navegación mientras está en curso una navegación actual.

- <xref:System.Windows.Navigation.NavigationService.NavigationFailed>. Se produce cuando se genera un error mientras se navega por el contenido solicitado.

- <xref:System.Windows.Navigation.NavigationService.LoadCompleted>. Se produce cuando el contenido al que se navegó se carga y se analiza, y empieza a representarse.

- <xref:System.Windows.Navigation.NavigationService.FragmentNavigation>. Se produce cuando se inicia la navegación a un fragmento de contenido, cosa que tiene lugar:

  - Inmediatamente, si el fragmento deseado está en el contenido actual.

  - Una vez se ha cargado el contenido de origen, si el fragmento deseado está en otro contenido.

Los eventos de navegación se generan en el orden que se muestra en la ilustración siguiente.

![Diagrama de flujo de navegación de páginas](./media/navigation-overview/order-of-navigation-events.png "Diagrama de flujo de eventos de navegación de páginas")

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

Si registra un controlador con un evento de navegación desde un <xref:System.Windows.Controls.Page>, como en el ejemplo anterior, también debe anular el registro del controlador de eventos. Si no lo hace, puede haber efectos secundarios con respecto a cómo recuerda la navegación de WPF <xref:System.Windows.Controls.Page> navegación con el diario.

<a name="NavigationHistory"></a>

### <a name="remembering-navigation-with-the-journal"></a>Registro de la navegación con el diario

WPF usa dos pilas para recordar las páginas desde las que ha navegado: una pila de retroceso y una pila de avance. Al desplazarse desde el <xref:System.Windows.Controls.Page> actual a un nuevo <xref:System.Windows.Controls.Page> o reenviar a un <xref:System.Windows.Controls.Page>existente, el <xref:System.Windows.Controls.Page> actual se agrega a la *pila de retroceso*. Cuando se desplaza desde el <xref:System.Windows.Controls.Page> actual hasta el <xref:System.Windows.Controls.Page>anterior, se agrega la <xref:System.Windows.Controls.Page> actual a la *pila de avance*. La pila de retroceso, la pila de avance y la funcionalidad para administrarlas se conocen en conjunto como el diario. Cada elemento de la pila de retroceso y la pila de reenvío es una instancia de la <xref:System.Windows.Navigation.JournalEntry> clase y se conoce como una *entrada de diario*.

#### <a name="navigating-the-journal-from-internet-explorer"></a>Navegación por el diario desde Internet Explorer

Conceptualmente, el diario funciona de la misma manera que los botones **atrás** y **adelante** de Internet Explorer. Esto se muestra en la siguiente ilustración.

![Botones atrás y adelante](./media/navigation-overview/back-and-forward-navigation.png "Navegue con los botones atrás y adelante.")

En el caso de las XBAP hospedadas por Internet Explorer, WPF integra el diario en la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de navegación de Internet Explorer. Esto permite a los usuarios navegar por las páginas de una aplicación XBAP mediante los botones de **Página** **atrás**, **adelante**y reciente de Internet Explorer.

> [!IMPORTANT]
> En Internet Explorer, cuando un usuario navega y vuelve a una aplicación XBAP, solo se conservan en el diario las entradas del diario de las páginas que no se mantuvieron activas. Para obtener información sobre cómo mantener las páginas activas, vea [duración de la página y el diario](#PageLifetime) más adelante en este tema.

De forma predeterminada, el texto de cada <xref:System.Windows.Controls.Page> que aparece en la lista de **páginas recientes** de Internet Explorer es el URI del <xref:System.Windows.Controls.Page>. En muchos casos, esto no es especialmente significativo para el usuario. Afortunadamente, puede cambiar el texto mediante una de las siguientes opciones:

1. El valor del atributo `JournalEntry.Name` adjunto.

2. Valor del atributo `Page.Title`.

3. El valor del atributo `Page.WindowTitle` y el URI de la <xref:System.Windows.Controls.Page>actual.

4. URI del <xref:System.Windows.Controls.Page>actual. (Predeterminado)

El orden en que se enumeran las opciones coincide con el orden de prioridad para buscar el texto. Por ejemplo, si se establece `JournalEntry.Name`, se omiten los demás valores.

En el ejemplo siguiente se utiliza el atributo `Page.Title` para cambiar el texto que aparece para una entrada del diario.

[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup1)]
[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup2)]

[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind1)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind1)]
[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind2)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind2)]

#### <a name="navigating-the-journal-using-wpf"></a>Navegación por el diario mediante WPF

Aunque un usuario puede navegar por el diario mediante las páginas **atrás**, **adelante**y **recientes** de Internet Explorer, también puede navegar por el diario mediante los mecanismos declarativos y de programación proporcionados por WPF. Una razón para ello es proporcionar interfaces de IU de navegación personalizadas en las páginas.

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

Considere una aplicación XBAP con varias páginas que contienen contenido enriquecido, como gráficos, animaciones y elementos multimedia. La superficie de memoria de este tipo de páginas podría ser bastante grande, especialmente si se usan elementos multimedia de audio y vídeo. Dado que el diario "recuerda" las páginas a las que se ha navegado, este tipo de aplicación XBAP podría consumir rápidamente una cantidad de memoria grande y notable.

Por esta razón, el comportamiento predeterminado del diario es almacenar <xref:System.Windows.Controls.Page> metadatos en cada entrada del diario en lugar de una referencia a un objeto <xref:System.Windows.Controls.Page>. Cuando se navega a una entrada del diario, sus metadatos de <xref:System.Windows.Controls.Page> se usan para crear una nueva instancia del <xref:System.Windows.Controls.Page>especificado. Como consecuencia, cada <xref:System.Windows.Controls.Page> a la que se navega tiene la duración que se muestra en la ilustración siguiente.

![Duración de la página](./media/navigation-overview/navigated-page-lifetime.png "Esto muestra la duración cuando se navega a una página.")

Aunque el uso del comportamiento de diario predeterminado puede ahorrar en el consumo de memoria, el rendimiento de la representación por página podría reducirse; la creación de instancias de un <xref:System.Windows.Controls.Page> puede llevar mucho tiempo, especialmente si tiene una gran cantidad de contenido. Si necesita conservar una instancia de <xref:System.Windows.Controls.Page> en el diario, puede dibujar dos técnicas para hacerlo. En primer lugar, puede navegar mediante programación a un objeto <xref:System.Windows.Controls.Page> llamando al método <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType>.

En segundo lugar, puede especificar que WPF conserve una instancia de un <xref:System.Windows.Controls.Page> en el diario estableciendo la propiedad <xref:System.Windows.Controls.Page.KeepAlive%2A> en `true` (el valor predeterminado es `false`). Como se muestra en el ejemplo siguiente, puede establecer <xref:System.Windows.Controls.Page.KeepAlive%2A> mediante declaración en el marcado.

[!code-xaml[NavigationOverviewSnippets#KeepAlivePageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/KeepAlivePage.xaml#keepalivepagexaml)]

La duración de un <xref:System.Windows.Controls.Page> que se mantiene activo es ligeramente diferente de la que no lo es. La primera vez que se navega a un <xref:System.Windows.Controls.Page> que se mantiene activo, se crea una instancia como una <xref:System.Windows.Controls.Page> que no se mantiene activa. Sin embargo, dado que una instancia del <xref:System.Windows.Controls.Page> se conserva en el diario, nunca se vuelve a crear una instancia de, siempre y cuando permanezca en el diario. Por consiguiente, si un <xref:System.Windows.Controls.Page> tiene lógica de inicialización que debe llamarse cada vez que se navega a la <xref:System.Windows.Controls.Page>, debe moverla del constructor a un controlador para el evento <xref:System.Windows.FrameworkElement.Loaded>. Como se muestra en la ilustración siguiente, los eventos <xref:System.Windows.FrameworkElement.Loaded> y <xref:System.Windows.FrameworkElement.Unloaded> se siguen generando cada vez que se navega a un <xref:System.Windows.Controls.Page> y desde, respectivamente.

![Cuando se producen los eventos Loaded y Unloaded](./media/navigation-overview/loaded-and-unloaded-events.png "Los eventos cargados y descargados se producen cuando una página se navega hacia y desde.")

Cuando un <xref:System.Windows.Controls.Page> no se mantiene activo, no debe realizar ninguna de las siguientes acciones:

- Almacenar una referencia a la base de datos ni ninguna parte de esta.

- Registrar controladores de eventos con eventos que no haya implementado.

Al realizar cualquiera de estas acciones se crearán referencias que obligan a que el <xref:System.Windows.Controls.Page> se conserve en la memoria, incluso después de que se haya quitado del diario.

En general, debería preferir el comportamiento predeterminado <xref:System.Windows.Controls.Page> de no mantener un <xref:System.Windows.Controls.Page> activo. Sin embargo, esto conlleva implicaciones de estado que se describen en la sección siguiente.

<a name="RetainingContentStateWithNavigationHistory"></a>

### <a name="retaining-content-state-with-navigation-history"></a>Conservación del estado del contenido con el historial de navegación

Si un <xref:System.Windows.Controls.Page> no se mantiene activo y tiene controles que recopilan datos del usuario, ¿qué ocurre con los datos si un usuario sale de la <xref:System.Windows.Controls.Page>y vuelve a ella? Desde la perspectiva de una experiencia de usuario, el usuario debería ver los datos que especificó anteriormente. Desafortunadamente, dado que se crea una nueva instancia de la <xref:System.Windows.Controls.Page> con cada navegación, se vuelve a crear una instancia de los controles que recopilaron los datos y se pierden los datos.

Afortunadamente, el diario proporciona compatibilidad para recordar datos a través de <xref:System.Windows.Controls.Page> navegaciones, incluidos los datos de control. En concreto, la entrada de diario para cada <xref:System.Windows.Controls.Page> actúa como un contenedor temporal para el estado de <xref:System.Windows.Controls.Page> asociado. En los pasos siguientes se describe cómo se usa esta compatibilidad cuando se navega desde un <xref:System.Windows.Controls.Page>:

1. Se agrega una entrada para el <xref:System.Windows.Controls.Page> actual al diario.

2. El estado de la <xref:System.Windows.Controls.Page> se almacena con la entrada de diario de esa página, que se agrega a la pila de retroceso.

3. Se navega a la nueva <xref:System.Windows.Controls.Page>.

Cuando se vuelve a navegar a la página <xref:System.Windows.Controls.Page>, con el diario, se llevan a cabo los siguientes pasos:

1. Se crea una instancia del <xref:System.Windows.Controls.Page> (la entrada del diario superior en la pila de retroceso).

2. El <xref:System.Windows.Controls.Page> se actualiza con el estado que se almacenó con la entrada de diario para el <xref:System.Windows.Controls.Page>.

3. Se vuelve a navegar a la <xref:System.Windows.Controls.Page>.

WPF usa automáticamente esta compatibilidad cuando se utilizan los siguientes controles en una <xref:System.Windows.Controls.Page>:

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

Si una <xref:System.Windows.Controls.Page> utiliza estos controles, los datos que se escriben en ellos se recuerdan en <xref:System.Windows.Controls.Page> navegaciones, como se muestra en el<xref:System.Windows.Controls.ListBox> de **colores favorito** de la ilustración siguiente.

![Página con controles que recuerdan el estado](./media/navigation-overview/data-remembered-across-page-navigations.png "Los datos especificados se recuerdan en las navegaciones de páginas.")

Cuando un <xref:System.Windows.Controls.Page> tiene controles distintos de los de la lista anterior, o cuando el estado se almacena en objetos personalizados, debe escribir código para hacer que el diario recuerde el estado en las navegaciones <xref:System.Windows.Controls.Page>.

Si necesita recordar pequeños fragmentos de estado en <xref:System.Windows.Controls.Page> navegaciones, puede usar las propiedades de dependencia (consulte <xref:System.Windows.DependencyProperty>) configuradas con la marca de metadatos <xref:System.Windows.FrameworkPropertyMetadata.Journal%2A?displayProperty=nameWithType>.

Si el estado que debe recordar el <xref:System.Windows.Controls.Page> entre las navegaciones consta de varios fragmentos de datos, puede que le resulte menos intenso el código para encapsular su estado en una sola clase e implementar la interfaz de <xref:System.Windows.Navigation.IProvideCustomContentState>.

Si necesita navegar por varios Estados de una sola <xref:System.Windows.Controls.Page>, sin navegar por el <xref:System.Windows.Controls.Page> mismo, puede usar <xref:System.Windows.Navigation.IProvideCustomContentState> y <xref:System.Windows.Navigation.NavigationService.AddBackEntry%2A?displayProperty=nameWithType>.

<a name="Cookies"></a>

### <a name="cookies"></a>Cookies

Otra forma en que las aplicaciones WPF pueden almacenar datos es con las cookies, que se crean, actualizan y eliminan mediante los métodos <xref:System.Windows.Application.SetCookie%2A> y <xref:System.Windows.Application.GetCookie%2A>. Las cookies que se pueden crear en WPF son las mismas cookies que usan otros tipos de aplicaciones Web. las cookies son fragmentos arbitrarios de datos que se almacenan en una aplicación en un equipo cliente durante o a través de sesiones de aplicación. Los datos de las cookies normalmente adoptan la forma de un par de nombre-valor en el formato siguiente.

*Nombre* `=` *valor*

Cuando los datos se pasan a <xref:System.Windows.Application.SetCookie%2A>, junto con el <xref:System.Uri> de la ubicación para la que se debe establecer la cookie, se crea una cookie en memoria y solo está disponible mientras dure la sesión de aplicación actual. Este tipo de cookie se conoce como cookie de *sesión*.

Para almacenar una cookie mediante sesiones de la aplicación, debe agregarse una fecha de expiración para la cookie, con el formato siguiente.

*Nombre* `=` *valor* `; expires=DAY, DD-MMM-YYYY HH:MM:SS GMT`

Una cookie con una fecha de expiración se almacena en la carpeta de archivos temporales de Internet de la instalación actual de Windows hasta que expire la cookie. Este tipo de cookie se conoce como *cookie persistente* porque se conserva entre las sesiones de la aplicación.

Puede recuperar las cookies de sesión y persistentes llamando al método <xref:System.Windows.Application.GetCookie%2A>, pasando el <xref:System.Uri> de la ubicación en la que se estableció la cookie con el método <xref:System.Windows.Application.SetCookie%2A>.

A continuación se muestran algunas de las formas en las que se admiten las cookies en WPF:

- Las aplicaciones independientes y XBAP de WPF pueden crear y administrar cookies.

- Se puede tener acceso a las cookies creadas por una aplicación XBAP desde el explorador.

- Las XBAP del mismo dominio pueden crear y compartir cookies.

- Las páginas XBAP y HTML del mismo dominio pueden crear y compartir cookies.

- Las cookies se envían cuando las XBAP y las páginas de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sueltos realizan solicitudes Web.

- Tanto las XBAP de nivel superior como las XBAP hospedadas en IFRAMEs pueden tener acceso a las cookies.

- La compatibilidad con cookies en WPF es la misma para todos los exploradores compatibles.

- En Internet Explorer, WPF respeta la Directiva de P3P que pertenece a las cookies, especialmente con respecto a las XBAP propias y de terceros.

<a name="Structured_Navigation"></a>

### <a name="structured-navigation"></a>Navegación estructurada

Si necesita pasar datos de un <xref:System.Windows.Controls.Page> a otro, puede pasar los datos como argumentos a un constructor sin parámetros de la <xref:System.Windows.Controls.Page>. Tenga en cuenta que si utiliza esta técnica, debe mantener el <xref:System.Windows.Controls.Page> activo; Si no es así, la próxima vez que navegue al <xref:System.Windows.Controls.Page>, WPF vuelve a crear una instancia del <xref:System.Windows.Controls.Page> mediante el constructor sin parámetros.

Como alternativa, el <xref:System.Windows.Controls.Page> puede implementar propiedades que se establecen con los datos que es necesario pasar. Sin embargo, las cosas son complicadas, cuando una <xref:System.Windows.Controls.Page> tiene que devolver los datos al <xref:System.Windows.Controls.Page> que ha navegado hasta él. El problema es que la navegación no admite de forma nativa mecanismos para garantizar que un <xref:System.Windows.Controls.Page> se devolverá después de que se navegue desde. Esencialmente, la navegación no admite la semántica de llamada/devolución. Para solucionar este problema, WPF proporciona la clase <xref:System.Windows.Navigation.PageFunction%601> que puede usar para asegurarse de que se devuelva un <xref:System.Windows.Controls.Page> de forma predecible y estructurada. Para obtener más información, vea [información general sobre la navegación estructurada](structured-navigation-overview.md).

<a name="The_NavigationWindow_Class"></a>

## <a name="the-navigationwindow-class"></a>Clase NavigationWindow

En este punto, ha visto la gama de servicios de navegación que probablemente usará para compilar aplicaciones con contenido navegable. Estos servicios se trataron en el contexto de las XBAP, aunque no se limitan a las XBAP. Los sistemas operativos modernos y las aplicaciones de Windows aprovechan la experiencia del explorador de los usuarios modernos para incorporar la navegación de estilo Explorador en aplicaciones independientes. Estos son algunos ejemplos comunes:

- **Diccionario de sinónimos de Word**: navegación por las opciones de Word.

- **Explorador de archivos**: navegación por archivos y carpetas.

- **Asistentes**: desglose de una tarea compleja en varias páginas entre las que se puede navegar. Un ejemplo es el Asistente para componentes de Windows que controla la adición y eliminación de características de Windows.

Para incorporar la navegación de estilo explorador a las aplicaciones independientes, puede usar la clase <xref:System.Windows.Navigation.NavigationWindow>. <xref:System.Windows.Navigation.NavigationWindow> deriva de <xref:System.Windows.Window> y lo extiende con la misma compatibilidad para la navegación que proporcionan las XBAP. Puede usar <xref:System.Windows.Navigation.NavigationWindow> como la ventana principal de la aplicación independiente o como una ventana secundaria, como un cuadro de diálogo.

Para implementar un <xref:System.Windows.Navigation.NavigationWindow>, al igual que con la mayoría de las clases de nivel superior en WPF (<xref:System.Windows.Window>, <xref:System.Windows.Controls.Page>, etc.), se usa una combinación de marcado y código subyacente. Esta implementación se muestra en el ejemplo siguiente.

[!code-xaml[IntroToNavNavigationWindowSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml#navigationwindowmarkup)]

[!code-csharp[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml.cs#navigationwindowcodebehind)]
[!code-vb[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/MainWindow.xaml.vb#navigationwindowcodebehind)]

Este código crea un <xref:System.Windows.Navigation.NavigationWindow> que navega automáticamente a un <xref:System.Windows.Controls.Page> (HomePage. xaml) cuando se abre la <xref:System.Windows.Navigation.NavigationWindow>. Si el <xref:System.Windows.Navigation.NavigationWindow> es la ventana principal de la aplicación, puede usar el atributo `StartupUri` para iniciarlo. Esto se muestra en la marcación siguiente.

[!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchNavWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/App.xaml#applaunchnavwindow)]

En la ilustración siguiente se muestra el <xref:System.Windows.Navigation.NavigationWindow> como la ventana principal de una aplicación independiente.

![Una ventana principal](./media/navigation-overview/navigation-window-as-main-window.png "Ventana de navegación como ventana principal")

En la ilustración, puede ver que el <xref:System.Windows.Navigation.NavigationWindow> tiene un título, aunque no se haya establecido en el código de implementación de <xref:System.Windows.Navigation.NavigationWindow> del ejemplo anterior. En su lugar, el título se establece mediante la propiedad <xref:System.Windows.Controls.Page.WindowTitle%2A>, que se muestra en el código siguiente.

[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup1)]
[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup2)]

La configuración de las propiedades <xref:System.Windows.Controls.Page.WindowWidth%2A> y <xref:System.Windows.Controls.Page.WindowHeight%2A> también afecta a la <xref:System.Windows.Navigation.NavigationWindow>.

Normalmente, se implementa su propia <xref:System.Windows.Navigation.NavigationWindow> cuando necesita personalizar su comportamiento o su apariencia. Si no realiza nada, puede usar un acceso directo. Si especifica el Pack URI de una <xref:System.Windows.Controls.Page> como <xref:System.Windows.Application.StartupUri%2A> en una aplicación independiente, <xref:System.Windows.Application> crea automáticamente un <xref:System.Windows.Navigation.NavigationWindow> para hospedar el <xref:System.Windows.Controls.Page>. En la marcación siguiente se muestra cómo habilitar esta opción.

[!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchPage](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/AnotherApp.xaml#applaunchpage)]

Si desea que una ventana de la aplicación secundaria, como un cuadro de diálogo, sea un <xref:System.Windows.Navigation.NavigationWindow>, puede usar el código del ejemplo siguiente para abrirla.

[!code-csharp[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/DialogOwnerWindow.xaml.cs#createnwdialogbox)]
[!code-vb[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/DialogOwnerWindow.xaml.vb#createnwdialogbox)]

En la siguiente ilustración se muestra el resultado.

![Un cuadro de diálogo](./media/navigation-overview/navigation-window-as-dialog-box.png "Ventana de navegación como un cuadro de diálogo")

Como puede ver, <xref:System.Windows.Navigation.NavigationWindow> muestra los botones **atrás** y **adelante** de Internet Explorer que permiten a los usuarios navegar por el diario. Estos botones proporcionan la misma experiencia de usuario, como se muestra en la ilustración siguiente.

![Botones atrás y adelante en NavigationWindow](./media/navigation-overview/back-and-forward-buttons-in-navigation-window.png "Botones atrás y adelante en una ventana de navegación")

Si las páginas proporcionan su propia compatibilidad y interfaz de usuario de navegación de diario, puede ocultar los botones **atrás** y **adelante** que se muestran en <xref:System.Windows.Navigation.NavigationWindow> estableciendo el valor de la propiedad <xref:System.Windows.Navigation.NavigationWindow.ShowsNavigationUI%2A> en `false`.

Como alternativa, puede usar la compatibilidad con la personalización en WPF para reemplazar el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] del <xref:System.Windows.Navigation.NavigationWindow> mismo.

<a name="Frame_in_Standalone_Applications"></a>

## <a name="the-frame-class"></a>Clase Frame

Tanto el explorador como el <xref:System.Windows.Navigation.NavigationWindow> son ventanas que hospedan contenido navegable. En algunos casos, las aplicaciones tienen contenido que no hace falta que los hospede una ventana completa. En su lugar, dicho contenido se hospeda dentro de otro contenido. Puede insertar contenido navegable en otro contenido mediante la clase <xref:System.Windows.Controls.Frame>. <xref:System.Windows.Controls.Frame> proporciona la misma compatibilidad que <xref:System.Windows.Navigation.NavigationWindow> y XBAP.

En el ejemplo siguiente se muestra cómo agregar un <xref:System.Windows.Controls.Frame> a un <xref:System.Windows.Controls.Page> mediante declaración con el elemento `Frame`.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml3)]

Este marcado establece el atributo `Source` del elemento `Frame` con un Pack URI para el <xref:System.Windows.Controls.Page> al que el <xref:System.Windows.Controls.Frame> debe navegar inicialmente. En la ilustración siguiente se muestra una aplicación XBAP con un <xref:System.Windows.Controls.Page> que tiene un <xref:System.Windows.Controls.Frame> que ha navegado entre varias páginas.

![Marco que ha navegado entre varias páginas](./media/navigation-overview/frame-navigation-between-multiple-pages.png "Esto muestra una navegación de fotogramas entre varias páginas.")

No solo tiene que usar <xref:System.Windows.Controls.Frame> dentro del contenido de un <xref:System.Windows.Controls.Page>. También es común hospedar una <xref:System.Windows.Controls.Frame> dentro del contenido de un <xref:System.Windows.Window>.

De forma predeterminada, <xref:System.Windows.Controls.Frame> solo utiliza su propio diario en ausencia de otro diario. Si una <xref:System.Windows.Controls.Frame> forma parte del contenido que se hospeda en un <xref:System.Windows.Navigation.NavigationWindow> o en una aplicación XBAP, <xref:System.Windows.Controls.Frame> utiliza el diario que pertenece al <xref:System.Windows.Navigation.NavigationWindow> o a XBAP. A veces, sin embargo, es posible que un <xref:System.Windows.Controls.Frame> deba ser responsable de su propio diario. Una razón para hacerlo es permitir la navegación por el diario dentro de las páginas que se hospedan en un <xref:System.Windows.Controls.Frame>. Esto se muestra en la ilustración siguiente.

![Diagrama de marco y de página](./media/navigation-overview/journal-navigation-within-pages-hosted-by-a-frame.png "Esto muestra la navegación del diario dentro de las páginas hospedadas por un marco.")

En este caso, puede configurar el <xref:System.Windows.Controls.Frame> para utilizar su propio diario estableciendo la propiedad <xref:System.Windows.Controls.Frame.JournalOwnership%2A> de la <xref:System.Windows.Controls.Frame> en <xref:System.Windows.Navigation.JournalOwnership.OwnsJournal>. Esto se muestra en la marcación siguiente.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml3)]

En la ilustración siguiente se muestra el efecto de desplazarse dentro de una <xref:System.Windows.Controls.Frame> que utiliza su propio diario.

![Marco que usa su propio diario](./media/navigation-overview/frame-uses-its-own-journal.png "Esto muestra el efecto de navegar dentro de un marco que usa su propio diario.")

Tenga en cuenta que las entradas del diario se muestran en la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de navegación en el <xref:System.Windows.Controls.Frame>, en lugar de en Internet Explorer.

> [!NOTE]
> Si una <xref:System.Windows.Controls.Frame> forma parte del contenido que se hospeda en un <xref:System.Windows.Window>, <xref:System.Windows.Controls.Frame> utiliza su propio diario y, por consiguiente, muestra su propia [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]de navegación.

Si la experiencia del usuario requiere un <xref:System.Windows.Controls.Frame> para proporcionar su propio diario sin mostrar el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]de navegación, puede ocultar la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de navegación estableciendo la <xref:System.Windows.Controls.Frame.NavigationUIVisibility%2A> en <xref:System.Windows.Visibility.Hidden>. Esto se muestra en la marcación siguiente.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml3)]

<a name="Navigation_Hosts"></a>

## <a name="navigation-hosts"></a>Hosts de navegación

<xref:System.Windows.Controls.Frame> y <xref:System.Windows.Navigation.NavigationWindow> son clases conocidas como hosts de navegación. Un *host de navegación* es una clase que puede navegar y mostrar el contenido. Para ello, cada host de navegación utiliza su propio <xref:System.Windows.Navigation.NavigationService> y Journal. La construcción de un host de navegación básica se muestra en la ilustración siguiente.

![Diagramas de navegador](./media/navigation-overview/navigation-host-construction.png "Construcción básica de un host de navegación")

En esencia, esto permite a <xref:System.Windows.Navigation.NavigationWindow> y <xref:System.Windows.Controls.Frame> proporcionar la misma compatibilidad de navegación que proporciona una aplicación XBAP cuando se hospeda en el explorador.

Además de usar <xref:System.Windows.Navigation.NavigationService> y un diario, los hosts de navegación implementan los mismos miembros que implementa <xref:System.Windows.Navigation.NavigationService>. Esto se muestra en la ilustración siguiente.

![Un diario en un marco y en NavigationWindow](./media/navigation-overview/navigation-window-and-frame.png "Ventana de navegación y marco")

Esto le permite programar la compatibilidad con la navegación directamente con ellos. Puede considerar esto si necesita proporcionar una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de navegación personalizada para un <xref:System.Windows.Controls.Frame> que se hospede en un <xref:System.Windows.Window>. Además, ambos tipos implementan miembros adicionales relacionados con la navegación, como `BackStack` (<xref:System.Windows.Navigation.NavigationWindow.BackStack%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Frame.BackStack%2A?displayProperty=nameWithType>) y `ForwardStack` (<xref:System.Windows.Navigation.NavigationWindow.ForwardStack%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Frame.ForwardStack%2A?displayProperty=nameWithType>), que le permiten enumerar las entradas del diario en la pila de retroceso y la pila de reenvío, respectivamente.

Como se mencionó anteriormente, pueden haber varios diarios dentro de una aplicación. En la siguiente ilustración se muestra un ejemplo de cuándo ocurre esto.

![Varios diarios dentro de una aplicación](./media/navigation-overview/multiple-journals-in-one-application.png "Este es un ejemplo de más de un diario en una aplicación.")

<a name="Navigating_to_Content_Other_than_Pages"></a>

## <a name="navigating-to-content-other-than-xaml-pages"></a>Navegar a contenido distinto de páginas XAML

A lo largo de este tema, se han usado <xref:System.Windows.Controls.Page> y paquetes XBAP para demostrar las distintas funcionalidades de navegación de WPF. Sin embargo, un <xref:System.Windows.Controls.Page> que se compila en una aplicación no es el único tipo de contenido al que se puede navegar y empaquetar las XBAP no es la única manera de identificar el contenido.

Como se muestra en esta sección, también puede desplazarse a archivos de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sueltos, archivos HTML y objetos.

<a name="Navigating_to_Loose_XAML_Files"></a>

### <a name="navigating-to-loose-xaml-files"></a>Navegación por archivos XAML dinámicos

Un archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dinámico es un archivo con las siguientes características:

- Solo contiene [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (es decir, sin código).

- Tiene una declaración de espacio de nombres adecuada.

- Tiene la extensión de nombre de archivo .xaml.

Por ejemplo, considere el siguiente contenido almacenado como un archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] suelto, Person. Xaml.

[!code-xaml[NavigationOverviewSnippets#LooseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Person.xaml#loosexaml)]

Al hacer doble clic en el archivo, el explorador se abre y se desplaza al contenido y lo muestra. Esto se muestra en la siguiente ilustración.

![Presentación del contenido en el archivo person. XAML](./media/navigation-overview/contents-of-person-xaml-file.png "Muestra el contenido del archivo person. XAML.")

Puede mostrar un archivo de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] suelto a partir de lo siguiente:

- Un sitio web en la máquina local, la intranet o Internet.

- Un recurso compartido de archivos UNC (Convención de nomenclatura universal).

- El disco local.

Se puede Agregar un archivo de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dinámico a los favoritos del explorador o ser la Página principal del explorador.

> [!NOTE]
> Para obtener más información sobre la publicación y el inicio de páginas de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sueltos, vea [implementar una aplicación de WPF](deploying-a-wpf-application-wpf.md).

Una limitación con respecto a los [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sueltos es que solo se puede hospedar contenido seguro para ejecutarse en confianza parcial. Por ejemplo, `Window` no puede ser el elemento raíz de un archivo de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dinámico. Para obtener más información, vea [Seguridad de confianza parcial de WPF](../wpf-partial-trust-security.md).

<a name="Navigating_to_HTML_Files_Using_Frame"></a>

### <a name="navigating-to-html-files-by-using-frame"></a>Navegación a archivos HTML mediante Frame

Como cabría esperar, también puede navegar a HTML. Solo tiene que proporcionar un URI que use el esquema http. Por ejemplo, en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] siguiente se muestra un <xref:System.Windows.Controls.Frame> que navega a una página HTML.

[!code-xaml[NavigationOverviewSnippets#FrameHtmlNavMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHTMLNavPage.xaml#framehtmlnavmarkup)]

La navegación a HTML requiere permisos especiales. Por ejemplo, no se puede navegar desde una aplicación XBAP que se ejecuta en el espacio aislado de seguridad de confianza parcial de zona de Internet. Para obtener más información, vea [Seguridad de confianza parcial de WPF](../wpf-partial-trust-security.md).

<a name="Navigating_to_HTML_Files_Using_WebBrowser"></a>

### <a name="navigating-to-html-files-by-using-the-webbrowser-control"></a>Navegación a archivos HTML mediante el Control WebBrowser

El control <xref:System.Windows.Controls.WebBrowser> admite la interoperabilidad de hospedaje de documentos HTML, navegación y script/código administrado. Para obtener información detallada sobre el control de <xref:System.Windows.Controls.WebBrowser>, vea <xref:System.Windows.Controls.WebBrowser>.

Como <xref:System.Windows.Controls.Frame>, la navegación a HTML con <xref:System.Windows.Controls.WebBrowser> requiere permisos especiales. Por ejemplo, desde una aplicación de confianza parcial, solo puede navegar a HTML ubicado en el sitio de origen. Para obtener más información, vea [Seguridad de confianza parcial de WPF](../wpf-partial-trust-security.md).

<a name="Navigating_to_Objects"></a>

### <a name="navigating-to-custom-objects"></a>Navegación por objetos personalizados

Si tiene datos que se almacenan como objetos personalizados, una manera de mostrar los datos consiste en crear un <xref:System.Windows.Controls.Page> con contenido enlazado a esos objetos (consulte [información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)). Si no necesita la sobrecarga de la creación de una página completa para mostrar los objetos, puede navegar directamente a ellos en su lugar.

Tenga en cuenta la `Person` clase que se implementa en el código siguiente.

[!code-csharp[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/Person.cs#personclasscode)]
[!code-vb[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/Person.vb#personclasscode)]

Para ir a ella, llame al método <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A?displayProperty=nameWithType>, tal y como se muestra en el código siguiente.

[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject1)]
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject2)]
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject3)]

[!code-csharp[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml.cs#pagethatnavstoobjectcodebehind)]
[!code-vb[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/HomePage.xaml.vb#pagethatnavstoobjectcodebehind)]

En la siguiente ilustración se muestra el resultado.

![Página que navega a una clase](./media/navigation-overview/page-navigates-to-an-object.png "Este es un ejemplo de una página que navega a un objeto.")

En esta ilustración, puede ver que no se muestra nada útil. De hecho, el valor que se muestra es el valor devuelto del método `ToString` para el objeto **Person** ; de forma predeterminada, este es el único valor que WPF puede usar para representar el objeto. Puede invalidar el método `ToString` para devolver información más significativa, aunque seguirá siendo solo un valor de cadena. Una técnica que se puede usar que aprovecha las funcionalidades de presentación de WPF es usar una plantilla de datos. Puede implementar una plantilla de datos que WPF puede asociar a un objeto de un tipo determinado. En el código siguiente se muestra una plantilla de datos para el objeto `Person`.

[!code-xaml[NavigateToObjectSnippets#DataTemplateMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/App.xaml#datatemplatemarkup)]

En este caso, la plantilla de datos está asociada al tipo de `Person` mediante el `x:Type` extensión de marcado en el atributo `DataType`. A continuación, la plantilla de datos enlaza `TextBlock` elementos (vea <xref:System.Windows.Controls.TextBlock>) a las propiedades de la clase `Person`. En la siguiente ilustración se muestra la apariencia actualizada del objeto `Person`.

![Desplazarse a una clase que tiene una plantilla de datos](./media/navigation-overview/navigating-to-a-class.png "Desplazarse a una clase que tiene una plantilla de datos.")

Una ventaja de esta técnica es la coherencia que obtiene al poder volver a usar la plantilla de datos para mostrar los objetos de forma coherente en cualquier parte de la aplicación.

Para obtener más información sobre las plantillas de datos, vea [información general sobre plantillas de datos](../data/data-templating-overview.md).

<a name="Security"></a>

## <a name="security"></a>de seguridad

La compatibilidad con la navegación de WPF permite navegar a XBAP a través de Internet y permite a las aplicaciones hospedar contenido de terceros. Para proteger tanto las aplicaciones como los usuarios del comportamiento perjudicial, WPF proporciona una variedad de características de seguridad que se describen en [seguridad](../security-wpf.md) y [seguridad de confianza parcial de WPF](../wpf-partial-trust-security.md).

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Application.SetCookie%2A>
- <xref:System.Windows.Application.GetCookie%2A>
- [Información general sobre la administración de aplicaciones](application-management-overview.md)
- [Identificadores URI de paquete en WPF](pack-uris-in-wpf.md)
- [Información general sobre la navegación estructurada](structured-navigation-overview.md)
- [Información general sobre topologías de navegación](navigation-topologies-overview.md)
- [Temas "Cómo..."](navigation-how-to-topics.md)
- [Implementar una aplicación de WPF](deploying-a-wpf-application-wpf.md)

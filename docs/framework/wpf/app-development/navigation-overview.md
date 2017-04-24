---
title: "Informaci&#243;n general sobre navegaci&#243;n | Microsoft Docs"
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
  - "estado del contenido [WPF]"
  - "objetos personalizados [WPF]"
  - "navegación en fragmentos [WPF]"
  - "marcos [WPF]"
  - "HTML (archivos) [WPF]"
  - "hipervínculos [WPF]"
  - "diarios [WPF]"
  - "duración [WPF]"
  - "archivos XAML separados [WPF]"
  - "hosts de navegación [WPF]"
  - "páginas [WPF]"
  - "navegación mediante programación [WPF]"
  - "retener el estado del contenido [WPF]"
  - "página de inicio [WPF]"
  - "navegación estructurada [WPF]"
  - "Identificador uniforme de recursos (URI)"
  - "URI (identificador uniforme de recursos)"
  - "ventanas [WPF]"
ms.assetid: 86ad2143-606a-4e34-bf7e-51a2594248b8
caps.latest.revision: 69
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 65
---
# Informaci&#243;n general sobre navegaci&#243;n
[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] admite navegación de explorador que se puede utilizar en dos tipos de aplicaciones: aplicaciones independientes y [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]. Para empaquetar el contenido para la navegación, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] proporciona la clase <xref:System.Windows.Controls.Page>.  Se puede navegar de un objeto <xref:System.Windows.Controls.Page> a otro mediante declaración, utilizando un objeto <xref:System.Windows.Documents.Hyperlink>, o mediante programación, utilizando el objeto <xref:System.Windows.Navigation.NavigationService>. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] utiliza el diario para recordar las páginas desde y a las que se ha navegado.  
  
 <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Navigation.NavigationService> y el diario son los componentes esenciales de la compatibilidad de navegación proporcionada por [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  En esta introducción se describen detalladamente estas características antes de abordar el tema de la compatibilidad de navegación avanzada, que incluye la navegación a archivos [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] independientes, a archivos [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] y a objetos.  
  
> [!NOTE]
>  En este tema, el término "explorador" hace referencia únicamente a los exploradores que pueden hospedar aplicaciones [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], que actualmente son [!INCLUDE[TLA#tla_ie](../../../../includes/tlasharptla-ie-md.md)] y Firefox.  Cuando sólo se admiten determinadas características de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] en un explorador concreto, se hace referencia a la versión del explorador.  
  
   
  
<a name="XAMLBrowserApplications"></a>   
## Navegación en aplicaciones de WPF  
 En este tema se proporciona información general sobre las funciones de navegación principales en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  Estas funciones están disponibles para las aplicaciones independientes y [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], aunque en este tema se describen en el contexto de [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  
  
> [!NOTE]
>  En este tema no se explica cómo compilar e implementar [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  Para obtener más información sobre [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], vea [Información general sobre las aplicaciones de explorador XAML de WPF](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md).  
  
 En esta sección se explican y muestran los aspectos siguientes de la navegación:  
  
-   [Implementar una página](#CreatingAXAMLPage)  
  
-   [Configurar una página principal](#Configuring_a_Start_Page)  
  
-   [Configurar el título, ancho y alto de la ventana host](#ConfiguringAXAMLPage)  
  
-   [Navegación por hipervínculos](#NavigatingBetweenXAMLPages)  
  
-   [Navegación por fragmentos](#FragmentNavigation)  
  
-   [Servicio de navegación](#NavigationService)  
  
-   [Navegación mediante programación con el servicio de navegación](#Programmatic_Navigation_with_the_Navigation_Service)  
  
-   [Duración de la navegación](#Navigation_Lifetime)  
  
-   [Recordar la navegación con el diario](#NavigationHistory)  
  
-   [Duración y diario de páginas](#PageLifetime)  
  
-   [Conservar el estado del contenido con el historial de navegación](#RetainingContentStateWithNavigationHistory)  
  
-   [Cookies](#Cookies)  
  
-   [Navegación estructurada](#Structured_Navigation)  
  
<a name="CreatingAXAMLPage"></a>   
### Implementar una página  
 En [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], puede navegar a varios tipos de contenido, como objetos, objetos personalizados, valores de enumeración y controles de usuario de [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)], archivos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y archivos [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)].  Sin embargo, descubrirá que la forma más común y útil de empaquetar contenido consiste en utilizar <xref:System.Windows.Controls.Page>.  Además, <xref:System.Windows.Controls.Page> implementa características específicas de la navegación para mejorar la apariencia y simplificar el desarrollo.  
  
 Con <xref:System.Windows.Controls.Page>, puede implementar mediante declaración una página navegable de contenido [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] utilizando marcado como el siguiente.  
  
 [!code-xml[NavigationOverviewSnippets#Page1XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page1.xaml#page1xaml)]  
  
 Un objeto <xref:System.Windows.Controls.Page> que se implementa en marcado [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] tiene `Page` como su elemento raíz y requiere la declaración de espacio de nombres [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)][!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)].  El elemento `Page` incluye el contenido al que desea navegar y que desea mostrar.  El contenido se agrega estableciendo el elemento de propiedad `Page.Content`, como se muestra en el marcado siguiente.  
  
 [!code-xml[NavigationOverviewSnippets#Page2XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page2.xaml#page2xaml)]  
  
 ¡`Page.Content` sólo puede contener un elemento secundario; en el ejemplo anterior, el contenido es una sola cadena, "Hello, Page\!". En la práctica, utilizará normalmente un control de diseño como elemento secundario \(vea [Diseño](../../../../docs/framework/wpf/advanced/layout.md)\) para incluir y crear el contenido.  
  
 Se considera que los elementos secundarios de un elemento `Page` son el contenido de <xref:System.Windows.Controls.Page> y, por tanto, no necesita utilizar la declaración `Page.Content` explícita.  El siguiente marcado es el equivalente declarativo del ejemplo anterior.  
  
 [!code-xml[NavigationOverviewSnippets#Page3XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page3.xaml#page3xaml)]  
  
 En este caso, `Page.Content` se establece automáticamente con los elementos secundarios del elemento `Page`.  Para obtener más información, vea [Modelo de contenido de WPF](../../../../docs/framework/wpf/controls/wpf-content-model.md).  
  
 Un objeto <xref:System.Windows.Controls.Page> de sólo marcado sirve para mostrar contenido.  Sin embargo, un objeto <xref:System.Windows.Controls.Page> puede mostrar también controles que permitan a los usuarios interactuar con la página, y puede responder a la interacción del usuario controlando eventos y la lógica de la aplicación de llamada.  Un objeto <xref:System.Windows.Controls.Page> interactivo se implementa mediante una combinación de marcado y código subyacente, como se muestra en el ejemplo siguiente.  
  
 [!code-xml[XBAPAppDefSnippets#HomePageMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml#homepagemarkup)]  
  
 [!code-csharp[XBAPAppDefSnippets#HomePageCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml.cs#homepagecodebehind)]
 [!code-vb[XBAPAppDefSnippets#HomePageCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/HomePage.xaml.vb#homepagecodebehind)]  
  
 Para permitir que un archivo de marcado y un archivo de código subyacente funcionen conjuntamente, se requiere la siguiente configuración:  
  
-   En el marcado, el elemento `Page` debe incluir el atributo `x:Class`.  Al generar la aplicación, la existencia de `x:Class` en el archivo de marcado permite que [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] cree una clase `partial` que se derive de <xref:System.Windows.Controls.Page>y tenga el nombre especificado por el atributo `x:Class`.  Para ello, es necesario agregar una declaración de espacio de nombres [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] para el esquema [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] \(`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`\).  La clase `partial` generada implementa `InitializeComponent`, al que se llama para registrar los eventos y establecer las propiedades que se implementan en el marcado.  
  
-   En el archivo de código subyacente, la clase debe ser una clase `partial` con el mismo nombre que el que especificó el atributo `x:Class` en el marcado, y debe derivarse de <xref:System.Windows.Controls.Page>.  Esto permite que el archivo de código subyacente se asocie a la clase `partial` que se genera para el archivo de marcado cuando se compila la aplicación \(vea [Compilar una aplicación de WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)\).  
  
-   En el archivo de código subyacente, la clase <xref:System.Windows.Controls.Page> debe implementar un constructor que llame al método `InitializeComponent`.  La clase `InitializeComponent` se implementa mediante la clase `partial` generada del archivo de marcado para registrar eventos y establecer las propiedades que se definen en el marcado.  
  
> [!NOTE]
>  Al agregar un nuevo objeto <xref:System.Windows.Controls.Page> a su proyecto con [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], se implementa <xref:System.Windows.Controls.Page> utilizando el marcado y el código subyacente; este control incluye la configuración necesaria para crear la asociación entre los archivos de código subyacente y de marcado tal como aquí se describe.  
  
 Cuando ya tenga un objeto <xref:System.Windows.Controls.Page>, podrá navegar a él.  Para especificar el primer objeto <xref:System.Windows.Controls.Page> al que navega una aplicación, necesita configurar el objeto <xref:System.Windows.Controls.Page> de inicio.  
  
<a name="Configuring_a_Start_Page"></a>   
### Configurar una página principal  
 Las [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] exigen que una determinada cantidad de infraestructura de la aplicación esté hospedada en un explorador.  En [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], la clase <xref:System.Windows.Application> forma parte de una definición de aplicación que establece la infraestructura de aplicación necesaria \(vea [Información general sobre la administración de aplicaciones](../../../../docs/framework/wpf/app-development/application-management-overview.md)\).  
  
 Una definición de aplicación se suele implementar mediante marcado y código subyacente, con el archivo de marcado configurado como un elemento `ApplicationDefinition` de [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]. A continuación se ofrece una definición de aplicación para [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  
  
 [!code-xml[XBAPAppDefSnippets#XBAPApplicationDefinitionMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]  
  
 [!code-csharp[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml.cs#xbapapplicationdefinitioncodebehind)]
 [!code-vb[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/Application.xaml.vb#xbapapplicationdefinitioncodebehind)]  
  
 Una [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] puede utilizar su definición de aplicación para especificar un objeto <xref:System.Windows.Controls.Page> de inicio, que es el objeto <xref:System.Windows.Controls.Page> que se carga automáticamente cuando se inicia la [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  Para ello, se establece la propiedad <xref:System.Windows.Application.StartupUri%2A> con el [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] del objeto <xref:System.Windows.Controls.Page> deseado.  
  
> [!NOTE]
>  Normalmente, el objeto <xref:System.Windows.Controls.Page> se compila o se implementa con una aplicación.  En tales casos, el [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que identifica un objeto <xref:System.Windows.Controls.Page>es un pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], que es un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] compatible con el esquema *pack*.  El paquete [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] se describe más detalladamente en [Empaquetar URI en WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md). También puede navegar al contenido mediante el esquema http, que se describe a continuación.  
  
 Puede establecer <xref:System.Windows.Application.StartupUri%2A> mediante declaración en el marcado, como se muestra en el ejemplo siguiente.  
  
 [!code-xml[NavigationOverviewSnippets#XBAPApplicationDefinitionMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]  
  
 En este ejemplo, el atributo `StartupUri` se establece con un pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] relativo que identifica HomePage.xaml.  Cuando se inicia [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], se navega automáticamente a HomePage.xaml y se muestra.  Esto se muestra en la ilustración siguiente, en la que se inicia una [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] desde un servidor web.  
  
 ![Página XBAP](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure9.png "NavigationOverviewFigure9")  
  
> [!NOTE]
>  Para obtener más información relacionada con el desarrollo y la implementación de [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], vea [Información general sobre las aplicaciones de explorador XAML de WPF](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md) y [Implementar una aplicación de WPF](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md).  
  
<a name="ConfiguringAXAMLPage"></a>   
### Configurar el título, ancho y alto de la ventana host  
 Es posible que haya advertido que en la figura anterior el título del explorador y del panel de fichas es el [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] de la [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  Además de largo, el título no tiene un aspecto atractivo ni aporta información.  Por este motivo, <xref:System.Windows.Controls.Page> proporciona un modo de cambiar el título estableciendo la propiedad <xref:System.Windows.Controls.Page.WindowTitle%2A>.  Asimismo, puede configurar el ancho y alto de la ventana del explorador estableciendo <xref:System.Windows.Controls.Page.WindowWidth%2A> y <xref:System.Windows.Controls.Page.WindowHeight%2A>, respectivamente.  
  
 Puede establecer <xref:System.Windows.Controls.Page.WindowTitle%2A>, <xref:System.Windows.Controls.Page.WindowWidth%2A> y <xref:System.Windows.Controls.Page.WindowHeight%2A> mediante declaración en el marcado, como se muestra en el ejemplo siguiente.  
  
 [!code-xml[NavigationOverviewSnippets#HomePageMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/HomePage.xaml#homepagemarkup)]  
  
 El resultado se muestra en la ilustración siguiente.  
  
 ![Título, alto y ancho de ventana](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure2.png "NavigationOverviewFigure2")  
  
<a name="NavigatingBetweenXAMLPages"></a>   
### Navegación por hipervínculos  
 Una [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] típica comprende varias páginas.  La manera más simple de navegar de una página a otra es utilizar un objeto <xref:System.Windows.Documents.Hyperlink>.  Puede agregar mediante declaración un objeto <xref:System.Windows.Documents.Hyperlink>a <xref:System.Windows.Controls.Page> utilizando el elemento `Hyperlink`, que se muestra en el marcado siguiente.  
  
 [!code-xml[NavigationOverviewSnippets#HyperlinkXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]  
[!code-xml[NavigationOverviewSnippets#HyperlinkXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]  
[!code-xml[NavigationOverviewSnippets#HyperlinkXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]  
  
 Un elemento `Hyperlink` requiere lo siguiente:  
  
-   El pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] del objeto <xref:System.Windows.Controls.Page> al que se va navegar, especificado por el atributo `NavigateUri`.  
  
-   El contenido en el que un usuario puede hacer clic para iniciar la navegación, como texto e imágenes \(para saber qué contenido se puede incluir en el elemento `Hyperlink`, vea <xref:System.Windows.Documents.Hyperlink>\).  
  
 En la ilustración siguiente se muestra una [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] con <xref:System.Windows.Controls.Page> que tiene un objeto <xref:System.Windows.Documents.Hyperlink>.  
  
 ![Página con hipervínculo](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure3.png "NavigationOverviewFigure3")  
  
 Como era de prever, al hacer clic en <xref:System.Windows.Documents.Hyperlink> [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] se desplaza al control <xref:System.Windows.Controls.Page>, identificado por el atributo `NavigateUri`.  Además, la [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] agrega una entrada para el objeto <xref:System.Windows.Controls.Page> anterior a la lista Páginas recientes de [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)].  Este comportamiento se muestra en la ilustración siguiente.  
  
 ![Botones Atrás y Adelante](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure4.png "NavigationOverviewFigure4")  
  
 Además de permitir la navegación de un objeto <xref:System.Windows.Controls.Page> a otro, <xref:System.Windows.Documents.Hyperlink> admite la navegación por fragmentos.  
  
<a name="FragmentNavigation"></a>   
### Navegación por fragmentos  
 La *navegación por fragmentos* es la navegación a un fragmento de contenido en el objeto <xref:System.Windows.Controls.Page> u otro objeto <xref:System.Windows.Controls.Page>.  En [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], un fragmento de contenido es el contenido incluido en un elemento con nombre.  Un elemento con nombre es un elemento que tiene establecido su atributo `Name`.  En el marcado siguiente se muestra un elemento `TextBlock` con nombre que contiene un fragmento de contenido.  
  
 [!code-xml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup1)]  
[!code-xml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup2)]  
[!code-xml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup3)]  
  
 Para que un objeto <xref:System.Windows.Documents.Hyperlink> navegue a un fragmento de contenido, el atributo `NavigateUri` debe incluir lo siguiente:  
  
-   El [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] del objeto <xref:System.Windows.Controls.Page> con el fragmento de contenido al que se va a navegar.  
  
-   Un carácter "\#".  
  
-   El nombre del elemento del objeto <xref:System.Windows.Controls.Page> que contiene el fragmento de contenido.  
  
 Un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] de fragmento tiene el siguiente formato.  
  
 *PageURI* `#` *ElementName*  
  
 A continuación, se muestra un ejemplo de un objeto `Hyperlink` configurado para navegar a un fragmento de contenido.  
  
 [!code-xml[NavigationOverviewSnippets#PageThatNavigatesXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml1)]  
[!code-xml[NavigationOverviewSnippets#PageThatNavigatesXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml2)]  
[!code-xml[NavigationOverviewSnippets#PageThatNavigatesXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml3)]  
  
> [!NOTE]
>  En esta sección se describe la implementación de navegación por fragmentos predeterminada en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] permite también implementar un esquema de navegación por fragmentos propio, que requiere parcialmente que se controle el evento <xref:System.Windows.Navigation.NavigationService.FragmentNavigation?displayProperty=fullName>.  
  
> [!IMPORTANT]
>  Sólo puede navegar a fragmentos en páginas [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] independientes \(archivos de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de sólo marcado con `Page` como elemento raíz\) si las páginas se pueden examinar mediante [!INCLUDE[TLA2#tla_http](../../../../includes/tla2sharptla-http-md.md)].  
>   
>  Sin embargo, una página [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] independiente puede navegar a sus propios fragmentos.  
  
<a name="NavigationService"></a>   
### Servicio de navegación  
 Aunque <xref:System.Windows.Documents.Hyperlink> permite que un usuario inicie la navegación en un objeto <xref:System.Windows.Controls.Page> determinado, la clase <xref:System.Windows.Navigation.NavigationService> es la encargada de buscar y descargar la página.  Básicamente, <xref:System.Windows.Navigation.NavigationService> proporciona la capacidad de procesar una solicitud de navegación en nombre de código cliente, como <xref:System.Windows.Documents.Hyperlink>.  Además, <xref:System.Windows.Navigation.NavigationService> implementa la compatibilidad de nivel superior para realizar el seguimiento y dirigir las solicitudes de navegación.  
  
 Al hacer clic en <xref:System.Windows.Documents.Hyperlink>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] llama a <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=fullName> para buscar y descargar el objeto <xref:System.Windows.Controls.Page> en el pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] especificado.  El objeto <xref:System.Windows.Controls.Page> descargado se convierte en un árbol de objetos cuyo objeto raíz es una instancia del objeto <xref:System.Windows.Controls.Page> descargado.  En la propiedad <xref:System.Windows.Navigation.NavigationService.Content%2A?displayProperty=fullName> se almacena una referencia al objeto <xref:System.Windows.Controls.Page> raíz.  El pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] del contenido al que se navegó se almacena en la propiedad <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=fullName>, mientras que <xref:System.Windows.Navigation.NavigationService.CurrentSource%2A?displayProperty=fullName> almacena el pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] de la última página a la que se navegó.  
  
> [!NOTE]
>  Es posible que una aplicación de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] tenga más de un objeto <xref:System.Windows.Navigation.NavigationService> actualmente activo.  Para obtener más información, vea [Hosts de navegación](#Navigation_Hosts) más adelante en este tema.  
  
<a name="Programmatic_Navigation_with_the_Navigation_Service"></a>   
### Navegación mediante programación con el servicio de navegación  
 No necesita conocer <xref:System.Windows.Navigation.NavigationService> si la navegación se implementa mediante declaración en el marcado utilizando <xref:System.Windows.Documents.Hyperlink>, porque <xref:System.Windows.Documents.Hyperlink> utiliza <xref:System.Windows.Navigation.NavigationService> en su nombre.  Esto significa que, siempre y cuando el elemento primario directo o indirecto de <xref:System.Windows.Documents.Hyperlink> sea un host de navegación \(vea [Hosts de navegación](#Navigation_Hosts)\), <xref:System.Windows.Documents.Hyperlink> podrá buscar y utilizar el servicio de navegación del host de desplazamiento para procesar una solicitud de navegación.  
  
 Sin embargo, hay situaciones en las que tendrá que usar <xref:System.Windows.Navigation.NavigationService> directamente, como las siguientes:  
  
-   Cuando tenga que crear una instancia de <xref:System.Windows.Controls.Page> utilizando un constructor no predeterminado.  
  
-   Cuando tenga que establecer propiedades en el objeto <xref:System.Windows.Controls.Page> antes de navegar a él.  
  
-   Cuando el objeto <xref:System.Windows.Controls.Page> al que hay que navegar sólo pueda determinarse en tiempo de ejecución.  
  
 En estas situaciones, deberá escribir código para iniciar la navegación mediante programación llamando al método <xref:System.Windows.Navigation.NavigationService.Navigate%2A> del objeto <xref:System.Windows.Navigation.NavigationService>.  Para ello, es necesario obtener una referencia a un objeto <xref:System.Windows.Navigation.NavigationService>.  
  
#### Obtener una referencia a NavigationService  
 Por los motivos explicados en la sección [Hosts de navegación](#Navigation_Hosts), una aplicación de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] puede tener más de un objeto <xref:System.Windows.Navigation.NavigationService>.  Esto significa que el código necesita un modo de encontrar <xref:System.Windows.Navigation.NavigationService>, que normalmente es el objeto <xref:System.Windows.Navigation.NavigationService> que navegó al control <xref:System.Windows.Controls.Page> actual. Puede obtener una referencia a <xref:System.Windows.Navigation.NavigationService> llamando al método `static` <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A?displayProperty=fullName>.  Para obtener el objeto <xref:System.Windows.Navigation.NavigationService> que navegó a un objeto <xref:System.Windows.Controls.Page> determinado, tendrá que pasar una referencia al objeto <xref:System.Windows.Controls.Page> como argumento del método <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A>.  En el ejemplo de código siguiente se muestra cómo obtener el <xref:System.Windows.Navigation.NavigationService> para el objeto <xref:System.Windows.Controls.Page> actual.  
  
 [!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind1)]  
[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPage.xaml.vb#getnscodebehind2)]  
  
 Para simplificar la búsqueda de un <xref:System.Windows.Navigation.NavigationService> para un objeto <xref:System.Windows.Controls.Page>, <xref:System.Windows.Controls.Page> implementa la propiedad <xref:System.Windows.Controls.Page.NavigationService%2A>.  El ejemplo siguiente muestra esta opción.  
  
 [!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind1)]  
[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPageShortCut.xaml.vb#getnsshortcutcodebehind2)]  
  
> [!NOTE]
>  Un objeto <xref:System.Windows.Controls.Page> sólo puede obtener una referencia a su <xref:System.Windows.Navigation.NavigationService> cuando <xref:System.Windows.Controls.Page> provoca el evento <xref:System.Windows.FrameworkElement.Loaded>.  
  
#### Navegación mediante programación a un objeto Page  
 En el ejemplo siguiente se muestra cómo utilizar el objeto <xref:System.Windows.Navigation.NavigationService> para navegar a un objeto <xref:System.Windows.Controls.Page> mediante programación.  Se requiere la navegación mediante programación porque sólo se puede crear una instancia del control <xref:System.Windows.Controls.Page> al que se navega mediante un constructor no predeterminado.  El objeto <xref:System.Windows.Controls.Page> con el constructor no predeterminado se muestra en el siguiente marcado y código.  
  
 [!code-xml[NavigationOverviewSnippets#PageWithNonDefaultConstructorXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml#pagewithnondefaultconstructorxaml)]  
  
 [!code-csharp[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml.cs#pagewithnondefaultconstructorcodebehind)]
 [!code-vb[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithNonDefaultConstructor.xaml.vb#pagewithnondefaultconstructorcodebehind)]  
  
 El objeto <xref:System.Windows.Controls.Page> que navega al objeto <xref:System.Windows.Controls.Page> con el constructor no predeterminado se muestra en el siguiente marcado y código.  
  
 [!code-xml[NavigationOverviewSnippets#NSNavigationPageXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml#nsnavigationpagexaml)]  
  
 [!code-csharp[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml.cs#nsnavigationpagecodebehind)]
 [!code-vb[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSNavigationPage.xaml.vb#nsnavigationpagecodebehind)]  
  
 Al hacer clic en el objeto <xref:System.Windows.Documents.Hyperlink> de este <xref:System.Windows.Controls.Page>, se inicia la navegación mediante la creación de una instancia del objeto <xref:System.Windows.Controls.Page> al que se va a navegar con el constructor no predeterminado y llamando al método <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=fullName>.  <xref:System.Windows.Navigation.NavigationService.Navigate%2A> acepta una referencia al objeto al que va a navegar el <xref:System.Windows.Navigation.NavigationService>, en lugar de un pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
#### Navegación mediante programación con un pack URI  
 Si necesita crear un Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] mediante programación \(por ejemplo, cuando sólo pueda determinar el Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] en tiempo de ejecución\), puede utilizar el método <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=fullName>.  El ejemplo siguiente muestra esta opción.  
  
 [!code-xml[NavigationOverviewSnippets#NSUriNavigationPageXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml#nsurinavigationpagexaml)]  
  
 [!code-csharp[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml.cs#nsurinavigationpagecodebehind)]
 [!code-vb[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSUriNavigationPage.xaml.vb#nsurinavigationpagecodebehind)]  
  
#### Actualiza la página actual  
 Un objeto <xref:System.Windows.Controls.Page> no se descarga si tiene el mismo pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que el pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] almacenado en la propiedad <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=fullName>.  Para forzar a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] a que descargue de nuevo la página actual, puede llamar al método <xref:System.Windows.Navigation.NavigationService.Refresh%2A?displayProperty=fullName>, como se muestra en el ejemplo siguiente.  
  
 [!code-xml[NavigationOverviewSnippets#NSRefreshNavigationPageXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml#nsrefreshnavigationpagexaml1)]  
  
 [!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind1)]
 [!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind1)]  
[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind2)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind2)]  
  
<a name="Navigation_Lifetime"></a>   
### Duración de la navegación  
 Como puede ver, hay muchas formas de iniciar la navegación.  Cuando se inicia la navegación, y mientras la navegación está en curso, puede controlar y dirigir la navegación mediante los eventos siguientes implementados por <xref:System.Windows.Navigation.NavigationService>:  
  
-   <xref:System.Windows.Navigation.NavigationService.Navigating>.  Se produce cuando se solicita una nueva navegación.  Se puede utilizar para cancelar la navegación.  
  
-   <xref:System.Windows.Navigation.NavigationService.NavigationProgress>.  Se produce periódicamente durante una descarga para proporcionar información sobre el progreso de navegación.  
  
-   <xref:System.Windows.Navigation.NavigationService.Navigated>.  Se produce cuando la página se ha encontrado y descargado.  
  
-   <xref:System.Windows.Navigation.NavigationService.NavigationStopped>.  Se produce cuando se detiene la navegación \(llamando al método <xref:System.Windows.Navigation.NavigationService.StopLoading%2A>\), o cuando se solicita una nueva navegación mientras la navegación actual está en curso.  
  
-   <xref:System.Windows.Navigation.NavigationService.NavigationFailed>.  Se provoca cuando se produce un error al navegar al contenido solicitado.  
  
-   <xref:System.Windows.Navigation.NavigationService.LoadCompleted>.  Se produce cuando se ha cargado, se ha analizado y se ha empezado a presentar el contenido al que se navegó.  
  
-   <xref:System.Windows.Navigation.NavigationService.FragmentNavigation>.  Se produce cuando se inicia la navegación a un fragmento de contenido, que tiene lugar:  
  
    -   Inmediatamente, si el fragmento deseado está en el contenido actual.  
  
    -   Una vez cargado el contenido de origen, si el fragmento deseado está en contenido diferente.  
  
 Los eventos de navegación se provocan en el orden que se indica en la siguiente ilustración.  
  
 ![Gráfico de flujo de navegación de páginas](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure11.png "NavigationOverviewFigure11")  
  
 En general, los objetos <xref:System.Windows.Controls.Page> no tienen que ocuparse de estos eventos.  Es más probable que una aplicación tenga que ocuparse de ellos, razón por la cual la clase <xref:System.Windows.Application> provoca también estos eventos:  
  
-   <xref:System.Windows.Application.Navigating?displayProperty=fullName>  
  
-   <xref:System.Windows.Application.NavigationProgress?displayProperty=fullName>  
  
-   <xref:System.Windows.Application.Navigated?displayProperty=fullName>  
  
-   <xref:System.Windows.Application.NavigationFailed?displayProperty=fullName>  
  
-   <xref:System.Windows.Application.NavigationStopped?displayProperty=fullName>  
  
-   <xref:System.Windows.Application.LoadCompleted?displayProperty=fullName>  
  
-   <xref:System.Windows.Application.FragmentNavigation?displayProperty=fullName>  
  
 Cada vez que <xref:System.Windows.Navigation.NavigationService> genera un evento, la clase <xref:System.Windows.Application> genera el evento correspondiente.  <xref:System.Windows.Controls.Frame> y <xref:System.Windows.Navigation.NavigationWindow> ofrecen los mismos eventos para detectar la navegación dentro de sus ámbitos respectivos.  
  
 En algunos casos, un objeto <xref:System.Windows.Controls.Page> podría tener que ocuparse de estos eventos.  Por ejemplo, un objeto <xref:System.Windows.Controls.Page> podría controlar el evento <xref:System.Windows.Navigation.NavigationService.Navigating?displayProperty=fullName> para determinar si debe cancelar o no la navegación fuera del propio objeto.  El ejemplo siguiente muestra esta opción.  
  
 [!code-xml[NavigationOverviewSnippets#CancelNavigationPageXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml#cancelnavigationpagexaml)]  
  
 [!code-csharp[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml.cs#cancelnavigationpagecodebehind)]
 [!code-vb[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/CancelNavigationPage.xaml.vb#cancelnavigationpagecodebehind)]  
  
 Si registra un controlador con un evento de navegación desde un objeto <xref:System.Windows.Controls.Page>, como en el ejemplo anterior, también debe cancelar el registro del controlador de eventos.  Si no lo hace, se podrían producir efectos secundarios relacionados con el modo en que la navegación de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] recuerda la navegación de <xref:System.Windows.Controls.Page> a través del diario.  
  
<a name="NavigationHistory"></a>   
### Recordar la navegación con el diario  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] utiliza dos pilas para recordar las páginas desde las que se ha navegado: una pila de retroceso y una pila de avance.  Al navegar desde el objeto <xref:System.Windows.Controls.Page>actual a un nuevo objeto <xref:System.Windows.Controls.Page> o avanzar a un objeto <xref:System.Windows.Controls.Page>existente, el objeto <xref:System.Windows.Controls.Page> actual se agrega a la *pila de retroceso*.  Al retroceder desde el objeto <xref:System.Windows.Controls.Page> al objeto <xref:System.Windows.Controls.Page> anterior, el objeto <xref:System.Windows.Controls.Page> se agrega a la *pila de avance*.  La pila de retroceso, la pila de avance y las funciones para administrar estas pilas reciben en conjunto el nombre de diario.  Cada elemento de la pila de retroceso y de la pila de avance es una instancia de la clase <xref:System.Windows.Navigation.JournalEntry> y se hace referencia a él como una *entrada del diario*.  
  
#### Navegar por el diario desde Internet Explorer  
 Conceptualmente, el diario funciona de la misma manera que los botones **Atrás** y **Adelante** de [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)].  Este comportamiento se muestra en la siguiente ilustración.  
  
 ![Botones Atrás y Adelante](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure4.png "NavigationOverviewFigure4")  
  
 Para las [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] hospedadas por [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] integra el diario en la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de navegación de [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)].  Esto permite a los usuarios navegar por las páginas de [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] utilizando los botones **Atrás**, **Adelante** y **Páginas recientes** de [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]. El diario no se integra en [!INCLUDE[TLA2#tla_ie6](../../../../includes/tla2sharptla-ie6-md.md)] de la misma manera que para [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)] o Internet Explorer 8.  En lugar de ello, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] representa una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de navegación alternativa.  
  
> [!IMPORTANT]
>  En [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], cuando un usuario sale y vuelve a una [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], sólo se conservan en el diario las entradas de las páginas que no se mantuvieron activas.  Para obtener una explicación sobre el mantenimiento activo de las páginas, vea [Duración y diario de páginas](#PageLifetime) más adelante en este tema.  
  
 De forma predeterminada, el texto de cada <xref:System.Windows.Controls.Page> que aparece en la lista **Páginas recientes** de [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] es el [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] de <xref:System.Windows.Controls.Page>.  En muchos casos, esto no le resulta particularmente significativo al usuario.  Afortunadamente, puede cambiar el texto mediante una las opciones siguientes:  
  
1.  El valor del atributo `JournalEntry.Name` asociado.  
  
2.  El valor del atributo `Page.Title`.  
  
3.  El valor del atributo `Page.WindowTitle` y el [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] del objeto <xref:System.Windows.Controls.Page> actual.  
  
4.  El [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] del objeto <xref:System.Windows.Controls.Page> actual.  \(Valor predeterminado\)  
  
 El orden en que se indican las opciones es el mismo que el orden de prioridad de la búsqueda de texto.  Por ejemplo, si se establece `JournalEntry.Name`, se omiten los demás valores.  
  
 En el ejemplo siguiente se utiliza el atributo `Page.Title` para cambiar el texto que aparece para una entrada del diario.  
  
 [!code-xml[NavigationOverviewSnippets#PageTitleMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup1)]  
[!code-xml[NavigationOverviewSnippets#PageTitleMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup2)]  
  
 [!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind1)]
 [!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind1)]  
[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind2)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind2)]  
  
#### Navegar por el diario mediante WPF  
 Aunque un usuario puede navegar por el diario mediante los botones **Atrás**, **Adelante** y **Páginas recientes** de [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], también puede utilizar para tal fin los mecanismos declarativos y de programación proporcionados por [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  Esto puede ser necesario, por ejemplo, para proporcionar una [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] de navegación personalizada en sus páginas.  
  
 Puede permitir mediante declaración la navegación por el diario utilizando los comandos de navegación expuestos por <xref:System.Windows.Input.NavigationCommands>.  En el siguiente ejemplo se muestra cómo utilizar el comando de navegación `BrowseBack`.  
  
 [!code-xml[NavigationOverviewSnippets#NavigationCommandsPageXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml1)]  
[!code-xml[NavigationOverviewSnippets#NavigationCommandsPageXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml2)]  
[!code-xml[NavigationOverviewSnippets#NavigationCommandsPageXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml3)]  
[!code-xml[NavigationOverviewSnippets#NavigationCommandsPageXAML4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml4)]  
  
 Puede navegar por el diario mediante programación utilizando alguno de los miembros siguientes de la clase <xref:System.Windows.Navigation.NavigationService>:  
  
-   <xref:System.Windows.Navigation.NavigationService.GoBack%2A>  
  
-   <xref:System.Windows.Navigation.NavigationService.GoForward%2A>  
  
-   <xref:System.Windows.Navigation.NavigationService.CanGoBack%2A>  
  
-   <xref:System.Windows.Navigation.NavigationService.CanGoForward%2A>  
  
 El diario se puede manipular también mediante programación, como se describe en [Conservar el estado del contenido con un historial de navegación](#RetainingContentStateWithNavigationHistory) más adelante en este tema.  
  
<a name="PageLifetime"></a>   
### Duración y diario de páginas  
 Considere una [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] con varias páginas que hospedan contenido avanzado, como gráficos, animación y elementos multimedia.  La superficie de memoria para páginas como estas podría ser bastante grande, sobre todo si se utilizan elementos multimedia de audio y vídeo.  Como el diario "recuerda" las páginas a las que se ha navegado, una [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] podría utilizar una cantidad considerable de memoria rápidamente.  
  
 Por esta razón, el comportamiento predeterminado del diario es almacenar los metadatos de <xref:System.Windows.Controls.Page> en cada entrada del diario en lugar de una referencia a un objeto <xref:System.Windows.Controls.Page>.  Cuando se navega a una entrada del diario, se utilizan sus metadatos de <xref:System.Windows.Controls.Page> para crear una nueva instancia del objeto <xref:System.Windows.Controls.Page>especificado.  Por consiguiente, cada objeto <xref:System.Windows.Controls.Page> visitado tiene la duración que se muestra en la siguiente ilustración.  
  
 ![Duración de la página](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure10.PNG "NavigationOverviewFigure10")  
  
 Aunque el uso del comportamiento del diario predeterminado puede ahorrar memoria, podría dar lugar a una reducción del rendimiento de la representación de cada página, ya que crear una nueva instancia de un objeto <xref:System.Windows.Controls.Page> puede ser laborioso, especialmente si tiene mucho contenido.  Si necesita conservar una instancia de <xref:System.Windows.Controls.Page> en el diario, puede utilizar dos técnicas para ello.  En primer lugar, puede navegar mediante programación a un objeto <xref:System.Windows.Controls.Page> llamando al método <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=fullName>.  
  
 En segundo lugar, puede especificar que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] conserve una instancia de <xref:System.Windows.Controls.Page> en el diario estableciendo la propiedad <xref:System.Windows.Controls.Page.KeepAlive%2A> en `true` \(el valor predeterminado es `false`\).  Como se muestra en el ejemplo siguiente, puede establecer <xref:System.Windows.Controls.Page.KeepAlive%2A> mediante declaración en el marcado.  
  
 [!code-xml[NavigationOverviewSnippets#KeepAlivePageXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/KeepAlivePage.xaml#keepalivepagexaml)]  
  
 La duración de un objeto <xref:System.Windows.Controls.Page> que se mantiene activo es ligeramente diferente al de uno inactivo.  La primera vez que se navega a un objeto <xref:System.Windows.Controls.Page> que se mantiene activo, se crea una instancia de dicho objeto, como ocurre con un objeto <xref:System.Windows.Controls.Page> que no se mantiene activo.  Sin embargo, como se conserva una instancia de <xref:System.Windows.Controls.Page> en el diario, no se vuelve a crear nunca más una nueva instancia mientras ésta permanezca en el diario.  Por tanto, si un objeto <xref:System.Windows.Controls.Page> contiene lógica de inicialización a la que hay que llamar cada vez que se navega a <xref:System.Windows.Controls.Page>, deberá mover esa lógica del constructor a un controlador del evento <xref:System.Windows.FrameworkElement.Loaded>.  Como se muestra en la ilustración siguiente, los eventos <xref:System.Windows.FrameworkElement.Loaded> y <xref:System.Windows.FrameworkElement.Unloaded> se provocan igualmente cada vez que se navega a y desde un objeto <xref:System.Windows.Controls.Page>, respectivamente.  
  
 ![Cuándo se provocan los eventos Loaded y Unloaded](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure17.png "NavigationOverviewFigure17")  
  
 Cuando un objeto <xref:System.Windows.Controls.Page> no se mantiene activo, no debe realizar ninguna de las operaciones siguientes:  
  
-   Almacenar una referencia al objeto o a alguna parte del mismo.  
  
-   Registrar controladores de eventos con eventos no implementados por el objeto.  
  
 Si realiza alguna de estas operaciones, creará referencias que obliguen al objeto <xref:System.Windows.Controls.Page> a conservarse en memoria, incluso después de que se quite del diario.  
  
 En general, debería optar por el comportamiento <xref:System.Windows.Controls.Page> predeterminado, que no mantiene el objeto <xref:System.Windows.Controls.Page> activo.  Sin embargo, este comportamiento tiene implicaciones que afectan al estado, descritas en la siguiente sección.  
  
<a name="RetainingContentStateWithNavigationHistory"></a>   
### Conservar el estado del contenido con el historial de navegación  
 Si un objeto <xref:System.Windows.Controls.Page> no se mantiene activo y tiene controles que recopilan datos del usuario, ¿qué ocurre con los datos si un usuario avanza y retrocede al objeto <xref:System.Windows.Controls.Page>?  Desde la perspectiva de la experiencia del usuario, el usuario debe esperar ver los datos que especificó previamente.  Desgraciadamente, como se crea una nueva instancia de <xref:System.Windows.Controls.Page> con cada navegación, se crean nuevas instancias de los controles que recopilaron los datos y los datos se pierden.  
  
 Por fortuna, el diario proporciona compatibilidad para recordar los datos durante la navegación por <xref:System.Windows.Controls.Page>, incluidos los datos de los controles.  En concreto, la entrada del diario de cada <xref:System.Windows.Controls.Page> actúa como un contenedor temporal para el estado de <xref:System.Windows.Controls.Page> asociado.  En los pasos siguientes se explica brevemente cómo funciona esta compatibilidad cuando se navega desde un objeto <xref:System.Windows.Controls.Page>:  
  
1.  Se agrega una entrada del objeto <xref:System.Windows.Controls.Page> actual al diario.  
  
2.  El estado del objeto <xref:System.Windows.Controls.Page> se almacena con la entrada del diario de esa página, que se agrega a la pila de retroceso.  
  
3.  Se navega al nuevo objeto <xref:System.Windows.Controls.Page>.  
  
 Cuando se retrocede al objeto <xref:System.Windows.Controls.Page>, gracias al diario, se producen las siguientes operaciones:  
  
1.  Se crea una instancia de <xref:System.Windows.Controls.Page> \(la entrada superior del diario en la pila de retroceso\).  
  
2.  El objeto <xref:System.Windows.Controls.Page> se actualiza con el estado que se almacenó con la entrada del diario para el objeto <xref:System.Windows.Controls.Page>.  
  
3.  Se retrocede al objeto <xref:System.Windows.Controls.Page>.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] utiliza automáticamente esta compatibilidad cuando se utilizan los controles siguientes en un objeto <xref:System.Windows.Controls.Page>:  
  
-   <xref:System.Windows.Controls.CheckBox>  
  
-   <xref:System.Windows.Controls.ComboBox>  
  
-   <xref:System.Windows.Controls.Expander>  
  
-   <xref:System.Windows.Controls.Frame>  
  
-   <xref:System.Windows.Controls.ListBox>  
  
-   <xref:System.Windows.Controls.ListBoxItem>  
  
-   <xref:System.Windows.Controls.MenuItem>  
  
-   <xref:System.Windows.Controls.ProgressBar>  
  
-   <xref:System.Windows.Controls.RadioButton>  
  
-   <xref:System.Windows.Controls.Slider>  
  
-   <xref:System.Windows.Controls.TabControl>  
  
-   <xref:System.Windows.Controls.TabItem>  
  
-   <xref:System.Windows.Controls.TextBox>  
  
 Si un objeto <xref:System.Windows.Controls.Page> utiliza estos controles, los datos registrados en ellos se recuerdan durante la navegación por <xref:System.Windows.Controls.Page>, como se muestra en **Favorite color**<xref:System.Windows.Controls.ListBox> en la ilustración siguiente.  
  
 ![Página con controles que recuerdan el estado](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure13.png "NavigationOverviewFigure13")  
  
 Cuando un objeto <xref:System.Windows.Controls.Page> tiene controles distintos de los de la lista anterior, o cuando el estado se almacena en objetos personalizados, debe escribir código que permita al diario recordar el estado durante la navegación por <xref:System.Windows.Controls.Page>.  
  
 Si necesita recordar pequeños segmentos de estado durante la navegación por <xref:System.Windows.Controls.Page>, puede utilizar propiedades de dependencia \(vea <xref:System.Windows.DependencyProperty>\) que se configuran con el marcador de metadatos de <xref:System.Windows.FrameworkPropertyMetadata.Journal%2A?displayProperty=fullName>.  
  
 Si el estado que el objeto <xref:System.Windows.Controls.Page> necesita recordar durante la navegación consta de varios segmentos de datos, puede resultarle más sencillo encapsular el estado en una clase única e implementar la interfaz <xref:System.Windows.Navigation.IProvideCustomContentState>.  
  
 Si necesita desplazarse por varios estados de un mismo objeto <xref:System.Windows.Controls.Page>, sin navegar desde el propio objeto <xref:System.Windows.Controls.Page>, puede utilizar <xref:System.Windows.Navigation.IProvideCustomContentState> y <xref:System.Windows.Navigation.NavigationService.AddBackEntry%2A?displayProperty=fullName>.  
  
<a name="Cookies"></a>   
### Cookies  
 Otro modo en que las aplicaciones de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] pueden almacenar datos es mediante cookies, que se crean, actualizan y eliminan con los métodos <xref:System.Windows.Application.SetCookie%2A> y <xref:System.Windows.Application.GetCookie%2A>.  Las cookies que puede crear en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] son las mismas cookies que utilizan otros tipos de aplicaciones web; las cookies son segmentos arbitrarios de datos que almacena una aplicación en un equipo cliente durante una o varias sesiones.  Los datos de las cookies normalmente son pares de nombre y valor con el formato siguiente.  
  
 *Nombre* `=` *Valor*  
  
 Cuando se pasan los datos a <xref:System.Windows.Application.SetCookie%2A>, junto con el <xref:System.Uri> de la ubicación para la que se debe establecer la cookie, se crea una cookie en memoria, y sólo está disponible durante la sesión de la aplicación actual.  Este tipo de cookie se denomina *cookie de sesión*.  
  
 Para almacenar una cookie en varias sesiones de la aplicación, debe agregarse una fecha de expiración a la cookie, con el formato siguiente.  
  
 *NOMBRE* `=` *VALOR* `; expires=DAY, DD-MMM-YYYY HH:MM:SS GMT`  
  
 Una cookie con fecha de expiración se almacena en la carpeta Archivos temporales de Internet de la instalación de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] hasta que la cookie expira.  Este tipo de cookie se denomina *cookie persistente* porque se conserva durante las sesiones de la aplicación.  
  
 Puede recuperar las cookies de sesión y persistentes llamando al método <xref:System.Windows.Application.GetCookie%2A>, pasando el <xref:System.Uri> de la ubicación donde se estableció la cookie con el método <xref:System.Windows.Application.SetCookie%2A>.  
  
 A continuación, se indican algunas de las formas en que se admiten cookies en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]:  
  
-   Las aplicaciones de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] independientes y las [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] pueden crear y administrar cookies.  
  
-   Se puede tener acceso a las cookies creadas por una [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] desde el explorador.  
  
-   Las [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] del mismo dominio pueden crear y compartir cookies.  
  
-   Las [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] y las páginas [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] del mismo dominio pueden crear y compartir cookies.  
  
-   Las cookies se envían cuando las [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] y las páginas [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] independientes crean solicitudes web.  
  
-   Las [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] de alto nivel y las [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] hospedadas en IFRAMES pueden tener acceso a las cookies.  
  
-   La compatibilidad de las cookies en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] es la misma para todos los exploradores compatibles.  
  
-   En [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplica la directiva P3P relacionada con las cookies, especialmente en relación con [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] propias y de otros fabricantes.  
  
<a name="Structured_Navigation"></a>   
### Navegación estructurada  
 Si necesita pasar datos de un objeto <xref:System.Windows.Controls.Page> a otro, puede pasarlos como argumentos a un constructor no predeterminado de <xref:System.Windows.Controls.Page>.  Tenga en cuenta que si utiliza esta técnica, debe mantener el objeto <xref:System.Windows.Controls.Page> activo ya que, de lo contrario, la próxima vez que navegue al objeto <xref:System.Windows.Controls.Page>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] creará una nueva instancia del objeto <xref:System.Windows.Controls.Page> mediante el constructor predeterminado.  
  
 <xref:System.Windows.Controls.Page> puede implementar también propiedades que se establezcan con los datos que debe pasar.  Sin embargo, las cosas se complican cuando un objeto <xref:System.Windows.Controls.Page> tiene que volver a pasar datos al objeto <xref:System.Windows.Controls.Page> que navegó a él.  El problema reside en que la navegación no permite de forma nativa mecanismos que garanticen que se vuelva a un objeto <xref:System.Windows.Controls.Page> una vez abandonado.  Esencialmente, la navegación no admite la semántica de llamada\/devolución.  Para resolver este problema, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] proporciona la clase <xref:System.Windows.Navigation.PageFunction%601>, que se puede utilizar para garantizar que se vuelva a un objeto <xref:System.Windows.Controls.Page> de un modo previsible y estructurado.  Para obtener más información, vea [Información general sobre la navegación estructurada](../../../../docs/framework/wpf/app-development/structured-navigation-overview.md).  
  
<a name="The_NavigationWindow_Class"></a>   
## La clase NavigationWindow  
 Llegados a este punto, ya se han abordado los servicios de navegación que probablemente utilizará con más frecuencia para crear aplicaciones con contenido navegable.  Estos servicios se describen en el contexto de las [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], pero no se limitan a las [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  Los sistemas operativos modernos y las aplicaciones de [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] aprovechan la experiencia de los usuarios con el uso de los exploradores para incorporar una navegación similar a la de un explorador en las aplicaciones independientes. Algunos ejemplos son:  
  
-   **Diccionario de sinónimos de Word**: navegación por opciones de palabras.  
  
-   **Explorador de archivos**: navegación por archivos y carpetas.  
  
-   **Asistentes**: descomposición de una tarea compleja en varias páginas por las que se puede navegar.  Un ejemplo es el Asistente para componentes de Windows que controla la incorporación y eliminación de características de [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)].  
  
 Para incorporar una navegación similar a la de los exploradores en sus aplicaciones independientes, puede usar la clase <xref:System.Windows.Navigation.NavigationWindow>.  <xref:System.Windows.Navigation.NavigationWindow> se deriva de <xref:System.Windows.Window> y la extiende con la misma compatibilidad de navegación que proporciona [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]. Puede utilizar <xref:System.Windows.Navigation.NavigationWindow> como la ventana principal de la aplicación independiente o como una ventana secundaria, como un cuadro de diálogo.  
  
 Para implementar <xref:System.Windows.Navigation.NavigationWindow>, al igual que con la mayoría de las clases de nivel superior de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] \(<xref:System.Windows.Window>, <xref:System.Windows.Controls.Page>, etc.\), se utiliza una combinación de marcado y código subyacente.  El ejemplo siguiente muestra esta opción.  
  
 [!code-xml[IntroToNavNavigationWindowSnippets#NavigationWindowMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml#navigationwindowmarkup)]  
  
 [!code-csharp[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml.cs#navigationwindowcodebehind)]
 [!code-vb[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/MainWindow.xaml.vb#navigationwindowcodebehind)]  
  
 Este código crea un objeto <xref:System.Windows.Navigation.NavigationWindow> que navega automáticamente a un objeto <xref:System.Windows.Controls.Page> \(HomePage.xaml\) cuando se abre <xref:System.Windows.Navigation.NavigationWindow>.  Si <xref:System.Windows.Navigation.NavigationWindow> es la ventana principal de la aplicación, puede utilizar el atributo `StartupUri` para iniciarla.  Esto queda reflejado en el marcado siguiente.  
  
 [!code-xml[IntroToNavNavigationWindowSnippets#AppLaunchNavWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/App.xaml#applaunchnavwindow)]  
  
 En la ilustración siguiente se muestra el objeto <xref:System.Windows.Navigation.NavigationWindow> como la ventana principal de una aplicación independiente.  
  
 ![Ventana principal](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure18.png "NavigationOverviewFigure18")  
  
 En la ilustración, puede ver que <xref:System.Windows.Navigation.NavigationWindow> tiene un título, aunque no se estableció en el código de implementación de <xref:System.Windows.Navigation.NavigationWindow> del ejemplo anterior.  El título se establece mediante la propiedad <xref:System.Windows.Controls.Page.WindowTitle%2A>, que se muestra en el código siguiente.  
  
 [!code-xml[IntroToNavNavigationWindowSnippets#HomePageMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup1)]  
[!code-xml[IntroToNavNavigationWindowSnippets#HomePageMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup2)]  
  
 El establecimiento de las propiedades <xref:System.Windows.Controls.Page.WindowWidth%2A> y <xref:System.Windows.Controls.Page.WindowHeight%2A> afecta también al objeto <xref:System.Windows.Navigation.NavigationWindow>.  
  
 Normalmente, implementará su propio <xref:System.Windows.Navigation.NavigationWindow> cuando necesite personalizar su comportamiento o su apariencia.  Si no es el caso, hay una alternativa más simple.  Si especifica el pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] de un objeto <xref:System.Windows.Controls.Page> como <xref:System.Windows.Application.StartupUri%2A> en una aplicación independiente, <xref:System.Windows.Application> crea automáticamente un objeto <xref:System.Windows.Navigation.NavigationWindow> para hospedar el objeto <xref:System.Windows.Controls.Page>.  Esta operación se muestra en el marcado siguiente.  
  
 [!code-xml[IntroToNavNavigationWindowSnippets#AppLaunchPage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/AnotherApp.xaml#applaunchpage)]  
  
 Si desea que una ventana de la aplicación secundaria como un cuadro de diálogo sea un objeto <xref:System.Windows.Navigation.NavigationWindow>, puede utilizar el código del ejemplo siguiente para abrirla.  
  
 [!code-csharp[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/DialogOwnerWindow.xaml.cs#createnwdialogbox)]
 [!code-vb[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/DialogOwnerWindow.xaml.vb#createnwdialogbox)]  
  
 En la ilustración siguiente se muestra el resultado.  
  
 ![Cuadro de diálogo](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure19.png "NavigationOverviewFigure19")  
  
 Como puede ver, <xref:System.Windows.Navigation.NavigationWindow> muestra los botones **Atrás** y **Adelante** con el formato de [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], que permiten a los usuarios navegar por el diario.  Estos botones proporcionan la misma experiencia del usuario, como se muestra en la ilustración siguiente.  
  
 ![Botones Atrás y Adelante en NavigationWindow](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure20.png "NavigationOverviewFigure20")  
  
 Si sus páginas proporcionan su propia compatibilidad e interfaz de usuario de navegación por el diario, puede ocultar los botones **Atrás** y **Adelante** mostrados por <xref:System.Windows.Navigation.NavigationWindow> estableciendo el valor de la propiedad <xref:System.Windows.Navigation.NavigationWindow.ShowsNavigationUI%2A> en `false`.  
  
 También puede utilizar la compatibilidad de personalización de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] para reemplazar la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] del propio <xref:System.Windows.Navigation.NavigationWindow>.  
  
<a name="Frame_in_Standalone_Applications"></a>   
## La clase Frame  
 Tanto el explorador como <xref:System.Windows.Navigation.NavigationWindow> son ventanas que hospedan contenido navegable.  En algunos casos, las aplicaciones tienen contenido que no necesita hospedarse en una ventana completa.  Este contenido se puede hospedar dentro de otro contenido.  Puede insertar contenido navegable en otro contenido utilizando la clase <xref:System.Windows.Controls.Frame>.  <xref:System.Windows.Controls.Frame> proporciona la misma compatibilidad que <xref:System.Windows.Navigation.NavigationWindow> y [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  
  
 En el ejemplo siguiente se muestra cómo agregar mediante declaración un objeto <xref:System.Windows.Controls.Frame> a <xref:System.Windows.Controls.Page> con el elemento `Frame`.  
  
 [!code-xml[NavigationOverviewSnippets#FrameHostPageXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml1)]  
[!code-xml[NavigationOverviewSnippets#FrameHostPageXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml2)]  
[!code-xml[NavigationOverviewSnippets#FrameHostPageXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml3)]  
  
 Este marcado establece el atributo `Source` del elemento `Frame` con un pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para el <xref:System.Windows.Controls.Page> al que <xref:System.Windows.Controls.Frame> debe navegar inicialmente.  En la ilustración siguiente se muestra una [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] con un objeto <xref:System.Windows.Controls.Page> que tiene un <xref:System.Windows.Controls.Frame> que ha navegado por varias páginas.  
  
 ![Marco que ha navegado entre varias páginas](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure5.png "NavigationOverviewFigure5")  
  
 No sólo tiene que utilizar <xref:System.Windows.Controls.Frame> dentro del contenido de un objeto <xref:System.Windows.Controls.Page>.  También es habitual hospedar un <xref:System.Windows.Controls.Frame> dentro del contenido de un objeto <xref:System.Windows.Window>.  
  
 De forma predeterminada, <xref:System.Windows.Controls.Frame> sólo utiliza su propio diario si no existe ningún otro.  Si un <xref:System.Windows.Controls.Frame> forma parte del contenido que se hospeda dentro de un objeto <xref:System.Windows.Navigation.NavigationWindow> o [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], <xref:System.Windows.Controls.Frame> utiliza el diario que pertenece a <xref:System.Windows.Navigation.NavigationWindow> o [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. Sin embargo, en ocasiones, puede que <xref:System.Windows.Controls.Frame> necesite responsabilizarse de su propio diario.  Sin embargo, en algunas ocasiones, es posible que un objeto <xref:System.Windows.Controls.Frame> tenga que ocuparse de su propio diario.  Esto se muestra en la ilustración siguiente.  
  
 ![Diagrama de marco y página](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure7.png "NavigationOverviewFigure7")  
  
 En este caso, puede configurar el objeto <xref:System.Windows.Controls.Frame> para que utilice su propio diario estableciendo la propiedad <xref:System.Windows.Controls.Frame.JournalOwnership%2A> de <xref:System.Windows.Controls.Frame> en <xref:System.Windows.Navigation.JournalOwnership>.  Esto queda reflejado en el marcado siguiente.  
  
 [!code-xml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml1)]  
[!code-xml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml2)]  
[!code-xml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml3)]  
  
 En la ilustración siguiente se muestra el efecto de navegar dentro de un objeto <xref:System.Windows.Controls.Frame> que utiliza su propio diario.  
  
 ![Marco que usa su propio diario](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure8.png "NavigationOverviewFigure8")  
  
 Observe que es la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de navegación de <xref:System.Windows.Controls.Frame> y no [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], la que muestra las entradas del diario.  
  
> [!NOTE]
>  Si un objeto <xref:System.Windows.Controls.Frame> forma parte del contenido hospedado en <xref:System.Windows.Window>, <xref:System.Windows.Controls.Frame> utiliza su propio diario y, por tanto, presenta su propia [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de navegación.  
  
 Si la experiencia de usuario requiere que un objeto <xref:System.Windows.Controls.Frame> proporcione su propio diario sin mostrar la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de navegación, puede ocultar la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de navegación estableciendo <xref:System.Windows.Controls.Frame.NavigationUIVisibility%2A> en <xref:System.Windows.Visibility>.  Esto queda reflejado en el marcado siguiente.  
  
 [!code-xml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml1)]  
[!code-xml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml2)]  
[!code-xml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml3)]  
  
<a name="Navigation_Hosts"></a>   
## Hosts de navegación  
 <xref:System.Windows.Controls.Frame> y <xref:System.Windows.Navigation.NavigationWindow> son clases que se denominan hosts de navegación.  Un *host de navegación* es una clase que puede navegar a contenido y mostrarlo.  Para tal fin, cada host de navegación utiliza su propio <xref:System.Windows.Navigation.NavigationService> y diario.  La creación básica de un host de navegación se muestra en la ilustración siguiente.  
  
 ![Diagramas de navegador](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure15.png "NavigationOverviewFigure15")  
  
 Básicamente, este host permite que <xref:System.Windows.Navigation.NavigationWindow> y <xref:System.Windows.Controls.Frame> proporcionen la misma compatibilidad de navegación que la que proporciona una [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] cuando se hospeda en el explorador.  
  
 Además de utilizar <xref:System.Windows.Navigation.NavigationService> y un diario, los hosts de navegación implementan los mismos miembros que implementa <xref:System.Windows.Navigation.NavigationService>.  Esto se muestra en la ilustración siguiente.  
  
 ![Diario en un marco y en NavigationWindow](../../../../docs/framework/wpf/app-development/media/naivgationoverviewfigure24.png "NaivgationOverviewFigure24")  
  
 Esto permite programar directamente en ellos la compatibilidad de navegación.  Puede considerar esto si necesita proporcionar una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de navegación personalizada para un control <xref:System.Windows.Controls.Frame> hospedado en <xref:System.Windows.Window>. Además, ambos tipos implementan miembros adicionales, relacionados con la navegación, incluidos `BackStack` \(<xref:System.Windows.Navigation.NavigationWindow.BackStack%2A?displayProperty=fullName>, <xref:System.Windows.Controls.Frame.BackStack%2A?displayProperty=fullName>\) y `ForwardStack` \(<xref:System.Windows.Navigation.NavigationWindow.ForwardStack%2A?displayProperty=fullName>, <xref:System.Windows.Controls.Frame.ForwardStack%2A?displayProperty=fullName>\), que permiten enumerar las entradas del diario en la pila de retroceso y de reenvío, respectivamente.  
  
 Como se indicó anteriormente, puede haber varios diarios en una aplicación.  En la ilustración siguiente se proporciona un ejemplo de esta circunstancia.  
  
 ![Varios diarios dentro de una aplicación](../../../../docs/framework/wpf/app-development/media/naivgationoverviewfigure25.png "NaivgationOverviewFigure25")  
  
<a name="Navigating_to_Content_Other_than_Pages"></a>   
## Navegar a contenido distinto de páginas XAML  
 A lo largo de este tema, se han utilizado <xref:System.Windows.Controls.Page> y [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] de paquete para mostrar las distintas opciones de navegación de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  Sin embargo, un objeto <xref:System.Windows.Controls.Page> compilado en una aplicación no es el único tipo de contenido al que se puede navegar, y las [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] de paquete no constituyen el único modo de identificar contenido.  
  
 Como se muestra en esta sección, puede navegar también a archivos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] independientes, a archivos [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] y a objetos.  
  
<a name="Navigating_to_Loose_XAML_Files"></a>   
### Navegar a archivos XAML independientes  
 Un archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] independiente es un archivo con las características siguientes:  
  
-   Sólo contiene [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] \(es decir, no contiene código\).  
  
-   Tiene una declaración de espacio de nombres adecuada.  
  
-   Tiene la extensión de nombre de archivo .xaml.  
  
 Considere, por ejemplo, el contenido siguiente que está almacenado como un archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] independiente, Person.xaml.  
  
 [!code-xml[NavigationOverviewSnippets#LooseXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Person.xaml#loosexaml)]  
  
 Al hacer doble clic en el archivo, el explorador se abre, se desplaza al contenido y lo muestra.  Este comportamiento se muestra en la ilustración siguiente.  
  
 ![Presentación del contenido del archivo Person.XAML](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure21.png "NavigationOverviewFigure21")  
  
 Puede mostrar un archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] independiente desde los siguientes elementos:  
  
-   Un sitio web en el equipo local, la intranet o Internet.  
  
-   Un recurso compartido de archivos [!INCLUDE[TLA#tla_unc](../../../../includes/tlasharptla-unc-md.md)].  
  
-   El disco local.  
  
 Un archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] independiente se puede agregar a los favoritos del explorador o convertirse en la página principal del explorador.  
  
> [!NOTE]
>  Para obtener más información sobre cómo publicar e iniciar páginas [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] independientes, vea [Implementar una aplicación de WPF](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md).  
  
 Una limitación de los archivos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] independientes es que sólo permiten hospedar contenido que se pueda ejecutar de forma segura en una relación de confianza parcial.  Por ejemplo, `Window` no puede ser el elemento raíz de un archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] independiente.  Para obtener más información, vea [Seguridad de confianza parcial de WPF](../../../../docs/framework/wpf/wpf-partial-trust-security.md).  
  
<a name="Navigating_to_HTML_Files_Using_Frame"></a>   
### Navegar a archivos HTML mediante Frame  
 Como cabe esperar, también es posible navegar a [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)].  Sólo tiene que proporcionar un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que utilice el esquema http.  Por ejemplo, el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] siguiente muestra un objeto <xref:System.Windows.Controls.Frame> que navega a una página [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)].  
  
 [!code-xml[NavigationOverviewSnippets#FrameHtmlNavMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHTMLNavPage.xaml#framehtmlnavmarkup)]  
  
 Para navegar a [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] se requieren permisos especiales.  Por ejemplo, no se puede navegar desde [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] en ejecución en el recinto de seguridad de confianza parcial de la zona de Internet. Para obtener más información, vea [Seguridad de confianza parcial de WPF](../../../../docs/framework/wpf/wpf-partial-trust-security.md).  
  
<a name="Navigating_to_HTML_Files_Using_WebBrowser"></a>   
### Navegar a archivos HTML mediante el control WebBrowser  
 El control <xref:System.Windows.Controls.WebBrowser> admite el hospedaje de documentos [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)], la navegación y la interoperabilidad de script\/código administrado.  Para obtener información detallada acerca del control <xref:System.Windows.Controls.WebBrowser>, vea <xref:System.Windows.Controls.WebBrowser>.  
  
 Al igual que sucede con <xref:System.Windows.Controls.Frame>, para navegar a [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] mediante <xref:System.Windows.Controls.WebBrowser> se necesitan permisos especiales.  Por ejemplo, desde una aplicación de confianza parcial, únicamente puede navegar hasta el [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] que se encuentra en el sitio de origen.  Para obtener más información, vea [Seguridad de confianza parcial de WPF](../../../../docs/framework/wpf/wpf-partial-trust-security.md).  
  
<a name="Navigating_to_Objects"></a>   
### Navegar a objetos personalizados  
 Si tiene datos que están almacenados como objetos personalizados, una manera de mostrar esos datos es crear un objeto <xref:System.Windows.Controls.Page> con contenido enlazado a esos objetos \(vea [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)\).  Si puede prescindir del trabajo adicional que supone crear una página completa para mostrar simplemente los objetos, puede navegar directamente a ellos.  
  
 Considere la clase `Person` que se implementa en el código siguiente.  
  
 [!code-csharp[NavigateToObjectSnippets#PersonClassCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/Person.cs#personclasscode)]
 [!code-vb[NavigateToObjectSnippets#PersonClassCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/Person.vb#personclasscode)]  
  
 Para navegar a ella, llama al método <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A?displayProperty=fullName>, como se muestra en el código siguiente.  
  
 [!code-xml[NavigateToObjectSnippets#PageThatNavsToObject1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject1)]  
[!code-xml[NavigateToObjectSnippets#PageThatNavsToObject2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject2)]  
[!code-xml[NavigateToObjectSnippets#PageThatNavsToObject3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject3)]  
  
 [!code-csharp[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml.cs#pagethatnavstoobjectcodebehind)]
 [!code-vb[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/HomePage.xaml.vb#pagethatnavstoobjectcodebehind)]  
  
 En la ilustración siguiente se muestra el resultado.  
  
 ![Página que navega a una clase](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure22.png "NavigationOverviewFigure22")  
  
 En esta ilustración, puede ver que no se muestra ninguna información útil.  De hecho, el valor que se muestra es el valor devuelto por el método `ToString` para el objeto **Person**; de forma predeterminada, éste es el único valor que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] puede utilizar para representar el objeto.  Podría invalidar el método `ToString` para devolver información más útil, pero seguiría siendo simplemente un valor de cadena.  Una técnica posible que aprovecha las funciones de presentación [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] es usar una plantilla de datos.  Puede implementar una plantilla de datos que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] pueda asociar a un objeto de un tipo determinado.  En el código siguiente se muestra una plantilla de datos para el objeto `Person`.  
  
 [!code-xml[NavigateToObjectSnippets#DataTemplateMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/App.xaml#datatemplatemarkup)]  
  
 Aquí, la plantilla de datos está asociada al tipo `Person` mediante la extensión de marcado `x:Type` del atributo `DataType`.  La plantilla de datos enlaza los elementos `TextBlock` \(vea <xref:System.Windows.Controls.TextBlock>\) a las propiedades de la clase `Person`.  En la ilustración siguiente se muestra el aspecto actualizado del objeto `Person`.  
  
 ![Navegar a una clase que tiene una plantilla de datos](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure23.png "NavigationOverviewFigure23")  
  
 Una ventaja de esta técnica es la coherencia conseguida al ser capaz de reutilizar la plantilla de datos para mostrar los objetos con un aspecto similar en cualquier lugar de la aplicación.  
  
 Para obtener más información sobre las plantillas de datos, vea [Información general sobre plantillas de datos](../../../../docs/framework/wpf/data/data-templating-overview.md).  
  
<a name="Security"></a>   
## Seguridad  
 La compatibilidad de navegación de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] permite utilizar las [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] para toda la navegación por Internet, y permite que las aplicaciones hospeden contenido de otros fabricantes.  Para proteger las aplicaciones y a los usuarios de un comportamiento malintencionado, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] proporciona un conjunto de características de seguridad que se describen en [Seguridad](../../../../docs/framework/wpf/security-wpf.md) y [Seguridad de confianza parcial de WPF](../../../../docs/framework/wpf/wpf-partial-trust-security.md).  
  
## Vea también  
 <xref:System.Windows.Application.SetCookie%2A>   
 <xref:System.Windows.Application.GetCookie%2A>   
 [Información general sobre la administración de aplicaciones](../../../../docs/framework/wpf/app-development/application-management-overview.md)   
 [Empaquetar URI en WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)   
 [Información general sobre la navegación estructurada](../../../../docs/framework/wpf/app-development/structured-navigation-overview.md)   
 [Información general sobre topologías de navegación](../../../../docs/framework/wpf/app-development/navigation-topologies-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/app-development/navigation-how-to-topics.md)   
 [Implementar una aplicación de WPF](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)
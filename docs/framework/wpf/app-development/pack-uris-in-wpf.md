---
title: Pack URI en WPF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pack URI scheme [WPF]
- loading embedded resources [WPF]
- URIs (Uniform Resource Identifiers)
- Uniform Resource Identifiers (URIs)
- loading non-resource files
- application management [WPF]
ms.assetid: 43adb517-21a7-4df3-98e8-09e9cdf764c4
caps.latest.revision: 35
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d90345f6c6e44bfdd98d2a1313a36372cdfe8b06
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="pack-uris-in-wpf"></a>Pack URI en WPF
En Windows Presentation Foundation (WPF), [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] se usan para identificar y cargar archivos de muchas maneras, incluido lo siguiente:  
  
-   Especificar el [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] para mostrar cuando una aplicación inicia por primera vez.  
  
-   Cargando imágenes.  
  
-   Navegando a páginas.  
  
-   Cargando archivos de datos no ejecutables.  
  
 Además, [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] puede usarse para identificar y cargar archivos desde una variedad de ubicaciones, incluidos los siguientes:  
  
-   Ensamblado actual.  
  
-   El ensamblado al que se hace referencia.  
  
-   Una ubicación relativa a un ensamblado.  
  
-   El sitio de origen de la aplicación.  
  
 Para proporcionar un mecanismo coherente para identificar y cargar estos tipos de archivos de estas ubicaciones, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aprovecha la extensibilidad de la *esquema de pack URI*. Este tema proporciona información general sobre el esquema, se describe cómo construir pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] para una variedad de escenarios, se describen absolute y relative [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] y [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] resolución, antes de que se muestra cómo utilizar el módulo [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] en ambos marcado y el código.  
  
  
<a name="The_Pack_URI_Scheme"></a>   
## <a name="the-pack-uri-scheme"></a>Esquema de Pack URI  
 El módulo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] esquema utilizado por el [Open Packaging Conventions](http://go.microsoft.com/fwlink/?LinkID=71255) especificación (OPC), que describe un modelo para organizar e identificar contenido. Los elementos clave de este modelo son paquetes y las partes, donde un *paquete* es un contenedor lógico para uno o más lógica *elementos*. La figura siguiente ilustra este concepto.  
  
 ![Diagrama de paquete y elementos](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure1.PNG "WPFPackURISchemeFigure1")  
  
 Para identificar las partes, la especificación de OPC aprovecha la extensibilidad de RFC 2396 (identificadores uniformes de recursos (URI): sintaxis genérica) para definir el módulo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] esquema.  
  
 El esquema especificado por un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] se define por su prefijo; http, ftp y file son ejemplos conocidos. El módulo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] esquema utiliza "pack" como su esquema y contiene dos componentes: autoridad y ruta de acceso. Éste es el formato de un módulo de [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
 Pack: / /*autoridad*/*ruta de acceso*
  
 El *autoridad* especifica el tipo de paquete que contiene un elemento, mientras que la *ruta de acceso* especifica la ubicación de un elemento dentro de un paquete.  
  
 Este concepto se muestra en la ilustración siguiente:  
  
 ![Relación entre paquete, autoridad y ruta de acceso](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure2.PNG "WPFPackURISchemeFigure2")  
  
 Los paquetes y los elementos son análogos a las aplicaciones y los archivos, donde una aplicación (paquete) puede incluir uno o más archivos (elementos), como los siguientes:  
  
-   Archivos de recursos que se compilan en el ensamblado local.  
  
-   Archivos de recursos que se compilan en un ensamblado al que se hace referencia.  
  
-   Archivos de recursos que se compilan en un ensamblado que hace referencia.  
  
-   Archivos de contenido.  
  
-   Archivos de sitio de origen.  
  
 Para obtener acceso a estos tipos de archivos, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] admite dos autoridades: application: / / / y siteoforigin: / / /. La autoridad application:/// identifica los archivos de datos de aplicación que se conocen en tiempo de compilación, incluidos los archivos de recursos y de contenido. La autoridad siteoforigin:/// identifica los archivos de sitio de origen. El ámbito de cada autoridad se muestra en la figura siguiente.  
  
 ![Diagrama de Pack URI](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure4.png "WPFPackURISchemeFigure4")  
  
> [!NOTE]
>  El componente de autoridad de un módulo de [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] está incrustada [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que apunta a un paquete y debe ajustarse a RFC 2396. Además, el carácter "/" se debe reemplazar por el carácter ",", y los caracteres reservados "%" y "?" deben incluirse en secuencias de escape. Consulte la especificación de OPC para detalles.  
  
 Las siguientes secciones explican cómo construir pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] utilizando estas dos autoridades junto con las rutas apropiadas para la identificación de recurso, el contenido y el sitio de los archivos de origen.  
  
<a name="Resource_File_Pack_URIs___Local_Assembly"></a>   
## <a name="resource-file-pack-uris"></a>Pack URI de archivos de recursos  
 Archivos de recursos se configuran como [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Resource` los elementos y se compilan en ensamblados. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] admite la construcción del módulo de [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] que puede usarse para identificar los archivos de recursos que se compilan en el ensamblado local o compila en un ensamblado que se hace referencia desde el ensamblado local.  
  
<a name="Local_Assembly_Resource_File"></a>   
### <a name="local-assembly-resource-file"></a>Archivo de recursos del ensamblado local  
 El módulo de [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para un recurso de archivo que se compila en el ensamblado local utiliza la siguiente autoridad y ruta de acceso:  
  
-   **Autoridad**: application:///.  
  
-   **Ruta de acceso**: nombre del archivo de recursos, incluida su ruta de acceso relativa a la carpeta raíz del proyecto de ensamblado local.  
  
 En el ejemplo siguiente se muestra el módulo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo de recursos que se encuentra en la raíz de la carpeta del proyecto de ensamblado local.  
  
 `pack://application:,,,/ResourceFile.xaml`  
  
 En el ejemplo siguiente se muestra el módulo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo de recursos que se encuentra en una subcarpeta de la carpeta del proyecto de ensamblado local.  
  
 `pack://application:,,,/Subfolder/ResourceFile.xaml`  
  
<a name="Resource_File_Pack_URIs___Referenced_Assembly"></a>   
### <a name="referenced-assembly-resource-file"></a>Archivo de recursos del ensamblado al que se hace referencia  
 El módulo de [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para un recurso de archivo que se compila en un ensamblado que se hace referencia utiliza la siguiente autoridad y ruta de acceso:  
  
-   **Autoridad**: application:///.  
  
-   **Ruta de acceso**: nombre de un archivo de recursos que se compila en un ensamblado al que se hace referencia. La ruta de acceso debe tener el formato siguiente:  
  
     *NombreCortoDeEnsamblado*{*; Versión*] {*; PublicKey*]; component /*ruta de acceso*  
  
    -   **AssemblyShortName**: nombre corto del ensamblado al que se hace referencia.  
  
    -   **;Version** [opcional]: versión del ensamblado al que se hace referencia y que contiene el archivo de recursos. Se usa cuando hay cargados dos o más ensamblados a los que se hace referencia con el mismo nombre corto.  
  
    -   **;PublicKey** [opcional]: clave pública que se usó para firmar el ensamblado al que se hace referencia. Se usa cuando hay cargados dos o más ensamblados a los que se hace referencia con el mismo nombre corto.  
  
    -   **;component**: especifica que la referencia al ensamblado se hace desde el ensamblado local.  
  
    -   **/Path**: nombre del archivo de recursos, incluida su ruta de acceso relativa a la raíz de la carpeta del proyecto del ensamblado al que se hace referencia.  
  
 En el ejemplo siguiente se muestra el módulo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo de recursos que se encuentra en la raíz de la carpeta del proyecto del ensamblado que se hace referencia.  
  
 `pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml`  
  
 En el ejemplo siguiente se muestra el módulo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo de recursos que se encuentra en una subcarpeta de la carpeta del proyecto del ensamblado que se hace referencia.  
  
 `pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml`  
  
 En el ejemplo siguiente se muestra el módulo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo de recursos que se encuentra en la carpeta raíz de la carpeta del proyecto de un ensamblado que se hace referencia, específico de la versión.  
  
 `pack://application:,,,/ReferencedAssembly;v1.0.0.1;component/ResourceFile.xaml`  
  
 Tenga en cuenta que el módulo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] sintaxis para archivos de recursos de ensamblado que se hace referencia se puede usar únicamente con la aplicación: / / / entidad. Por ejemplo, los siguientes no se admiten en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 `pack://siteoforigin:,,,/SomeAssembly;component/ResourceFile.xaml`  
  
<a name="Content_File_Pack_URIs"></a>   
## <a name="content-file-pack-uris"></a>Pack URI de archivos de contenido  
 El módulo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] de un archivo de contenido utiliza la siguiente autoridad y ruta de acceso:  
  
-   **Autoridad**: application:///.  
  
-   **Ruta de acceso**: nombre del archivo de contenido, incluida su ruta de acceso relativa a la ubicación del sistema de archivos del ensamblado ejecutable principal de la aplicación.  
  
 En el ejemplo siguiente se muestra el módulo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo de contenido, ubicado en la misma carpeta que el ensamblado ejecutable.  
  
 `pack://application:,,,/ContentFile.xaml`  
  
 En el ejemplo siguiente se muestra el módulo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo de contenido, ubicado en una subcarpeta que esté en relación con el ensamblado ejecutable de la aplicación.  
  
 `pack://application:,,,/Subfolder/ContentFile.xaml`  
  
> [!NOTE]
>  No se puede navegar a los archivos de contenido [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)]. El [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] esquema solo admite la navegación a [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] archivos que se encuentran en el sitio de origen.  
  
<a name="The_siteoforigin_____Authority"></a>   
## <a name="site-of-origin-pack-uris"></a>Pack URI de sitio de origen  
 El módulo de [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para un sitio de origen archivo utiliza la siguiente autoridad y ruta de acceso:  
  
-   **Autoridad**: siteoforigin:///.  
  
-   **Ruta de acceso**: nombre del archivo de sitio de origen, incluida su ruta de acceso relativa a la ubicación desde donde se inició el ensamblado ejecutable.  
  
 En el ejemplo siguiente se muestra el módulo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sitio del archivo de origen, almacenado en la ubicación desde la que se inicia el ensamblado ejecutable.  
  
 `pack://siteoforigin:,,,/SiteOfOriginFile.xaml`  
  
 En el ejemplo siguiente se muestra el módulo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sitio del archivo de origen, almacenado en la subcarpeta que es relativa a la ubicación desde la que se inicia el ensamblado ejecutable de la aplicación.  
  
 `pack://siteoforigin:,,,/Subfolder/SiteOfOriginFile.xaml`  
  
<a name="Page_Files"></a>   
## <a name="page-files"></a>Archivos de paginación  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivos que están configurados como [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` elementos se compilan en ensamblados de la misma manera como archivos de recursos. Por lo tanto, [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` elementos pueden identificarse mediante el uso de módulo [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] para archivos de recursos.  
  
 Los tipos de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivos que normalmente están configurados como [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` elementos tienen uno de los siguientes como su elemento raíz:  
  
-   <xref:System.Windows.Window?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Controls.Page?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Navigation.PageFunction%601?displayProperty=nameWithType>  
  
-   <xref:System.Windows.ResourceDictionary?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Documents.FlowDocument?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>  
  
<a name="Absolute_vs_Relative_Pack_URIs"></a>   
## <a name="absolute-vs-relative-pack-uris"></a>Comparación entre Pack URI absolutos y relativos  
 Un módulo completo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] incluye el esquema, la autoridad y la ruta de acceso, y se considera un módulo absoluto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]. Como simplificación para los desarrolladores, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elementos normalmente le permiten establecer los atributos adecuados con un módulo relativo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], que incluye solo la ruta de acceso.  
  
 Por ejemplo, considere el siguiente pack absoluto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] un archivo de recursos en el ensamblado local.  
  
 `pack://application:,,,/ResourceFile.xaml`  
  
 El módulo relativo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que hace referencia a este recurso de archivo sería la siguiente.  
  
 `/ResourceFile.xaml`  
  
> [!NOTE]
>  Porque el sitio de los archivos de origen no están asociados a ensamblados, pueden solo hacer referencia absoluta Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)].  
  
 De forma predeterminada, un módulo relativo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] se considera relativa a la ubicación del marcado o el código que contiene la referencia. Si se usa una barra diagonal inversa inicial, sin embargo, la relación del módulo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] referencia, a continuación, se considera relativa a la raíz de la aplicación. Por ejemplo, considere la estructura de proyecto siguiente.  
  
 `App.xaml`  
  
 `Page2.xaml`  
  
 `\SubFolder`  
  
 `+ Page1.xaml`  
  
 `+ Page2.xaml`  
  
 Si Page1.xaml contiene un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que hace referencia a *raíz*\SubFolder\Page2.xaml, la referencia puede utilizar el siguiente módulo relativo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
 `Page2.xaml`  
  
 Si Page1.xaml contiene un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que hace referencia a *raíz*\Page2.xaml, la referencia puede utilizar el siguiente módulo relativo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
 `/Page2.xaml`  
  
<a name="Pack_URI_Resolution"></a>   
## <a name="pack-uri-resolution"></a>Resolución de Pack URI  
 El formato de módulo [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] hace posible para el módulo [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] para diferentes tipos de archivos que se va a tener la misma apariencia. Por ejemplo, considere el siguiente pack absoluto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
 `pack://application:,,,/ResourceOrContentFile.xaml`  
  
 Este módulo absoluta [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] podría referirse a un archivo de recursos en el ensamblado local o un archivo de contenido. Lo mismo puede decirse de la relación siguiente [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
 `/ResourceOrContentFile.xaml`  
  
 Para determinar el tipo de archivo que un módulo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] hace referencia a, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] resuelve [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] para archivos de recursos en los ensamblados locales y los archivos de contenido mediante la heurística siguiente:  
  
1.  Sondeo de los metadatos del ensamblado para una <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> atributo que coincida con el módulo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
2.  Si el <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> se encuentra el atributo, la ruta de acceso del módulo de [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] hace referencia a un archivo de contenido.  
  
3.  Si el <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> no se encuentra el atributo, el sondeo de los archivos de recursos de conjunto que se compilan en el ensamblado local.  
  
4.  Si un archivo de recursos que coincide con la ruta de acceso del módulo de [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] se encuentra la ruta de acceso del módulo de [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] hace referencia a un archivo de recursos.  
  
5.  Si el recurso no se encuentra, creado internamente <xref:System.Uri> no es válido.  
  
 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] resolución no se aplica a [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] que hacen referencia a lo siguiente:  
  
-   Archivos de contenido en los ensamblados que se hace referencia: estos tipos de archivo no son compatibles con [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
-   Archivos incrustados en ensamblados de referencia: [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] que los identifican son únicos porque incluyen tanto el nombre del ensamblado que se hace referencia y la `;component` sufijo.  
  
-   Sitio de los archivos de origen: [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] que identifican son únicos porque son solo los archivos que se pueden identificar por módulo [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] que contienen el siteoforigin: / / / entidad.  
  
 Simplificación de un módulo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] resolución permite es para que código que sean un poco independientes de las ubicaciones de archivos de recursos y de contenido. Por ejemplo, si tiene un archivo de recursos en el ensamblado local que se vuelve a configurar para que sea un archivo de contenido, el módulo de [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para el recurso sigue siendo el mismo, al igual que el código que usa el módulo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
<a name="Programming_with_Pack_URIs"></a>   
## <a name="programming-with-pack-uris"></a>Programación con Pack URI  
 Muchos [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] clases implementan propiedades que se pueden establecer con el módulo [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], incluido:  
  
-   <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Controls.Frame.Source%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Documents.Hyperlink.NavigateUri%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Window.Icon%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Controls.Image.Source%2A?displayProperty=nameWithType>  
  
 Estas propiedades se pueden establecer tanto desde el marcado como desde el código. En esta sección se muestran las construcciones básicas para ambos y, luego, se muestran ejemplos de escenarios comunes.  
  
<a name="Using_Pack_URIs_in_Markup"></a>   
### <a name="using-pack-uris-in-markup"></a>Uso de los Pack URI en el marcado  
 Un módulo de [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] se especifica en el marcado estableciendo el elemento de un atributo con el módulo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]. Por ejemplo:  
  
 `<element attribute="pack://application:,,,/File.xaml" />`  
  
 Tabla 1 muestra los diversos pack absoluto [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] que puede especificar en el marcado.  
  
 Tabla 1: Pack URI absolutos en el marcado  
  
|Archivo|Módulo absoluta [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|  
|----------|-------------------------------------------------------------------------------------------------------------------------|  
|Archivo de recursos: ensamblado local|`"pack://application:,,,/ResourceFile.xaml"`|  
|Archivo de recursos en subcarpeta: ensamblado local|`"pack://application:,,,/Subfolder/ResourceFile.xaml"`|  
|Archivo de recursos: ensamblado al que se hace referencia|`"pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml"`|  
|Archivo de recursos en subcarpeta del ensamblado al que se hace referencia|`"pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|  
|Archivo de recursos en el ensamblado al que se hace referencia con versiones|`"pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml"`|  
|Archivo de contenido|`"pack://application:,,,/ContentFile.xaml"`|  
|Archivo de contenido en subcarpeta|`"pack://application:,,,/Subfolder/ContentFile.xaml"`|  
|Archivo de sitio de origen|`"pack://siteoforigin:,,,/SOOFile.xaml"`|  
|Archivo de sitio de origen en subcarpeta|`"pack://siteoforigin:,,,/Subfolder/SOOFile.xaml"`|  
  
 Tabla 2 muestra los diversos pack relativo [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] que puede especificar en el marcado.  
  
 Tabla 2: Pack URI relativos en el marcado  
  
|Archivo|Módulo relativa [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|  
|----------|-------------------------------------------------------------------------------------------------------------------------|  
|Archivo de recursos en el ensamblado local|`"/ResourceFile.xaml"`|  
|Archivo de recursos en subcarpeta del ensamblado local|`"/Subfolder/ResourceFile.xaml"`|  
|Archivo de recursos en el ensamblado al que se hace referencia|`"/ReferencedAssembly;component/ResourceFile.xaml"`|  
|Archivo de recursos en subcarpeta del ensamblado al que se hace referencia|`"/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|  
|Archivo de contenido|`"/ContentFile.xaml"`|  
|Archivo de contenido en subcarpeta|`"/Subfolder/ContentFile.xaml"`|  
  
<a name="Using_Pack_URIs_in_Code"></a>   
### <a name="using-pack-uris-in-code"></a>Uso de los Pack URI en el código  
 Especificar un paquete [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] en código creando instancias de la <xref:System.Uri> clase y pasando el módulo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] como un parámetro al constructor. Esto último se muestra en el ejemplo siguiente.  
  
```csharp  
Uri uri = new Uri("pack://application:,,,/File.xaml");  
```  
  
 De forma predeterminada, el <xref:System.Uri> clase considera pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] para ser absolutos. Por lo tanto, se produce una excepción cuando una instancia de la <xref:System.Uri> se crea una clase con un módulo relativo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
```csharp  
Uri uri = new Uri("/File.xaml");  
```  
  
 Afortunadamente, la <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> sobrecarga de la <xref:System.Uri> constructor de clase acepta un parámetro de tipo <xref:System.UriKind> para que pueda especificar si un módulo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] es absoluta o relativa.  
  
```csharp  
// Absolute URI (default)  
Uri absoluteUri = new Uri("pack://application:,,,/File.xaml", UriKind.Absolute);  
// Relative URI  
Uri relativeUri = new Uri("/File.xaml",   
                        UriKind.Relative);  
```  
  
 Sólo se debe especificar <xref:System.UriKind.Absolute> o <xref:System.UriKind.Relative> cuando esté seguro de que el paquete proporcionado [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] es uno de los dos. Si no conoce el tipo de módulo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que se utiliza, por ejemplo, cuando un usuario entra en un módulo de [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] en tiempo de ejecución, use <xref:System.UriKind.RelativeOrAbsolute> en su lugar.  
  
```csharp  
// Relative or Absolute URI provided by user via a text box  
TextBox userProvidedUriTextBox = new TextBox();  
Uri uri = new Uri(userProvidedUriTextBox.Text, UriKind.RelativeOrAbsolute);  
```  
  
 Tabla 3 muestra los diversos pack relativo [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] que puede especificar en el código mediante el uso de <xref:System.Uri?displayProperty=nameWithType>.  
  
 Tabla 3: Pack URI absolutos en el código  
  
|Archivo|Módulo absoluta [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|  
|----------|-------------------------------------------------------------------------------------------------------------------------|  
|Archivo de recursos: ensamblado local|`Uri uri = new Uri("pack://application:,,,/ResourceFile.xaml", UriKind.Absolute);`|  
|Archivo de recursos en subcarpeta: ensamblado local|`Uri uri = new Uri("pack://application:,,,/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|  
|Archivo de recursos: ensamblado al que se hace referencia|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Absolute);`|  
|Archivo de recursos en subcarpeta del ensamblado al que se hace referencia|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|  
|Archivo de recursos en el ensamblado al que se hace referencia con versiones|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml", UriKind.Absolute);`|  
|Archivo de contenido|`Uri uri = new Uri("pack://application:,,,/ContentFile.xaml", UriKind.Absolute);`|  
|Archivo de contenido en subcarpeta|`Uri uri = new Uri("pack://application:,,,/Subfolder/ContentFile.xaml", UriKind.Absolute);`|  
|Archivo de sitio de origen|`Uri uri = new Uri("pack://siteoforigin:,,,/SOOFile.xaml", UriKind.Absolute);`|  
|Archivo de sitio de origen en subcarpeta|`Uri uri = new Uri("pack://siteoforigin:,,,/Subfolder/SOOFile.xaml", UriKind.Absolute);`|  
  
 Tabla 4 muestran los diversos pack relativo [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] que puede especificar en el código mediante <xref:System.Uri?displayProperty=nameWithType>.  
  
 Tabla 4: Pack URI relativos en el código  
  
|Archivo|Módulo relativa [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|  
|----------|-------------------------------------------------------------------------------------------------------------------------|  
|Archivo de recursos: ensamblado local|`Uri uri = new Uri("/ResourceFile.xaml", UriKind.Relative);`|  
|Archivo de recursos en subcarpeta: ensamblado local|`Uri uri = new Uri("/Subfolder/ResourceFile.xaml", UriKind.Relative);`|  
|Archivo de recursos: ensamblado al que se hace referencia|`Uri uri = new Uri("/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Relative);`|  
|Archivo de recursos en subcarpeta: ensamblado al que se hace referencia|`Uri uri = new Uri("/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Relative);`|  
|Archivo de contenido|`Uri uri = new Uri("/ContentFile.xaml", UriKind.Relative);`|  
|Archivo de contenido en subcarpeta|`Uri uri = new Uri("/Subfolder/ContentFile.xaml", UriKind.Relative);`|  
  
<a name="Common_Pack_URI_Scenarios"></a>   
### <a name="common-pack-uri-scenarios"></a>Escenarios comunes de Pack URI  
 En las secciones anteriores se han explicado cómo construir pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] para identificar el recurso, el contenido y el sitio de los archivos de origen. En [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], estas construcciones se usan en una variedad de formas y las secciones siguientes tratan varios usos comunes.  
  
<a name="Specifying_the_UI_to_Show_when_an_Application_Starts"></a>   
#### <a name="specifying-the-ui-to-show-when-an-application-starts"></a>Especificación de la UI que se va a mostrar cuando una aplicación se inicia por primera vez  
 <xref:System.Windows.Application.StartupUri%2A> Especifica el primer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] para mostrar cuándo una [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] se inicia la aplicación. Para aplicaciones independientes, la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] puede ser una ventana, tal como se muestra en el ejemplo siguiente.  
  
 [!code-xaml[PackURIOverviewSnippets#StartupUriWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/Copy of App.xaml#startupuriwindow)]  
  
 Las aplicaciones independientes y [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] también se puede especificar una página como la interfaz de usuario inicial, tal como se muestra en el ejemplo siguiente.  
  
 [!code-xaml[PackURIOverviewSnippets#StartupUriPage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/App.xaml#startupuripage)]  
  
 Si la aplicación es una aplicación independiente y se especifica una página con <xref:System.Windows.Application.StartupUri%2A>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] abre un <xref:System.Windows.Navigation.NavigationWindow> para hospedar la página. Para [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], la página se muestra en el explorador del host.  
  
<a name="Navigating_to_a_Page"></a>   
#### <a name="navigating-to-a-page"></a>Navegación a una página  
 En el ejemplo siguiente se muestra cómo navegar a una página.  
  
 [!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]  
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]  
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]  
  
 Para obtener más información sobre las diversas maneras de navegar por [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], consulte [Navigation Overview](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
<a name="Specifying_a_Window_Icon"></a>   
#### <a name="specifying-a-window-icon"></a>Especificación de un icono de ventana  
 En el ejemplo siguiente se muestra cómo usar un identificador URI para especificar el icono de una ventana.  
  
 [!code-xaml[WindowIconSnippets#WindowIconSetXAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/WindowIconSnippets/XAML/MainWindow.xaml#windowiconsetxaml)]  
  
 Para obtener más información, consulta <xref:System.Windows.Window.Icon%2A>.  
  
<a name="Loading_Image__Audio__and_Video_Files"></a>   
#### <a name="loading-image-audio-and-video-files"></a>Carga de archivos de imagen, audio y vídeo  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] permite que las aplicaciones utilizan una gran variedad de tipos de medios, todos los cuales pueden identificar y cargar Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], tal y como se muestra en los ejemplos siguientes.  
  
 [!code-xaml[MediaPlayerVideoSample#VideoPackURIAtSOO](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerVideoSample/CS/HomePage.xaml#videopackuriatsoo)]  
  
 [!code-xaml[MediaPlayerAudioSample#AudioPackURIAtSOO](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerAudioSample/CS/HomePage.xaml#audiopackuriatsoo)]  
  
 [!code-xaml[ImageSample#ImagePackURIContent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageSample/CS/HomePage.xaml#imagepackuricontent)]  
  
 Para obtener más información sobre cómo trabajar con contenido multimedia, consulte [gráficos y Multimedia](../../../../docs/framework/wpf/graphics-multimedia/index.md).  
  
<a name="Loading_a_Resource_Dictionary_from_the_Site_of_Origin"></a>   
#### <a name="loading-a-resource-dictionary-from-the-site-of-origin"></a>Carga de un diccionario de recursos desde el sitio de origen  
 Los diccionarios de recursos (<xref:System.Windows.ResourceDictionary>) puede utilizarse para admitir los temas de la aplicación. Una forma de crear y administrar temas consiste en crear varios temas como diccionarios de recursos que están ubicados en el sitio de origen de una aplicación. Esto permite agregar temas y actualizarlos sin tener que volver a compilar e implementar una aplicación. Estos diccionarios de recursos se puede identificar y cargar mediante pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], que se muestra en el ejemplo siguiente.  
  
 [!code-xaml[ResourceDictionarySnippets#ResourceDictionaryPackURI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourceDictionarySnippets/CS/App.xaml#resourcedictionarypackuri)]  
  
 Para obtener información general de los temas en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], consulte [estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
## <a name="see-also"></a>Vea también  
 [Archivos de recursos, contenido y datos de aplicaciones de WPF](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)

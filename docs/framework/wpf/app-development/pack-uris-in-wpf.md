---
title: "Empaquetar URI en WPF | Microsoft Docs"
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
  - "administración de aplicaciones [WPF]"
  - "cargar recursos incrustados"
  - "cargar archivos que no son de recursos"
  - "Pack URI (esquema)"
  - "Identificador uniforme de recursos (URI)"
  - "URI (identificador uniforme de recursos)"
ms.assetid: 43adb517-21a7-4df3-98e8-09e9cdf764c4
caps.latest.revision: 35
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 31
---
# Empaquetar URI en WPF
En [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)], se utilizan [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] para identificar y cargar archivos de muchas maneras, incluidas las que figuran a continuación:  
  
-   Especificando la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] que se va a mostrar cuando se inicie una aplicación por primera vez.  
  
-   Cargando imágenes.  
  
-   Navegando a páginas.  
  
-   Cargando archivos de datos no ejecutables.  
  
 Además, se pueden usar [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] para identificar y cargar archivos desde diversas ubicaciones, como las que figuran a continuación:  
  
-   El ensamblado actual.  
  
-   Un ensamblado al que se hace referencia.  
  
-   Una ubicación relativa a un ensamblado.  
  
-   El sitio de origen de la aplicación.  
  
 Para proporcionar un mecanismo coherente para identificar y cargar estos tipos de archivo desde estas ubicaciones, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aprovecha la extensibilidad del *esquema de pack URI*.  En este tema se proporciona información general sobre el esquema, se describe cómo construir pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] para diversos escenarios, se explican los [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] absolutos y relativos y la resolución de [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] antes de mostrar cómo utilizar los pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] tanto desde el marcado como desde el código.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="The_Pack_URI_Scheme"></a>   
## Esquema de pack URI  
 El esquema de pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] se utiliza en la especificación de [Open Packaging Conventions](http://go.microsoft.com/fwlink/?LinkID=71255) \(OPC\), que describe un modelo para organizar e identificar contenido.  Los elementos clave de este modelo son los paquetes y las partes, donde un *paquete* es un contenedor lógico para una o varias *partes* lógicas.  La figura siguiente ilustra este concepto.  
  
 ![Diagrama de paquete y partes](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure1.png "WPFPackURISchemeFigure1")  
  
 Para identificar las partes, la especificación de OPC aprovecha la extensibilidad de RFC 2396 \(Identificadores uniformes de recursos \(URI\): sintaxis genérica\) para definir el esquema de pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
 El esquema especificado por un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] se define por su prefijo; http, ftp y file son ejemplos conocidos.  El esquema de pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] utiliza "pack" como esquema y tiene dos componentes: la autoridad y la ruta de acceso.  A continuación figura el formato de un pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
 pack:\/\/*autoridad*\/*ruta de acceso*  
  
 La *autoridad* especifica el tipo de paquete que contiene una parte, mientras que la *ruta de acceso* especifica la ubicación de una parte dentro de un paquete.  
  
 Este concepto se ilustra en la siguiente figura:  
  
 ![Relación entre paquete, autoridad y ruta de acceso](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure2.png "WPFPackURISchemeFigure2")  
  
 Los paquetes y las partes son análogos a las aplicaciones y los archivos, puesto que una aplicación \(paquete\) puede incluir uno o varios archivos \(partes\), como los siguientes:  
  
-   Archivos de recursos que se compilan en el ensamblado local.  
  
-   Archivos de recursos que se compilan en un ensamblado al que se hace referencia.  
  
-   Archivos de recursos que se compilan en un ensamblado que hace referencia.  
  
-   Archivos de contenido.  
  
-   Archivos de sitio de origen.  
  
 Para obtener acceso a estos tipos de archivo, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] admite dos autoridades: application:\/\/\/ y siteoforigin:\/\/\/.  La autoridad application:\/\/\/ identifica los archivos de datos de aplicación que se conocen en tiempo de compilación, incluidos los archivos de recursos y de contenido.  La autoridad siteoforigin:\/\/\/ identifica los archivos de sitio de origen.  El ámbito de cada autoridad se muestra en la figura siguiente.  
  
 ![Diagrama de URI de paquete](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure4.png "WPFPackURISchemeFigure4")  
  
> [!NOTE]
>  El componente de autoridad de un pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] es un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] incrustado que apunta a un paquete y debe ajustarse a RFC 2396.  Además, el carácter "\/" debe sustituirse por el carácter "," y los caracteres reservados tales como "%" y "?" deben incluirse en secuencias de escape.  Vea la especificación de OPC para obtener información detallada.  
  
 En las secciones siguientes se explica cómo construir pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] utilizando estas dos autoridades junto con las rutas de acceso adecuadas para identificar los archivos de recursos, de contenido y de sitio de origen.  
  
<a name="Resource_File_Pack_URIs___Local_Assembly"></a>   
## Pack URI de archivos de recursos  
 Los archivos de recursos se configuran como elementos [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Resource` y se compilan en ensamblados.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] admite la construcción de pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] que se pueden utilizar para identificar los archivos de recursos compilados en el ensamblado local o compilados en un ensamblado al que se hace referencia desde el ensamblado local.  
  
<a name="Local_Assembly_Resource_File"></a>   
### Archivo de recursos del ensamblado local  
 El pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para un archivo de recursos compilado en el ensamblado local utiliza la siguiente autoridad y ruta de acceso:  
  
-   **Autoridad**: application:\/\/\/.  
  
-   **Ruta de acceso**: nombre del archivo de recursos, incluida su ruta de acceso relativa a la carpeta raíz del proyecto de ensamblado local.  
  
 En el ejemplo siguiente se muestra el pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para un archivo de recursos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que se encuentra en la carpeta raíz del proyecto de ensamblado local.  
  
 `pack://application:,,,/ResourceFile.xaml`  
  
 En el ejemplo siguiente se muestra el pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para un archivo de recursos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que se encuentra en una subcarpeta de la carpeta del proyecto de ensamblado local.  
  
 `pack://application:,,,/Subfolder/ResourceFile.xaml`  
  
<a name="Resource_File_Pack_URIs___Referenced_Assembly"></a>   
### Archivo de recursos del ensamblado al que se hace referencia  
 El pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para un archivo de recursos compilado en un ensamblado al que se hace referencia utiliza la siguiente autoridad y ruta de acceso:  
  
-   **Autoridad**: application:\/\/\/.  
  
-   **Ruta de acceso**: nombre de un archivo de recursos compilado en un ensamblado al que se hace referencia.  La ruta de acceso debe tener el formato siguiente:  
  
     *nombreCortoDeEnsamblado*\[*;Versión*\]\[*;clavePública*\];component\/*rutaDeAcceso*  
  
    -   **nombreCortoDeEnsamblado**: nombre corto del ensamblado al que se hace referencia.  
  
    -   **;Versión** \[opcional\]: versión del ensamblado al que se hace referencia y que contiene el archivo de recursos.  Se utiliza cuando hay cargados dos o más ensamblados a los que se hace referencia con el mismo nombre corto.  
  
    -   **;clavePública** \[opcional\]: clave pública utilizada para firmar el ensamblado al que se hace referencia.  Se utiliza cuando hay cargados dos o más ensamblados a los que se hace referencia con el mismo nombre corto.  
  
    -   **;component**: especifica que la referencia al ensamblado se hace desde el ensamblado local.  
  
    -   **\/rutaDeAcceso**: nombre del archivo de recursos, incluida su ruta de acceso relativa a la carpeta raíz del proyecto del ensamblado al que se hace referencia.  
  
 En el ejemplo siguiente se muestra el pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para un archivo de recursos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que se encuentra en la carpeta raíz del proyecto de ensamblado al que se hace referencia.  
  
 `pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml`  
  
 En el ejemplo siguiente se muestra el pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para un archivo de recursos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que se encuentra en una subcarpeta de la carpeta del proyecto de ensamblado al que se hace referencia.  
  
 `pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml`  
  
 En el ejemplo siguiente se muestra el pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para un archivo de recursos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que se encuentra en la carpeta raíz de un proyecto de ensamblado específico de la versión al que se hace referencia.  
  
 `pack://application:,,,/ReferencedAssembly;v1.0.0.1;component/ResourceFile.xaml`  
  
 Observe que la sintaxis del pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para los archivos de recursos de ensamblado a los que se hace referencia solamente se puede utilizar con la autoridad application:\/\/\/.  Por ejemplo, no se admite lo siguiente en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 `pack://siteoforigin:,,,/SomeAssembly;component/ResourceFile.xaml`  
  
<a name="Content_File_Pack_URIs"></a>   
## Pack URI de archivo de contenido  
 El pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para un archivo de contenido utiliza la siguiente autoridad y ruta de acceso:  
  
-   **Autoridad**: application:\/\/\/.  
  
-   **Ruta de acceso**: nombre del archivo de contenido, incluida su ruta de acceso relativa a la ubicación del sistema de archivos del ensamblado ejecutable principal de la aplicación.  
  
 En el ejemplo siguiente se muestra el pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para un archivo de contenido [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], ubicado en la misma carpeta que el ensamblado ejecutable.  
  
 `pack://application:,,,/ContentFile.xaml`  
  
 En el ejemplo siguiente se muestra el pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para un archivo de contenido [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], situado en una subcarpeta relativa al ensamblado ejecutable de la aplicación.  
  
 `pack://application:,,,/Subfolder/ContentFile.xaml`  
  
> [!NOTE]
>  No se puede navegar a los archivos de contenido [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)].  El esquema de [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] solamente admite la navegación a archivos [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] ubicados en el sitio de origen.  
  
<a name="The_siteoforigin_____Authority"></a>   
## Pack URI de sitio de origen  
 El pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para un archivo de sitio de origen utiliza la siguiente autoridad y ruta de acceso:  
  
-   **Autoridad**: siteoforigin:\/\/\/.  
  
-   **Ruta de acceso**: nombre del archivo de sitio de origen, incluida su ruta de acceso relativa a la ubicación desde la que se inició el ensamblado ejecutable.  
  
 En el ejemplo siguiente se muestra el pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para un archivo de sitio de origen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], almacenado en la ubicación desde la que se inicia el ensamblado ejecutable.  
  
 `pack://siteoforigin:,,,/SiteOfOriginFile.xaml`  
  
 En el ejemplo siguiente se muestra el pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para un archivo de sitio de origen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], almacenado en una subcarpeta relativa a la ubicación desde la que se inicia el ensamblado ejecutable de la aplicación.  
  
 `pack://siteoforigin:,,,/Subfolder/SiteOfOriginFile.xaml`  
  
<a name="Page_Files"></a>   
## Archivos de paginación  
 Los archivos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] configurados como elementos `Page` de [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] se compilan en ensamblados del mismo modo que los archivos de recursos.  Por consiguiente, los elementos `Page` de [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] se pueden identificar mediante los pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] para los archivos de recursos.  
  
 Los tipos de archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que se configuran habitualmente como elementos `Page` de [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] tienen uno de los siguientes elementos como elemento raíz:  
  
-   <xref:System.Windows.Window?displayProperty=fullName>  
  
-   <xref:System.Windows.Controls.Page?displayProperty=fullName>  
  
-   <xref:System.Windows.Navigation.PageFunction%601?displayProperty=fullName>  
  
-   <xref:System.Windows.ResourceDictionary?displayProperty=fullName>  
  
-   <xref:System.Windows.Documents.FlowDocument?displayProperty=fullName>  
  
-   <xref:System.Windows.Controls.UserControl?displayProperty=fullName>  
  
<a name="Absolute_vs_Relative_Pack_URIs"></a>   
## Pack URI absolutosy relativos  
 Un pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] completo incluye el esquema, la autoridad y la ruta de acceso, y se considera un pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] absoluto.  Como simplificación para los desarrolladores, los elementos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] suelen permitir que se establezcan los atributos adecuados con un pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] relativo, que incluye solamente la ruta de acceso.  
  
 Por ejemplo, considere el siguiente pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] absoluto para un archivo de recursos en el ensamblado local.  
  
 `pack://application:,,,/ResourceFile.xaml`  
  
 El pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] relativo que hace referencia a este archivo de recursos sería el siguiente.  
  
 `/ResourceFile.xaml`  
  
> [!NOTE]
>  Dado que los archivos de sitio de origen no están asociados a ensamblados, solamente se puede hacer referencia a ellos con pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] absolutos.  
  
 De forma predeterminada, un pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] relativo se considera relativo a la ubicación del marcado o del código que contiene la referencia.  Sin embargo, si se utiliza una barra diagonal inversa inicial, el pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] relativo se considera relativo a la raíz de la aplicación.  Por ejemplo, considere la estructura de proyecto siguiente.  
  
 `App.xaml`  
  
 `Page2.xaml`  
  
 `\SubFolder`  
  
 `+ Page1.xaml`  
  
 `+ Page2.xaml`  
  
 Si Page1.xaml contiene un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que hace referencia a *Raíz*\\SubFolder\\Page2.xaml, la referencia puede utilizar el siguiente pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
 `Page2.xaml`  
  
 Si Page1.xaml contiene un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que hace referencia a *Raíz*\\Page2.xaml, la referencia puede utilizar el siguiente pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] relativo.  
  
 `/Page2.xaml`  
  
<a name="Pack_URI_Resolution"></a>   
## Resolución de pack URI  
 El formato de los pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] permite que los pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] para diferentes tipos de archivo tengan la misma apariencia.  Por ejemplo, considere el siguiente pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] absoluto.  
  
 `pack://application:,,,/ResourceOrContentFile.xaml`  
  
 Este pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] absoluto podría hacer referencia a un archivo de recursos del ensamblado local o a un archivo de contenido.  Lo mismo se aplica al siguiente [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] relativo.  
  
 `/ResourceOrContentFile.xaml`  
  
 Para determinar el tipo de archivo al que hace referencia un pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] resuelve los [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] para los archivos de recursos en ensamblados locales y los archivos de contenido usando la siguiente heurística:  
  
1.  Sondear los metadatos del ensamblado para buscar un atributo <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> que coincida con el pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
2.  Si se encuentra el atributo <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>, la ruta de acceso del pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] hace referencia a un archivo de contenido.  
  
3.  Si no se encuentra el atributo <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>, sondee los archivos de recursos establecidos que están compilados en el ensamblado local.  
  
4.  Si se encuentra un archivo de recursos que coincida con el pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], la ruta de acceso del pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] hace referencia a un archivo de recursos.  
  
5.  Si no se encuentra el recurso, el <xref:System.Uri> creado internamente no es válido.  
  
 La resolución de [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] no se aplica a los [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] que hacen referencia a los siguientes archivos:  
  
-   Archivos de contenido en ensamblados a los que se hace referencia: [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] no admite estos tipos de archivo.  
  
-   Archivos incrustados en ensamblados a los que se hace referencia: los [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] que los identifican son únicos porque incluyen tanto el nombre del ensamblado al que se hace referencia como el sufijo `;component`.  
  
-   Archivos de sitio de origen: los [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] que los identifican son únicos porque son los únicos archivos que se pueden identificar mediante pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] que contienen la autoridad siteoforigin:\/\/\/.  
  
 Una simplificación que permite la resolución de pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] es que el código sea independiente, hasta cierto punto, de la ubicación de los archivos de recursos y de contenido.  Por ejemplo, si tiene un archivo de recursos en el ensamblado local que se ha reconfigurado para que sea un archivo de contenido, el pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] para el recurso continuará siendo el mismo, al igual que el código que utiliza el pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
<a name="Programming_with_Pack_URIs"></a>   
## Programar con pack URI  
 Muchas clases de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] implementan propiedades que se pueden establecer con pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], como:  
  
-   <xref:System.Windows.Application.StartupUri%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Controls.Frame.Source%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Documents.Hyperlink.NavigateUri%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Window.Icon%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Controls.Image.Source%2A?displayProperty=fullName>  
  
 Estas propiedades se pueden establecer tanto desde marcado como desde código.  En esta sección se muestran las construcciones básicas para ambos y, a continuación, se muestra ejemplos de escenarios comunes.  
  
<a name="Using_Pack_URIs_in_Markup"></a>   
### Utilizar pack URI en el marcado  
 Un pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] se especifica en el marcado estableciendo el elemento de un atributo con el pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  Por ejemplo:  
  
 `<element attribute="pack://application:,,,/File.xaml" />`  
  
 En la tabla 1 se muestran los diversos pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] absolutos que se pueden especificar en el marcado.  
  
 Tabla 1: pack URI absolutos en el marcado  
  
|Archivo|Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] absoluto|  
|-------------|--------------------------------------------------------------------------------|  
|Archivo de recursos: ensamblado local|`"pack://application:,,,/ResourceFile.xaml"`|  
|Archivo de recursos en subcarpeta: ensamblado local|`"pack://application:,,,/Subfolder/ResourceFile.xaml"`|  
|Archivo de recursos: ensamblado al que se hace referencia|`"pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml"`|  
|Archivo de recursos en subcarpeta del ensamblado al que se hace referencia|`"pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|  
|Archivo de recursos en el ensamblado al que se hace referencia con versión|`"pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml"`|  
|Archivo de contenido|`"pack://application:,,,/ContentFile.xaml"`|  
|Archivo de contenido en subcarpeta|`"pack://application:,,,/Subfolder/ContentFile.xaml"`|  
|Archivo de sitio de origen|`"pack://siteoforigin:,,,/SOOFile.xaml"`|  
|Archivo de sitio de origen en subcarpeta|`"pack://siteoforigin:,,,/Subfolder/SOOFile.xaml"`|  
  
 En la tabla 2 se muestran los diversos pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] relativos que se pueden especificar en el marcado.  
  
 Tabla 2: pack URI relativos en el marcado  
  
|Archivo|Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] relativo|  
|-------------|--------------------------------------------------------------------------------|  
|Archivo de recursos en ensamblado local|`"/ResourceFile.xaml"`|  
|Archivo de recursos en subcarpeta del ensamblado local|`"/Subfolder/ResourceFile.xaml"`|  
|Archivo de recursos en ensamblado al que se hace referencia|`"/ReferencedAssembly;component/ResourceFile.xaml"`|  
|Archivo de recursos en subcarpeta del ensamblado al que se hace referencia|`"/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|  
|Archivo de contenido|`"/ContentFile.xaml"`|  
|Archivo de contenido en subcarpeta|`"/Subfolder/ContentFile.xaml"`|  
  
<a name="Using_Pack_URIs_in_Code"></a>   
### Utilizar pack URI en el código  
 Para especificar un pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] en el código, puede crear una instancia de la clase <xref:System.Uri> y pasar el pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] como parámetro al constructor.  Esto último se muestra en el ejemplo siguiente.  
  
```csharp  
Uri uri = new Uri("pack://application:,,,/File.xaml");  
```  
  
 De forma predeterminada, la clase <xref:System.Uri> considera que el pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] es absoluto.  Por consiguiente, se produce una excepción cuando se crea una instancia de la clase <xref:System.Uri> con un pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] relativo.  
  
```csharp  
Uri uri = new Uri("/File.xaml");  
```  
  
 Afortunadamente, la sobrecarga <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> del constructor de clase <xref:System.Uri> acepta un parámetro de tipo <xref:System.UriKind> para permitir que se especifique si un pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] es absoluto o relativo.  
  
```csharp  
// Absolute URI (default)  
Uri absoluteUri = new Uri("pack://application:,,,/File.xaml", UriKind.Absolute);  
// Relative URI  
Uri relativeUri = new Uri("/File.xaml", UriKind.Relative);  
```  
  
 Solamente se debe especificar <xref:System.UriKind> o <xref:System.UriKind> cuando se tiene la seguridad de que el pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] proporcionado es uno u otro.  Si no conoce el tipo de pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que se utiliza, como cuando un usuario escribe un pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] en tiempo de ejecución, utilice <xref:System.UriKind>.  
  
```csharp  
// Relative or Absolute URI provided by user via a text box  
TextBox userProvidedUriTextBox = new TextBox();  
Uri uri = new Uri(userProvidedUriTextBox.Text, UriKind.RelativeOrAbsolute);  
```  
  
 En la tabla 3 se muestran los diversos pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] relativos que se pueden especificar en el código utilizando <xref:System.Uri?displayProperty=fullName>.  
  
 Tabla 3: pack URI absolutos en el código  
  
|Archivo|Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] absoluto|  
|-------------|--------------------------------------------------------------------------------|  
|Archivo de recursos: ensamblado local|`Uri uri = new Uri("pack://application:,,,/ResourceFile.xaml", UriKind.Absolute);`|  
|Archivo de recursos en subcarpeta: ensamblado local|`Uri uri = new Uri("pack://application:,,,/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|  
|Archivo de recursos: ensamblado al que se hace referencia|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Absolute);`|  
|Archivo de recursos en subcarpeta del ensamblado al que se hace referencia|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|  
|Archivo de recursos en el ensamblado al que se hace referencia con versión|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml", UriKind.Absolute);`|  
|Archivo de contenido|`Uri uri = new Uri("pack://application:,,,/ContentFile.xaml", UriKind.Absolute);`|  
|Archivo de contenido en subcarpeta|`Uri uri = new Uri("pack://application:,,,/Subfolder/ContentFile.xaml", UriKind.Absolute);`|  
|Archivo de sitio de origen|`Uri uri = new Uri("pack://siteoforigin:,,,/SOOFile.xaml", UriKind.Absolute);`|  
|Archivo de sitio de origen en subcarpeta|`Uri uri = new Uri("pack://siteoforigin:,,,/Subfolder/SOOFile.xaml", UriKind.Absolute);`|  
  
 En la tabla 4 se muestran los diversos pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] relativos que se pueden especificar en el código utilizando <xref:System.Uri?displayProperty=fullName>.  
  
 Tabla 4: pack URI relativos en el código  
  
|Archivo|Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] relativo|  
|-------------|--------------------------------------------------------------------------------|  
|Archivo de recursos: ensamblado local|`Uri uri = new Uri("/ResourceFile.xaml", UriKind.Relative);`|  
|Archivo de recursos en subcarpeta: ensamblado local|`Uri uri = new Uri("/Subfolder/ResourceFile.xaml", UriKind.Relative);`|  
|Archivo de recursos: ensamblado al que se hace referencia|`Uri uri = new Uri("/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Relative);`|  
|Archivo de recursos en subcarpeta: ensamblado al que se hace referencia|`Uri uri = new Uri("/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Relative);`|  
|Archivo de contenido|`Uri uri = new Uri("/ContentFile.xaml", UriKind.Relative);`|  
|Archivo de contenido en subcarpeta|`Uri uri = new Uri("/Subfolder/ContentFile.xaml", UriKind.Relative);`|  
  
<a name="Common_Pack_URI_Scenarios"></a>   
### Escenarios comunes de pack URI  
 En las secciones anteriores se ha explicado cómo construir pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] para identificar archivos de recursos, de contenido y de sitio de origen.  En [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], estas construcciones se utilizan de diversas maneras. En las secciones siguientes, se abordan varios usos comunes.  
  
<a name="Specifying_the_UI_to_Show_when_an_Application_Starts"></a>   
#### Especificar la interfaz de usuario que se va a mostrar cuando se inicie una aplicación  
 <xref:System.Windows.Application.StartupUri%2A> especifica la primera [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que se va a mostrar cuando se inicie una aplicación [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  En el caso de las aplicaciones independientes, la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] puede ser una ventana, como se muestra en el ejemplo siguiente.  
  
 [!code-xml[PackURIOverviewSnippets#StartupUriWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/Copy of App.xaml#startupuriwindow)]  
  
 Las aplicaciones independientes y las [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] también pueden especificar una página como interfaz de usuario inicial, tal como se muestra en el ejemplo siguiente.  
  
 [!code-xml[PackURIOverviewSnippets#StartupUriPage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/App.xaml#startupuripage)]  
  
 Si la aplicación es una aplicación independiente y hay una página especificada con <xref:System.Windows.Application.StartupUri%2A>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] abre un objeto <xref:System.Windows.Navigation.NavigationWindow> para hospedar la página.  En el caso de las [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], la página se muestra en el explorador del host.  
  
<a name="Navigating_to_a_Page"></a>   
#### Navegar a una página  
 En el ejemplo siguiente se muestra cómo navegar a una página.  
  
 [!code-xml[NavigationOverviewSnippets#HyperlinkXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]  
[!code-xml[NavigationOverviewSnippets#HyperlinkXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]  
[!code-xml[NavigationOverviewSnippets#HyperlinkXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]  
  
 Para obtener más información sobre las diversas maneras de navegar en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], vea [Información general sobre navegación](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
<a name="Specifying_a_Window_Icon"></a>   
#### Especificar un icono de ventana  
 En el ejemplo siguiente se muestra cómo utilizar un URI para especificar el icono de una ventana.  
  
 [!code-xml[WindowIconSnippets#WindowIconSetXAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/WindowIconSnippets/XAML/MainWindow.xaml#windowiconsetxaml)]  
  
 Para obtener más información, vea <xref:System.Windows.Window.Icon%2A>.  
  
<a name="Loading_Image__Audio__and_Video_Files"></a>   
#### Cargar archivos de imagen, audio y vídeo  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] permite a las aplicaciones utilizar una amplia variedad de tipos multimedia, que se pueden identificar y cargar todos con pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], tal como se muestra en los ejemplos siguientes.  
  
 [!code-xml[MediaPlayerVideoSample#VideoPackURIAtSOO](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerVideoSample/CS/HomePage.xaml#videopackuriatsoo)]  
  
 [!code-xml[MediaPlayerAudioSample#AudioPackURIAtSOO](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerAudioSample/CS/HomePage.xaml#audiopackuriatsoo)]  
  
 [!code-xml[ImageSample#ImagePackURIContent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageSample/CS/HomePage.xaml#imagepackuricontent)]  
  
 Para obtener más información sobre cómo trabajar con contenido multimedia, vea [Gráficos y multimedia](../../../../docs/framework/wpf/graphics-multimedia/index.md).  
  
<a name="Loading_a_Resource_Dictionary_from_the_Site_of_Origin"></a>   
#### Cargar un diccionario de recursos desde el sitio de origen  
 Los diccionarios de recursos \(<xref:System.Windows.ResourceDictionary>\) se pueden utilizar para ofrecer compatibilidad con los temas de aplicación.  Una manera de crear y administrar temas consiste en crear varios temas como diccionarios de recursos que se encuentran en el sitio de origen de una aplicación.  Esto permite agregar temas y actualizarlos sin tener que volver a compilar e implementar una aplicación.  Estos diccionarios de recursos se pueden identificar y cargar mediante pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], tal como se muestra en el ejemplo siguiente.  
  
 [!code-xml[ResourceDictionarySnippets#ResourceDictionaryPackURI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourceDictionarySnippets/CS/App.xaml#resourcedictionarypackuri)]  
  
 Para obtener información general sobre los temas en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], vea [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
## Vea también  
 [Archivos de recursos, contenido y datos de aplicaciones de WPF](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)
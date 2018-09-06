---
title: Archivos de recursos, contenido y datos de aplicaciones de WPF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WPF application [WPF], files
- loose resources [WPF]
- content files [WPF]
- Site of Origin files [WPF]
- resource files [WPF]
- remote files [WPF]
- embedded resources [WPF]
- files [WPF]
- referencing application files [WPF]
- application development [WPF], files
- application management [WPF]
ms.assetid: 7ad2943b-3961-41d3-8fc6-1582d43f5d99
ms.openlocfilehash: 5bf1a0e1d4d8f620f83aab50aa50009a0f6a6cf4
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43855977"
---
# <a name="wpf-application-resource-content-and-data-files"></a>Archivos de recursos, contenido y datos de aplicaciones de WPF
[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] las aplicaciones a menudo dependen de los archivos que contienen datos no ejecutable, como [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], imágenes, vídeo y audio. Windows Presentation Foundation (WPF) ofrece una compatibilidad especial para configurar, identificar y usar estos tipos de archivos de datos, que se denominan archivos de datos de aplicación. Esta compatibilidad gira en torno a un conjunto específico de tipos de archivo de datos de aplicación, entre los que se incluyen:  
  
-   **Archivos de recursos**: archivos de datos que se compilan en un archivo ejecutable o biblioteca [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ensamblado.  
  
-   **Archivos de contenido**: archivos de datos independientes que tienen una asociación explícita con un archivo ejecutable [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ensamblado.  
  
-   **Sitio de archivos de origen**: archivos de datos independientes que no tienen ninguna asociación con un archivo ejecutable [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ensamblado.  
  
 Una diferencia importante entre estos tres tipos de archivos es que tanto los archivos de recursos como los archivos de contenido se conocen en el momento de la compilación; un ensamblado tiene un conocimiento explícito de ellos. Para archivos de sitio de origen, sin embargo, un ensamblado puede tener ningún conocimiento de ellos, o un conocimiento implícito a través de un paquete [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] referencia; en el caso de que el último caso, no hay ninguna garantía de que el sitio del archivo de origen que se hace referencia existe realmente.  
  
 Para hacer referencia a archivos de datos de aplicación, Windows Presentation Foundation (WPF) usa el módulo [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] esquema, que se describe detalladamente en [Pack URI en WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)).  
  
 En este tema se describe cómo configurar y usar archivos de datos de aplicaciones.  
  
  
<a name="Resource_Files"></a>   
## <a name="resource-files"></a>Archivos de recursos  
 Si un archivo de datos de la aplicación debe estar siempre disponible para una aplicación, la única forma de garantizar la disponibilidad es compilarlo en el ensamblado ejecutable principal de una aplicación o en uno de sus ensamblados referenciados. Este tipo de archivo de datos de aplicación se conoce como un *archivo de recursos*.  
  
 Los archivos de recursos se deben usar cuando:  
  
-   No es necesario actualizar el contenido del archivo de recursos después de que se compila en un ensamblado.  
  
-   Desea simplificar la complejidad de la distribución de una aplicación mediante la reducción del número de dependencias de los archivos.  
  
-   El archivo de datos de la aplicación debe ser localizable (vea [WPF Globalization and Localization Overview](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)).  
  
> [!NOTE]
>  Los archivos de recursos que se describen en esta sección son diferentes de los archivos de recursos se describen en [recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md) y diferentes de los recursos incrustados o vinculados que se describe en [administrar aplicación de recursos (. NET) ](https://msdn.microsoft.com/library/f2582734-8ada-4baa-8a7c-e2ef943ddf7e).  
  
### <a name="configuring-resource-files"></a>Configuración de archivos de recursos  
 En [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], un archivo de recursos es un archivo que se incluye en un [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] proyecto como un `Resource` elemento.  
  
```xml  
<Project "xmlns=http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Resource Include="ResourceFile.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  En [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], cree un archivo de recursos mediante la adición de un archivo a un proyecto y su `Build Action` a `Resource`.  
  
 Cuando se compila el proyecto, [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] compila el recurso en el ensamblado.  
  
### <a name="using-resource-files"></a>Uso de archivos de recursos  
 Para cargar un archivo de recursos, puede llamar a la <xref:System.Windows.Application.GetResourceStream%2A> método de la <xref:System.Windows.Application> (clase), pasando un pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que identifica el archivo de recurso deseado. <xref:System.Windows.Application.GetResourceStream%2A> Devuelve un <xref:System.Windows.Resources.StreamResourceInfo> objeto, que expone el archivo de recursos como un <xref:System.IO.Stream> y describe su tipo de contenido.  
  
 Por ejemplo, el código siguiente muestra cómo usar <xref:System.Windows.Application.GetResourceStream%2A> para cargar un <xref:System.Windows.Controls.Page> recursos de archivos y establecerlo como contenido de un <xref:System.Windows.Controls.Frame> (`pageFrame`):  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 Durante la llamada a <xref:System.Windows.Application.GetResourceStream%2A> proporciona acceso a la <xref:System.IO.Stream>, deberá realizar el trabajo adicional de convertirlo en el tipo de la propiedad que se establecerá con. En su lugar, puede dejar que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] se encargan de abrir y convertir la <xref:System.IO.Stream> cargando un archivo de recursos directamente en la propiedad de un tipo mediante código.  
  
 El ejemplo siguiente muestra cómo cargar un <xref:System.Windows.Controls.Page> directamente en un <xref:System.Windows.Controls.Frame> (`pageFrame`) mediante código.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 El ejemplo siguiente es el equivalente de marcación del ejemplo anterior.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### <a name="application-code-files-as-resource-files"></a>Archivos de código de aplicación como archivos de recursos  
 Un conjunto especial de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] pueden hacer referencia a los archivos de código de aplicación mediante el módulo [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], incluidos windows, páginas, documentos dinámicos y diccionarios de recursos. Por ejemplo, puede establecer el <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> propiedad con un módulo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que hace referencia a la ventana o página que le gustaría cargar cuando se inicia una aplicación.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 Puede hacerlo cuando una [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo está incluido en un [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] proyecto como un `Page` elemento.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Page Include="MainWindow.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  En [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], se agrega un nuevo <xref:System.Windows.Window>, <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.FlowDocument>, o <xref:System.Windows.ResourceDictionary> a un proyecto, el `Build Action` el marcado archivo valor predeterminado es `Page`.  
  
 Cuando un proyecto con `Page` elementos se compila, el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elementos se convierten a formato binario y se compilan en el ensamblado asociado. Por consiguiente, estos archivos se pueden utilizar de la misma forma que los archivos de recursos típicos.  
  
> [!NOTE]
>  Si un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo está configurado como un `Resource` de elemento y no tiene un archivo de código subyacente, sin formato [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se compila en un ensamblado en lugar de una versión binaria sin formato [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
<a name="Content_Files"></a>   
## <a name="content-files"></a>Archivos de contenido  
 Un *archivo de contenido* se distribuye como un archivo dinámico junto a un ensamblado ejecutable. Aunque no se compilan en un ensamblado, los ensamblados se compilan con metadatos que establecen una asociación con cada archivo de contenido.  
  
 Los archivos de contenido se deben usar cuando la aplicación requiere un conjunto específico de archivos de datos de aplicación que desee poder actualizar sin volver a compilar el ensamblado que los consume.  
  
### <a name="configuring-content-files"></a>Configuración de archivos de contenido  
 Para agregar un archivo de contenido a un proyecto, se debe incluir como un archivo de datos de la aplicación un `Content` elemento. Además, dado que no se compila un archivo de contenido directamente en el ensamblado, debe establecer el [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `CopyToOutputDirectory` metadatos de elemento para especificar que el archivo de contenido se copia en una ubicación que es relativa al ensamblado generado. Si desea que el recurso que se va a copiar en la carpeta de salida de compilación cada vez se compila un proyecto, establecer el `CopyToOutputDirectory` elemento de metadatos con el `Always` valor. En caso contrario, puede asegurarse de que solo la versión más reciente del recurso se copia en la carpeta de salida de compilación mediante la `PreserveNewest` valor.  
  
 A continuación muestra un archivo que se configura como un archivo de contenido que se copia en la carpeta de salida de compilación solo cuando se agrega al proyecto una nueva versión del recurso.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Content Include="ContentFile.xaml">  
      <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
    </Content>  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  En [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], cree un archivo de contenido mediante la adición de un archivo a un proyecto y su `Build Action` a `Content`y establezca su `Copy to Output Directory` a `Copy always` (igual que `Always`) y `Copy if newer` (igual que `PreserveNewest`).  
  
 Cuando se compila el proyecto, un <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> atributo se compila en los metadatos del ensamblado para cada archivo de contenido.  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 El valor de la <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> implica la ruta de acceso al archivo de contenido en relación con su posición en el proyecto. Por ejemplo, si un archivo de contenido se encontraba en una subcarpeta del proyecto, la información de ruta de acceso adicional se incorporaría el <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> valor.  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 El <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> valor también es el valor de la ruta de acceso al archivo de contenido en la carpeta de salida de compilación.  
  
### <a name="using-content-files"></a>Uso de archivos de contenido  
 Para cargar un archivo de contenido, puede llamar a la <xref:System.Windows.Application.GetContentStream%2A> método de la <xref:System.Windows.Application> (clase), pasando un pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que identifica el archivo de contenido deseado. <xref:System.Windows.Application.GetContentStream%2A> Devuelve un <xref:System.Windows.Resources.StreamResourceInfo> objeto, que expone el archivo de contenido como un <xref:System.IO.Stream> y describe su tipo de contenido.  
  
 Por ejemplo, el código siguiente muestra cómo usar <xref:System.Windows.Application.GetContentStream%2A> para cargar un <xref:System.Windows.Controls.Page> archivo de contenido y establecerlo como contenido de un <xref:System.Windows.Controls.Frame> (`pageFrame`).  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 Durante la llamada a <xref:System.Windows.Application.GetContentStream%2A> proporciona acceso a la <xref:System.IO.Stream>, deberá realizar el trabajo adicional de convertirlo en el tipo de la propiedad que se establecerá con. En su lugar, puede dejar que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] se encargan de abrir y convertir la <xref:System.IO.Stream> cargando un archivo de recursos directamente en la propiedad de un tipo mediante código.  
  
 El ejemplo siguiente muestra cómo cargar un <xref:System.Windows.Controls.Page> directamente en un <xref:System.Windows.Controls.Frame> (`pageFrame`) mediante código.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 El ejemplo siguiente es el equivalente de marcación del ejemplo anterior.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>   
## <a name="site-of-origin-files"></a>Sitio de archivos de origen  
 Archivos de recursos tienen una relación explícita con los ensamblados que se distribuyen, tal como se define por la <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>. Sin embargo, hay veces en las que puede desear establecer una relación implícita o inexistente entre un ensamblado y un archivo de datos de aplicación, incluyendo cuándo:  
  
-   No existe un archivo en tiempo de compilación.  
  
-   No sabe qué archivos requerirá el ensamblado hasta el tiempo de ejecución.  
  
-   Desea poder actualizar los archivos sin volver a compilar el ensamblado al que están asociados.  
  
-   La aplicación utiliza archivos de datos grandes, como audio y vídeo, y solo desea que los usuarios los descarguen si eligen hacerlo.  
  
 Es posible cargar estos tipos de archivos mediante el uso de tradicionales [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] esquemas, como los esquemas file:/// y http://.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 Sin embargo, los esquemas file:/// y http:// requieren que la aplicación tenga plena confianza. Si la aplicación es un [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] que se inició desde Internet o intranet y solicita solo el conjunto de permisos que se permiten para las aplicaciones iniciadas desde esas ubicaciones, solo se pueden cargar archivos separados del sitio de la aplicación de origen ( ubicación de inicio). Estos archivos se denominan *sitio de origen* archivos.  
  
 Los archivos del sitio de origen son la única opción para las aplicaciones de confianza parcial, aunque no se limitan a ese tipo de aplicaciones. Es posible que las aplicaciones de plena confianza aún necesiten cargar archivos de datos de aplicación que desconocen en tiempo de compilación; mientras que las aplicaciones de plena confianza pueden utilizar file:///, es probable que los archivos de datos de la aplicación se instalarán en la misma carpeta que el ensamblado de la aplicación, o en una subcarpeta de él. En este caso, es más sencillo usar la referencia del sitio de origen que file:///, ya que el uso de file:/// requiere que se determine la ruta de acceso completa del archivo.  
  
> [!NOTE]
>  Sitio de origen no se almacenan en caché los archivos con un [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] en un equipo cliente, mientras que son archivos de contenido. Por consiguiente, sólo se descargan cuando se solicita específicamente. Si un [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] aplicación tiene archivos multimedia grandes, configurarlos como sitio de archivos de origen significa que el inicio de la aplicación es mucho más rápido y solo se descargan los archivos a petición.  
  
### <a name="configuring-site-of-origin-files"></a>Configuración de archivos de sitio de origen  
 Si su sitio de archivos de origen es inexistentes o desconocido en tiempo de compilación, deberá usar la implementación tradicional mecanismos para garantizar los archivos necesarios están disponibles en tiempo de ejecución, incluido el uso de cualquiera el `XCopy` programa de línea de comandos o el [!INCLUDE[TLA#tla_wininstall](../../../../includes/tlasharptla-wininstall-md.md)].  
  
 Si conoce en tiempo de compilación de los archivos que lo haría que se encuentren en el sitio de origen, pero todavía desea evitar una dependencia explícita, puede agregar dichos archivos a un [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] como `None` elemento. Como en los archivos de contenido, debe establecer el [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `CopyToOutputDirectory` atributo para especificar que el archivo de sitio de origen se copia en una ubicación que es relativa al ensamblado generado, especificando el `Always` valor o el `PreserveNewest` valor.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <None Include="PageSiteOfOriginFile.xaml">  
    <CopyToOutputDirectory>Always</CopyToOutputDirectory>  
  </None>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  En [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], cree un archivo de sitio de origen mediante la adición de un archivo a un proyecto y su `Build Action` a `None`.  
  
 Cuando se compila el proyecto, [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] copia los archivos especificados en la carpeta de salida de compilación.  
  
### <a name="using-site-of-origin-files"></a>Uso de archivos del sitio de origen  
 Para cargar un archivo de sitio de origen, puede llamar a la <xref:System.Windows.Application.GetRemoteStream%2A> método de la <xref:System.Windows.Application> (clase), pasando un pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que identifica el sitio deseado del archivo de origen. <xref:System.Windows.Application.GetRemoteStream%2A> Devuelve un <xref:System.Windows.Resources.StreamResourceInfo> objeto, que expone el sitio del archivo de origen como un <xref:System.IO.Stream> y describe su tipo de contenido.  
  
 Por ejemplo, el código siguiente muestra cómo usar <xref:System.Windows.Application.GetRemoteStream%2A> para cargar un <xref:System.Windows.Controls.Page> sitio de origen de archivo y establecerlo como contenido de un <xref:System.Windows.Controls.Frame> (`pageFrame`).  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 Durante la llamada a <xref:System.Windows.Application.GetRemoteStream%2A> proporciona acceso a la <xref:System.IO.Stream>, deberá realizar el trabajo adicional de convertirlo en el tipo de la propiedad que se establecerá con. En su lugar, puede dejar que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] se encargan de abrir y convertir la <xref:System.IO.Stream> cargando un archivo de recursos directamente en la propiedad de un tipo mediante código.  
  
 El ejemplo siguiente muestra cómo cargar un <xref:System.Windows.Controls.Page> directamente en un <xref:System.Windows.Controls.Frame> (`pageFrame`) mediante código.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 El ejemplo siguiente es el equivalente de marcación del ejemplo anterior.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>   
## <a name="rebuilding-after-changing-build-type"></a>Nueva compilación después de cambiar el tipo de compilación  
 Después de cambiar el tipo de compilación de un archivo de datos de aplicación, es preciso volver a compilar toda la aplicación para asegurarse de que se aplican los cambios. Si solo compila la aplicación, no se aplican los cambios.  
  
## <a name="see-also"></a>Vea también  
 [Identificadores URI de paquete en WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)

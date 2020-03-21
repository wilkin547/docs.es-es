---
title: Archivos de recursos, contenido y datos de aplicaciones
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
ms.openlocfilehash: f17898972eeef66447060db32bae5fae377b710e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186204"
---
# <a name="wpf-application-resource-content-and-data-files"></a>Archivos de recursos, contenido y datos de aplicaciones de WPF
Las aplicaciones de Microsoft Windows a menudo dependen [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]de archivos que contienen datos no ejecutables, como imágenes, vídeo y audio. Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF) ofrece compatibilidad especial para configurar, identificar y usar estos tipos de archivos de datos, que se denominan archivos de datos de aplicación. Esta compatibilidad gira en torno a un conjunto específico de tipos de archivo de datos de aplicación, entre los que se incluyen:  
  
- **Archivos de**recursos: archivos de datos que se compilan en un ensamblado WPF ejecutable o de biblioteca.  
  
- **Archivos de**contenido: archivos de datos independientes que tienen una asociación explícita con un ensamblado WPF ejecutable.  
  
- **Site of Origin Files**: Archivos de datos independientes que no tienen ninguna asociación con un ensamblado WPF ejecutable.  
  
 Una diferencia importante entre estos tres tipos de archivos es que tanto los archivos de recursos como los archivos de contenido se conocen en el momento de la compilación; un ensamblado tiene un conocimiento explícito de ellos. Para los archivos de sitio de origen, sin embargo, un ensamblado puede no tener ningún conocimiento de ellos en absoluto, o conocimiento implícito a través de una referencia de identificador uniforme de recursos (URI) del paquete; el caso de este último, no hay garantía de que el archivo de sitio de origen al que se hace referencia exista realmente.  
  
 Para hacer referencia a los archivos de datos de la aplicación, Windows Presentation Foundation (WPF) usa el esquema de identificador uniforme de recursos (URI) Pack, que se describe en detalle en [Pack URIs en WPF](pack-uris-in-wpf.md)).  
  
 En este tema se describe cómo configurar y usar archivos de datos de aplicaciones.  

<a name="Resource_Files"></a>
## <a name="resource-files"></a>Archivos de recursos  
 Si un archivo de datos de la aplicación debe estar siempre disponible para una aplicación, la única forma de garantizar la disponibilidad es compilarlo en el ensamblado ejecutable principal de una aplicación o en uno de sus ensamblados referenciados. Este tipo de archivo de datos de aplicación se conoce como archivo de *recursos.*  
  
 Los archivos de recursos se deben usar cuando:  
  
- No es necesario actualizar el contenido del archivo de recursos después de que se compila en un ensamblado.  
  
- Desea simplificar la complejidad de la distribución de una aplicación mediante la reducción del número de dependencias de los archivos.  
  
- El archivo de datos de la aplicación debe ser localizable (consulte Información general sobre [la globalización y la localización](../advanced/wpf-globalization-and-localization-overview.md)de WPF ).  
  
> [!NOTE]
> Los archivos de recursos descritos en esta sección son diferentes de los archivos de recursos descritos en [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md) y diferentes de los recursos incrustados o vinculados descritos en Administrar recursos de aplicación [(.NET)](/visualstudio/ide/managing-application-resources-dotnet).  
  
### <a name="configuring-resource-files"></a>Configuración de archivos de recursos  
 En WPFWPF, un archivo de recursos es un archivo que se incluye `Resource` en un proyecto de motor de compilación de Microsoft (MSBuild) como un elemento.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Resource Include="ResourceFile.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
> En Visual Studio, se crea un archivo de recursos `Build Action` agregando un archivo a un proyecto y estableciendo su valor `Resource`en .  
  
 Cuando se compila el proyecto, MSBuild compila el recurso en el ensamblado.  
  
### <a name="using-resource-files"></a>Uso de archivos de recursos  
 Para cargar un archivo de <xref:System.Windows.Application.GetResourceStream%2A> recursos, <xref:System.Windows.Application> puede llamar al método de la clase, pasando un URI de paquete que identifica el archivo de recursos deseado. <xref:System.Windows.Application.GetResourceStream%2A>devuelve <xref:System.Windows.Resources.StreamResourceInfo> un objeto, que expone el <xref:System.IO.Stream> archivo de recursos como a y describe su tipo de contenido.  
  
 Por ejemplo, el código siguiente <xref:System.Windows.Application.GetResourceStream%2A> muestra cómo <xref:System.Windows.Controls.Page> cargar un archivo de recursos <xref:System.Windows.Controls.Frame> `pageFrame`y establecerlo como el contenido de un ( ):  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 Mientras <xref:System.Windows.Application.GetResourceStream%2A> que la <xref:System.IO.Stream>llamada le da acceso a la , debe realizar el trabajo adicional de convertirlo en el tipo de la propiedad que va a establecer con. En su lugar, puede dejar que WPFWPF se encargue de abrir y convertir mediante la <xref:System.IO.Stream> carga de un archivo de recursos directamente en la propiedad de un tipo mediante código.  
  
 En el ejemplo siguiente <xref:System.Windows.Controls.Page> se muestra <xref:System.Windows.Controls.Frame> `pageFrame`cómo cargar un directamente en un ( ) mediante código.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 El ejemplo siguiente es el equivalente de marcación del ejemplo anterior.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### <a name="application-code-files-as-resource-files"></a>Archivos de código de aplicación como archivos de recursos  
 Se puede hacer referencia a un conjunto especial de archivos de código de aplicación WPF mediante URI de paquete, incluidas ventanas, páginas, documentos de flujo y diccionarios de recursos. Por ejemplo, puede <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> establecer la propiedad con un URI de paquete que haga referencia a la ventana o página que desea cargar cuando se inicia una aplicación.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 Puede hacerlo cuando se incluye un archivo XAML en `Page` un proyecto de MSBuild como elemento.  
  
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
> En Visual Studio, agregue <xref:System.Windows.Window> <xref:System.Windows.Navigation.NavigationWindow>un <xref:System.Windows.Controls.Page> <xref:System.Windows.Documents.FlowDocument>nuevo <xref:System.Windows.ResourceDictionary> , , , `Build Action` , , o `Page`a un proyecto, el archivo de marcado se establecerá de forma predeterminada en .  
  
 Cuando se `Page` compila un proyecto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] con elementos, los elementos se convierten al formato binario y se compilan en el ensamblado asociado. Por consiguiente, estos archivos se pueden utilizar de la misma forma que los archivos de recursos típicos.  
  
> [!NOTE]
> Si [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] un archivo está `Resource` configurado como un elemento y no tiene [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] un archivo de código subyacente, el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]sin formato se compila en un ensamblado en lugar de una versión binaria del archivo sin formato.  
  
<a name="Content_Files"></a>
## <a name="content-files"></a>Archivos de contenido  
 Un archivo de *contenido* se distribuye como un archivo suelto junto a un ensamblado ejecutable. Aunque no se compilan en un ensamblado, los ensamblados se compilan con metadatos que establecen una asociación con cada archivo de contenido.  
  
 Los archivos de contenido se deben usar cuando la aplicación requiere un conjunto específico de archivos de datos de aplicación que desee poder actualizar sin volver a compilar el ensamblado que los consume.  
  
### <a name="configuring-content-files"></a>Configuración de archivos de contenido  
 Para agregar un archivo de contenido a un proyecto, `Content` se debe incluir un archivo de datos de aplicación como elemento. Además, dado que un archivo de contenido no se compila directamente en el ensamblado, debe establecer el elemento de metadatos de MSBuild `CopyToOutputDirectory` para especificar que el archivo de contenido se copia en una ubicación relativa al ensamblado compilado. Si desea que el recurso se copie en la carpeta de salida `CopyToOutputDirectory` de compilación `Always` cada vez que se compila un proyecto, establezca el elemento de metadatos con el valor. De lo contrario, puede asegurarse de que solo se copia la versión más reciente del recurso en la carpeta de salida de compilación mediante el `PreserveNewest` valor.  
  
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
> En Visual Studio, se crea un archivo de contenido `Build Action` agregando un archivo a un proyecto y estableciendo su `Content`en , y establezca su `Copy to Output Directory` en `Copy always` (igual que `Always`) y `Copy if newer` (igual que `PreserveNewest`).  
  
 Cuando se compila el <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> proyecto, se compila un atributo en los metadatos del ensamblado para cada archivo de contenido.  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 El valor <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> de la implica la ruta de acceso al archivo de contenido en relación con su posición en el proyecto. Por ejemplo, si un archivo de contenido se encuentra en una subcarpeta <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> de proyecto, la información de ruta de acceso adicional se incorporaría al valor.  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 El <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> valor también es el valor de la ruta de acceso al archivo de contenido en la carpeta de salida de compilación.  
  
### <a name="using-content-files"></a>Uso de archivos de contenido  
 Para cargar un archivo de <xref:System.Windows.Application.GetContentStream%2A> contenido, <xref:System.Windows.Application> puede llamar al método de la clase, pasando un URI de paquete que identifica el archivo de contenido deseado. <xref:System.Windows.Application.GetContentStream%2A>devuelve <xref:System.Windows.Resources.StreamResourceInfo> un objeto, que expone el <xref:System.IO.Stream> archivo de contenido como a y describe su tipo de contenido.  
  
 Por ejemplo, el código siguiente <xref:System.Windows.Application.GetContentStream%2A> muestra cómo <xref:System.Windows.Controls.Page> cargar un archivo de contenido <xref:System.Windows.Controls.Frame> `pageFrame`y establecerlo como el contenido de un ( ).  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 Mientras <xref:System.Windows.Application.GetContentStream%2A> que la <xref:System.IO.Stream>llamada le da acceso a la , debe realizar el trabajo adicional de convertirlo en el tipo de la propiedad que va a establecer con. En su lugar, puede dejar que WPFWPF se encargue de abrir y convertir mediante la <xref:System.IO.Stream> carga de un archivo de recursos directamente en la propiedad de un tipo mediante código.  
  
 En el ejemplo siguiente <xref:System.Windows.Controls.Page> se muestra <xref:System.Windows.Controls.Frame> `pageFrame`cómo cargar un directamente en un ( ) mediante código.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 El ejemplo siguiente es el equivalente de marcación del ejemplo anterior.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>
## <a name="site-of-origin-files"></a>Sitio de archivos de origen  
 Los archivos de recursos tienen una relación explícita con los ensamblados que se distribuyen junto, según lo definido por el <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>archivo . Sin embargo, hay veces en las que puede desear establecer una relación implícita o inexistente entre un ensamblado y un archivo de datos de aplicación, incluyendo cuándo:  
  
- Un archivo no existe en tiempo de compilación.  
  
- No sabe qué archivos requerirá el ensamblado hasta el tiempo de ejecución.  
  
- Desea poder actualizar los archivos sin volver a compilar el ensamblado al que están asociados.  
  
- La aplicación utiliza archivos de datos grandes, como audio y vídeo, y solo desea que los usuarios los descarguen si eligen hacerlo.  
  
 Es posible cargar estos tipos de archivos mediante esquemas URI tradicionales, como los esquemas de file:/// y http://.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 Sin embargo, los esquemas file:/// y http:// requieren que la aplicación tenga plena confianza. Si la aplicación es una aplicación de explorador XAML (XBAP) que se inició desde Internet o intranet, y solo solicita el conjunto de permisos permitidos para las aplicaciones iniciadas desde esas ubicaciones, los archivos sueltos solo se pueden cargar desde el lugar de origen de la aplicación (ubicación de lanzamiento). Tales archivos se conocen como archivos *de sitio de origen.*  
  
 Los archivos del sitio de origen son la única opción para las aplicaciones de confianza parcial, aunque no se limitan a ese tipo de aplicaciones. Es posible que las aplicaciones de plena confianza aún necesiten cargar archivos de datos de aplicación que desconocen en tiempo de compilación; mientras que las aplicaciones de plena confianza pueden utilizar file:///, es probable que los archivos de datos de la aplicación se instalarán en la misma carpeta que el ensamblado de la aplicación, o en una subcarpeta de él. En este caso, es más sencillo usar la referencia del sitio de origen que file:///, ya que el uso de file:/// requiere que se determine la ruta de acceso completa del archivo.  
  
> [!NOTE]
> Los archivos de sitio de origen no se almacenan en caché con una aplicación de explorador XAML (XBAP) en un equipo cliente, mientras que los archivos de contenido lo son. Por consiguiente, sólo se descargan cuando se solicita específicamente. Si una aplicación de explorador XAML (XBAP) tiene archivos multimedia de gran tamaño, configurarlos como archivos de sitio de origen significa que el inicio inicial de la aplicación es mucho más rápido y los archivos solo se descargan a petición.  
  
### <a name="configuring-site-of-origin-files"></a>Configuración de archivos de sitio de origen  
 Si los archivos de sitio de origen son inexistentes o desconocidos en tiempo de compilación, debe usar mecanismos de `XCopy` implementación tradicionales para garantizar que los archivos necesarios estén disponibles en tiempo de ejecución, incluido el programa de línea de comandos o Microsoft Windows Installer.  
  
 Si sabe en tiempo de compilación los archivos que desea que se encuentren en el sitio de origen, pero aún así `None` desea evitar una dependencia explícita, puede agregar esos archivos a un proyecto de MSBuild como elemento. Al igual que con los archivos de `CopyToOutputDirectory` contenido, debe establecer el atributo MSBuild para especificar que el archivo de `Always` sitio de `PreserveNewest` origen se copia en una ubicación relativa al ensamblado compilado, especificando el valor o el valor.  
  
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
> En Visual Studio, se crea un archivo de sitio de `Build Action` origen `None`agregando un archivo a un proyecto y estableciendo su valor en .  
  
 Cuando se compila el proyecto, MSBuild copia los archivos especificados en la carpeta de salida de compilación.  
  
### <a name="using-site-of-origin-files"></a>Uso de archivos del sitio de origen  
 Para cargar un archivo de sitio <xref:System.Windows.Application.GetRemoteStream%2A> de origen, puede llamar al método de la <xref:System.Windows.Application> clase, pasando un URI de paquete que identifica el archivo de sitio de origen deseado. <xref:System.Windows.Application.GetRemoteStream%2A>devuelve <xref:System.Windows.Resources.StreamResourceInfo> un objeto, que expone el archivo <xref:System.IO.Stream> de sitio de origen como a y describe su tipo de contenido.  
  
 Por ejemplo, el código siguiente <xref:System.Windows.Application.GetRemoteStream%2A> muestra cómo <xref:System.Windows.Controls.Page> usar para cargar un archivo de <xref:System.Windows.Controls.Frame> `pageFrame`sitio de origen y establecerlo como el contenido de un ( ).  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 Mientras <xref:System.Windows.Application.GetRemoteStream%2A> que la <xref:System.IO.Stream>llamada le da acceso a la , debe realizar el trabajo adicional de convertirlo en el tipo de la propiedad que va a establecer con. En su lugar, puede dejar que WPFWPF se encargue de abrir y convertir mediante la <xref:System.IO.Stream> carga de un archivo de recursos directamente en la propiedad de un tipo mediante código.  
  
 En el ejemplo siguiente <xref:System.Windows.Controls.Page> se muestra <xref:System.Windows.Controls.Frame> `pageFrame`cómo cargar un directamente en un ( ) mediante código.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 El ejemplo siguiente es el equivalente de marcación del ejemplo anterior.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>
## <a name="rebuilding-after-changing-build-type"></a>Nueva compilación después de cambiar el tipo de compilación  
 Después de cambiar el tipo de compilación de un archivo de datos de aplicación, es preciso volver a compilar toda la aplicación para asegurarse de que se aplican los cambios. Si solo compila la aplicación, no se aplican los cambios.  
  
## <a name="see-also"></a>Consulte también

- [Empaquetar URI en WPF](pack-uris-in-wpf.md)

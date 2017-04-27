---
title: "Archivos de recursos, contenido y datos de aplicaciones de WPF | Microsoft Docs"
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
  - "desarrollo de aplicaciones [WPF], archivos"
  - "administración de aplicaciones [WPF]"
  - "archivos de contenido [WPF]"
  - "recursos incrustados [WPF]"
  - "archivos [WPF]"
  - "recursos separados [WPF]"
  - "hacer referencia a archivos de aplicación [WPF]"
  - "archivos remotos [WPF]"
  - "archivos de recursos [WPF]"
  - "Archivos del sitio de origen [WPF]"
  - "aplicación WPF, archivos"
ms.assetid: 7ad2943b-3961-41d3-8fc6-1582d43f5d99
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Archivos de recursos, contenido y datos de aplicaciones de WPF
Las aplicaciones para [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] suelen depender de archivos que contienen datos no ejecutables, como [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], imágenes, vídeo y audio.  [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] proporciona una compatibilidad especial para configurar, identificar y utilizar estos tipos de archivos de datos, que se denominan archivos de datos de aplicación.  Esta compatibilidad gira en torno a un conjunto específico de tipos de archivos de datos de aplicación, como:  
  
-   **Archivos de recursos**: archivos de datos que se generan en un ejecutable o en un ensamblado de biblioteca de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
-   **Archivos de contenido**: archivos de datos independientes que tienen una asociación explícita con un ensamblado ejecutable de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
-   **Archivos de sitio de origen**: archivos de datos independientes que no tienen ninguna asociación con un ensamblado ejecutable de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 Hay una diferencia importante entre estos tres tipos de archivos: los archivos de recursos y los archivos de contenido se conocen en tiempo de compilación; un ensamblado tiene conocimiento explícito de ellos.  En el caso de los archivos de sitio de origen, sin embargo, es posible que el ensamblado no tenga conocimiento de ellos o tenga un conocimiento implícito a través de una referencia de pack [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]; en este último caso, no hay ninguna garantía de que exista realmente el archivo de sitio de origen al que se hace referencia.  
  
 Para hacer referencia a los archivos de datos de aplicación, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] utiliza el esquema de pack [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], que se describe detalladamente en [Empaquetar URI en WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md).  
  
 En este tema se describe cómo configurar y utilizar los archivos de datos de aplicación.  
  
   
  
<a name="Resource_Files"></a>   
## Archivos de recursos  
 Si un archivo de datos de aplicación debe estar siempre disponible para una aplicación, la única manera de garantizar la disponibilidad es generarlo en el ensamblado ejecutable principal de una aplicación o en uno de los ensamblados a los que hace referencia.  Este tipo de archivo de datos de aplicación se conoce como *archivo de recursos*.  
  
 Los archivos de recursos deben usarse cuando:  
  
-   No es necesario actualizar el contenido del archivo de recursos una vez generado en un ensamblado.  
  
-   Se desea simplificar la distribución de la aplicación reduciendo el número de dependencias de archivo.  
  
-   El archivo de datos de aplicación debe ser localizable \(vea [Información general sobre la localización y globalización de WPF](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)\).  
  
> [!NOTE]
>  Los archivos de recursos descritos en esta sección son diferentes de los archivos de recursos descritos en [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md) y diferentes que los recursos incrustados o vinculados descritos en [Administrar los recursos de la aplicación \(.NET\)](../Topic/Managing%20Application%20Resources%20\(.NET\).md).  
  
### Configurar archivos de recursos  
 En [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], un archivo de recursos es un archivo que está incluido en un proyecto de [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] como un elemento `Resource`.  
  
```  
<Project "xmlns=http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Resource Include="ResourceFile.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  En [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], se crea un archivo de recursos agregando un archivo a un proyecto y estableciendo el valor de `Build Action` en `Resource`.  
  
 Una vez compilado el proyecto, [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] genera el recurso en el ensamblado.  
  
### Usar archivos de recursos  
 Para cargar un archivo de recursos, puede llamar al método <xref:System.Windows.Application.GetResourceStream%2A> de la clase <xref:System.Windows.Application>, pasando un pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que identifique el archivo de recursos deseado.  <xref:System.Windows.Application.GetResourceStream%2A> devuelve un objeto <xref:System.Windows.Resources.StreamResourceInfo>, que expone el archivo de recursos como un objeto <xref:System.IO.Stream> y describe su tipo de contenido.  
  
 Como ejemplo, en el código siguiente se muestra cómo utilizar <xref:System.Windows.Application.GetResourceStream%2A> para cargar un archivo de recursos <xref:System.Windows.Controls.Page> y establecerlo como contenido de un control <xref:System.Windows.Controls.Frame> \(`pageFrame`\):  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 Aunque al llamar a <xref:System.Windows.Application.GetResourceStream%2A> se obtiene acceso a <xref:System.IO.Stream>, debe realizar el trabajo adicional de convertirlo en el tipo de la propiedad con la que lo establecerá.  Como alternativa, puede dejar que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] se ocupe de abrir y convertir el objeto <xref:System.IO.Stream> cargando un archivo de recursos directamente en la propiedad de un tipo mediante código.  
  
 En el ejemplo siguiente, se muestra cómo se carga un control <xref:System.Windows.Controls.Page> directamente en un control <xref:System.Windows.Controls.Frame> \(`pageFrame`\) mediante código.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 El ejemplo siguiente es el equivalente en marcado del ejemplo anterior.  
  
 [!code-xml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### Archivos de código de aplicación como archivos de recursos  
 Se puede hacer referencia a un conjunto especial de archivos de código de aplicación de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] utilizando pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], incluidos documentos dinámicos, ventanas, páginas y diccionarios de recursos.  Por ejemplo, puede establecer la propiedad <xref:System.Windows.Application.StartupUri%2A?displayProperty=fullName> con un pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que hace referencia a la ventana o página que desee cargar cuando se inicie una aplicación.  
  
 [!code-xml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 Puede hacer esto cuando se incluye un archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en un proyecto de [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] como un elemento `Page`.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Page Include="MainWindow.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  En [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], agregue un nuevo objeto <xref:System.Windows.Window>, <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.FlowDocument> o <xref:System.Windows.ResourceDictionary> a un proyecto; el valor predeterminado de `Build Action` para el archivo de marcado será `Page`.  
  
 Cuando se genera un proyecto con elementos `Page`, los elementos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se convierten al formato binario y se generan en el ensamblado asociado.  Por consiguiente, estos archivos se pueden utilizar de la misma manera que los archivos de recursos típicos.  
  
> [!NOTE]
>  Si un archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se configura como un elemento `Resource` y no tiene un archivo de código subyacente, el código [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sin formato se generará en un ensamblado en lugar de una versión binaria del código [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sin formato.  
  
<a name="Content_Files"></a>   
## Archivos de contenido  
 Un *archivo de contenido* se distribuye como un archivo separado junto a un ensamblado ejecutable.  Aunque no estén generados en un ensamblado, los ensamblados se generan con metadatos que establecen una asociación con cada archivo de contenido.  
  
 Se recomienda utilizar archivos de contenido cuando la aplicación requiere un conjunto concreto de archivos de datos de aplicación que se desee poder actualizar sin tener que volver a generar el ensamblado que los consume.  
  
### Configurar archivos de contenido  
 Para agregar un archivo de contenido a un proyecto, se debe incluir un archivo de datos de aplicación como un elemento `Content`.  Además, dado que un archivo de contenido no se compila directamente en el ensamblado, es necesario establecer el elemento de metadatos `CopyToOutputDirectory` de [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`` para especificar que el archivo de contenido se copie en una ubicación relativa al ensamblado compilado.  Si desea que el recurso se copie en la carpeta de resultados de la compilación cada vez que se genere un proyecto, establezca el elemento de metadatos `CopyToOutputDirectory` en el valor `Always`.  De lo contrario, para asegurarse de que sólo se copie la versión más reciente del recurso en la carpeta de resultados de la compilación, use el valor `PreserveNewest`.  
  
 A continuación se muestra un archivo configurado como archivo de contenido que sólo se copia en la carpeta de resultados de la compilación cuando se agrega al proyecto una nueva versión del recurso.  
  
```  
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
>  En [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], puede crear un archivo de contenido agregando un archivo a un proyecto y estableciendo el valor de `Build Action` en `Content`; establezca el valor de `Copy to Output Directory` en `Copy always` \(es lo mismo que `Always`\) y `Copy if newer` \(es lo mismo que `PreserveNewest`\).  
  
 Cuando se genera el proyecto, se compila un atributo <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> en los metadatos del ensamblado para cada archivo de contenido.  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 El valor de <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> implica la ruta de acceso al archivo de contenido con respecto a su posición en el proyecto.  Por ejemplo, si un archivo de contenido se encontrara en una subcarpeta del proyecto, la información adicional de ruta de acceso se incorporaría en el valor de <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>.  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 El valor de <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> es también el valor de la ruta de acceso al archivo de contenido en la carpeta de resultados de la compilación.  
  
### Utilizar archivos de contenido  
 Para cargar un archivo de contenido, puede llamar al método <xref:System.Windows.Application.GetContentStream%2A> de la clase <xref:System.Windows.Application>, pasando un pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que identifique el archivo de contenido deseado.  <xref:System.Windows.Application.GetContentStream%2A> devuelve un objeto <xref:System.Windows.Resources.StreamResourceInfo>, que expone el archivo de contenido como un objeto <xref:System.IO.Stream> y describe su tipo de contenido.  
  
 Como ejemplo, en el código siguiente se muestra cómo utilizar <xref:System.Windows.Application.GetContentStream%2A> para cargar un archivo de contenido <xref:System.Windows.Controls.Page> y establecerlo como contenido de un control <xref:System.Windows.Controls.Frame> \(`pageFrame`\).  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 Aunque al llamar a <xref:System.Windows.Application.GetContentStream%2A> se obtiene acceso a <xref:System.IO.Stream>, debe realizar el trabajo adicional de convertirlo en el tipo de la propiedad con la que lo establecerá.  Como alternativa, puede dejar que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] se ocupe de abrir y convertir el objeto <xref:System.IO.Stream> cargando un archivo de recursos directamente en la propiedad de un tipo mediante código.  
  
 En el ejemplo siguiente, se muestra cómo se carga un control <xref:System.Windows.Controls.Page> directamente en un control <xref:System.Windows.Controls.Frame> \(`pageFrame`\) mediante código.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 El ejemplo siguiente es el equivalente en marcado del ejemplo anterior.  
  
 [!code-xml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>   
## Archivos de sitio de origen  
 Los archivos de recursos tienen una relación explícita con los ensamblados junto a los que se distribuyen, según lo definido en <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>.  No obstante, habrá ocasiones en las que quizá desee establecer una relación implícita o inexistente entre un ensamblado y un archivo de datos de aplicación, por ejemplo cuando:  
  
-   Un archivo no exista en tiempo de compilación.  
  
-   No sepa qué archivos necesitará el ensamblado hasta el tiempo de ejecución.  
  
-   Desee poder actualizar los archivos sin tener que volver a generar el ensamblado al que están asociados.  
  
-   La aplicación utilice archivos de datos grandes, como los de audio y vídeo, y desee que los usuarios los descarguen sólo si así lo eligen.  
  
 Es posible cargar estos tipos de archivo utilizando esquemas de [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] tradicionales, como los esquemas file:\/\/\/ y http:\/\/.  
  
 [!code-xml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 Sin embargo, los esquemas file:\/\/\/ y http:\/\/ requieren que la aplicación sea de plena confianza.  Si la aplicación es una aplicación [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] iniciada desde Internet o desde una intranet y solicita solamente el conjunto de permisos que se permiten para las aplicaciones iniciadas desde esas ubicaciones, los archivos separados solamente se podrán cargar desde el sitio de origen de la aplicación \(ubicación de inicio\).  Esos archivos se conocen como archivos de *sitio de origen*.  
  
 Los archivos de sitio de origen son la única opción para las aplicaciones de confianza parcial, aunque no se limitan a ellas.  Puede que las aplicaciones de plena confianza necesiten cargar archivos de datos de aplicación que desconocen en tiempo de compilación; aunque las aplicaciones de plena confianza podrían utilizar file:\/\/\/, es probable que los archivos de datos de aplicación se instalen en la misma carpeta o en una subcarpeta del ensamblado de la aplicación.  En este caso, el uso de referencias al sitio de origen es más fácil que el uso de file:\/\/\/ porque en este último caso es necesario especificar la ruta de acceso completa al archivo.  
  
> [!NOTE]
>  A diferencia de los archivos de contenido, los archivos de sitio de origen no se almacenan en la memoria caché con una aplicación [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] en un equipo cliente.  Por consiguiente, se descargan sólo cuando se solicita específicamente su descarga.  Si una aplicación [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] tiene archivos multimedia grandes, configurarlos como archivos de sitio de origen significa que el inicio de la aplicación será mucho más rápido y que los archivos solamente se descargarán a petición.  
  
### Configurar archivos de sitio de origen  
 Si los archivos de sitio de origen son inexistentes o se desconocen en tiempo de compilación, necesitará utilizar los mecanismos de distribución tradicionales para asegurarse de que los archivos necesarios están disponibles en tiempo de ejecución, como el programa de línea de comandos `XCopy` o [!INCLUDE[TLA#tla_wininstall](../../../../includes/tlasharptla-wininstall-md.md)].  
  
 Si desconoce en tiempo de compilación los archivos que deben encontrarse en el sitio de origen, pero aún desea evitar dependencias explícitas, puede agregar esos archivos a un proyecto de [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] como elemento `None`.  Al igual que en el caso de los archivos de contenido, es necesario establecer el atributo [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `CopyToOutputDirectory` para especificar que el archivo de sitio de origen se copie en una ubicación relativa al ensamblado compilado, especificando el valor `Always` o el valor `PreserveNewest`.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <None Include="PageSiteOfOriginFile.xaml">  
    <CopyToOutputDirectory>Always</CopyToOutputDirectory>  
  </None>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  En [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], se crea un archivo de sitio de origen agregando un archivo a un proyecto y estableciendo el valor de `Build Action` en `None`.  
  
 Al generar el proyecto, [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] copia los archivos especificados en la carpeta de resultados de la compilación.  
  
### Utilizar archivos de sitio de origen  
 Para cargar un archivo de sitio de origen, puede llamar al método <xref:System.Windows.Application.GetRemoteStream%2A> de la clase <xref:System.Windows.Application>, pasando un pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] que identifique el archivo de sitio de origen deseado.  <xref:System.Windows.Application.GetRemoteStream%2A> devuelve un objeto <xref:System.Windows.Resources.StreamResourceInfo>, que expone el archivo de sitio de origen como <xref:System.IO.Stream> y describe su tipo de contenido.  
  
 Como ejemplo, en el código siguiente se muestra cómo utilizar <xref:System.Windows.Application.GetRemoteStream%2A> para cargar un archivo de sitio de origen <xref:System.Windows.Controls.Page> y establecerlo como contenido de un control <xref:System.Windows.Controls.Frame> \(`pageFrame`\).  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 Aunque al llamar a <xref:System.Windows.Application.GetRemoteStream%2A> se obtiene acceso a <xref:System.IO.Stream>, debe realizar el trabajo adicional de convertirlo en el tipo de la propiedad con la que lo establecerá.  Como alternativa, puede dejar que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] se ocupe de abrir y convertir el objeto <xref:System.IO.Stream> cargando un archivo de recursos directamente en la propiedad de un tipo mediante código.  
  
 En el ejemplo siguiente, se muestra cómo se carga un control <xref:System.Windows.Controls.Page> directamente en un control <xref:System.Windows.Controls.Frame> \(`pageFrame`\) mediante código.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 El ejemplo siguiente es el equivalente en marcado del ejemplo anterior.  
  
 [!code-xml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>   
## Recompilar después de cambiar el tipo de compilación  
 Después de cambiar el tipo de compilación de un archivo de datos de aplicación, debe recompilar la aplicación completa para asegurarse de que se apliquen esos cambios.  Si solamente compila la aplicación, no se aplicarán los cambios.  
  
## Vea también  
 [Empaquetar URI en WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)
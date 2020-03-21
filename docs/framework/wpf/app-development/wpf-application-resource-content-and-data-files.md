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
# <a name="wpf-application-resource-content-and-data-files"></a><span data-ttu-id="dfda1-102">Archivos de recursos, contenido y datos de aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="dfda1-102">WPF Application Resource, Content, and Data Files</span></span>
<span data-ttu-id="dfda1-103">Las aplicaciones de Microsoft Windows a menudo dependen [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]de archivos que contienen datos no ejecutables, como imágenes, vídeo y audio.</span><span class="sxs-lookup"><span data-stu-id="dfda1-103">Microsoft Windows applications often depend on files that contain non-executable data, such as [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], images, video, and audio.</span></span> <span data-ttu-id="dfda1-104">Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF) ofrece compatibilidad especial para configurar, identificar y usar estos tipos de archivos de datos, que se denominan archivos de datos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="dfda1-104">Windows Presentation Foundation (WPF) offers special support for configuring, identifying, and using these types of data files, which are called application data files.</span></span> <span data-ttu-id="dfda1-105">Esta compatibilidad gira en torno a un conjunto específico de tipos de archivo de datos de aplicación, entre los que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="dfda1-105">This support revolves around a specific set of application data file types, including:</span></span>  
  
- <span data-ttu-id="dfda1-106">**Archivos de**recursos: archivos de datos que se compilan en un ensamblado WPF ejecutable o de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="dfda1-106">**Resource Files**: Data files that are compiled into either an executable or library WPF assembly.</span></span>  
  
- <span data-ttu-id="dfda1-107">**Archivos de**contenido: archivos de datos independientes que tienen una asociación explícita con un ensamblado WPF ejecutable.</span><span class="sxs-lookup"><span data-stu-id="dfda1-107">**Content Files**: Standalone data files that have an explicit association with an executable WPF assembly.</span></span>  
  
- <span data-ttu-id="dfda1-108">**Site of Origin Files**: Archivos de datos independientes que no tienen ninguna asociación con un ensamblado WPF ejecutable.</span><span class="sxs-lookup"><span data-stu-id="dfda1-108">**Site of Origin Files**: Standalone data files that have no association with an executable WPF assembly.</span></span>  
  
 <span data-ttu-id="dfda1-109">Una diferencia importante entre estos tres tipos de archivos es que tanto los archivos de recursos como los archivos de contenido se conocen en el momento de la compilación; un ensamblado tiene un conocimiento explícito de ellos.</span><span class="sxs-lookup"><span data-stu-id="dfda1-109">One important distinction to make between these three types of files is that resource files and content files are known at build time; an assembly has explicit knowledge of them.</span></span> <span data-ttu-id="dfda1-110">Para los archivos de sitio de origen, sin embargo, un ensamblado puede no tener ningún conocimiento de ellos en absoluto, o conocimiento implícito a través de una referencia de identificador uniforme de recursos (URI) del paquete; el caso de este último, no hay garantía de que el archivo de sitio de origen al que se hace referencia exista realmente.</span><span class="sxs-lookup"><span data-stu-id="dfda1-110">For site of origin files, however, an assembly may have no knowledge of them at all, or implicit knowledge through a pack uniform resource identifier (URI) reference; the case of the latter, there is no guarantee that the referenced site of origin file actually exists.</span></span>  
  
 <span data-ttu-id="dfda1-111">Para hacer referencia a los archivos de datos de la aplicación, Windows Presentation Foundation (WPF) usa el esquema de identificador uniforme de recursos (URI) Pack, que se describe en detalle en [Pack URIs en WPF](pack-uris-in-wpf.md)).</span><span class="sxs-lookup"><span data-stu-id="dfda1-111">To reference application data files, Windows Presentation Foundation (WPF) uses the Pack uniform resource identifier (URI) Scheme, which is described in detail in [Pack URIs in WPF](pack-uris-in-wpf.md)).</span></span>  
  
 <span data-ttu-id="dfda1-112">En este tema se describe cómo configurar y usar archivos de datos de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="dfda1-112">This topic describes how to configure and use application data files.</span></span>  

<a name="Resource_Files"></a>
## <a name="resource-files"></a><span data-ttu-id="dfda1-113">Archivos de recursos</span><span class="sxs-lookup"><span data-stu-id="dfda1-113">Resource Files</span></span>  
 <span data-ttu-id="dfda1-114">Si un archivo de datos de la aplicación debe estar siempre disponible para una aplicación, la única forma de garantizar la disponibilidad es compilarlo en el ensamblado ejecutable principal de una aplicación o en uno de sus ensamblados referenciados.</span><span class="sxs-lookup"><span data-stu-id="dfda1-114">If an application data file must always be available to an application, the only way to guarantee availability is to compile it into an application's main executable assembly or one of its referenced assemblies.</span></span> <span data-ttu-id="dfda1-115">Este tipo de archivo de datos de aplicación se conoce como archivo de *recursos.*</span><span class="sxs-lookup"><span data-stu-id="dfda1-115">This type of application data file is known as a *resource file*.</span></span>  
  
 <span data-ttu-id="dfda1-116">Los archivos de recursos se deben usar cuando:</span><span class="sxs-lookup"><span data-stu-id="dfda1-116">You should use resource files when:</span></span>  
  
- <span data-ttu-id="dfda1-117">No es necesario actualizar el contenido del archivo de recursos después de que se compila en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dfda1-117">You don't need to update the resource file's content after it is compiled into an assembly.</span></span>  
  
- <span data-ttu-id="dfda1-118">Desea simplificar la complejidad de la distribución de una aplicación mediante la reducción del número de dependencias de los archivos.</span><span class="sxs-lookup"><span data-stu-id="dfda1-118">You want to simplify application distribution complexity by reducing the number of file dependencies.</span></span>  
  
- <span data-ttu-id="dfda1-119">El archivo de datos de la aplicación debe ser localizable (consulte Información general sobre [la globalización y la localización](../advanced/wpf-globalization-and-localization-overview.md)de WPF ).</span><span class="sxs-lookup"><span data-stu-id="dfda1-119">Your application data file needs to be localizable (see [WPF Globalization and Localization Overview](../advanced/wpf-globalization-and-localization-overview.md)).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dfda1-120">Los archivos de recursos descritos en esta sección son diferentes de los archivos de recursos descritos en [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md) y diferentes de los recursos incrustados o vinculados descritos en Administrar recursos de aplicación [(.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="dfda1-120">The resource files described in this section are different than the resource files described in [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md) and different than the embedded or linked resources described in [Manage Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
### <a name="configuring-resource-files"></a><span data-ttu-id="dfda1-121">Configuración de archivos de recursos</span><span class="sxs-lookup"><span data-stu-id="dfda1-121">Configuring Resource Files</span></span>  
 <span data-ttu-id="dfda1-122">En WPFWPF, un archivo de recursos es un archivo que se incluye `Resource` en un proyecto de motor de compilación de Microsoft (MSBuild) como un elemento.</span><span class="sxs-lookup"><span data-stu-id="dfda1-122">In WPF, a resource file is a file that is included in an Microsoft build engine (MSBuild) project as a `Resource` item.</span></span>  
  
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
> <span data-ttu-id="dfda1-123">En Visual Studio, se crea un archivo de recursos `Build Action` agregando un archivo a un proyecto y estableciendo su valor `Resource`en .</span><span class="sxs-lookup"><span data-stu-id="dfda1-123">In Visual Studio, you create a resource file by adding a file to a project and setting its `Build Action` to `Resource`.</span></span>  
  
 <span data-ttu-id="dfda1-124">Cuando se compila el proyecto, MSBuild compila el recurso en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dfda1-124">When the project is built, MSBuild compiles the resource into the assembly.</span></span>  
  
### <a name="using-resource-files"></a><span data-ttu-id="dfda1-125">Uso de archivos de recursos</span><span class="sxs-lookup"><span data-stu-id="dfda1-125">Using Resource Files</span></span>  
 <span data-ttu-id="dfda1-126">Para cargar un archivo de <xref:System.Windows.Application.GetResourceStream%2A> recursos, <xref:System.Windows.Application> puede llamar al método de la clase, pasando un URI de paquete que identifica el archivo de recursos deseado.</span><span class="sxs-lookup"><span data-stu-id="dfda1-126">To load a resource file, you can call the <xref:System.Windows.Application.GetResourceStream%2A> method of the <xref:System.Windows.Application> class, passing a pack URI that identifies the desired resource file.</span></span> <span data-ttu-id="dfda1-127"><xref:System.Windows.Application.GetResourceStream%2A>devuelve <xref:System.Windows.Resources.StreamResourceInfo> un objeto, que expone el <xref:System.IO.Stream> archivo de recursos como a y describe su tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="dfda1-127"><xref:System.Windows.Application.GetResourceStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the resource file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="dfda1-128">Por ejemplo, el código siguiente <xref:System.Windows.Application.GetResourceStream%2A> muestra cómo <xref:System.Windows.Controls.Page> cargar un archivo de recursos <xref:System.Windows.Controls.Frame> `pageFrame`y establecerlo como el contenido de un ( ):</span><span class="sxs-lookup"><span data-stu-id="dfda1-128">As an example, the following code shows how to use <xref:System.Windows.Application.GetResourceStream%2A> to load a <xref:System.Windows.Controls.Page> resource file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`):</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 <span data-ttu-id="dfda1-129">Mientras <xref:System.Windows.Application.GetResourceStream%2A> que la <xref:System.IO.Stream>llamada le da acceso a la , debe realizar el trabajo adicional de convertirlo en el tipo de la propiedad que va a establecer con.</span><span class="sxs-lookup"><span data-stu-id="dfda1-129">While calling <xref:System.Windows.Application.GetResourceStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="dfda1-130">En su lugar, puede dejar que WPFWPF se encargue de abrir y convertir mediante la <xref:System.IO.Stream> carga de un archivo de recursos directamente en la propiedad de un tipo mediante código.</span><span class="sxs-lookup"><span data-stu-id="dfda1-130">Instead, you can let WPF take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="dfda1-131">En el ejemplo siguiente <xref:System.Windows.Controls.Page> se muestra <xref:System.Windows.Controls.Frame> `pageFrame`cómo cargar un directamente en un ( ) mediante código.</span><span class="sxs-lookup"><span data-stu-id="dfda1-131">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 <span data-ttu-id="dfda1-132">El ejemplo siguiente es el equivalente de marcación del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="dfda1-132">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### <a name="application-code-files-as-resource-files"></a><span data-ttu-id="dfda1-133">Archivos de código de aplicación como archivos de recursos</span><span class="sxs-lookup"><span data-stu-id="dfda1-133">Application Code Files as Resource Files</span></span>  
 <span data-ttu-id="dfda1-134">Se puede hacer referencia a un conjunto especial de archivos de código de aplicación WPF mediante URI de paquete, incluidas ventanas, páginas, documentos de flujo y diccionarios de recursos.</span><span class="sxs-lookup"><span data-stu-id="dfda1-134">A special set of WPF application code files can be referenced using pack URIs, including windows, pages, flow documents, and resource dictionaries.</span></span> <span data-ttu-id="dfda1-135">Por ejemplo, puede <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> establecer la propiedad con un URI de paquete que haga referencia a la ventana o página que desea cargar cuando se inicia una aplicación.</span><span class="sxs-lookup"><span data-stu-id="dfda1-135">For example, you can set the <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> property with a pack URI that references the window or page that you would like to load when an application starts.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 <span data-ttu-id="dfda1-136">Puede hacerlo cuando se incluye un archivo XAML en `Page` un proyecto de MSBuild como elemento.</span><span class="sxs-lookup"><span data-stu-id="dfda1-136">You can do this when a XAML file is included in an MSBuild project as a `Page` item.</span></span>  
  
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
> <span data-ttu-id="dfda1-137">En Visual Studio, agregue <xref:System.Windows.Window> <xref:System.Windows.Navigation.NavigationWindow>un <xref:System.Windows.Controls.Page> <xref:System.Windows.Documents.FlowDocument>nuevo <xref:System.Windows.ResourceDictionary> , , , `Build Action` , , o `Page`a un proyecto, el archivo de marcado se establecerá de forma predeterminada en .</span><span class="sxs-lookup"><span data-stu-id="dfda1-137">In Visual Studio, you add a new <xref:System.Windows.Window>, <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.FlowDocument>, or <xref:System.Windows.ResourceDictionary> to a project, the `Build Action` for the markup file will default to `Page`.</span></span>  
  
 <span data-ttu-id="dfda1-138">Cuando se `Page` compila un proyecto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] con elementos, los elementos se convierten al formato binario y se compilan en el ensamblado asociado.</span><span class="sxs-lookup"><span data-stu-id="dfda1-138">When a project with `Page` items is compiled, the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] items are converted to binary format and compiled into the associated assembly.</span></span> <span data-ttu-id="dfda1-139">Por consiguiente, estos archivos se pueden utilizar de la misma forma que los archivos de recursos típicos.</span><span class="sxs-lookup"><span data-stu-id="dfda1-139">Consequently, these files can be used in the same way as typical resource files.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dfda1-140">Si [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] un archivo está `Resource` configurado como un elemento y no tiene [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] un archivo de código subyacente, el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]sin formato se compila en un ensamblado en lugar de una versión binaria del archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="dfda1-140">If a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is configured as a `Resource` item, and does not have a code-behind file, the raw [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is compiled into an assembly rather than a binary version of the raw [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
<a name="Content_Files"></a>
## <a name="content-files"></a><span data-ttu-id="dfda1-141">Archivos de contenido</span><span class="sxs-lookup"><span data-stu-id="dfda1-141">Content Files</span></span>  
 <span data-ttu-id="dfda1-142">Un archivo de *contenido* se distribuye como un archivo suelto junto a un ensamblado ejecutable.</span><span class="sxs-lookup"><span data-stu-id="dfda1-142">A *content file* is distributed as a loose file alongside an executable assembly.</span></span> <span data-ttu-id="dfda1-143">Aunque no se compilan en un ensamblado, los ensamblados se compilan con metadatos que establecen una asociación con cada archivo de contenido.</span><span class="sxs-lookup"><span data-stu-id="dfda1-143">Although they are not compiled into an assembly, assemblies are compiled with metadata that establishes an association with each content file.</span></span>  
  
 <span data-ttu-id="dfda1-144">Los archivos de contenido se deben usar cuando la aplicación requiere un conjunto específico de archivos de datos de aplicación que desee poder actualizar sin volver a compilar el ensamblado que los consume.</span><span class="sxs-lookup"><span data-stu-id="dfda1-144">You should use content files when your application requires a specific set of application data files that you want to be able to update without recompiling the assembly that consumes them.</span></span>  
  
### <a name="configuring-content-files"></a><span data-ttu-id="dfda1-145">Configuración de archivos de contenido</span><span class="sxs-lookup"><span data-stu-id="dfda1-145">Configuring Content Files</span></span>  
 <span data-ttu-id="dfda1-146">Para agregar un archivo de contenido a un proyecto, `Content` se debe incluir un archivo de datos de aplicación como elemento.</span><span class="sxs-lookup"><span data-stu-id="dfda1-146">To add a content file to a project, an application data file must be included as a `Content` item.</span></span> <span data-ttu-id="dfda1-147">Además, dado que un archivo de contenido no se compila directamente en el ensamblado, debe establecer el elemento de metadatos de MSBuild `CopyToOutputDirectory` para especificar que el archivo de contenido se copia en una ubicación relativa al ensamblado compilado.</span><span class="sxs-lookup"><span data-stu-id="dfda1-147">Furthermore, because a content file is not compiled directly into the assembly, you need to set the MSBuild `CopyToOutputDirectory` metadata element to specify that the content file is copied to a location that is relative to the built assembly.</span></span> <span data-ttu-id="dfda1-148">Si desea que el recurso se copie en la carpeta de salida `CopyToOutputDirectory` de compilación `Always` cada vez que se compila un proyecto, establezca el elemento de metadatos con el valor.</span><span class="sxs-lookup"><span data-stu-id="dfda1-148">If you want the resource to be copied to the build output folder every time a project is built, you set the `CopyToOutputDirectory` metadata element with the `Always` value.</span></span> <span data-ttu-id="dfda1-149">De lo contrario, puede asegurarse de que solo se copia la versión más reciente del recurso en la carpeta de salida de compilación mediante el `PreserveNewest` valor.</span><span class="sxs-lookup"><span data-stu-id="dfda1-149">Otherwise, you can ensure that only the newest version of the resource is copied to the build output folder by using the `PreserveNewest` value.</span></span>  
  
 <span data-ttu-id="dfda1-150">A continuación muestra un archivo que se configura como un archivo de contenido que se copia en la carpeta de salida de compilación solo cuando se agrega al proyecto una nueva versión del recurso.</span><span class="sxs-lookup"><span data-stu-id="dfda1-150">The following shows a file that is configured as a content file which is copied to the build output folder only when a new version of the resource is added to the project.</span></span>  
  
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
> <span data-ttu-id="dfda1-151">En Visual Studio, se crea un archivo de contenido `Build Action` agregando un archivo a un proyecto y estableciendo su `Content`en , y establezca su `Copy to Output Directory` en `Copy always` (igual que `Always`) y `Copy if newer` (igual que `PreserveNewest`).</span><span class="sxs-lookup"><span data-stu-id="dfda1-151">In Visual Studio, you create a content file by adding a file to a project and setting its `Build Action` to `Content`, and set its `Copy to Output Directory` to `Copy always` (same as `Always`) and `Copy if newer` (same as `PreserveNewest`).</span></span>  
  
 <span data-ttu-id="dfda1-152">Cuando se compila el <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> proyecto, se compila un atributo en los metadatos del ensamblado para cada archivo de contenido.</span><span class="sxs-lookup"><span data-stu-id="dfda1-152">When the project is built, an <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is compiled into the metadata of the assembly for each content file.</span></span>  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 <span data-ttu-id="dfda1-153">El valor <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> de la implica la ruta de acceso al archivo de contenido en relación con su posición en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="dfda1-153">The value of the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> implies the path to the content file relative to its position in the project.</span></span> <span data-ttu-id="dfda1-154">Por ejemplo, si un archivo de contenido se encuentra en una subcarpeta <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> de proyecto, la información de ruta de acceso adicional se incorporaría al valor.</span><span class="sxs-lookup"><span data-stu-id="dfda1-154">For example, if a content file was located in a project subfolder, the additional path information would be incorporated into the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> value.</span></span>  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 <span data-ttu-id="dfda1-155">El <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> valor también es el valor de la ruta de acceso al archivo de contenido en la carpeta de salida de compilación.</span><span class="sxs-lookup"><span data-stu-id="dfda1-155">The <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> value is also the value of the path to the content file in the build output folder.</span></span>  
  
### <a name="using-content-files"></a><span data-ttu-id="dfda1-156">Uso de archivos de contenido</span><span class="sxs-lookup"><span data-stu-id="dfda1-156">Using Content Files</span></span>  
 <span data-ttu-id="dfda1-157">Para cargar un archivo de <xref:System.Windows.Application.GetContentStream%2A> contenido, <xref:System.Windows.Application> puede llamar al método de la clase, pasando un URI de paquete que identifica el archivo de contenido deseado.</span><span class="sxs-lookup"><span data-stu-id="dfda1-157">To load a content file, you can call the <xref:System.Windows.Application.GetContentStream%2A> method of the <xref:System.Windows.Application> class, passing a pack URI that identifies the desired content file.</span></span> <span data-ttu-id="dfda1-158"><xref:System.Windows.Application.GetContentStream%2A>devuelve <xref:System.Windows.Resources.StreamResourceInfo> un objeto, que expone el <xref:System.IO.Stream> archivo de contenido como a y describe su tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="dfda1-158"><xref:System.Windows.Application.GetContentStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the content file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="dfda1-159">Por ejemplo, el código siguiente <xref:System.Windows.Application.GetContentStream%2A> muestra cómo <xref:System.Windows.Controls.Page> cargar un archivo de contenido <xref:System.Windows.Controls.Frame> `pageFrame`y establecerlo como el contenido de un ( ).</span><span class="sxs-lookup"><span data-stu-id="dfda1-159">As an example, the following code shows how to use <xref:System.Windows.Application.GetContentStream%2A> to load a <xref:System.Windows.Controls.Page> content file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`).</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 <span data-ttu-id="dfda1-160">Mientras <xref:System.Windows.Application.GetContentStream%2A> que la <xref:System.IO.Stream>llamada le da acceso a la , debe realizar el trabajo adicional de convertirlo en el tipo de la propiedad que va a establecer con.</span><span class="sxs-lookup"><span data-stu-id="dfda1-160">While calling <xref:System.Windows.Application.GetContentStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="dfda1-161">En su lugar, puede dejar que WPFWPF se encargue de abrir y convertir mediante la <xref:System.IO.Stream> carga de un archivo de recursos directamente en la propiedad de un tipo mediante código.</span><span class="sxs-lookup"><span data-stu-id="dfda1-161">Instead, you can let WPF take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="dfda1-162">En el ejemplo siguiente <xref:System.Windows.Controls.Page> se muestra <xref:System.Windows.Controls.Frame> `pageFrame`cómo cargar un directamente en un ( ) mediante código.</span><span class="sxs-lookup"><span data-stu-id="dfda1-162">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 <span data-ttu-id="dfda1-163">El ejemplo siguiente es el equivalente de marcación del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="dfda1-163">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>
## <a name="site-of-origin-files"></a><span data-ttu-id="dfda1-164">Sitio de archivos de origen</span><span class="sxs-lookup"><span data-stu-id="dfda1-164">Site of Origin Files</span></span>  
 <span data-ttu-id="dfda1-165">Los archivos de recursos tienen una relación explícita con los ensamblados que se distribuyen junto, según lo definido por el <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>archivo .</span><span class="sxs-lookup"><span data-stu-id="dfda1-165">Resource files have an explicit relationship with the assemblies that they are distributed alongside, as defined by the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>.</span></span> <span data-ttu-id="dfda1-166">Sin embargo, hay veces en las que puede desear establecer una relación implícita o inexistente entre un ensamblado y un archivo de datos de aplicación, incluyendo cuándo:</span><span class="sxs-lookup"><span data-stu-id="dfda1-166">But, there are times when you may want to establish either an implicit or non-existent relationship between an assembly and an application data file, including when:</span></span>  
  
- <span data-ttu-id="dfda1-167">Un archivo no existe en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="dfda1-167">A file doesn't exist at compile time.</span></span>  
  
- <span data-ttu-id="dfda1-168">No sabe qué archivos requerirá el ensamblado hasta el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="dfda1-168">You don't know what files your assembly will require until run time.</span></span>  
  
- <span data-ttu-id="dfda1-169">Desea poder actualizar los archivos sin volver a compilar el ensamblado al que están asociados.</span><span class="sxs-lookup"><span data-stu-id="dfda1-169">You want to be able to update files without recompiling the assembly that they are associated with.</span></span>  
  
- <span data-ttu-id="dfda1-170">La aplicación utiliza archivos de datos grandes, como audio y vídeo, y solo desea que los usuarios los descarguen si eligen hacerlo.</span><span class="sxs-lookup"><span data-stu-id="dfda1-170">Your application uses large data files, such as audio and video, and you only want users to download them if they choose to.</span></span>  
  
 <span data-ttu-id="dfda1-171">Es posible cargar estos tipos de archivos mediante esquemas URI tradicionales, como los esquemas de file:/// y http://.</span><span class="sxs-lookup"><span data-stu-id="dfda1-171">It is possible to load these types of files by using traditional URI schemes, such as the file:/// and http:// schemes.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 <span data-ttu-id="dfda1-172">Sin embargo, los esquemas file:/// y http:// requieren que la aplicación tenga plena confianza.</span><span class="sxs-lookup"><span data-stu-id="dfda1-172">However, the file:/// and http:// schemes require your application to have full trust.</span></span> <span data-ttu-id="dfda1-173">Si la aplicación es una aplicación de explorador XAML (XBAP) que se inició desde Internet o intranet, y solo solicita el conjunto de permisos permitidos para las aplicaciones iniciadas desde esas ubicaciones, los archivos sueltos solo se pueden cargar desde el lugar de origen de la aplicación (ubicación de lanzamiento).</span><span class="sxs-lookup"><span data-stu-id="dfda1-173">If your application is a XAML browser application (XBAP) that was launched from the Internet or intranet, and it requests only the set of permissions that are allowed for applications launched from those locations, loose files can only be loaded from the application's site of origin (launch location).</span></span> <span data-ttu-id="dfda1-174">Tales archivos se conocen como archivos *de sitio de origen.*</span><span class="sxs-lookup"><span data-stu-id="dfda1-174">Such files are known as *site of origin* files.</span></span>  
  
 <span data-ttu-id="dfda1-175">Los archivos del sitio de origen son la única opción para las aplicaciones de confianza parcial, aunque no se limitan a ese tipo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="dfda1-175">Site of origin files are the only option for partial trust applications, although are not limited to partial trust applications.</span></span> <span data-ttu-id="dfda1-176">Es posible que las aplicaciones de plena confianza aún necesiten cargar archivos de datos de aplicación que desconocen en tiempo de compilación; mientras que las aplicaciones de plena confianza pueden utilizar file:///, es probable que los archivos de datos de la aplicación se instalarán en la misma carpeta que el ensamblado de la aplicación, o en una subcarpeta de él.</span><span class="sxs-lookup"><span data-stu-id="dfda1-176">Full trust applications may still need to load application data files that they do not know about at build time; while full trust applications could use file:///, it is likely that the application data files will be installed in the same folder as, or a subfolder of, the application assembly.</span></span> <span data-ttu-id="dfda1-177">En este caso, es más sencillo usar la referencia del sitio de origen que file:///, ya que el uso de file:/// requiere que se determine la ruta de acceso completa del archivo.</span><span class="sxs-lookup"><span data-stu-id="dfda1-177">In this case, using site of origin referencing is easier than using file:///, because using file:/// requires you to work out the full path the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dfda1-178">Los archivos de sitio de origen no se almacenan en caché con una aplicación de explorador XAML (XBAP) en un equipo cliente, mientras que los archivos de contenido lo son.</span><span class="sxs-lookup"><span data-stu-id="dfda1-178">Site of origin files are not cached with an XAML browser application (XBAP) on a client machine, while content files are.</span></span> <span data-ttu-id="dfda1-179">Por consiguiente, sólo se descargan cuando se solicita específicamente.</span><span class="sxs-lookup"><span data-stu-id="dfda1-179">Consequently, they are only downloaded when specifically requested.</span></span> <span data-ttu-id="dfda1-180">Si una aplicación de explorador XAML (XBAP) tiene archivos multimedia de gran tamaño, configurarlos como archivos de sitio de origen significa que el inicio inicial de la aplicación es mucho más rápido y los archivos solo se descargan a petición.</span><span class="sxs-lookup"><span data-stu-id="dfda1-180">If an XAML browser application (XBAP) application has large media files, configuring them as site of origin files means the initial application launch is much faster, and the files are only downloaded on demand.</span></span>  
  
### <a name="configuring-site-of-origin-files"></a><span data-ttu-id="dfda1-181">Configuración de archivos de sitio de origen</span><span class="sxs-lookup"><span data-stu-id="dfda1-181">Configuring Site of Origin Files</span></span>  
 <span data-ttu-id="dfda1-182">Si los archivos de sitio de origen son inexistentes o desconocidos en tiempo de compilación, debe usar mecanismos de `XCopy` implementación tradicionales para garantizar que los archivos necesarios estén disponibles en tiempo de ejecución, incluido el programa de línea de comandos o Microsoft Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="dfda1-182">If your site of origin files are non-existent or unknown at compile time, you need to use traditional deployment mechanisms for ensuring the required files are available at run time, including using either the `XCopy` command-line program or the Microsoft Windows Installer.</span></span>  
  
 <span data-ttu-id="dfda1-183">Si sabe en tiempo de compilación los archivos que desea que se encuentren en el sitio de origen, pero aún así `None` desea evitar una dependencia explícita, puede agregar esos archivos a un proyecto de MSBuild como elemento.</span><span class="sxs-lookup"><span data-stu-id="dfda1-183">If you do know at compile time the files that you would like to be located at the site of origin, but still want to avoid an explicit dependency, you can add those files to an MSBuild project as `None` item.</span></span> <span data-ttu-id="dfda1-184">Al igual que con los archivos de `CopyToOutputDirectory` contenido, debe establecer el atributo MSBuild para especificar que el archivo de `Always` sitio de `PreserveNewest` origen se copia en una ubicación relativa al ensamblado compilado, especificando el valor o el valor.</span><span class="sxs-lookup"><span data-stu-id="dfda1-184">As with content files, you need to set the MSBuild `CopyToOutputDirectory` attribute to specify that the site of origin file is copied to a location that is relative to the built assembly, by specifying either the `Always` value or the `PreserveNewest` value.</span></span>  
  
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
> <span data-ttu-id="dfda1-185">En Visual Studio, se crea un archivo de sitio de `Build Action` origen `None`agregando un archivo a un proyecto y estableciendo su valor en .</span><span class="sxs-lookup"><span data-stu-id="dfda1-185">In Visual Studio, you create a site of origin file by adding a file to a project and setting its `Build Action` to `None`.</span></span>  
  
 <span data-ttu-id="dfda1-186">Cuando se compila el proyecto, MSBuild copia los archivos especificados en la carpeta de salida de compilación.</span><span class="sxs-lookup"><span data-stu-id="dfda1-186">When the project is built, MSBuild copies the specified files to the build output folder.</span></span>  
  
### <a name="using-site-of-origin-files"></a><span data-ttu-id="dfda1-187">Uso de archivos del sitio de origen</span><span class="sxs-lookup"><span data-stu-id="dfda1-187">Using Site of Origin Files</span></span>  
 <span data-ttu-id="dfda1-188">Para cargar un archivo de sitio <xref:System.Windows.Application.GetRemoteStream%2A> de origen, puede llamar al método de la <xref:System.Windows.Application> clase, pasando un URI de paquete que identifica el archivo de sitio de origen deseado.</span><span class="sxs-lookup"><span data-stu-id="dfda1-188">To load a site of origin file, you can call the <xref:System.Windows.Application.GetRemoteStream%2A> method of the <xref:System.Windows.Application> class, passing a pack URI that identifies the desired site of origin file.</span></span> <span data-ttu-id="dfda1-189"><xref:System.Windows.Application.GetRemoteStream%2A>devuelve <xref:System.Windows.Resources.StreamResourceInfo> un objeto, que expone el archivo <xref:System.IO.Stream> de sitio de origen como a y describe su tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="dfda1-189"><xref:System.Windows.Application.GetRemoteStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the site of origin file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="dfda1-190">Por ejemplo, el código siguiente <xref:System.Windows.Application.GetRemoteStream%2A> muestra cómo <xref:System.Windows.Controls.Page> usar para cargar un archivo de <xref:System.Windows.Controls.Frame> `pageFrame`sitio de origen y establecerlo como el contenido de un ( ).</span><span class="sxs-lookup"><span data-stu-id="dfda1-190">As an example, the following code shows how to use <xref:System.Windows.Application.GetRemoteStream%2A> to load a <xref:System.Windows.Controls.Page> site of origin file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`).</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 <span data-ttu-id="dfda1-191">Mientras <xref:System.Windows.Application.GetRemoteStream%2A> que la <xref:System.IO.Stream>llamada le da acceso a la , debe realizar el trabajo adicional de convertirlo en el tipo de la propiedad que va a establecer con.</span><span class="sxs-lookup"><span data-stu-id="dfda1-191">While calling <xref:System.Windows.Application.GetRemoteStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="dfda1-192">En su lugar, puede dejar que WPFWPF se encargue de abrir y convertir mediante la <xref:System.IO.Stream> carga de un archivo de recursos directamente en la propiedad de un tipo mediante código.</span><span class="sxs-lookup"><span data-stu-id="dfda1-192">Instead, you can let WPF take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="dfda1-193">En el ejemplo siguiente <xref:System.Windows.Controls.Page> se muestra <xref:System.Windows.Controls.Frame> `pageFrame`cómo cargar un directamente en un ( ) mediante código.</span><span class="sxs-lookup"><span data-stu-id="dfda1-193">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 <span data-ttu-id="dfda1-194">El ejemplo siguiente es el equivalente de marcación del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="dfda1-194">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>
## <a name="rebuilding-after-changing-build-type"></a><span data-ttu-id="dfda1-195">Nueva compilación después de cambiar el tipo de compilación</span><span class="sxs-lookup"><span data-stu-id="dfda1-195">Rebuilding After Changing Build Type</span></span>  
 <span data-ttu-id="dfda1-196">Después de cambiar el tipo de compilación de un archivo de datos de aplicación, es preciso volver a compilar toda la aplicación para asegurarse de que se aplican los cambios.</span><span class="sxs-lookup"><span data-stu-id="dfda1-196">After you change the build type of an application data file, you need to rebuild the entire application to ensure those changes are applied.</span></span> <span data-ttu-id="dfda1-197">Si solo compila la aplicación, no se aplican los cambios.</span><span class="sxs-lookup"><span data-stu-id="dfda1-197">If you only build the application, the changes are not applied.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfda1-198">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dfda1-198">See also</span></span>

- [<span data-ttu-id="dfda1-199">Empaquetar URI en WPF</span><span class="sxs-lookup"><span data-stu-id="dfda1-199">Pack URIs in WPF</span></span>](pack-uris-in-wpf.md)

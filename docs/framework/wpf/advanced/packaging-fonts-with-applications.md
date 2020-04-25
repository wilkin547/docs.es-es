---
title: Empaquetar fuentes con aplicaciones
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], packaging fonts with
- fonts [WPF], packaging with applications
- typography [WPF], packaging fonts with applications
- packaging fonts with applications [WPF]
ms.assetid: db15ee48-4d24-49f5-8b9d-a64460865286
ms.openlocfilehash: 7bdf3b11557d94ab39c93a21ac53b917e3a1767d
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141120"
---
# <a name="packaging-fonts-with-applications"></a><span data-ttu-id="edcdf-102">Empaquetar fuentes con aplicaciones</span><span class="sxs-lookup"><span data-stu-id="edcdf-102">Packaging Fonts with Applications</span></span>
<span data-ttu-id="edcdf-103">En este tema se proporciona información general sobre cómo empaquetar fuentes [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="edcdf-103">This topic provides an overview of how to package fonts with your [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="edcdf-104">Como con la mayoría de los tipos de software, los archivos de fuentes se otorgan bajo licencia, no se venden.</span><span class="sxs-lookup"><span data-stu-id="edcdf-104">As with most types of software, font files are licensed, rather than sold.</span></span> <span data-ttu-id="edcdf-105">Las licencias que rigen el uso de las fuentes varían de un proveedor a otro, pero en general, la mayoría de las licencias, incluidas las que abarcan las fuentes que Microsoft suministra con las aplicaciones y las ventanas, no permiten incrustar las fuentes dentro de aplicaciones ni redistribuirlas de ningún otro modo.</span><span class="sxs-lookup"><span data-stu-id="edcdf-105">Licenses that govern the use of fonts vary from vendor to vendor but in general most licenses, including those covering the fonts Microsoft supplies with applications and Windows, do not allow the fonts to be embedded within applications or otherwise redistributed.</span></span> <span data-ttu-id="edcdf-106">Así pues, como programador, su responsabilidad es asegurarse de disponer de los derechos de licencia necesarios para cualquier fuente que incruste en una aplicación o redistribuya de cualquier otro modo.</span><span class="sxs-lookup"><span data-stu-id="edcdf-106">Therefore, as a developer it is your responsibility to ensure that you have the required license rights for any font you embed within an application or otherwise redistribute.</span></span>  

<a name="introduction_to_packaging_fonts"></a>
## <a name="introduction-to-packaging-fonts"></a><span data-ttu-id="edcdf-107">Introducción al empaquetado de fuentes</span><span class="sxs-lookup"><span data-stu-id="edcdf-107">Introduction to Packaging Fonts</span></span>  
 <span data-ttu-id="edcdf-108">Puede empaquetar fuentes fácilmente como recursos dentro de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] las aplicaciones para mostrar el texto de la interfaz de usuario y otros tipos de contenido basado en texto.</span><span class="sxs-lookup"><span data-stu-id="edcdf-108">You can easily package fonts as resources within your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications to display user interface text and other types of text based content.</span></span> <span data-ttu-id="edcdf-109">Las fuentes pueden ser independientes de los archivos de ensamblado de la aplicación o incrustadas en dichos archivos.</span><span class="sxs-lookup"><span data-stu-id="edcdf-109">The fonts can be separate from or embedded within the application's assembly files.</span></span> <span data-ttu-id="edcdf-110">También puede crear una biblioteca de fuentes solo de recursos, a la que puede hacer referencia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="edcdf-110">You can also create a resource-only font library, which your application can reference.</span></span>  
  
 <span data-ttu-id="edcdf-111">Las fuentes OpenType y TrueType® contienen una marca de tipo, fsType, que indica los derechos de licencia de incrustación de fuentes para la fuente.</span><span class="sxs-lookup"><span data-stu-id="edcdf-111">OpenType and TrueType® fonts contain a type flag, fsType, that indicates font embedding licensing rights for the font.</span></span> <span data-ttu-id="edcdf-112">Sin embargo, este tipo de marca solo hace referencia a fuentes incrustadas almacenadas en un documento: no hace referencia a fuentes incrustadas en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="edcdf-112">However, this type flag only refers to embedded fonts stored in a document–it does not refer to fonts embedded in an application.</span></span> <span data-ttu-id="edcdf-113">Puede recuperar los derechos de incrustación de fuentes para una fuente creando <xref:System.Windows.Media.GlyphTypeface> un objeto y haciendo <xref:System.Windows.Media.GlyphTypeface.EmbeddingRights%2A> referencia a su propiedad.</span><span class="sxs-lookup"><span data-stu-id="edcdf-113">You can retrieve the font embedding rights for a font by creating a <xref:System.Windows.Media.GlyphTypeface> object and referencing its <xref:System.Windows.Media.GlyphTypeface.EmbeddingRights%2A> property.</span></span> <span data-ttu-id="edcdf-114">Consulte la sección "OS/2 y métricas de Windows" de la [especificación OpenType](https://www.microsoft.com/typography/otspec/os2.htm) para obtener más información sobre la marca fstype.</span><span class="sxs-lookup"><span data-stu-id="edcdf-114">Refer to the "OS/2 and Windows Metrics" section of the [OpenType Specification](https://www.microsoft.com/typography/otspec/os2.htm) for more information on the fsType flag.</span></span>  
  
 <span data-ttu-id="edcdf-115">El sitio web de [tipografía de Microsoft](https://docs.microsoft.com/typography/) incluye información de contacto que puede ayudarle a encontrar un proveedor de fuentes determinado o a encontrar un proveedor de fuentes para el trabajo personalizado.</span><span class="sxs-lookup"><span data-stu-id="edcdf-115">The [Microsoft Typography](https://docs.microsoft.com/typography/) Web site includes contact information that can help you locate a particular font vendor or find a font vendor for custom work.</span></span>  
  
<a name="adding_fonts_as_content_items"></a>
## <a name="adding-fonts-as-content-items"></a><span data-ttu-id="edcdf-116">Agregar fuentes como elementos de contenido</span><span class="sxs-lookup"><span data-stu-id="edcdf-116">Adding Fonts as Content Items</span></span>  
 <span data-ttu-id="edcdf-117">Puede agregar las fuentes a la aplicación como elementos de contenido del proyecto independientes de los archivos de ensamblado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="edcdf-117">You can add fonts to your application as project content items that are separate from the application's assembly files.</span></span> <span data-ttu-id="edcdf-118">Esto significa que los elementos de contenido no se incrustan como recursos en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="edcdf-118">This means that content items are not embedded as resources within an assembly.</span></span> <span data-ttu-id="edcdf-119">En el siguiente ejemplo de archivo de proyecto se muestra cómo definir elementos de contenido.</span><span class="sxs-lookup"><span data-stu-id="edcdf-119">The following project file example shows how to define content items.</span></span>  
  
```xml  
<Project DefaultTargets="Build"  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <!-- Other project build settings ... -->  
  
  <ItemGroup>  
    <Content Include="Peric.ttf" />  
    <Content Include="Pericl.ttf" />  
  </ItemGroup>  
</Project>  
```  
  
 <span data-ttu-id="edcdf-120">Para asegurarse de que la aplicación puede usar las fuentes en tiempo de ejecución, las fuentes deben ser accesibles en el directorio de implementación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="edcdf-120">In order to ensure that the application can use the fonts at run time, the fonts must be accessible in the application's deployment directory.</span></span> <span data-ttu-id="edcdf-121">El `<CopyToOutputDirectory>` elemento del archivo de proyecto de la aplicación permite copiar automáticamente las fuentes en el directorio de implementación de la aplicación durante el proceso de compilación.</span><span class="sxs-lookup"><span data-stu-id="edcdf-121">The `<CopyToOutputDirectory>` element in the application's project file allows you to automatically copy the fonts to the application deployment directory during the build process.</span></span> <span data-ttu-id="edcdf-122">En el siguiente ejemplo de archivo de proyecto se muestra cómo copiar las fuentes en el directorio de implementación.</span><span class="sxs-lookup"><span data-stu-id="edcdf-122">The following project file example shows how to copy fonts to the deployment directory.</span></span>  
  
```xml  
<ItemGroup>  
  <Content Include="Peric.ttf">  
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
  </Content>  
  <Content Include="Pericl.ttf">  
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
  </Content>  
</ItemGroup>  
```  
  
 <span data-ttu-id="edcdf-123">En el ejemplo de código siguiente se muestra cómo hacer referencia a la fuente de la aplicación como un elemento de contenido: el elemento de contenido al que se hace referencia debe estar en el mismo directorio que los archivos de ensamblado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="edcdf-123">The following code example shows how to reference the application's font as a content item—the referenced content item must be in the same directory as the application's assembly files.</span></span>  
  
 [!code-xaml[FontSnippets#FontPackageSnippet8](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet8)]  
  
<a name="adding_fonts_as_resource_items"></a>
## <a name="adding-fonts-as-resource-items"></a><span data-ttu-id="edcdf-124">Agregar fuentes como elementos de recursos</span><span class="sxs-lookup"><span data-stu-id="edcdf-124">Adding Fonts as Resource Items</span></span>  
 <span data-ttu-id="edcdf-125">Puede agregar fuentes a la aplicación como elementos de recursos del proyecto incrustados dentro de los archivos de ensamblado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="edcdf-125">You can add fonts to your application as project resource items that are embedded within the application's assembly files.</span></span> <span data-ttu-id="edcdf-126">Usar un subdirectorio independiente para los recursos ayuda a organizar los archivos de proyecto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="edcdf-126">Using a separate subdirectory for resources helps to organize the application's project files.</span></span> <span data-ttu-id="edcdf-127">En el siguiente ejemplo de archivo de proyecto se muestra cómo definir las fuentes como elementos de recursos en un subdirectorio independiente.</span><span class="sxs-lookup"><span data-stu-id="edcdf-127">The following project file example shows how to define fonts as resource items in a separate subdirectory.</span></span>  
  
```xml  
<Project DefaultTargets="Build"  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <!-- Other project build settings ... -->  
  
  <ItemGroup>  
    <Resource Include="resources\Peric.ttf" />  
    <Resource Include="resources\Pericl.ttf" />  
  </ItemGroup>  
</Project>  
```  
  
> [!NOTE]
> <span data-ttu-id="edcdf-128">Al agregar fuentes como recursos a la aplicación, asegúrese de que está estableciendo el `<Resource>` elemento, y no el `<EmbeddedResource>` elemento en el archivo de proyecto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="edcdf-128">When you add fonts as resources to your application, make sure you are setting the `<Resource>` element, and not the `<EmbeddedResource>` element in your application's project file.</span></span> <span data-ttu-id="edcdf-129">No `<EmbeddedResource>` se admite el elemento para la acción de compilación.</span><span class="sxs-lookup"><span data-stu-id="edcdf-129">The `<EmbeddedResource>` element for the build action is not supported.</span></span>  
  
 <span data-ttu-id="edcdf-130">En el ejemplo de marcado siguiente se muestra cómo hacer referencia a los recursos de fuentes de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="edcdf-130">The following markup example shows how to reference the application's font resources.</span></span>  
  
 [!code-xaml[FontSnippets#FontPackageSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet1)]  
  
### <a name="referencing-font-resource-items-from-code"></a><span data-ttu-id="edcdf-131">Hacer referencia a elementos de recursos de fuentes desde el código</span><span class="sxs-lookup"><span data-stu-id="edcdf-131">Referencing Font Resource Items from Code</span></span>  
 <span data-ttu-id="edcdf-132">Para hacer referencia a elementos de recursos de fuentes desde el código, debe proporcionar una referencia de recurso de fuente de dos partes: el identificador uniforme de recursos (URI) base; y la referencia de la ubicación de fuentes.</span><span class="sxs-lookup"><span data-stu-id="edcdf-132">In order to reference font resource items from code, you must supply a two-part font resource reference: the base uniform resource identifier (URI); and the font location reference.</span></span> <span data-ttu-id="edcdf-133">Estos valores se usan como parámetros para el <xref:System.Windows.Media.FontFamily.%23ctor%2A> método.</span><span class="sxs-lookup"><span data-stu-id="edcdf-133">These values are used as the parameters for the <xref:System.Windows.Media.FontFamily.%23ctor%2A> method.</span></span> <span data-ttu-id="edcdf-134">En el ejemplo de código siguiente se muestra cómo hacer referencia a los recursos de fuente de la aplicación en `resources`el subdirectorio del proyecto denominado.</span><span class="sxs-lookup"><span data-stu-id="edcdf-134">The following code example shows how to reference the application's font resources in the project subdirectory called `resources`.</span></span>  
  
 [!code-csharp[FontSnippets#FontPackageSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet2)]
 [!code-vb[FontSnippets#FontPackageSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet2)]  
  
 <span data-ttu-id="edcdf-135">El identificador uniforme de recursos (URI) base puede incluir el subdirectorio de la aplicación donde reside el recurso de fuente.</span><span class="sxs-lookup"><span data-stu-id="edcdf-135">The base uniform resource identifier (URI) can include the application subdirectory where the font resource resides.</span></span> <span data-ttu-id="edcdf-136">En este caso, la referencia de ubicación de fuentes no necesitaría especificar un directorio, pero tendría que incluir un "`./`" inicial, que indica que el recurso de fuente está en el mismo directorio especificado por el identificador uniforme de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="edcdf-136">In this case, the font location reference would not need to specify a directory, but would have to include a leading "`./`", which indicates the font resource is in the same directory specified by the base uniform resource identifier (URI).</span></span> <span data-ttu-id="edcdf-137">En el ejemplo de código siguiente se muestra una manera alternativa de hacer referencia al elemento de recursos de fuentes: es equivalente al ejemplo de código anterior.</span><span class="sxs-lookup"><span data-stu-id="edcdf-137">The following code example shows an alternate way of referencing the font resource item—it is equivalent to the previous code example.</span></span>  
  
 [!code-csharp[FontSnippets#FontPackageSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet5)]
 [!code-vb[FontSnippets#FontPackageSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet5)]  
  
### <a name="referencing-fonts-from-the-same-application-subdirectory"></a><span data-ttu-id="edcdf-138">Hacer referencia a fuentes desde el mismo subdirectorio de aplicación</span><span class="sxs-lookup"><span data-stu-id="edcdf-138">Referencing Fonts from the Same Application Subdirectory</span></span>  
 <span data-ttu-id="edcdf-139">Puede colocar archivos de contenido y de recursos de aplicación dentro del mismo subdirectorio definido por el usuario del proyecto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="edcdf-139">You can place both application content and resource files within the same user-defined subdirectory of your application project.</span></span> <span data-ttu-id="edcdf-140">En el siguiente ejemplo de archivo de proyecto se muestra una página de contenido y recursos de fuentes definidos en el mismo subdirectorio.</span><span class="sxs-lookup"><span data-stu-id="edcdf-140">The following project file example shows a content page and font resources defined in the same subdirectory.</span></span>  
  
```xml  
<ItemGroup>  
  <Page Include="pages\HomePage.xaml" />  
</ItemGroup>  
<ItemGroup>  
  <Resource Include="pages\Peric.ttf" />  
  <Resource Include="pages\Pericl.ttf" />  
</ItemGroup>  
```  
  
 <span data-ttu-id="edcdf-141">Puesto que el contenido de la aplicación y la fuente están en el mismo subdirectorio, la referencia de fuentes está relacionada con el contenido de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="edcdf-141">Since the application content and font are in the same subdirectory, the font reference is relative to the application content.</span></span> <span data-ttu-id="edcdf-142">En los ejemplos siguientes se muestra cómo hacer referencia a recursos de fuentes de la aplicación cuando la fuente está en el mismo directorio que la aplicación.</span><span class="sxs-lookup"><span data-stu-id="edcdf-142">The following examples show how to reference the application's font resource when the font is in the same directory as the application.</span></span>  
  
 [!code-xaml[FontSnippets#FontPackageSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml#fontpackagesnippet3)]  
  
 [!code-csharp[FontSnippets#FontPackageSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml.cs#fontpackagesnippet4)]
 [!code-vb[FontSnippets#FontPackageSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/pages/homepage.xaml.vb#fontpackagesnippet4)]  
  
### <a name="enumerating-fonts-in-an-application"></a><span data-ttu-id="edcdf-143">Enumerar fuentes en una aplicación</span><span class="sxs-lookup"><span data-stu-id="edcdf-143">Enumerating Fonts in an Application</span></span>  
 <span data-ttu-id="edcdf-144">Para enumerar las fuentes como elementos de recursos en la aplicación, use <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> el <xref:System.Windows.Media.Fonts.GetTypefaces%2A> método o.</span><span class="sxs-lookup"><span data-stu-id="edcdf-144">To enumerate fonts as resource items in your application, use either the <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> or <xref:System.Windows.Media.Fonts.GetTypefaces%2A> method.</span></span> <span data-ttu-id="edcdf-145">En el ejemplo siguiente se muestra cómo utilizar <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> el método para devolver la colección <xref:System.Windows.Media.FontFamily> de objetos de la ubicación de fuentes de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="edcdf-145">The following example shows how to use the <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> method to return the collection of <xref:System.Windows.Media.FontFamily> objects from the application font location.</span></span> <span data-ttu-id="edcdf-146">En este caso, la aplicación contiene un subdirectorio llamado "resources".</span><span class="sxs-lookup"><span data-stu-id="edcdf-146">In this case, the application contains a subdirectory named "resources".</span></span>  
  
 [!code-csharp[FontSnippets#FontsSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet3)]
 [!code-vb[FontSnippets#FontsSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet3)]  
  
 <span data-ttu-id="edcdf-147">En el ejemplo siguiente se muestra cómo utilizar <xref:System.Windows.Media.Fonts.GetTypefaces%2A> el método para devolver la colección <xref:System.Windows.Media.Typeface> de objetos de la ubicación de fuentes de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="edcdf-147">The following example shows how to use the <xref:System.Windows.Media.Fonts.GetTypefaces%2A> method to return the collection of <xref:System.Windows.Media.Typeface> objects from the application font location.</span></span> <span data-ttu-id="edcdf-148">En este caso, la aplicación contiene un subdirectorio llamado "resources".</span><span class="sxs-lookup"><span data-stu-id="edcdf-148">In this case, the application contains a subdirectory named "resources".</span></span>  
  
 [!code-csharp[FontSnippets#FontsSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet7)]
 [!code-vb[FontSnippets#FontsSnippet7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet7)]  
  
<a name="creating_a_font_resource_library"></a>
## <a name="creating-a-font-resource-library"></a><span data-ttu-id="edcdf-149">Crear una biblioteca de recursos de fuentes</span><span class="sxs-lookup"><span data-stu-id="edcdf-149">Creating a Font Resource Library</span></span>  
 <span data-ttu-id="edcdf-150">Puede crear una biblioteca solo de recursos que contenga solo fuentes: ningún código forma parte de este tipo de proyecto de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="edcdf-150">You can create a resource-only library that contains only fonts—no code is part of this type of library project.</span></span> <span data-ttu-id="edcdf-151">Crear una biblioteca solo de recursos es una técnica común para desacoplar los recursos del código de aplicación que los usa.</span><span class="sxs-lookup"><span data-stu-id="edcdf-151">Creating a resource-only library is a common technique for decoupling resources from the application code that uses them.</span></span> <span data-ttu-id="edcdf-152">Esto también permite que el ensamblado de biblioteca se incluya con varios proyectos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="edcdf-152">This also allows the library assembly to be included with multiple application projects.</span></span> <span data-ttu-id="edcdf-153">En el siguiente ejemplo de archivo de proyecto se muestran las partes clave de un proyecto de biblioteca solo de recursos.</span><span class="sxs-lookup"><span data-stu-id="edcdf-153">The following project file example shows the key portions of a resource-only library project.</span></span>  
  
```xml  
<PropertyGroup>  
  <AssemblyName>FontLibrary</AssemblyName>  
  <OutputType>library</OutputType>  
  ...  
</PropertyGroup>  
...
<ItemGroup>  
  <Resource Include="Kooten.ttf" />  
  <Resource Include="Pesca.ttf" />  
</ItemGroup  
```  
  
### <a name="referencing-a-font-in-a-resource-library"></a><span data-ttu-id="edcdf-154">Hacer referencia a una fuente en una biblioteca de recursos</span><span class="sxs-lookup"><span data-stu-id="edcdf-154">Referencing a Font in a Resource Library</span></span>  
 <span data-ttu-id="edcdf-155">Para hacer referencia a una fuente en una biblioteca de recursos de la aplicación, debe anteponer la referencia de la fuente con el nombre del ensamblado de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="edcdf-155">To reference a font in a resource library from your application, you must prefix the font reference with the name of the library assembly.</span></span> <span data-ttu-id="edcdf-156">En este caso, el ensamblado de recursos de fuentes es "FontLibrary".</span><span class="sxs-lookup"><span data-stu-id="edcdf-156">In this case, the font resource assembly is "FontLibrary".</span></span> <span data-ttu-id="edcdf-157">Para separar el nombre del ensamblado de la referencia dentro del ensamblado, use un carácter ";".</span><span class="sxs-lookup"><span data-stu-id="edcdf-157">To separate the assembly name from the reference within the assembly, use a ';' character.</span></span> <span data-ttu-id="edcdf-158">Agregar la palabra clave "Component" seguida de la referencia al nombre de la fuente completa toda la referencia en el recurso de la biblioteca de fuentes.</span><span class="sxs-lookup"><span data-stu-id="edcdf-158">Adding the "Component" keyword followed by the reference to the font name completes the full reference to the font library's resource.</span></span> <span data-ttu-id="edcdf-159">En el ejemplo de código siguiente se muestra cómo hacer referencia a una fuente en un ensamblado de biblioteca de recursos.</span><span class="sxs-lookup"><span data-stu-id="edcdf-159">The following code example shows how to reference a font in a resource library assembly.</span></span>  
  
 [!code-xaml[OpenTypeFontsSample#OpenTypeFontsSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontsSample/CS/Kootenay.xaml#opentypefontssample1)]  
  
> [!NOTE]
> <span data-ttu-id="edcdf-160">Este SDK contiene un conjunto de fuentes OpenType de ejemplo que puede usar con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="edcdf-160">This SDK contains a set of sample OpenType fonts that you can use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span> <span data-ttu-id="edcdf-161">Las fuentes se definen en una biblioteca solo de recursos.</span><span class="sxs-lookup"><span data-stu-id="edcdf-161">The fonts are defined in a resource-only library.</span></span> <span data-ttu-id="edcdf-162">Para obtener más información, vea [paquete de fuentes OpenType de ejemplo](sample-opentype-font-pack.md).</span><span class="sxs-lookup"><span data-stu-id="edcdf-162">For more information, see [Sample OpenType Font Pack](sample-opentype-font-pack.md).</span></span>  
  
<a name="limitations_on_font_usage"></a>
## <a name="limitations-on-font-usage"></a><span data-ttu-id="edcdf-163">Limitaciones de uso de fuentes</span><span class="sxs-lookup"><span data-stu-id="edcdf-163">Limitations on Font Usage</span></span>  
 <span data-ttu-id="edcdf-164">En la lista siguiente se describen varias limitaciones en el empaquetado y el uso [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de fuentes en aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="edcdf-164">The following list describes several limitations on the packaging and use of fonts in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications:</span></span>  
  
- <span data-ttu-id="edcdf-165">\*\*Bits de permisos de incrustación de fuentes: las aplicaciones \*\* [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no comprueban ni exigen ningún bit de permisos de incrustación de fuentes.</span><span class="sxs-lookup"><span data-stu-id="edcdf-165">**Font embedding permission bits:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not check or enforce any font embedding permission bits.</span></span> <span data-ttu-id="edcdf-166">Vea la sección [fuentes de Introduction_to_Packing](#introduction_to_packaging_fonts) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="edcdf-166">See the [Introduction_to_Packing Fonts](#introduction_to_packaging_fonts) section for more information.</span></span>  
  
- <span data-ttu-id="edcdf-167">**Fuentes de sitio de origen:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] las aplicaciones no admiten una referencia de fuente a un identificador uniforme de recursos (URI) de http o FTP.</span><span class="sxs-lookup"><span data-stu-id="edcdf-167">**Site of origin fonts:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not allow a font reference to an http or ftp uniform resource identifier (URI).</span></span>  
  
- <span data-ttu-id="edcdf-168">**URI absoluto mediante el Pack: Notation:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] las aplicaciones no le permiten crear un <xref:System.Windows.Media.FontFamily> objeto mediante programación usando "Pack:" como parte de la referencia absoluta del identificador uniforme de recursos (URI) a una fuente.</span><span class="sxs-lookup"><span data-stu-id="edcdf-168">**Absolute URI using the pack: notation:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not allow you to create a <xref:System.Windows.Media.FontFamily> object programmatically using "pack:" as part of the absolute uniform resource identifier (URI) reference to a font.</span></span> <span data-ttu-id="edcdf-169">Por ejemplo, `"pack://application:,,,/resources/#Pericles Light"` es una referencia de fuente no válida.</span><span class="sxs-lookup"><span data-stu-id="edcdf-169">For example, `"pack://application:,,,/resources/#Pericles Light"` is an invalid font reference.</span></span>  
  
- <span data-ttu-id="edcdf-170">**Incrustación de fuentes automática:** durante el tiempo de diseño, no hay ninguna compatibilidad para buscar el uso de fuentes de la aplicación ni para incrustar fuentes automáticamente en los recursos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="edcdf-170">**Automatic font embedding:** During design time, there is no support for searching an application's use of fonts and automatically embedding the fonts in the application's resources.</span></span>  
  
- <span data-ttu-id="edcdf-171">\*\*Subconjuntos de fuentes: las aplicaciones \*\* [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no admiten la creación de subconjuntos de fuentes para documentos no fijos.</span><span class="sxs-lookup"><span data-stu-id="edcdf-171">**Font subsets:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not support the creation of font subsets for non-fixed documents.</span></span>  
  
- <span data-ttu-id="edcdf-172">En casos donde hay una referencia incorrecta, la aplicación vuelve a usar una fuente disponible.</span><span class="sxs-lookup"><span data-stu-id="edcdf-172">In cases where there is an incorrect reference, the application falls back to using an available font.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edcdf-173">Vea también</span><span class="sxs-lookup"><span data-stu-id="edcdf-173">See also</span></span>

- <xref:System.Windows.Documents.Typography>
- <xref:System.Windows.Media.FontFamily>
- <span data-ttu-id="edcdf-174">[Microsoft Typography: Links, News, and Contacts](https://docs.microsoft.com/typography/) (Tipografía de Microsoft: vínculos, noticias y contactos)</span><span class="sxs-lookup"><span data-stu-id="edcdf-174">[Microsoft Typography: Links, News, and Contacts](https://docs.microsoft.com/typography/)</span></span>
- <span data-ttu-id="edcdf-175">[OpenType Specification](https://www.microsoft.com/typography/otspec/) (Especificación OpenType)</span><span class="sxs-lookup"><span data-stu-id="edcdf-175">[OpenType Specification](https://www.microsoft.com/typography/otspec/)</span></span>
- [<span data-ttu-id="edcdf-176">Características de las fuentes OpenType</span><span class="sxs-lookup"><span data-stu-id="edcdf-176">OpenType Font Features</span></span>](opentype-font-features.md)
- [<span data-ttu-id="edcdf-177">Paquete de fuentes OpenType de ejemplo</span><span class="sxs-lookup"><span data-stu-id="edcdf-177">Sample OpenType Font Pack</span></span>](sample-opentype-font-pack.md)

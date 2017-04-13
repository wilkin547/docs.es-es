---
title: "Empaquetar fuentes con aplicaciones | Microsoft Docs"
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
  - "aplicaciones, empaquetar fuentes con"
  - "fuentes, empaquetar con aplicaciones"
  - "empaquetar fuentes con aplicaciones"
  - "tipografía, empaquetar fuentes con aplicaciones"
ms.assetid: db15ee48-4d24-49f5-8b9d-a64460865286
caps.latest.revision: 29
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# Empaquetar fuentes con aplicaciones
En este tema se proporciona información general sobre cómo empaquetar fuentes con la aplicación de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
> [!NOTE]
>  Como con la mayoría de los tipos de software, los archivos de fuentes se otorgan bajo licencias, no se venden.  Las licencias que rigen el uso de las fuentes varían según el proveedor de que se trate pero, por lo general, la mayoría de las licencias, incluidas las proporcionadas por [!INCLUDE[TLA#tla_ms#initcap](../../../../includes/tlasharptla-mssharpinitcap-md.md)] con aplicaciones y [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], no permiten incrustar las fuentes dentro de aplicaciones ni redistribuirlas de ningún otro modo.  Así pues, como programador, es su responsabilidad asegurarse de disponer de los derechos de licencia necesarios para cualquier fuente que incruste en una aplicación o redistribuya de cualquier otro modo.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="introduction_to_packaging_fonts"></a>   
## Introducción al empaquetado de fuentes  
 Resulta fácil empaquetar fuentes como recursos dentro de las aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a fin de mostrar el texto de la interfaz de usuario y otros tipos de contenido basado en texto.  Las fuentes pueden ser independientes de los archivos de ensamblado de la aplicación o estar incrustadas en ellos.  También se puede crear una biblioteca de fuentes sólo de recursos, a la que haga referencia la aplicación.  
  
 Las fuentes [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] y [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)] contienen un marcador de tipo, fsType, que indica los derechos de licencia de incrustación de esa fuente.  Sin embargo, este marcador de tipo sólo se refiere a las fuentes incrustadas almacenadas en un documento, no a las que se incrustan en una aplicación.  Puede recuperar los derechos de incrustación de una fuente creando un objeto <xref:System.Windows.Media.GlyphTypeface> y haciendo referencia a su propiedad <xref:System.Windows.Media.GlyphTypeface.EmbeddingRights%2A>.  Consulte la sección "OS\/2 and Windows Metrics" de [OpenType Specification](http://www.microsoft.com/typography/otspec/os2.htm) para obtener más información sobre el marcador fsType.  
  
 El sitio web [Microsoft Typography](http://www.microsoft.com/typography/links/) incluye información de contacto que puede ayudarle a localizar al proveedor de una fuente concreta o a encontrar uno para un trabajo personalizado.  
  
<a name="adding_fonts_as_content_items"></a>   
## Agregar fuentes como elementos de contenido  
 Puede agregar fuentes a la aplicación como elementos de contenido del proyecto que son independientes de los archivos de ensamblado de la aplicación.  Esto significa que los elementos de contenido no se incrustan como recursos dentro de un ensamblado.  En el ejemplo de archivo de proyecto siguiente se muestra cómo definir elementos de contenido.  
  
```  
<Project DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <!-- Other project build settings ... -->  
  
  <ItemGroup>  
    <Content Include="Peric.ttf" />  
    <Content Include="Pericl.ttf" />  
  </ItemGroup>  
</Project>  
```  
  
 Para asegurarse de que la aplicación pueda utilizar las fuentes en tiempo de ejecución, éstas deben estar accesibles en el directorio de implementación de la aplicación.  El elemento `<CopyToOutputDirectory>` del archivo de proyecto de la aplicación permite copiar automáticamente las fuentes en el directorio de implementación de la aplicación durante el proceso de compilación.  En el ejemplo de archivo de proyecto siguiente se muestra cómo copiar las fuentes en el directorio de implementación.  
  
```  
<ItemGroup>  
  <Content Include="Peric.ttf">  
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
  </Content>  
  <Content Include="Pericl.ttf">  
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
  </Content>  
</ItemGroup>  
```  
  
 En el ejemplo de código siguiente se muestra cómo hacer referencia a la fuente de una aplicación como un elemento de contenido; el elemento de contenido al que se hace referencia debe estar en el mismo directorio que los archivos de ensamblado de la aplicación.  
  
 [!code-xml[FontSnippets#FontPackageSnippet8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet8)]  
  
<a name="adding_fonts_as_resource_items"></a>   
## Agregar fuentes como elementos de recursos  
 Puede agregar las fuentes a la aplicación como elementos de recursos del proyecto incrustados dentro de los archivos de ensamblado de la aplicación.  Utilizar un subdirectorio independiente para los recursos ayuda a organizar los archivos de proyecto de la aplicación.  En el ejemplo del archivo de proyecto siguiente se muestra cómo definir las fuentes como elementos de recursos en un subdirectorio independiente.  
  
```  
<Project DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <!-- Other project build settings ... -->  
  
  <ItemGroup>  
    <Resource Include="resources\Peric.ttf" />  
    <Resource Include="resources\Pericl.ttf" />  
  </ItemGroup>  
</Project>  
```  
  
> [!NOTE]
>  Cuando agregue fuentes como recursos a la aplicación, asegúrese de establecer el elemento `<Resource>`, y no el elemento `<EmbeddedResource>`, en el archivo de proyecto de la aplicación.  El elemento `<EmbeddedResource>` no se admite para la acción de compilación.  
  
 En el ejemplo de marcado siguiente se muestra cómo hacer referencia a los recursos de fuentes de la aplicación.  
  
 [!code-xml[FontSnippets#FontPackageSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet1)]  
  
### Hacer referencia a elementos de recursos de fuentes desde el código  
 Para hacer referencia a los elementos de recursos de fuentes desde el código, debe proporcionar una referencia de recurso de fuente con dos componentes: el [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] base y la referencia de ubicación de fuente.  Estos valores se utilizan como parámetros para el método <xref:System.Windows.Media.FontFamily.%23ctor%2A>.  En el ejemplo de código siguiente se muestra cómo hacer referencia a los recursos de fuentes de la aplicación en el subdirectorio del proyecto denominado `resources`.  
  
 [!code-csharp[FontSnippets#FontPackageSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet2)]
 [!code-vb[FontSnippets#FontPackageSnippet2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet2)]  
  
 El [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] base puede incluir el subdirectorio de la aplicación donde reside el recurso de fuente.  En este caso, no es necesario especificar un directorio en la referencia de ubicación de fuente, pero se tendría que incluir los caracteres iniciales "`./`" para indicar que el recurso de fuente se encuentra en el mismo directorio especificado por el [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] base.  En el ejemplo de código siguiente se muestra una manera alternativa de hacer referencia al elemento de recurso de fuente, equivalente al ejemplo de código anterior.  
  
 [!code-csharp[FontSnippets#FontPackageSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet5)]
 [!code-vb[FontSnippets#FontPackageSnippet5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet5)]  
  
### Hacer referencia a fuentes desde el mismo subdirectorio de aplicación  
 Puede colocar contenido de la aplicación y archivos de recursos dentro del mismo subdirectorio definido por el usuario del proyecto de aplicación.  En el ejemplo de archivo de proyecto siguiente se muestran una página de contenido y recursos de fuente definidos en el mismo subdirectorio.  
  
```  
<ItemGroup>  
  <Page Include="pages\HomePage.xaml" />  
</ItemGroup>  
<ItemGroup>  
  <Resource Include="pages\Peric.ttf" />  
  <Resource Include="pages\Pericl.ttf" />  
</ItemGroup>  
```  
  
 Puesto que el contenido de la aplicación y la fuente se encuentran en el mismo subdirectorio, la referencia a la fuente es relativa al contenido de la aplicación.  En los ejemplos siguientes se muestra cómo hacer referencia al recurso de fuente de la aplicación cuando la fuente está en el mismo directorio que la aplicación.  
  
 [!code-xml[FontSnippets#FontPackageSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml#fontpackagesnippet3)]  
  
 [!code-csharp[FontSnippets#FontPackageSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml.cs#fontpackagesnippet4)]
 [!code-vb[FontSnippets#FontPackageSnippet4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/pages/homepage.xaml.vb#fontpackagesnippet4)]  
  
### Enumerar fuentes en una aplicación  
 Para enumerar las fuentes como elementos de recursos de su aplicación, utilice el método <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> o <xref:System.Windows.Media.Fonts.GetTypefaces%2A>.  En el ejemplo siguiente se muestra cómo utilizar el método <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> para devolver la colección de objetos <xref:System.Windows.Media.FontFamily> de la ubicación de fuentes de la aplicación.  En este caso, la aplicación contiene un subdirectorio denominado "resources".  
  
 [!code-csharp[FontSnippets#FontsSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet3)]
 [!code-vb[FontSnippets#FontsSnippet3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet3)]  
  
 En el ejemplo siguiente se muestra cómo utilizar el método <xref:System.Windows.Media.Fonts.GetTypefaces%2A> para devolver la colección de objetos <xref:System.Windows.Media.Typeface> de la ubicación de fuentes de la aplicación.  En este caso, la aplicación contiene un subdirectorio denominado "resources".  
  
 [!code-csharp[FontSnippets#FontsSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet7)]
 [!code-vb[FontSnippets#FontsSnippet7](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet7)]  
  
<a name="creating_a_font_resource_library"></a>   
## Crear una biblioteca de recursos de fuentes  
 Puede crear una biblioteca sólo de recursos que únicamente contenga fuentes, un proyecto de librería de este tipo no contiene código.  Crear una biblioteca sólo de recursos es una técnica común para desacoplar los recursos del código de la aplicación que los utiliza.  Además, permite incluir el ensamblado de biblioteca en varios proyectos de aplicación.  En el ejemplo del archivo de proyecto siguiente se muestran los fragmentos esenciales de un proyecto de biblioteca sólo de recursos.  
  
```  
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
  
### Hacer referencia a una fuente de una biblioteca de recursos  
 Para hacer referencia a una fuente de una biblioteca de recursos desde la aplicación, debe agregar a la referencia de la fuente un prefijo consistente en el nombre del ensamblado de biblioteca.  En este caso, el ensamblado de recursos de fuentes es "FontLibrary".  Para separar el nombre del ensamblado de la referencia dentro del ensamblado, se utiliza el carácter ';'.  Con la adición de la palabra clave "Component" seguida por la referencia al nombre de fuente, se completa la referencia al recurso de la biblioteca de fuentes.  En el ejemplo de código siguiente se muestra cómo hacer referencia a una fuente de un ensamblado de biblioteca de recursos.  
  
 [!code-xml[OpenTypeFontsSample#OpenTypeFontsSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontsSample/CS/Kootenay.xaml#opentypefontssample1)]  
  
> [!NOTE]
>  Este SDK contiene un conjunto de fuentes [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] de ejemplo que puede utilizar con las aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Las fuentes se definen en una biblioteca sólo de recursos.  Para obtener más información, vea [Paquete de fuentes OpenType de ejemplo](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md).  
  
<a name="limitations_on_font_usage"></a>   
## Limitaciones del uso de fuentes  
 En la lista siguiente se describen varias limitaciones para el empaquetado y el uso de fuentes en aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
-   **Bits de permiso de incrustación de fuentes:** las aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no comprueban ni aplican ningún bit de permiso de incrustación de fuentes.  Vea la sección [Introducción al empaquetado de fuentes](#introduction_to_packaging_fonts) para obtener más información.  
  
-   **Fuentes del sitio de origen:** las aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no permiten las referencias de fuente a [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] http o ftp.  
  
-   **URI absoluto con la notación "pack:":** las aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no permiten crear un objeto <xref:System.Windows.Media.FontFamily> mediante programación que utilice "pack:" como parte de la referencia absoluta de [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] a una fuente.  Por ejemplo, `"pack://application:,,,/resources/#Pericles Light"` es una referencia no válida a una fuente.  
  
-   **Incrustación automática de fuentes:** durante el tiempo de diseño, no se proporciona ninguna compatibilidad con la búsqueda de las fuentes utilizadas en una aplicación ni con la incrustación automática de éstas en los recursos de la misma.  
  
-   **Subconjuntos de fuentes:** las aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no admiten la creación de subconjuntos de fuentes para documentos no fijos.  
  
-   En los casos en que exista una referencia incorrecta, la aplicación recurre a una fuente disponible.  
  
## Vea también  
 <xref:System.Windows.Documents.Typography>   
 <xref:System.Windows.Media.FontFamily>   
 [Microsoft Typography: Links, News, and Contacts](http://www.microsoft.com/typography/links/)   
 [OpenType Specification](http://www.microsoft.com/typography/otspec/)   
 [Características de las fuentes OpenType](../../../../docs/framework/wpf/advanced/opentype-font-features.md)   
 [Paquete de fuentes OpenType de ejemplo](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md)
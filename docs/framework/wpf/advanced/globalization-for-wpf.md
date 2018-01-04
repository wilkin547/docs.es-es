---
title: "Globalización de WPF"
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology: dotnet-wpf
ms.topic: article
helpviewer_keywords:
- XAML [WPF], international user interface
- XAML [WPF], globalization
- international user interface [WPF], XAML
- globalization [WPF]
ms.assetid: 4571ccfe-8a60-4f06-9b37-7ac0b1c2d10f
caps.latest.revision: "35"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e6f39d40284e6212715d85fece545e653ff2e60a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="globalization-for-wpf"></a>Globalización de WPF
Este tema presentan problemas que debe tener en cuenta al escribir [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] aplicaciones para el mercado global. Los elementos de programación de globalización se definen en [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] en `System.Globalization`.  
  

  
<a name="xaml_globalization"></a>   
## <a name="xaml-globalization"></a>Globalización XAML  
 [!INCLUDE[TLA#tla_xaml#initcap](../../../../includes/tlasharptla-xamlsharpinitcap-md.md)]se basa en [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] y aprovecha las ventajas de la compatibilidad de globalización que se define en el [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] especificación. En las siguientes secciones se describen algunas [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] características que debe tener en cuenta.  
  
<a name="char_reference"></a>   
### <a name="character-references"></a>Referencias de caracteres  
Una referencia de carácter proporciona la unidad de código UTF16 de ese [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] carácter se representa, en formato decimal o hexadecimal. En el ejemplo siguiente se muestra una referencia de carácter decimal COPTO letra mayúscula HORI o 'Ϩ':

```
&#1000;
```

En el ejemplo siguiente se muestra una referencia de carácter hexadecimal. Tenga en cuenta que tiene un **x** delante del número hexadecimal.

```
&#x3E8;
```

<a name="encoding"></a>   
### <a name="encoding"></a>Codificación  
 La codificación compatible con [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] son [!INCLUDE[TLA#tla_ascii](../../../../includes/tlasharptla-ascii-md.md)], [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] UTF-16 y UTF-8. La declaración de codificación está al principio de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] documento. Si no existe ningún atributo de codificación y no hay ningún orden de bytes, el analizador utiliza el valor predeterminado UTF-8. UTF-8 y UTF-16 son las codificaciones preferentes. No se admite UTF-7. En el ejemplo siguiente se muestra cómo especificar una codificación UTF-8 en un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo.  
  
```  
?xml encoding="UTF-8"?  
```  
  
<a name="lang_attrib"></a>   
### <a name="language-attribute"></a>Atributo de idioma  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]usa [XML: lang](../../../../docs/framework/xaml-services/xml-lang-handling-in-xaml.md) para representar el atributo de idioma de un elemento.  Para aprovechar la <xref:System.Globalization.CultureInfo> (clase), el valor del atributo de idioma debe ser uno de los nombres de referencias culturales predefinidos por <xref:System.Globalization.CultureInfo>. [xml:lang](../../../../docs/framework/xaml-services/xml-lang-handling-in-xaml.md) es heredable en el árbol de elementos (mediante reglas XML, no necesariamente debido a la herencia de las propiedades de dependencia) y su valor predeterminado es una cadena vacía si no se asigna de manera explícita.  
  
 El atributo de idioma es muy útil para especificar dialectos. Por ejemplo, el francés tiene una ortografía, un vocabulario y una pronunciación diferentes en Francia, Quebec, Bélgica y Suiza. También el chino, japonés y coreano comparten puntos de código [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)], pero las formas ideográficas son diferentes y usan fuentes totalmente distintas.  
  
 El siguiente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] en el ejemplo se usa el `fr-CA` atributo language para especificar el francés canadiense.  
  
```xml  
<TextBlock xml:lang="fr-CA">Découvrir la France</TextBlock>  
```  
  
<a name="unicode"></a>   
### <a name="unicode"></a>Unicode  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]todos los admite [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] características como suplentes. Siempre y cuando el juego de caracteres se puede asignar a [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)], se admite. Por ejemplo, GB18030 presenta algunos caracteres que se asignan a la extensión A y B de chino, japonés y coreano (CFK) y pares suplentes, por lo tanto, es totalmente compatible. A [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación puede utilizar <xref:System.Globalization.StringInfo> para manipular las cadenas sin reconocer si tienen pares suplentes o combinación de caracteres.  
  
<a name="design_intl_ui_with_xaml"></a>   
## <a name="designing-an-international-user-interface-with-xaml"></a>Diseñar una interfaz de usuario internacional con XAML  
 Esta sección se describen [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] características que se deben considerar al escribir una aplicación.  
  
<a name="intl_text"></a>   
### <a name="international-text"></a>Texto internacional  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]incluye el procesamiento integrado para todos los [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] admite sistemas de escritura.  
  
 Actualmente se admiten los siguientes scripts:  
  
-   Árabe  
  
-   Bengalí  
  
-   Devanagari  
  
-   Cirílico  
  
-   Griego  
  
-   Gujarati  
  
-   Gurmukhi  
  
-   Hebreo  
  
-   Scripts ideográficos  
  
-   Kannada  
  
-   Lao  
  
-   Latín  
  
-   Malayalam  
  
-   Mongol  
  
-   Odia  
  
-   Siríaco  
  
-   Tamul  
  
-   Telugu  
  
-   Thaana  
  
-   Tailandés*  
  
-   Tibetano  
  
 * En esta versión, la visualización y edición de texto tailandés es compatible; no lo es la separación de palabras.  
  
 Actualmente no se admiten los siguientes scripts:  
  
-   Khmer  
  
-   Hangul coreano antiguo  
  
-   Birmano  
  
-   Cingalés  
  
 Compatibilidad con motores de todo el sistema de escritura [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] fuentes. [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]las fuentes pueden incluir el [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] tablas de diseño que permiten a los creadores de fuentes diseñar fuentes tipográficas mejor internacionales y avanzadas. El [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] tablas de diseño de fuente contienen información sobre las sustituciones de glifo, posicionamiento de glifo, justificación y posición de línea de base, permitir que las aplicaciones de procesamiento de texto mejorar el diseño de texto.  
  
 [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]fuentes permiten el control del glifo grande conjuntos de uso [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] codificación. Esta codificación permite una amplia compatibilidad internacional, así como variantes tipográficas de los glifos.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]representación de texto se realiza gracias [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)] tecnología de píxel secundaria que es compatible con independencia de la resolución. Esto mejora significativamente la legibilidad y permite la capacidad de admitir documentos de estilo de revista de gran calidad para todos los scripts.  
  
<a name="intl_layout"></a>   
### <a name="international-layout"></a>Diseño internacional  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona una manera muy cómoda de admitir diseños horizontales, bidireccionales y verticales. En el marco de presentación de la <xref:System.Windows.FrameworkElement.FlowDirection%2A> propiedad puede utilizarse para definir el diseño. Los patrones de dirección de flujo son:  
  
-   *LeftToRight*: diseño horizontal para latín, Asia Oriental y demás.  
  
-   *RightToLeft*: bidireccional para árabe, hebreo y demás.  
  
<a name="developing_localizable_apps"></a>   
## <a name="developing-localizable-applications"></a>Desarrollar aplicaciones localizables  
 Al escribir una aplicación para su consumo global, debe tener en cuenta que la aplicación debe ser localizable. En los temas siguientes se señalan las cosas que deben tenerse en cuenta.  
  
<a name="mui"></a>   
### <a name="multilingual-user-interface"></a>Interfaz de usuario multilingüe  
 Interfaces de usuario multilingüe (MUI) es un [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] admite para la modificación de [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] de un idioma a otro. Un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación utiliza el modelo de ensamblado que admite MUI. Una aplicación contiene los ensamblados neutrales respecto al idioma, así como los ensamblados de recursos satélite dependientes del idioma. El punto de entrada es un .EXE administrado en el ensamblado principal.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]cargador de recursos aprovecha las ventajas de la [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)]del Administrador de recursos para admitir la búsqueda de recursos y de respaldo. Varios ensamblados satélite de idioma funcionan con el mismo ensamblado principal. El ensamblado de recursos que se carga depende de la <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> del subproceso actual.  
  
<a name="localizable_ui"></a>   
### <a name="localizable-user-interface"></a>Interfaz de usuario localizable  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]las aplicaciones utilizan [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para definir sus [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] permite a los desarrolladores especificar una jerarquía de objetos con un conjunto de propiedades y lógica. El uso principal de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] es desarrollar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones pero puede utilizarse para especificar una jerarquía de cualquier [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] objetos. Usa la mayoría de los desarrolladores [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para especificar su aplicación [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] y utilizar un lenguaje de programación como [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] para reaccionar a la interacción del usuario.  
  
 Desde un punto de vista de recursos, un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo diseñado para describir un dependiente del idioma [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] es un elemento de recurso y, por tanto, su formato de distribución final debe ser localizable para admitir distintos idiomas internacionales. Dado que [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] no puede controlar eventos muchas [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] aplicaciones contienen bloques de código para hacerlo. Para obtener más información, consulte [información general sobre XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md). Se elimina y se compila en binarios distintos código cuando una [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo se convierte en el formulario BAML de XAML. Los archivos, imágenes y otros tipos de objetos de recursos administrados con formato BAML de XAML se insertan en el ensamblado de recursos satélite, que se puede localizar a otros idiomas, o en el ensamblado principal, cuando no se requiere la localización.  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]las aplicaciones admiten todas las [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)] [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] recursos incluye las tablas de cadenas, imágenes y así sucesivamente.  
  
<a name="building_localizable_apps"></a>   
### <a name="building-localizable-applications"></a>Compilar aplicaciones localizables  
 Localización significa adaptar un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] a distintas referencias culturales. Para realizar un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] localizable, los desarrolladores necesitan compilar todos los recursos localizables en un ensamblado de recursos de la aplicación. El ensamblado de recursos se localiza a idiomas diferentes y el código subyacente utiliza la administración de recursos [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] para cargar. Uno de los archivos necesarios para un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación es un archivo de proyecto (proj). Todos los recursos que se usan en la aplicación deben incluirse en el archivo de proyecto. En el ejemplo siguiente de un archivo .csproj se muestra cómo hacerlo.  
  
```xml  
<Resource Include="data\picture1.jpg"/>  
<EmbeddedResource Include="data\stringtable.en-US.restext"/>  
```  
  
 Para usar un recurso en la aplicación crear una instancia de un <xref:System.Resources.ResourceManager> y cargue el recurso que desea utilizar. En el ejemplo siguiente se muestra cómo hacerlo:  
  
 [!code-csharp[LocalizationResources#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]  
  
<a name="using_clickonce"></a>   
## <a name="using-clickonce-with-localized-applications"></a>Utilizar ClickOnce con aplicaciones localizadas  
 ClickOnce es una nueva tecnología de implementación de Windows Forms que se incluirá con [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)]. Permite la instalación y actualización de aplicaciones web. Cuando se localiza una aplicación que se implementó con ClickOnce, solo puede verse en la referencia cultural localizada. Por ejemplo, si una aplicación implementada se localiza a japonés sólo puede verse en japonés [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] no en inglés [!INCLUDE[TLA2#tla_win](../../../../includes/tla2sharptla-win-md.md)]. Esto presenta un problema porque es un escenario común para los usuarios japoneses ejecutar una versión en inglés de [!INCLUDE[TLA2#tla_win](../../../../includes/tla2sharptla-win-md.md)].  
  
 La solución a este problema es establecer el atributo neutro de reserva de idioma. Como alternativa, un desarrollador de aplicaciones puede quitar recursos del ensamblado principal y especificar que los recursos puedan encontrarse en un ensamblado satélite correspondiente a una referencia cultural específica. Para controlar este proceso, utilice el <xref:System.Resources.NeutralResourcesLanguageAttribute>. El constructor de la <xref:System.Resources.NeutralResourcesLanguageAttribute> clase tiene dos firmas, una que tome un <xref:System.Resources.UltimateResourceFallbackLocation> parámetro para especificar la ubicación donde el <xref:System.Resources.ResourceManager> debe extraer la reserva de recursos: ensamblado principal o un ensamblado satélite. En el ejemplo siguiente se muestra cómo utilizar el atributo. Para la ubicación de reserva ultimate, el código provoca el <xref:System.Resources.ResourceManager> para buscar los recursos en el subdirectorio "de" del directorio del ensamblado en ejecución actualmente.  
  
```  
[assembly: NeutralResourcesLanguageAttribute(  
    "de" , UltimateResourceFallbackLocation.Satellite)]  
```  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre la globalización y la localización de WPF](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)

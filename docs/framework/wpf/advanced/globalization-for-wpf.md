---
title: Globalización de WPF
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], international user interface
- XAML [WPF], globalization
- international user interface [WPF], XAML
- globalization [WPF]
ms.assetid: 4571ccfe-8a60-4f06-9b37-7ac0b1c2d10f
ms.openlocfilehash: 1ab372f69792a00160edb2542762298114d3f8b4
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003442"
---
# <a name="globalization-for-wpf"></a>Globalización de WPF
En este tema se presentan los problemas que debe tener en cuenta al escribir [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] aplicaciones para el mercado mundial. Los elementos de programación de globalización se definen en .NET en el espacio de nombres <xref:System.Globalization>.

<a name="xaml_globalization"></a>
## <a name="xaml-globalization"></a>Globalización XAML
 Lenguaje XAML (XAML) se basa en [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] y aprovecha la compatibilidad de globalización definida en la especificación [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]. En las secciones siguientes se describen algunas características de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que debe tener en cuenta.

<a name="char_reference"></a>
### <a name="character-references"></a>Referencias de caracteres
Una referencia de carácter proporciona la unidad de código UTF16 del carácter [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] determinado que representa, en formato decimal o hexadecimal. En el ejemplo siguiente se muestra una referencia de carácter decimal para la letra mayúscula CÓPTICA HORI o ' Ϩ ':

```
&#1000;
```

En el ejemplo siguiente se muestra una referencia de carácter hexadecimal. Observe que tiene una **x** delante del número hexadecimal.

```
&#x3E8;
```

<a name="encoding"></a>
### <a name="encoding"></a>Codificación
 La codificación compatible con [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] son ASCII, [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] UTF-16 y UTF-8. La instrucción de codificación está al principio del documento [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Si no existe ningún atributo de codificación y no hay ningún orden de bytes, el analizador utiliza el valor predeterminado UTF-8. UTF-8 y UTF-16 son las codificaciones preferentes. No se admite UTF-7. En el ejemplo siguiente se muestra cómo especificar una codificación UTF-8 en un archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].

```xaml
?xml encoding="UTF-8"?
```

<a name="lang_attrib"></a>
### <a name="language-attribute"></a>Atributo de idioma
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usa [xml: lang](../../xaml-services/xml-lang-handling-in-xaml.md) para representar el atributo de idioma de un elemento.  Para aprovechar las ventajas de la clase <xref:System.Globalization.CultureInfo>, el valor del atributo Language debe ser uno de los nombres de referencia cultural predefinidos por <xref:System.Globalization.CultureInfo>. [xml:lang](../../xaml-services/xml-lang-handling-in-xaml.md) es heredable en el árbol de elementos (mediante reglas XML, no necesariamente debido a la herencia de las propiedades de dependencia) y su valor predeterminado es una cadena vacía si no se asigna de manera explícita.

 El atributo de idioma es muy útil para especificar dialectos. Por ejemplo, el francés tiene una ortografía, un vocabulario y una pronunciación diferentes en Francia, Quebec, Bélgica y Suiza. Además, el chino, el japonés y el coreano comparten puntos de código en [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)], pero las formas ideográficas son diferentes y usan fuentes totalmente diferentes.

 En el siguiente ejemplo de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] se usa el atributo de lenguaje `fr-CA` para especificar francés canadiense.

```xaml
<TextBlock xml:lang="fr-CA">Découvrir la France</TextBlock>
```

<a name="unicode"></a>
### <a name="unicode"></a>Unicode
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] es compatible con todas las características de [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)], incluidos los suplentes. Siempre que el juego de caracteres se pueda asignar a [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)], se admite. Por ejemplo, GB18030 presenta algunos caracteres que se asignan a la extensión A y B de chino, japonés y coreano (CFK) y pares suplentes, por lo tanto, es totalmente compatible. Una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] puede utilizar <xref:System.Globalization.StringInfo> para manipular cadenas sin comprender si tienen pares suplentes o caracteres combinables.

<a name="design_intl_ui_with_xaml"></a>
## <a name="designing-an-international-user-interface-with-xaml"></a>Diseñar una interfaz de usuario internacional con XAML
 En esta sección se describen las características de @no__t 0 que se deben tener en cuenta al escribir una aplicación.

<a name="intl_text"></a>
### <a name="international-text"></a>Texto internacional
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incluye el procesamiento integrado para todos los sistemas de escritura compatibles con Microsoft .NET Framework.

 Actualmente se admiten los siguientes scripts:

- Árabe

- Bengalí

- Devanagari

- Cirílico

- Griego

- Gujarati

- Gurmukhi

- Hebreo

- Scripts ideográficos

- Canarés

- Lao

- Latín

- Malayalam

- Mongol

- Odia

- Siríaco

- Tamul

- Telugu

- Thaana

- Tailandés*

- Tibetano

 \* En esta versión, la visualización y edición de texto tailandés es compatible; no lo es la separación de palabras.

 Actualmente no se admiten los siguientes scripts:

- Jemer

- Hangul coreano antiguo

- Birmano

- Cingalés

 Todos los motores del sistema de escritura admiten fuentes OpenType. Las fuentes OpenType pueden incluir las tablas de diseño OpenType que permiten a los creadores de fuentes diseñar mejores fuentes tipográficas internacionales y de gama alta. Las tablas de diseño de fuentes OpenType contienen información sobre las sustituciones de glifos, la posición del glifo, la justificación y la posición de línea base, lo que permite a las aplicaciones de procesamiento de texto mejorar el diseño del texto.

 Las fuentes OpenType permiten el control de grandes conjuntos de glifos mediante la codificación [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)]. Esta codificación permite una amplia compatibilidad internacional, así como variantes tipográficas de los glifos.

 la representación de texto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se basa en la tecnología de subpíxeles de ClearType de Microsoft, que admite la independencia de la resolución. Esto mejora significativamente la legibilidad y permite la capacidad de admitir documentos de estilo de revista de gran calidad para todos los scripts.

<a name="intl_layout"></a>
### <a name="international-layout"></a>Diseño internacional
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona una manera muy cómoda de admitir diseños horizontales, bidireccionales y verticales. En el marco de presentación, se puede usar la propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A> para definir el diseño. Los patrones de dirección de flujo son:

- *LeftToRight*: diseño horizontal para latín, Asia Oriental y demás.

- *RightToLeft*: bidireccional para árabe, hebreo y demás.

<a name="developing_localizable_apps"></a>
## <a name="developing-localizable-applications"></a>Desarrollar aplicaciones localizables
 Al escribir una aplicación para su consumo global, debe tener en cuenta que la aplicación debe ser localizable. En los temas siguientes se señalan las cosas que deben tenerse en cuenta.

<a name="mui"></a>
### <a name="multilingual-user-interface"></a>Interfaz de usuario multilingüe
 La interfaz de usuario multilingüe (MUI) es un servicio de soporte técnico de Microsoft para cambiar [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] de un idioma a otro. Una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utiliza el modelo de ensamblado para admitir MUI. Una aplicación contiene los ensamblados neutrales respecto al idioma, así como los ensamblados de recursos satélite dependientes del idioma. El punto de entrada es un .EXE administrado en el ensamblado principal.  el cargador de recursos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aprovecha el administrador de recursos de [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)] para admitir la búsqueda de recursos y la reserva. Varios ensamblados satélite de idioma funcionan con el mismo ensamblado principal. El ensamblado de recursos que se carga depende de la <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> del subproceso actual.

<a name="localizable_ui"></a>
### <a name="localizable-user-interface"></a>Interfaz de usuario localizable
 las aplicaciones [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usan [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para definir su @no__t 2. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] permite a los desarrolladores especificar una jerarquía de objetos con un conjunto de propiedades y lógica. El uso principal de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] es desarrollar aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], pero se puede usar para especificar una jerarquía de cualquier objeto de Common Language Runtime (CLR). La mayoría de los desarrolladores usan [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para especificar el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de su aplicación y usar un C# lenguaje de programación como para reaccionar a la interacción del usuario.

 Desde el punto de vista de los recursos, un archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] diseñado para describir un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] dependiente del idioma es un elemento de recurso y, por tanto, su formato de distribución final debe ser localizable para admitir idiomas internacionales. Dado que [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] no puede controlar eventos, muchas aplicaciones de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] contienen bloques de código para hacerlo. Para obtener más información, vea [información general sobre XAML (WPF)](xaml-overview-wpf.md). El código se quita y se compila en archivos binarios diferentes cuando un archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se acorta en el formato BAML de XAML. Los archivos, imágenes y otros tipos de objetos de recursos administrados con formato BAML de XAML se insertan en el ensamblado de recursos satélite, que se puede localizar a otros idiomas, o en el ensamblado principal, cuando no se requiere la localización.

> [!NOTE]
> las aplicaciones [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] admiten todos los recursos [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)]CLR, como tablas de cadenas, imágenes, etc.

<a name="building_localizable_apps"></a>
### <a name="building-localizable-applications"></a>Compilar aplicaciones localizables
 La localización significa adaptar un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] a diferentes referencias culturales. Para convertir una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en localizable, los desarrolladores deben compilar todos los recursos localizables en un ensamblado de recursos. El ensamblado de recursos se localiza en idiomas diferentes y el código subyacente usa la API de administración de recursos para cargar. Uno de los archivos necesarios para una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es un archivo de proyecto (. proj). Todos los recursos que se usan en la aplicación deben incluirse en el archivo de proyecto. En el ejemplo siguiente de un archivo .csproj se muestra cómo hacerlo.

```xml
<Resource Include="data\picture1.jpg"/>
<EmbeddedResource Include="data\stringtable.en-US.restext"/>
```

 Para usar un recurso en la aplicación, cree una instancia de <xref:System.Resources.ResourceManager> y cargue el recurso que desea usar. En el ejemplo siguiente se muestra cómo hacerlo:

 [!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]

<a name="using_clickonce"></a>
## <a name="using-clickonce-with-localized-applications"></a>Utilizar ClickOnce con aplicaciones localizadas
 ClickOnce es una nueva tecnología de implementación de Windows Forms que se incluirá con Visual Studio 2005. Permite la instalación y actualización de aplicaciones web. Cuando se localiza una aplicación que se implementó con ClickOnce, solo puede verse en la referencia cultural localizada. Por ejemplo, si una aplicación implementada se localiza en japonés, solo se puede ver en japonés @no__t no en las ventanas inglesas. Esto supone un problema porque se trata de un escenario común para que los usuarios japoneses ejecuten una versión en Inglés de Windows.

 La solución a este problema es establecer el atributo neutro de reserva de idioma. Como alternativa, un desarrollador de aplicaciones puede quitar recursos del ensamblado principal y especificar que los recursos puedan encontrarse en un ensamblado satélite correspondiente a una referencia cultural específica. Para controlar este proceso, use el <xref:System.Resources.NeutralResourcesLanguageAttribute>. El constructor de la clase <xref:System.Resources.NeutralResourcesLanguageAttribute> tiene dos firmas, una que toma un parámetro <xref:System.Resources.UltimateResourceFallbackLocation> para especificar la ubicación donde <xref:System.Resources.ResourceManager> debe extraer los recursos de reserva: ensamblado principal o ensamblado satélite. En el ejemplo siguiente se muestra cómo utilizar el atributo. En el caso de la ubicación de reserva definitiva, el código hace que el <xref:System.Resources.ResourceManager> busque los recursos en el subdirectorio "de" del directorio del ensamblado que se está ejecutando actualmente.

```csharp
[assembly: NeutralResourcesLanguageAttribute(
    "de" , UltimateResourceFallbackLocation.Satellite)]
```

## <a name="see-also"></a>Vea también

- [Información general sobre la globalización y la localización de WPF](wpf-globalization-and-localization-overview.md)

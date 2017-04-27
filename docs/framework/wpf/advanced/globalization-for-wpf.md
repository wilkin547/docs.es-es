---
title: "Globalizaci&#243;n de WPF | Microsoft Docs"
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
  - "globalización"
  - "interfaz de usuario internacional, XAML"
  - "XAML, globalización"
  - "XAML, interfaz de usuario internacional"
ms.assetid: 4571ccfe-8a60-4f06-9b37-7ac0b1c2d10f
caps.latest.revision: 35
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 31
---
# Globalizaci&#243;n de WPF
En este tema se presentan las cuestiones que debe tener en cuenta al escribir aplicaciones [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] para el mercado global.  En [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)], los elementos de programación de globalización se definen en `System.Globalization`.  
  
   
  
<a name="xaml_globalization"></a>   
## Globalización XAML  
 [!INCLUDE[TLA#tla_xaml#initcap](../../../../includes/tlasharptla-xamlsharpinitcap-md.md)] se basa en [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] y se beneficia de la compatibilidad con la globalización definida en la especificación [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].  En las secciones siguientes se describen algunas características de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que debe tener en cuenta.  
  
<a name="char_reference"></a>   
### Referencias de caracteres  
 Una referencia de carácter proporciona el número del carácter [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] concreto que representa, en formato decimal o hexadecimal.  En el ejemplo siguiente se muestra una referencia de carácter en formato decimal.  
  
```  
Ϩ  
```  
  
 En este ejemplo se muestra una referencia de carácter en formato hexadecimal.  Observe que tiene una **x** delante del número hexadecimal.  
  
```  
Ϩ  
```  
  
<a name="encoding"></a>   
### Codificación  
 Las codificaciones compatibles con [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] son [!INCLUDE[TLA#tla_ascii](../../../../includes/tlasharptla-ascii-md.md)], [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] UTF\-16 y UTF\-8.  La instrucción de codificación se encuentra al principio del documento [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Si no existe ningún atributo de codificación y no se especifica ningún orden de bytes, el analizador utiliza el valor predeterminado UTF\-8.  UTF\-8 y UTF\-16 son las codificaciones preferentes.  UTF\-7 no se admite.  En el ejemplo siguiente se muestra cómo especificar una codificación UTF\-8 en un archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
```  
?xml encoding="UTF-8"?  
```  
  
<a name="lang_attrib"></a>   
### Atributo Language  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] utiliza [xml:lang](../../../../docs/framework/xaml-services/xml-lang-handling-in-xaml.md) para representar el atributo de idioma de un elemento.  Para sacar partido de la clase <xref:System.Globalization.CultureInfo>, el valor del atributo de idioma debe ser uno de los nombres de referencias culturales predefinidos por <xref:System.Globalization.CultureInfo>.  [xml:lang](../../../../docs/framework/xaml-services/xml-lang-handling-in-xaml.md) se puede heredar en el árbol de elementos \(según las reglas XML, no necesariamente debido a la herencia de propiedades de dependencia\) y su valor predeterminado es una cadena vacía si no se asigna de manera explícita.  
  
 El atributo de idioma es muy útil para especificar dialectos.  Por ejemplo, el francés tiene una ortografía, un vocabulario y una pronunciación diferentes en Francia, Quebec, Bélgica y Suiza.  También el chino, el japonés y el coreano comparten puntos de código en [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)], pero las formas ideográficas son diferentes y utilizan fuentes totalmente distintas.  
  
 En el ejemplo de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] siguiente se utiliza el atributo de idioma `fr-CA` para especificar el francés canadiense.  
  
```  
<TextBlock xml:lang="fr-CA">Découvrir la France</TextBlock>  
```  
  
<a name="unicode"></a>   
### Unicode  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] admite todas las características de [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)], incluso los suplentes.  Siempre y cuando el juego de caracteres se pueda asignar a [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)], se admite.  Por ejemplo, GB18030 introduce algunos caracteres que se asignan a la extensión A y B del chino, japonés y coreano \(CFK\) y pares suplentes, de manera que es totalmente compatible.  Una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] puede utilizar <xref:System.Globalization.StringInfo> para manipular las cadenas sin reconocer si tienen pares suplentes o caracteres combinables.  
  
<a name="design_intl_ui_with_xaml"></a>   
## Diseñar una interfaz de usuario internacional con XAML  
 En esta sección se describen características de [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] que debe tener en cuenta al escribir una aplicación.  
  
<a name="intl_text"></a>   
### Texto internacional  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incluye el procesamiento integrado para todos los sistemas de escritura de  [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] admitidos.  
  
 En la actualidad, se admiten los sistemas de escritura siguientes:  
  
-   Árabe  
  
-   Bengalí  
  
-   Devanagari  
  
-   Cirílico  
  
-   Griego  
  
-   Gujarati  
  
-   Gurmukhi  
  
-   Hebreo  
  
-   Sistemas de escritura ideográficos  
  
-   Kannada  
  
-   Lao  
  
-   Latino  
  
-   Malayalam  
  
-   Mongol  
  
-   Odia  
  
-   Sirio  
  
-   Tamil  
  
-   Telugu  
  
-   Thaana  
  
-   Tailandés\*  
  
-   Tibetano  
  
 \*En esta versión se admite la presentación y edición de texto tailandés, pero no la separación de palabras.  
  
 En la actualidad, no se admiten los sistemas de escritura siguientes:  
  
-   Khmer  
  
-   Hangul coreano antiguo  
  
-   Birmano  
  
-   Cingalés  
  
 Todos los motores de sistema de escritura admiten las fuentes [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)].  Las fuentes [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] pueden incluir las tablas de diseño [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] que permiten a los creadores de fuentes diseñar mejores fuentes tipográficas internacionales y avanzadas.  Las tablas de diseño de fuentes [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] contienen información sobre sustituciones de glifos, colocación de glifos, justificación y la posición de línea base, lo que permite mejorar el diseño del texto en las aplicaciones de procesamiento de textos.  
  
 Las fuentes [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] permiten controlar juegos de glifos grandes mediante la codificación [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)].  Esta codificación permite una amplia compatibilidad internacional, además de variaciones tipográficas de los glifos.  
  
 La representación de texto en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es posible gracias a la tecnología de subpíxel de [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)], que admite la independencia de la resolución.  Con ello se mejora significativamente la legibilidad y se proporciona compatibilidad con documentos en un estilo de revista de gran calidad para todos los sistemas de escritura.  
  
<a name="intl_layout"></a>   
### Diseño internacional  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona una manera muy cómoda de admitir los diseños horizontales, bidireccionales y verticales.  En el marco de trabajo de presentación, se puede utilizar la propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A> para definir el diseño.  Los modelos de dirección de flujo son:  
  
-   *LeftToRight*: diseño horizontal para fuentes latinas, de Asia oriental, etc.  
  
-   *RightToLeft*: diseño bidireccional para fuentes árabes, hebreas, etc.  
  
<a name="developing_localizable_apps"></a>   
## Desarrollar aplicaciones localizables  
 Cuando se escribe una aplicación para su consumo en todo el mundo, debe tener presente que la aplicación debe poder localizarse.  En los temas siguientes se señalan aspectos que debe tener en cuenta.  
  
<a name="mui"></a>   
### Interfaz de usuario multilingüe  
 Las interfaces de usuario multilingües \(MUI\) son una característica de compatibilidad de [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] para pasar de un idioma a otro en las [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)].  Una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utiliza el modelo de ensamblado que admite las MUI.  Una aplicación contiene los ensamblados neutrales con respecto al idioma, así como los ensamblados de recursos satélite dependientes del idioma.  El punto de entrada es un .EXE administrado en el ensamblado principal.  El cargador de recursos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aprovecha el administrador de recursos de [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)] para admitir la búsqueda y reserva de recursos.  Los ensamblados satélite de varios idiomas funcionan con el mismo ensamblado principal.  El ensamblado de recursos que se carga depende de la propiedad <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> del subproceso actual.  
  
<a name="localizable_ui"></a>   
### Interfaz de usuario localizable  
 Las aplicaciones [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usan [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para definir su [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] permite a los desarrolladores especificar una jerarquía de objetos con un conjunto de propiedades y lógica.  El uso primario de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] es programar aplicaciones [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], pero se puede utilizar para especificar una jerarquía de cualesquiera objetos [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)].  La mayoría de los programadores utilizan [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para especificar la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de su aplicación y utilizan un lenguaje de programación como [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] para reaccionar a las interacciones con el usuario.  
  
 Desde un punto de vista de los recursos, un archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] diseñado para describir una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] dependiente del idioma es un elemento de recurso y, por consiguiente, su formato de distribución definitivo deberá poder localizarse para admitir distintos idiomas internacionales.  Dado que [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] no puede controlar eventos, muchas aplicaciones [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] contienen bloques de código para ello.  Para obtener más información, vea [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  El código se secciona y compila en distintos binarios cuando un archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se convierte al formato BAML de XAML con tokens. Los archivos, imágenes y otros tipos de objetos de recursos administrados con formato BAML de XAML se incrustan en el ensamblado de recursos satélite, que se puede localizar a otros idiomas, o en el ensamblado principal si no se necesita localización.  
  
> [!NOTE]
>  Las aplicaciones [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] admiten todos los recursos [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)], incluidas las tablas de cadenas, imágenes, etc.  
  
<a name="building_localizable_apps"></a>   
### Compilar aplicaciones localizables  
 La localización significa adaptar una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] a otras referencias culturales.  Para que una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sea localizable, los programadores deben integrar todos los recursos localizables en un ensamblado de recursos.  El ensamblado de recursos se localiza a distintos idiomas y el código subyacente utiliza la [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] de administración de recursos para cargarse.  Uno de los archivos requeridos para una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es un archivo de proyecto \(.proj\).  Todos los recursos que se utilizan en una aplicación deben incluirse en el archivo de proyecto.  En el ejemplo siguiente de un archivo .csproj se muestra cómo hacerlo.  
  
```  
<Resource Include="data\picture1.jpg"/>  
<EmbeddedResource Include="data\stringtable.en-US.restext"/>  
```  
  
 Para utilizar un recurso en la aplicación, cree una instancia de <xref:System.Resources.ResourceManager> y cargue el recurso que desea utilizar.  En el ejemplo siguiente se muestra cómo hacerlo:  
  
 [!code-csharp[LocalizationResources#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]  
  
<a name="using_clickonce"></a>   
## Utilizar ClickOnce con aplicaciones localizadas  
 ClickOnce es una nueva tecnología de implementación de formularios Windows Forms que se distribuirá con [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)].  Permite la instalación de aplicaciones y la actualización de aplicaciones web.  Cuando se localiza una aplicación que se implementó con ClickOnce, únicamente se podrá ver en la referencia cultural en la que se haya localizado.  Por ejemplo, si una aplicación implementada se localiza a japonés, únicamente se podrá ver en la versión japonesa de [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)], y no en la versión inglesa de [!INCLUDE[TLA2#tla_win](../../../../includes/tla2sharptla-win-md.md)].  Esto presenta un problema porque es frecuente que los usuarios japoneses ejecuten una versión inglesa de [!INCLUDE[TLA2#tla_win](../../../../includes/tla2sharptla-win-md.md)].  
  
 La solución a este problema reside en establecer el atributo de recursos de reserva neutrales con respecto al idioma.  Un programador de aplicaciones puede quitar recursos del ensamblado principal, si lo desea, y especificar que los recursos se encuentran en un ensamblado satélite que corresponde a una referencia cultural concreta.  Para controlar este proceso, se utiliza la clase <xref:System.Resources.NeutralResourcesLanguageAttribute>.  El constructor de la clase <xref:System.Resources.NeutralResourcesLanguageAttribute> tiene dos firmas, una de ellas acepta un parámetro <xref:System.Resources.UltimateResourceFallbackLocation> para especificar la ubicación de la que <xref:System.Resources.ResourceManager> debería extraer los recursos de reserva: el ensamblado principal o el ensamblado satélite.  En el ejemplo siguiente se muestra cómo utilizar el atributo.  En el caso de la ubicación de los recursos de reserva definitivos, el código hace que <xref:System.Resources.ResourceManager> busque los recursos en el subdirectorio "de" del directorio del ensamblado que se está ejecutando actualmente.  
  
```  
[assembly: NeutralResourcesLanguageAttribute(  
    "de" , UltimateResourceFallbackLocation.Satellite)]  
  
```  
  
## Vea también  
 [Información general sobre la localización y globalización de WPF](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)
---
title: "Caracter&#237;sticas de las fuentes OpenType | Microsoft Docs"
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
  - "fuentes OpenType"
  - "tipografía, tecnología de fuentes OpenType"
  - "tecnología de fuentes OpenType"
ms.assetid: 4061a9d1-fe8b-4921-9e17-18ec7d2e3ea2
caps.latest.revision: 38
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 37
---
# Caracter&#237;sticas de las fuentes OpenType
Este tema proporciona información general de algunas de las características clave de [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] tecnología de fuentes en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
   
  
<a name="overview"></a>   
## <a name="opentype-font-format"></a>Formato de fuente OpenType  
 El [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] el formato de fuente es una extensión de la [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)] formato de fuente, agregar compatibilidad para datos de fuentes PostScript. El [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] el formato de fuente fue desarrollado conjuntamente por [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] y Adobe Corporation. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]las fuentes y el sistema operativo de servicios que la compatibilidad con [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] fuentes proporcionan a los usuarios una manera sencilla de instalar y utilizar fuentes, si contienen las fuentes [!INCLUDE[TLA2#tla_truetype](../../../../includes/tla2sharptla-truetype-md.md)] esquemas o contornos CFF (PostScript).  
  
 El [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] el formato de fuente soluciona los desafíos de desarrollo siguientes:  
  
-   Mayor compatibilidad multiplataforma.  
  
-   Mejor compatibilidad con juegos de caracteres internacionales.  
  
-   Mejor protección para los datos de fuente.  
  
-   Archivos más pequeños para hacer más eficaz la distribución de la fuente.  
  
-   Mayor compatibilidad para el control tipográfico avanzado.  
  
> [!NOTE]
>  El SDK de Windows contiene un conjunto de muestra [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] fuentes que puede utilizar con [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] aplicaciones. Estas fuentes ofrecen la mayoría de las características ilustradas en el resto de este tema. Para obtener más información, consulte [paquete de fuentes OpenType de ejemplo](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md).  
  
 Consulte la [especificación OpenType](http://go.microsoft.com/fwlink/?LinkId=96731) para obtener detalles de la [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] el formato de fuente.  
  
### <a name="advanced-typographic-extensions"></a>Extensiones tipográficas avanzadas  
 Las tablas tipográficas avanzadas ([!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] tablas de diseño) amplían la funcionalidad de fuentes con cualquiera [!INCLUDE[TLA2#tla_truetype](../../../../includes/tla2sharptla-truetype-md.md)] o CFF contornos. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]Fuentes de distribución contienen información adicional que amplía las capacidades de las fuentes para admitir tipografía internacional de alta calidad. La mayoría [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] fuentes exponen solo un subconjunto del total [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] características disponibles. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]las fuentes proporcionan las siguientes características.  
  
-   Asignación enriquecida entre caracteres y glifos que admiten ligaduras, formas posicionales, alternativas y otras sustituciones de fuentes.  
  
-   Compatibilidad con datos adjuntos de glifo y posicionamiento bidimensional.  
  
-   Información explícita de alfabeto e idioma contenida en fuente, por lo que una aplicación de procesamiento de textos puedan ajustar su comportamiento en consecuencia.  
  
 El [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] tablas de diseño se describen con más detalle en la ["Tablas de archivos de fuentes"](http://www.microsoft.com/typography/otspec/otff.htm) sección de la [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] especificación.  
  
 El resto de esta introducción presenta la amplitud y la flexibilidad de algunas visualmente interesante [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] características que se exponen mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto. Para obtener más información sobre este objeto, vea [clase Typography](#typography_class).  
  
<a name="variants"></a>   
## <a name="variants"></a>Variantes  
 Las variantes se utilizan para representar diferentes estilos tipográficos, tales como superíndices y subíndices.  
  
### <a name="superscripts-and-subscripts"></a>Superíndices y subíndices  
 El <xref:System.Windows.Documents.Typography.Variants%2A> propiedad le permite establecer los valores superíndice y el subíndice de un [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] fuente.  
  
 El texto siguiente muestra superíndices para la fuente Palatino Linotype.  
  
 ![Texto que usa superíndices OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont14.png "opentypefont14")  
Texto que usa superíndices OpenType  
  
 En el ejemplo de marcado siguiente se muestra cómo se definen superíndices para la fuente Palatino Linotype, mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xml[OpenTypeFontSamples#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#12)]  
  
 El texto siguiente muestran subíndices para la fuente Palatino Linotype.  
  
 ![Texto que usa subíndices OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont15.png "opentypefont15")  
Texto que usa subíndices OpenType  
  
 En el ejemplo de marcado siguiente se muestra cómo se definen los subíndices para la fuente Palatino Linotype, mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xml[OpenTypeFontSamples#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#13)]  
  
### <a name="decorative-uses-of-superscripts-and-subscripts"></a>Usos decorativos de superíndices y subíndices  
 También puede utilizar superíndices y subíndices para crear efectos decorativos con texto mixto de mayúsculas. El texto siguiente muestra el texto de superíndice y el subíndice de la fuente Palatino Linotype. Tenga en cuenta que las mayúsculas no se ven afectadas.  
  
 ![Texto que usa superíndices y subíndices OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont16.png "opentypefont16")  
Texto que usa superíndices y subíndices OpenType  
  
 En el ejemplo de marcado siguiente se muestra cómo se definen superíndices y subíndices para una fuente, mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xml[OpenTypeFontSamples#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#14)]  
  
<a name="capitals"></a>   
## <a name="capitals"></a>Mayúsculas  
 Las mayúsculas son un conjunto de formatos tipográficos que representan el texto en glifos con estilo de mayúscula. Normalmente, cuando se representa el texto en mayúsculas, el espaciado entre las letras puede parecer demasiado apretado y el peso y la proporción de las letras, demasiado fuerte. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]admite varios formatos de estilo para las mayúsculas, incluido versales, mayúsculas pequeñas, títulos y espaciado de mayúsculas. Estos formatos le permiten controlar el aspecto de las mayúsculas.  
  
 El texto siguiente muestra las letras mayúsculas estándar para la fuente Pescadero, seguidas de letras con estilo "SmallCaps" y "AllSmallCaps". En este caso, se utiliza el mismo tamaño de fuente para las tres palabras.  
  
 ![Texto que usa mayúsculas OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont11.png "opentypefont11")  
Texto que usa mayúsculas OpenType  
  
 En el ejemplo de marcado siguiente se muestra cómo se definen las mayúsculas para la fuente Pescadero, mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto. Cuando se utiliza el formato "SmallCaps", se omite cualquier letra mayúscula inicial.  
  
 [!code-xml[OpenTypeFontSamples#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
### <a name="titling-capitals"></a>Mayúsculas titling  
 Mayúsculas de títulos son más claro en el peso y proporción y diseñado para dar un aspecto más elegante de mayúsculas normales. Mayúsculas de títulos se utilizan normalmente en tamaños de fuente mayores como encabezados. El texto siguiente muestra mayúsculas normales y de títulos para la fuente Pescadero. Tenga en cuenta el ancho de las astas más estrecho del texto en la segunda línea.  
  
 ![Texto que usa mayúsculas titling OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont20.png "OpenTypeFont20")  
Texto que usa mayúsculas titling OpenType  
  
 En el ejemplo de marcado siguiente se muestra cómo se definen las mayúsculas de títulos para la fuente Pescadero, mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xml[OpenTypeFontSamples#OpenTypeFontSnippet17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet17)]  
  
### <a name="capital-spacing"></a>Espaciado de mayúsculas  
 Espaciado de mayúsculas es una característica que le permite proporcionar más espaciado de mayúsculas en texto. Letras mayúsculas están diseñadas para combinarse con letras minúsculas. Espaciado que parece correcto entre y una letra mayúscula y una minúscula pueden parecer demasiado apretados cuando se utilizan todas las letras mayúsculas. El texto siguiente muestra el espaciado normal y de mayúsculas para la fuente Pescadero.  
  
 ![Texto que usa espaciado de mayúsculas OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont21.png "OpenTypeFont21")  
Texto que usa espaciado de mayúsculas OpenType  
  
 En el ejemplo de marcado siguiente se muestra cómo definir el espaciado de mayúsculas para la fuente Pescadero, mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xml[OpenTypeFontSamples#OpenTypeFontSnippet18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet18)]  
  
<a name="ligatures"></a>   
## <a name="ligatures"></a>Ligaduras  
 Ligaduras son dos o más glifos que se crean en un solo glifo para crear texto más legible o atractivo. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]las fuentes admiten cuatro tipos de ligaduras:  
  
-   **Ligaduras estándar**. Diseñado para mejorar la legibilidad. Ligaduras estándar incluyen "fi", "fl" y "ff".  
  
-   **Ligaduras contextuales**. Diseñado para mejorar la legibilidad al proporcionar el comportamiento de la mejor unión entre los caracteres que constituyen la ligadura.  
  
-   **Ligaduras discrecionales**. Diseñado para ser ornamentales y no están diseñadas para mejorar la legibilidad.  
  
-   **Ligaduras históricas**. Diseñado para ser históricas y no están diseñadas para mejorar la legibilidad.  
  
 El texto siguiente muestra los glifos de Ligadura estándar para la fuente Pericles.  
  
 ![Texto que usa ligaduras estándar OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont04.png "opentypefont04")  
Texto que usa ligaduras estándar OpenType  
  
 En el ejemplo de marcado siguiente se muestra cómo se definen los glifos de Ligadura estándar para la fuente Pericles, mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xml[OpenTypeFontSamples#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#4)]  
  
 El texto siguiente muestra los glifos de ligadura discrecional para la fuente Pericles.  
  
 ![Texto que usa ligaduras discrecionales OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont05.png "opentypefont05")  
Texto que usa ligaduras discrecionales OpenType  
  
 En el ejemplo de marcado siguiente se muestra cómo se definen los glifos de ligadura discrecional para la fuente Pericles, mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xml[OpenTypeFontSamples#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#5)]  
  
 De forma predeterminada, [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] fuentes en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] habilitan las ligaduras estándar. Por ejemplo, si utiliza la fuente Palatino Linotype, las ligaduras estándar "fi", "ff" y "fl" aparecen como un glifo de caracteres combinados. Observe que el par de caracteres de cada Ligadura estándar tocan.  
  
 ![Texto que usa ligaduras estándar OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont06.png "opentypefont06")  
Texto que usa ligaduras estándar OpenType  
  
 Sin embargo, puede deshabilitar las características de Ligadura estándar para que una ligadura estándar como "ff" se muestra como dos glifos independientes, en lugar de un glifo de caracteres combinados.  
  
 ![Texto que usa ligaduras estándar OpenType deshabilitadas](../../../../docs/framework/wpf/advanced/media/opentypefont07.png "opentypefont07")  
Texto que usa ligaduras estándar OpenType deshabilitadas  
  
 En el ejemplo de marcado siguiente se muestra cómo deshabilitar glifos de Ligadura estándar para la fuente Palatino Linotype, mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xml[OpenTypeFontSamples#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#6)]  
  
<a name="swashes"></a>   
## <a name="swashes"></a>Glifos floreados  
 Caracteres decorativos son glifos decorativos que utilizan adornos detallados que suelen asociada a la caligrafía. El texto siguiente muestra glifos estándar y floreados para la fuente Pescadero.  
  
 ![Texto que usa glifos estándar y floreados de OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont08.png "opentypefont08")  
Texto que usa glifos OpenType estándar y floreados  
  
 Glifos floreados se utilizan a menudo como elementos decorativos en frases cortas, como anuncios de eventos. El texto siguiente utiliza glifos floreados para destacar las letras mayúsculas del nombre del evento.  
  
 ![Texto que usa swash OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont09.png "opentypefont09")  
Texto que usa swash OpenType  
  
 En el ejemplo de marcado siguiente se muestra cómo se definen los floreados para una fuente, mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xml[OpenTypeFontSamples#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#7)]  
  
### <a name="contextual-swashes"></a>Glifos floreados contextuales  
 Algunas combinaciones de glifos floreados pueden producir un aspecto poco atractivo, como superpuestos trazos descendentes en letras adyacentes. Uso de floreo contextual permite utilizar un glifo floreado sustituto que ofrezca un mejor aspecto. El texto siguiente muestra la misma palabra antes y después de aplicar un floreados contextuales.  
  
 ![Texto que usa swash contextual](../../../../docs/framework/wpf/advanced/media/opentypefont19.png "OpenTypeFont19")  
Texto que usa swash contextual OpenType  
  
 En el ejemplo de marcado siguiente se muestra cómo definir un floreados contextuales para la fuente Pescadero, mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xml[OpenTypeFontSamples#OpenTypeFontSnippet16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet16)]  
  
<a name="alternates"></a>   
## <a name="alternates"></a>Alterna  
 Las alternativas son glifos que se pueden sustituir por un glifo estándar. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]las fuentes, como la fuente Pericles usada en los ejemplos siguientes, pueden contener glifos alternativos que se puede utilizar para crear diferentes aspectos de texto. El texto siguiente muestran glifos estándar para la fuente Pericles.  
  
 ![Texto que usa glifos estándar OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont01.png "opentypefont01")  
Texto que usa glifos estándar OpenType  
  
 El Pericles [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] fuente contiene glifos adicionales que proporcionan alternativas estilísticas al conjunto estándar de glifos. El texto siguiente muestra glifos alternativos de estilo.  
  
 ![Texto que usa glifos alternativos de estilo OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont02.png "opentypefont02")  
Texto que usa glifos alternativos de estilo OpenType  
  
 En el ejemplo de marcado siguiente se muestra cómo definir los glifos de alternativas estilísticas para la fuente Pericles, mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xml[OpenTypeFontSamples#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#2)]  
  
 El texto siguiente muestran varios otros glifos de alternativas estilísticas para la fuente Pericles.  
  
 ![Texto que usa glifos alternativos de estilo OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont03.png "opentypefont03")  
Texto que usa glifos alternativos de estilo OpenType  
  
 En el ejemplo de marcado siguiente se muestra cómo se definen estos otros glifos alternativos de estilo.  
  
 [!code-xml[OpenTypeFontSamples#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#3)]  
  
### <a name="random-contextual-alternates"></a>Alternativas contextuales aleatorias  
 Alternativas contextuales aleatorias proporcionan varios glifos sustitutos para un único carácter. Cuando se implementa con fuentes de tipo script, esta característica puede simular la escritura a mano mediante el uso de un conjunto de glifos elegidos aleatoriamente con ligeras diferencias de aspecto. El texto siguiente usa a alternativas contextuales aleatorias para la fuente Lindsey. Observe que la letra "a" varía ligeramente de aspecto  
  
 ![Texto que usa a alternativas contextuales aleatorias OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont23.png "OpenTypeFont23")  
Texto que usa alternativas contextuales aleatorias OpenType  
  
 En el ejemplo de marcado siguiente se muestra cómo definir las alternativas contextuales aleatorias para la fuente Lindsey, mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xml[OpenTypeFontSamples#OpenTypeFontSnippet20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet20)]  
  
### <a name="historical-forms"></a>Formularios históricos  
 Las formas históricas son convenciones tipográficas utilizadas comúnmente en el pasado. El texto siguiente muestra la frase "Boston, Massachusetts" utilizando un formato histórico de glifos para la fuente Palatino Linotype.  
  
 ![Texto que usa formas históricas OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont10.png "opentypefont10")  
Texto que usa formas históricas OpenType  
  
 En el ejemplo de marcado siguiente se muestra cómo se definen formas históricas para la fuente Palatino Linotype, mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xml[OpenTypeFontSamples#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#8)]  
  
<a name="numerical_styles"></a>   
## <a name="numerical-styles"></a>Estilos numéricos  
 Las fuentes OpenType admiten un gran número de características que se pueden usar con valores numéricos en texto.  
  
### <a name="fractions"></a>Fracciones  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]las fuentes admiten estilos de fracción apilada y con barra.  
  
 El texto siguiente muestra los estilos de fracción para la fuente Palatino Linotype.  
  
 ![Texto que usa OpenType fracciones verticales y barra diagonal](../../../../docs/framework/wpf/advanced/media/opentypefont12.png "opentypefont12")  
Texto que usa fracciones verticales y con barra diagonal OpenType  
  
 En el ejemplo de marcado siguiente se muestra cómo se definen estilos de fracción para la fuente Palatino Linotype, mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xml[OpenTypeFontSamples#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#10)]  
  
### <a name="old-style-numerals"></a>Números de estilo antiguo  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]las fuentes admiten un formato numeral de estilo antiguo. Este formato es útil para mostrar números en estilos que ya no son estándar. El texto siguiente muestra una fecha del siglo XVIII en formato numérico de estilo estándar y antiguo para la fuente Palatino Linotype.  
  
 ![Texto que usa números de estilo antiguo OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont24.png "OpenTypeFont24")  
Texto que usa números de estilo antiguo OpenType  
  
 El texto siguiente muestra números estándar para la fuente Palatino Linotype, seguido de números de estilo antiguo.  
  
 ![Texto que usa conjuntos de números de estilo antiguos OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont13.png "opentypefont13")  
Texto que usa conjuntos de números de estilo antiguo OpenType  
  
 En el ejemplo de marcado siguiente se muestra cómo definir los números de estilo antiguo para la fuente Palatino Linotype, mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xml[OpenTypeFontSamples#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#11)]  
  
### <a name="proportional-and-tabular-figures"></a>Cifras proporcionales y tabulares  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]las fuentes admiten una característica de cifra proporcional y tabular para controlar la alineación de ancho al utilizar los números. Cifras proporcionales tratan los números como si tuvieran un ancho diferente: "1" es más estrecho que "5". Las cifras tabulares se tratan como números de igual ancho para que se alineen verticalmente, lo que aumenta la legibilidad de la información de tipo financiero.  
  
 El texto siguiente muestra dos cifras proporcionales en la primera columna con la fuente Miramonte. Tenga en cuenta la diferencia de ancho entre los números "5" y "1". La segunda columna muestra los mismos dos valores numéricos con los anchos ajustados utilizando la característica de cifra tabular.  
  
 ![Texto que usa figuras tabulares aspecto proporcionales de OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont22.png "OpenTypeFont22")  
Texto que usa figuras proporcionales y tabulares de OpenType  
  
 En el ejemplo de marcado siguiente se muestra cómo se definen las cifras proporcionales y tabulares para la fuente Miramonte, mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xml[OpenTypeFontSamples#OpenTypeFontSnippet19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet19)]  
  
### <a name="slashed-zero"></a>Cero con barra diagonal  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]fuentes admiten un formato del numeral cero para resaltar la diferencia entre la letra "O" y el numeral "0". Cruzado que numeral cero cruzado se utiliza a menudo para los identificadores en la información financiera y comercial.  
  
 El texto siguiente muestra un identificador de orden con la fuente Miramonte. La primera línea utiliza numerales estándares. La segunda línea utilizada cero cruzado para conseguir un mejor contraste con la letra "O" mayúscula.  
  
 ![Texto que usa OpenType cero cruzado](../../../../docs/framework/wpf/advanced/media/opentypefont17.png "OpenTypeFont17")  
Texto que usa números cero con barra diagonal OpenType  
  
 En el ejemplo de marcado siguiente se muestra cómo definir cero cruzado para la fuente Miramonte, mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xml[OpenTypeFontSamples#OpenTypeFontSnippet15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet15)]  
  
<a name="typography_class"></a>   
## <a name="typography-class"></a>Clase Typography  
 El <xref:System.Windows.Documents.Typography> objeto expone el conjunto de características que una [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] admite la fuente. Al establecer las propiedades de <xref:System.Windows.Documents.Typography> en marcado, puede crear fácilmente documentos que saquen partido de [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] características.  
  
 El texto siguiente muestra las letras mayúsculas estándar para la fuente Pescadero, seguidas de letras con estilo "SmallCaps" y "AllSmallCaps". En este caso, se utiliza el mismo tamaño de fuente para las tres palabras.  
  
 ![Texto que usa mayúsculas OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont11.png "opentypefont11")  
Texto que usa mayúsculas OpenType  
  
 En el ejemplo de marcado siguiente se muestra cómo se definen las mayúsculas para la fuente Pescadero, mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto. Cuando se utiliza el formato "SmallCaps", se omite cualquier letra mayúscula inicial.  
  
 [!code-xml[OpenTypeFontSamples#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
 En el ejemplo de código siguiente se realiza la misma tarea que el ejemplo anterior de marcado.  
  
 [!code-csharp[TypographyCodeSnippets#TypographyCodeSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TypographyCodeSnippets/CSharp/Page1.xaml.cs#typographycodesnippet1)]
 [!code-vb[TypographyCodeSnippets#TypographyCodeSnippet1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TypographyCodeSnippets/visualbasic/page1.xaml.vb#typographycodesnippet1)]  
  
### <a name="typography-class-properties"></a>Propiedades de la clase de tipografía  
 La tabla siguiente enumeran las propiedades, valores y configuraciones predeterminadas de la <xref:System.Windows.Documents.Typography> objeto.  
  
|Propiedad|Valores|Default Value|  
|--------------|----------------|-------------------|  
|<xref:System.Windows.Documents.Typography.AnnotationAlternates%2A>|Valor numérico - byte|0|  
|<xref:System.Windows.Documents.Typography.Capitals%2A>|<xref:System.Windows.FontCapitals> | <xref:System.Windows.FontCapitals> | <xref:System.Windows.FontCapitals> | <xref:System.Windows.FontCapitals> | <xref:System.Windows.FontCapitals> | <xref:System.Windows.FontCapitals> | <xref:System.Windows.FontCapitals>|<xref:System.Windows.FontCapitals?displayProperty=fullName>|  
|<xref:System.Windows.Documents.Typography.CapitalSpacing%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.CaseSensitiveForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.ContextualAlternates%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualSwashes%2A>|Valor numérico - byte|0|  
|<xref:System.Windows.Documents.Typography.DiscretionaryLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianExpertForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianLanguage%2A>|<xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage>|<xref:System.Windows.FontEastAsianLanguage?displayProperty=fullName>|  
|<xref:System.Windows.Documents.Typography.EastAsianWidths%2A>|<xref:System.Windows.FontEastAsianWidths> | <xref:System.Windows.FontEastAsianWidths> | <xref:System.Windows.FontEastAsianWidths> | <xref:System.Windows.FontEastAsianWidths> | <xref:System.Windows.FontEastAsianWidths> | <xref:System.Windows.FontEastAsianWidths>|<xref:System.Windows.FontEastAsianWidths?displayProperty=fullName>|  
|<xref:System.Windows.Documents.Typography.Fraction%2A>|<xref:System.Windows.FontFraction> | <xref:System.Windows.FontFraction> | <xref:System.Windows.FontFraction>|<xref:System.Windows.FontFraction?displayProperty=fullName>|  
|<xref:System.Windows.Documents.Typography.HistoricalForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.HistoricalLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.Kerning%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.MathematicalGreek%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.NumeralAlignment%2A>|<xref:System.Windows.FontNumeralAlignment> | <xref:System.Windows.FontNumeralAlignment> | <xref:System.Windows.FontNumeralAlignment>|<xref:System.Windows.FontNumeralAlignment?displayProperty=fullName>|  
|<xref:System.Windows.Documents.Typography.NumeralStyle%2A>|<xref:System.Boolean>|<xref:System.Windows.FontNumeralStyle?displayProperty=fullName>|  
|<xref:System.Windows.Documents.Typography.SlashedZero%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StandardLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.StandardSwashes%2A>|valor numérico: byte|0|  
|<xref:System.Windows.Documents.Typography.StylisticAlternates%2A>|valor numérico: byte|0|  
|<xref:System.Windows.Documents.Typography.StylisticSet1%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet2%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet3%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet4%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet5%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet6%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet7%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet8%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet9%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet10%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet11%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet12%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet13%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet14%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet15%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet16%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet17%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet18%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet19%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet20%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.Variants%2A>|<xref:System.Windows.FontVariants> | <xref:System.Windows.FontVariants> | <xref:System.Windows.FontVariants> | <xref:System.Windows.FontVariants> | <xref:System.Windows.FontVariants> | <xref:System.Windows.FontVariants>|<xref:System.Windows.FontVariants?displayProperty=fullName>|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Documents.Typography>   
 [Especificación de OpenType](http://go.microsoft.com/fwlink/?LinkId=96731)   
 [Tipografía en WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)   
 [Paquete de fuentes OpenType de ejemplo](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md)   
 [Empaquetar fuentes con aplicaciones](../../../../docs/framework/wpf/advanced/packaging-fonts-with-applications.md)
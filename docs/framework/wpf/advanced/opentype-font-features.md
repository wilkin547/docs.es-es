---
title: Características de las fuentes OpenType
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [WPF], OpenType
- typography [WPF], OpenType font technology
- OpenType font technology [WPF]
ms.assetid: 4061a9d1-fe8b-4921-9e17-18ec7d2e3ea2
ms.openlocfilehash: f3d1dd9f7ef8122ac5573121e4f779fade776c8c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43862149"
---
# <a name="opentype-font-features"></a>Características de las fuentes OpenType
En este tema se proporciona información general sobre algunas de las características clave de la tecnología de fuentes [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  

  
<a name="overview"></a>   
## <a name="opentype-font-format"></a>Formato de fuente OpenType  
 El formato de fuente [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] es una extensión del formato de fuente [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)] y agrega compatibilidad para datos de fuentes PostScript. El formato de fuente [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] fue desarrollado conjuntamente por [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] y Adobe Corporation. Las fuentes [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] y los servicios del sistema operativo compatibles con las fuentes [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] proporcionan a los usuarios una manera sencilla de instalar y usar fuentes, si las fuentes contienen esquemas [!INCLUDE[TLA2#tla_truetype](../../../../includes/tla2sharptla-truetype-md.md)] o CFF (PostScript).  
  
 El formato de fuente [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] soluciona los desafíos de desarrollo siguientes:  
  
-   Más compatibilidad con varias plataformas.  
  
-   Más compatibilidad con juegos de caracteres internacionales.  
  
-   Mejor protección para los datos de fuente.  
  
-   Tamaños de archivo más pequeños para hacer más eficaz la distribución de la fuente.  
  
-   Más compatibilidad con el control tipográfico avanzado.  
  
> [!NOTE]
>  El SDK de Windows contiene un conjunto de fuentes [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] de muestra que puede usar con aplicaciones [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Estas fuentes proporcionan la mayoría de las características ilustradas en el resto de este tema. Para obtener más información, vea [Paquete de fuentes OpenType de ejemplo](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md).  
  
 Consulte [Especificación OpenType](https://go.microsoft.com/fwlink/?LinkId=96731) para obtener más información sobre el formato de fuente [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)].  
  
### <a name="advanced-typographic-extensions"></a>Extensiones tipográficas avanzadas  
 Las tablas tipográficas avanzadas (tablas de diseño [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]) amplían la funcionalidad de fuentes con esquemas [!INCLUDE[TLA2#tla_truetype](../../../../includes/tla2sharptla-truetype-md.md)] o CFF. Las fuentes de diseño [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] contienen información adicional que amplía las capacidades de las fuentes para admitir tipografía internacional de alta calidad. La mayoría de fuentes [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] exponen solo un subconjunto del total de características [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] disponibles. Las fuentes [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] proporcionan las siguientes características.  
  
-   Asignación enriquecida entre caracteres y glifos que admiten ligaduras, formas posicionales, alternativas y otras sustituciones de fuentes.  
  
-   Compatibilidad con datos adjuntos de glifo y posicionamiento en dos dimensiones.  
  
-   Información explícita de script y lenguaje que contiene la fuente, para que una aplicación de procesamiento de textos pueda ajustar su comportamiento en consecuencia.  
  
 Las tablas de diseño [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] se describen con más detalle en la sección ["Tablas de archivos de fuentes"](https://www.microsoft.com/typography/otspec/otff.htm) sección de la especificación de [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)].  
  
 El resto de esta introducción presenta la amplitud y la flexibilidad de algunas visualmente interesante [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] características que se exponen mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto. Para obtener más información sobre este objeto, consulte [Clase de tipografía](#typography_class).  
  
<a name="variants"></a>   
## <a name="variants"></a>Variantes  
 Las variantes se usan para representar varios estilos tipográficos, como superíndices y subíndices.  
  
### <a name="superscripts-and-subscripts"></a>Superíndices y subíndices  
 El <xref:System.Windows.Documents.Typography.Variants%2A> propiedad le permite establecer los valores de superíndice y subíndice de un [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] fuente.  
  
 En el texto siguiente se muestran superíndices para la fuente Palatino Linotype.  
  
 ![Texto que usa superíndices OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont14.gif "opentypefont14")  
Texto que usa superíndices OpenType  
  
 En el ejemplo de marcación siguiente se muestra cómo se definen los superíndices para la fuente Palatino Linotype mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xaml[OpenTypeFontSamples#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#12)]  
  
 El texto siguiente muestran subíndices para la fuente Palatino Linotype.  
  
 ![Texto que usa subíndices OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont15.gif "opentypefont15")  
Texto que usa subíndices OpenType  
  
 En el ejemplo de marcación siguiente se muestra cómo se definen los subíndices para la fuente Palatino Linotype mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xaml[OpenTypeFontSamples#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#13)]  
  
### <a name="decorative-uses-of-superscripts-and-subscripts"></a>Usos decorativos de superíndices y subíndices  
 También puede usar superíndices y subíndices para crear efectos decorativos con texto en mayúsculas y minúsculas. En el texto siguiente se muestra texto con superíndices y subíndices para la fuente Palatino Linotype. Tenga en cuenta que las mayúsculas no se ven afectadas.  
  
 ![Texto que usa superíndices OpenType y subíndices](../../../../docs/framework/wpf/advanced/media/opentypefont16.gif "opentypefont16")  
Texto que usa superíndices y subíndices OpenType  
  
 En el ejemplo de marcación siguiente se muestra cómo se definen los superíndices y subíndices para una fuente mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xaml[OpenTypeFontSamples#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#14)]  
  
<a name="capitals"></a>   
## <a name="capitals"></a>Mayúsculas  
 Las mayúsculas son un conjunto de formatos tipográficos que representan el texto en glifos con estilo de mayúscula. Normalmente, cuando se representa todo un texto en mayúsculas, el espaciado entre las letras puede parecer demasiado estrecho y el espesor y la proporción de las letras, demasiado anchos. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] admite varios formatos de estilo para las mayúsculas, incluido versales, mayúsculas pequeñas, títulos y espaciado de mayúsculas. Estos formatos de estilo le permiten controlar el aspecto de las mayúsculas.  
  
 En el texto siguiente se muestran letras en mayúsculas estándar para la fuente Pescadero, seguidas de letras con estilo "SmallCaps" y "AllSmallCaps". En este caso, se usa el mismo tamaño de fuente para las tres palabras.  
  
 ![Texto que usa mayúsculas OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont11.gif "opentypefont11")  
Texto que usa mayúsculas OpenType  
  
 En el ejemplo de marcación siguiente se muestra cómo se definen las mayúsculas para la fuente Pescadero mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto. Cuando se usa el formato "SmallCaps", se omite cualquier letra mayúscula inicial.  
  
 [!code-xaml[OpenTypeFontSamples#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
### <a name="titling-capitals"></a>Mayúsculas de título  
 Las mayúsculas de título son más estrechas en espesor y proporción y están diseñadas para dar un aspecto más elegante que las mayúsculas corrientes. Las mayúsculas se utilizan normalmente en tamaños de fuente mayores como encabezados. El texto siguiente muestran las mayúsculas normales y de títulos para la fuente Pescadero. Tenga en cuenta los anchos de stem más estrechos del texto en la segunda línea.  
  
 ![Texto que usa mayúsculas titling OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont20.gif "OpenTypeFont20")  
Texto que usa mayúsculas titling OpenType  
  
 En el ejemplo de marcación siguiente se muestra cómo se definen las mayúsculas para la fuente Pescadero mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet17)]  
  
### <a name="capital-spacing"></a>Espaciado de mayúsculas  
 El espaciado de mayúsculas es una característica que le permite proporcionar más espacio al usar las mayúsculas en un texto. Letras mayúsculas normalmente están diseñadas para combinarse con letras minúsculas. Espaciado que parece correcto entre y una letra mayúscula y minúscula pueden parecer demasiado estrecho cuando se utilizan todas las letras mayúsculas. El texto siguiente muestra un espaciado normal y de capital para la fuente Pescadero.  
  
 ![Texto que usa espaciado de mayúsculas OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont21.gif "OpenTypeFont21")  
Texto que usa espaciado de mayúsculas OpenType  
  
 En el ejemplo de marcación siguiente se muestra cómo definir el espaciado de mayúsculas para la fuente Pescadero mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet18)]  
  
<a name="ligatures"></a>   
## <a name="ligatures"></a>Ligaduras  
 Las ligaduras son dos o más glifos que se unen en un solo glifo para crear texto más legible o atractivo. Las fuentes [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] admiten cuatro tipos de ligaduras:  
  
-   **Ligaduras estándar**. Diseñadas para mejorar la legibilidad. Las ligaduras estándar incluyen "fi", "fl" y "ff".  
  
-   **Ligaduras contextuales**. Diseñadas para mejorar la legibilidad al proporcionar un comportamiento de unión mejor entre los caracteres que constituyen la ligadura.  
  
-   **Ligaduras discrecionales**. Diseñadas para ser ornamentales y no específicamente para la legibilidad.  
  
-   **Ligaduras históricas**. Diseñadas para ser históricas y no específicamente para la legibilidad.  
  
 En el texto siguiente se muestran glifos de ligadura estándar para la fuente Pericles.  
  
 ![Texto que usa ligaduras estándar OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont04.gif "opentypefont04")  
Texto que usa ligaduras estándar OpenType  
  
 En el ejemplo de marcación siguiente se muestra cómo se definen los glifos de Ligadura estándar para la fuente Pericles mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xaml[OpenTypeFontSamples#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#4)]  
  
 En el texto siguiente se muestran los glifos de ligadura discrecional para la fuente Pericles.  
  
 ![Texto que usa ligaduras discrecionales OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont05.gif "opentypefont05")  
Texto que usa ligaduras discrecionales OpenType  
  
 En el ejemplo de marcación siguiente se muestra cómo se definen los glifos de ligadura discrecional para la fuente Pericles mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xaml[OpenTypeFontSamples#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#5)]  
  
 De forma predeterminada, las fuentes [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] permiten las ligaduras estándar. Por ejemplo, si usa la fuente Palatino Linotype, las ligaduras estándar "fi", "ff" y "fl" aparecen como un glifo de caracteres combinados. Tenga en cuenta que el par de caracteres de cada Ligadura estándar touch entre sí.  
  
 ![Texto que usa ligaduras estándar OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont06.gif "opentypefont06")  
Texto que usa ligaduras estándar OpenType  
  
 Sin embargo, puede deshabilitar las características de ligadura estándar para que una ligadura estándar, como "ff", se muestre como dos glifos independientes, en lugar de un glifo de caracteres combinados.  
  
 ![Texto con ligaduras estándar OpenType deshabilitadas](../../../../docs/framework/wpf/advanced/media/opentypefont07.gif "opentypefont07")  
Texto que usa ligaduras estándar OpenType deshabilitadas  
  
 En el ejemplo de marcación siguiente se muestra cómo deshabilitar los glifos de Ligadura estándar para la fuente Palatino Linotype mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xaml[OpenTypeFontSamples#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#6)]  
  
<a name="swashes"></a>   
## <a name="swashes"></a>Caracteres floreados  
 Los caracteres floreados son glifos decorativos que usan adornos elaborados que suelen asociarse a la caligrafía. El texto siguiente muestran glifos estándar y floreados para la fuente Pescadero.  
  
 ![Texto que usa glifos OpenType estándar y floreados](../../../../docs/framework/wpf/advanced/media/opentypefont08.gif "opentypefont08")  
Texto que usa glifos OpenType estándar y floreados  
  
 Los caracteres floreados se usan a menudo como elementos decorativos en frases cortas, como anuncios de eventos. El texto siguiente utiliza caracteres floreados para destacar las letras en mayúscula del nombre del evento.  
  
 ![Texto que usa swash OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont09.gif "opentypefont09")  
Texto que usa swash OpenType  
  
 En el ejemplo de marcación siguiente se muestra cómo se definen los caracteres floreados para una fuente mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xaml[OpenTypeFontSamples#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#7)]  
  
### <a name="contextual-swashes"></a>Caracteres floreados contextuales  
 Algunas combinaciones de glifos floreados pueden producir un aspecto poco atractivo, como trazos superpuestos descendentes en letras adyacentes. Uso de un carácter floreado contextual permite utilizar un glifo floreado sustituto que genera un mejor aspecto. El texto siguiente muestra la misma palabra antes y después de aplica un carácter floreado contextual.  
  
 ![Texto que usa swash contextual OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont19.gif "OpenTypeFont19")  
Texto que usa swash contextual OpenType  
  
 En el ejemplo de marcación siguiente se muestra cómo definir un carácter floreado contextual para la fuente Pescadero mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet16)]  
  
<a name="alternates"></a>   
## <a name="alternates"></a>Alternativas  
 Las alternativas son glifos que se pueden sustituir por un glifo estándar. Las fuentes [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)], como la fuente Pericles usada en los ejemplos siguientes, pueden contener glifos alternativos que se puede usar para crear diferentes aspectos de texto. En el texto siguiente se muestran glifos estándar para la fuente Pericles.  
  
 ![Texto que usa glifos estándares OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont01.gif "opentypefont01")  
Texto que usa glifos estándar OpenType  
  
 La fuente [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Pericles contiene glifos adicionales que proporcionan alternativas estilísticas al conjunto estándar de glifos. En el texto siguiente se muestran glifos alternativos de estilo.  
  
 ![Texto que usa glifos alternativos de estilo OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont02.gif "opentypefont02")  
Texto que usa glifos alternativos de estilo OpenType  
  
 En el ejemplo de marcación siguiente se muestra cómo se definen los glifos alternativos de estilo para la fuente Pericles mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xaml[OpenTypeFontSamples#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#2)]  
  
 El texto siguiente muestran varios otros glifos alternativos de estilo para la fuente Pericles.  
  
 ![Texto que usa glifos alternativos de estilo OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont03.gif "opentypefont03")  
Texto que usa glifos alternativos de estilo OpenType  
  
 En el ejemplo de marcación siguiente se muestra cómo se definen estos otros glifos alternativos de estilo.  
  
 [!code-xaml[OpenTypeFontSamples#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#3)]  
  
### <a name="random-contextual-alternates"></a>Alternativas contextuales aleatorias  
 Las alternativas contextuales aleatorias proporcionan varios glifos sustitutos para un único carácter. Cuando se implementa con fuentes del tipo de secuencia de comandos, esta característica puede simular la escritura a mano mediante el uso de un conjunto de glifos elegidos aleatoriamente con ligeras diferencias de apariencia. El texto siguiente usa a alternativas contextuales aleatorias para la fuente Lindsey. Tenga en cuenta que la letra "a" varía ligeramente de aspecto  
  
 ![Texto que usa alternativas contextuales aleatorias OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont23.gif "OpenTypeFont23")  
Texto que usa alternativas contextuales aleatorias OpenType  
  
 En el ejemplo de marcación siguiente se muestra cómo se definen alternativas contextuales aleatorias para la fuente Lindsey mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet20)]  
  
### <a name="historical-forms"></a>Formas históricas  
 Las formas históricas son convenciones tipográficas usadas comúnmente en el pasado. El texto siguiente muestra la frase "Boston, Massachusetts," utilizando un formato histórico de glifos para la fuente Palatino Linotype.  
  
 ![Texto que usa formas históricas OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont10.gif "opentypefont10")  
Texto que usa formas históricas OpenType  
  
 En el ejemplo de marcación siguiente se muestra cómo se definen los formatos históricos para la fuente Palatino Linotype mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xaml[OpenTypeFontSamples#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#8)]  
  
<a name="numerical_styles"></a>   
## <a name="numerical-styles"></a>Estilos numéricos  
 Las fuentes OpenType admiten un gran número de características que se pueden usar con valores numéricos en texto.  
  
### <a name="fractions"></a>Fracciones  
 Las fuentes [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] admiten estilos para las fracciones, ya sean verticales o con barra diagonal.  
  
 En el texto siguiente se muestran estilos de fracciones para la fuente Palatino Linotype.  
  
 ![Texto OpenType que usa fracciones verticales y con barra diagonal](../../../../docs/framework/wpf/advanced/media/opentypefont12.gif "opentypefont12")  
Texto que usa fracciones verticales y con barra diagonal OpenType  
  
 En el ejemplo de marcación siguiente se muestra cómo se definen los estilos de fracción para la fuente Palatino Linotype mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xaml[OpenTypeFontSamples#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#10)]  
  
### <a name="old-style-numerals"></a>Números de estilo antiguo  
 Las fuentes [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] admiten un formato de números de estilo antiguo. Este formato es útil para mostrar números en estilos que ya no son estándar. El texto siguiente muestra una fecha del siglo XVIII en formatos de números de estilo antiguo y estándar para la fuente Palatino Linotype.  
  
 ![Texto que usa números de estilo antiguo OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont24.gif "OpenTypeFont24")  
Texto que usa números de estilo antiguo OpenType  
  
 En el texto siguiente se muestran números estándar para la fuente Palatino Linotype, seguidos de números de estilo antiguo.  
  
 ![Texto que usa conjuntos de números de estilo antiguo OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont13.gif "opentypefont13")  
Texto que usa conjuntos de números de estilo antiguo OpenType  
  
 En el ejemplo de marcación siguiente se muestra cómo se definen los números de estilo antiguo para la fuente Palatino Linotype mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xaml[OpenTypeFontSamples#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#11)]  
  
### <a name="proportional-and-tabular-figures"></a>Cifras proporcionales y tabulares  
 Las fuentes [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] admiten una característica de cifra proporcional y tabular para controlar la alineación de ancho al usar números. Las cifras proporcionales tratan los números como si tuvieran un ancho diferente: "1" es más estrecho que "5". Las cifras tabulares se tratan como números de igual ancho que se alinean verticalmente, lo que aumenta la legibilidad de la información de tipo financiero.  
  
 El texto siguiente muestran dos cifras proporcionales en la primera columna con la fuente Miramonte. Tenga en cuenta la diferencia en el ancho entre los números "5" y "1". La segunda columna muestra los mismos dos valores numéricos con los anchos ajustados mediante la característica de cifra tabular.  
  
 ![Texto que usa figuras tabulares y proporcionales OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont22.gif "OpenTypeFont22")  
Texto que usa cifras tabulares y proporcionales OpenType  
  
 En el ejemplo de marcación siguiente se muestra cómo se definen las cifras proporcionales y tabulares para la fuente Miramonte mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet19)]  
  
### <a name="slashed-zero"></a>Cero con barra diagonal  
 Las fuentes [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] admiten un formato numérico de cero con barra diagonal para resaltar la diferencia entre la letra "O" y el número "0". El número cero con barra diagonal se usa a menudo para identificadores en información financiera y comercial.  
  
 El texto siguiente muestra un identificador de pedido de ejemplo con la fuente Miramonte. La primera línea usa números estándar. La segunda línea usa cero cruzado para conseguir un mejor contraste con la letra "O" mayúscula.  
  
 ![Texto que usa OpenType cero cruzado](../../../../docs/framework/wpf/advanced/media/opentypefont17.gif "OpenTypeFont17")  
Texto que usa números cero con barra diagonal OpenType  
  
 En el ejemplo de marcación siguiente se muestra cómo definir cero cruzado para la fuente Miramonte mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet15)]  
  
<a name="typography_class"></a>   
## <a name="typography-class"></a>Clase de tipografía  
 El <xref:System.Windows.Documents.Typography> objeto expone el conjunto de características que una [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] fuente admite. Al establecer las propiedades de <xref:System.Windows.Documents.Typography> en marcado, puede crear fácilmente documentos que saquen partido de [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] características.  
  
 En el texto siguiente se muestran letras en mayúsculas estándar para la fuente Pescadero, seguidas de letras con estilo "SmallCaps" y "AllSmallCaps". En este caso, se usa el mismo tamaño de fuente para las tres palabras.  
  
 ![Texto que usa mayúsculas OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont11.gif "opentypefont11")  
Texto que usa mayúsculas OpenType  
  
 En el ejemplo de marcación siguiente se muestra cómo se definen las mayúsculas para la fuente Pescadero mediante las propiedades de la <xref:System.Windows.Documents.Typography> objeto. Cuando se usa el formato "SmallCaps", se omite cualquier letra mayúscula inicial.  
  
 [!code-xaml[OpenTypeFontSamples#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
 En el ejemplo de código siguiente se realiza la misma tarea que en el ejemplo anterior de marcación.  
  
 [!code-csharp[TypographyCodeSnippets#TypographyCodeSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TypographyCodeSnippets/CSharp/Page1.xaml.cs#typographycodesnippet1)]
 [!code-vb[TypographyCodeSnippets#TypographyCodeSnippet1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TypographyCodeSnippets/visualbasic/page1.xaml.vb#typographycodesnippet1)]  
  
### <a name="typography-class-properties"></a>Propiedades de la clase de tipografía  
 En la tabla siguiente se enumera las propiedades, valores y configuraciones predeterminadas de la <xref:System.Windows.Documents.Typography> objeto.  
  
|Property|Valores|Valor predeterminado|  
|--------------|----------------|-------------------|  
|<xref:System.Windows.Documents.Typography.AnnotationAlternates%2A>|Valor numérico: byte|0|  
|<xref:System.Windows.Documents.Typography.Capitals%2A>|<xref:System.Windows.FontCapitals.AllPetiteCaps> &#124; <xref:System.Windows.FontCapitals.AllSmallCaps> &#124; <xref:System.Windows.FontCapitals.Normal> &#124; <xref:System.Windows.FontCapitals.PetiteCaps> &#124; <xref:System.Windows.FontCapitals.SmallCaps> &#124; <xref:System.Windows.FontCapitals.Titling> &#124; <xref:System.Windows.FontCapitals.Unicase>|<xref:System.Windows.FontCapitals.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.CapitalSpacing%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.CaseSensitiveForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.ContextualAlternates%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualSwashes%2A>|Valor numérico: byte|0|  
|<xref:System.Windows.Documents.Typography.DiscretionaryLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianExpertForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianLanguage%2A>|<xref:System.Windows.FontEastAsianLanguage.HojoKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis04> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis78> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis83> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis90> &#124; <xref:System.Windows.FontEastAsianLanguage.NlcKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Normal> &#124; <xref:System.Windows.FontEastAsianLanguage.Simplified> &#124; <xref:System.Windows.FontEastAsianLanguage.Traditional> &#124; <xref:System.Windows.FontEastAsianLanguage.TraditionalNames>|<xref:System.Windows.FontEastAsianLanguage.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.EastAsianWidths%2A>|<xref:System.Windows.FontEastAsianWidths.Full> &#124; <xref:System.Windows.FontEastAsianWidths.Half> &#124; <xref:System.Windows.FontEastAsianWidths.Normal> &#124; <xref:System.Windows.FontEastAsianWidths.Proportional> &#124; <xref:System.Windows.FontEastAsianWidths.Quarter> &#124; <xref:System.Windows.FontEastAsianWidths.Third>|<xref:System.Windows.FontEastAsianWidths.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.Fraction%2A>|<xref:System.Windows.FontFraction.Normal> &#124; <xref:System.Windows.FontFraction.Slashed> &#124; <xref:System.Windows.FontFraction.Stacked>|<xref:System.Windows.FontFraction.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.HistoricalForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.HistoricalLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.Kerning%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.MathematicalGreek%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.NumeralAlignment%2A>|<xref:System.Windows.FontNumeralAlignment.Normal> &#124; <xref:System.Windows.FontNumeralAlignment.Proportional> &#124; <xref:System.Windows.FontNumeralAlignment.Tabular>|<xref:System.Windows.FontNumeralAlignment.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.NumeralStyle%2A>|<xref:System.Boolean>|<xref:System.Windows.FontNumeralStyle.Normal?displayProperty=nameWithType>|  
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
|<xref:System.Windows.Documents.Typography.Variants%2A>|<xref:System.Windows.FontVariants.Inferior> &#124; <xref:System.Windows.FontVariants.Normal> &#124; <xref:System.Windows.FontVariants.Ordinal> &#124; <xref:System.Windows.FontVariants.Ruby> &#124; <xref:System.Windows.FontVariants.Subscript> &#124; <xref:System.Windows.FontVariants.Superscript>|<xref:System.Windows.FontVariants.Normal?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Documents.Typography>  
 [Especificación OpenType](https://go.microsoft.com/fwlink/?LinkId=96731)  
 [Tipografía en WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)  
 [Paquete de fuentes OpenType de ejemplo](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md)  
 [Empaquetar fuentes con aplicaciones](../../../../docs/framework/wpf/advanced/packaging-fonts-with-applications.md)

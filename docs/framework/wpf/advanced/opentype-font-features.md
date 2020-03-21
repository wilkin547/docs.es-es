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
ms.openlocfilehash: 52fe73bccd625c9508b398874fd6b075af2445e0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186805"
---
# <a name="opentype-font-features"></a>Características de las fuentes OpenType

En este tema se proporciona información general sobre algunas de las características clave de la tecnología de fuentes OpenType en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
<a name="overview"></a>
## <a name="opentype-font-format"></a>Formato de fuente OpenType  
 El formato de fuente OpenType es una extensión del formato de fuente TrueType®, que agrega compatibilidad con los datos de fuente PostScript. El formato de fuente OpenType fue desarrollado conjuntamente por Microsoft y Adobe Corporation. Las fuentes OpenType y los servicios del sistema operativo que admiten fuentes OpenType proporcionan a los usuarios una forma sencilla de instalar y utilizar fuentes, independientemente de si las fuentes contienen contornos TrueType o CFF (PostScript).  
  
 El formato de fuente OpenType aborda los siguientes desafíos para desarrolladores:  
  
- Más compatibilidad con varias plataformas.  
  
- Más compatibilidad con juegos de caracteres internacionales.  
  
- Mejor protección para los datos de fuente.  
  
- Tamaños de archivo más pequeños para hacer más eficaz la distribución de la fuente.  
  
- Más compatibilidad con el control tipográfico avanzado.  
  
> [!NOTE]
> El Windows SDK contiene un conjunto de fuentes [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] OpenType de ejemplo que puede usar con aplicaciones. Estas fuentes proporcionan la mayoría de las características ilustradas en el resto de este tema. Para obtener más información, vea [Sample OpenType Font Pack](sample-opentype-font-pack.md).  
  
Para obtener más información sobre el formato de fuente OpenType, consulte la [especificación OpenType](https://docs.microsoft.com/typography/opentype/spec/).  
  
### <a name="advanced-typographic-extensions"></a>Extensiones tipográficas avanzadas  
 Las tablas tipográficas avanzadas (tablas OpenType Layout) amplían la funcionalidad de las fuentes con contornos TrueType o CFF. Las fuentes OpenType Layout contienen información adicional que amplía las capacidades de las fuentes para admitir la tipografía internacional de alta calidad. La mayoría de las fuentes OpenType exponen solo un subconjunto de las características OpenType totales disponibles. Las fuentes OpenType proporcionan las siguientes características.  
  
- Asignación enriquecida entre caracteres y glifos que admiten ligaduras, formas posicionales, alternativas y otras sustituciones de fuentes.  
  
- Compatibilidad con datos adjuntos de glifo y posicionamiento en dos dimensiones.  
  
- Información explícita de script y lenguaje que contiene la fuente, para que una aplicación de procesamiento de textos pueda ajustar su comportamiento en consecuencia.  
  
 Las tablas OpenType Layout se describen con más detalle en la sección ["Tablas](https://www.microsoft.com/typography/otspec/otff.htm) de archivos de fuente" de la especificación OpenType.  
  
 El resto de esta información general presenta la amplitud y flexibilidad de algunas de las características <xref:System.Windows.Documents.Typography> de OpenType visualmente interesantes que se exponen por las propiedades del objeto. Para obtener más información sobre este objeto, consulte [Clase de tipografía](#typography_class).  
  
<a name="variants"></a>
## <a name="variants"></a>Variantes  
 Las variantes se usan para representar varios estilos tipográficos, como superíndices y subíndices.  
  
### <a name="superscripts-and-subscripts"></a>Superíndices y subíndices  
 La <xref:System.Windows.Documents.Typography.Variants%2A> propiedad permite establecer valores de superíndice y subíndice para una fuente OpenType.  
  
 En el texto siguiente se muestran superíndices para la fuente Palatino Linotype.  
  
 ![Texto que usa superíndices OpenType](./media/opentype-font-features/opentype-superscripts.gif "Texto que usa superíndices OpenType")  
  
 En el ejemplo de marcado siguiente se muestra cómo definir superíndices para la fuente Palatino Linotype, utilizando las propiedades del <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xaml[OpenTypeFontSamples#12](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#12)]  
  
 El texto siguiente muestra los subíndices de la fuente Palatino Linotype.  
  
 ![Texto que usa subíndices OpenType](./media/opentype-font-features/opentype-subscripts.gif "Texto que usa subíndices OpenType")  
  
 En el ejemplo de marcado siguiente se muestra cómo definir subíndices para la fuente Palatino Linotype, utilizando las propiedades del <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xaml[OpenTypeFontSamples#13](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#13)]  
  
### <a name="decorative-uses-of-superscripts-and-subscripts"></a>Usos decorativos de superíndices y subíndices  
 También puede usar superíndices y subíndices para crear efectos decorativos con texto en mayúsculas y minúsculas. En el texto siguiente se muestra texto con superíndices y subíndices para la fuente Palatino Linotype. Tenga en cuenta que las mayúsculas no se ven afectadas.  
  
 ![Texto que usa superíndices y subíndices OpenType](./media/opentype-font-features/opentype-superscripts-subscripts.gif "Texto que usa superíndices y subíndices OpenType")  

 En el siguiente ejemplo de marcado se muestra cómo definir superíndices y subíndices para una fuente, utilizando las propiedades del <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xaml[OpenTypeFontSamples#14](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#14)]  
  
<a name="capitals"></a>
## <a name="capitals"></a>Mayúsculas  
 Las mayúsculas son un conjunto de formatos tipográficos que representan el texto en glifos con estilo de mayúscula. Normalmente, cuando se representa todo un texto en mayúsculas, el espaciado entre las letras puede parecer demasiado estrecho y el espesor y la proporción de las letras, demasiado anchos. OpenType admite una serie de formatos de estilo para mayúsculas, incluidos mayúsculas pequeñas, mayúsculas pequeñas, titulación y espaciado de mayúsculas. Estos formatos de estilo le permiten controlar el aspecto de las mayúsculas.  
  
 En el texto siguiente se muestran letras en mayúsculas estándar para la fuente Pescadero, seguidas de letras con estilo "SmallCaps" y "AllSmallCaps". En este caso, se utiliza el mismo tamaño de fuente para las tres palabras.  
  
 ![Texto que usa mayúsculas OpenType](./media/opentype-font-features/opentype-capitals.gif "Texto que usa mayúsculas OpenType")  
  
 En el ejemplo de marcado siguiente se muestra cómo definir mayúsculas para la fuente Pescadero, utilizando las propiedades del <xref:System.Windows.Documents.Typography> objeto. Cuando se usa el formato "SmallCaps", se omite cualquier letra mayúscula inicial.  
  
 [!code-xaml[OpenTypeFontSamples#9](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
### <a name="titling-capitals"></a>Mayúsculas de título  
 Las mayúsculas de título son más estrechas en espesor y proporción y están diseñadas para dar un aspecto más elegante que las mayúsculas corrientes. Las mayúsculas de título se utilizan normalmente en tamaños de fuente más grandes como encabezados. El texto siguiente muestra mayúsculas normales y titulatorias para la fuente Pescadero. Observe los anchos de vástago más estrechos del texto en la segunda línea.  
  
 ![Texto que usa mayúsculas de título OpenType](./media/opentype-font-features/opentype-titling-capitals.gif "Texto que usa mayúsculas titling OpenType")  
  
 En el ejemplo de marcado siguiente se muestra cómo definir mayúsculas de <xref:System.Windows.Documents.Typography> titulación para la fuente Pescadero, utilizando las propiedades del objeto.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet17](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet17)]  
  
### <a name="capital-spacing"></a>Espaciado de mayúsculas  
 El espaciado de mayúsculas es una característica que le permite proporcionar más espacio al usar las mayúsculas en un texto. Las letras mayúsculas suelen estar diseñadas para mezclarse con letras minúsculas. El espaciado que parece atractivo entre una letra mayúscula y una letra minúscula puede parecer demasiado apretado cuando se utilizan todas las letras mayúsculas. El texto siguiente muestra el espaciado normal y mayúscula para la fuente Pescadero.  
  
 ![Texto que usa espaciado de mayúsculas OpenType](./media/opentype-font-features/opentype-capital-spacing.gif "Texto que usa espaciado de mayúsculas OpenType")  

 En el ejemplo de marcado siguiente se muestra cómo definir el <xref:System.Windows.Documents.Typography> espaciado de capital para la fuente Pescadero, utilizando las propiedades del objeto.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet18](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet18)]  
  
<a name="ligatures"></a>
## <a name="ligatures"></a>Ligaduras  
 Las ligaduras son dos o más glifos que se unen en un solo glifo para crear texto más legible o atractivo. Las fuentes OpenType admiten cuatro tipos de ligaduras:  
  
- **Ligaduras estándar**. Diseñadas para mejorar la legibilidad. Las ligaduras estándar incluyen "fi", "fl" y "ff".  
  
- **Ligaduras contextuales**. Diseñadas para mejorar la legibilidad al proporcionar un comportamiento de unión mejor entre los caracteres que constituyen la ligadura.  
  
- **Ligaduras discrecionales**. Diseñadas para ser ornamentales y no específicamente para la legibilidad.  
  
- **Ligaduras históricas**. Diseñadas para ser históricas y no específicamente para la legibilidad.  
  
 En el texto siguiente se muestran glifos de ligadura estándar para la fuente Pericles.  
  
 ![Texto que usa ligaduras estándar OpenType](./media/opentype-font-features/opentype-standard-ligatures.gif "Texto que usa ligaduras estándar OpenType")  
  
 En el ejemplo de marcado siguiente se muestra cómo definir glifos de <xref:System.Windows.Documents.Typography> ligadura estándar para la fuente Pericles, utilizando las propiedades del objeto.  
  
 [!code-xaml[OpenTypeFontSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#4)]  
  
 En el texto siguiente se muestran los glifos de ligadura discrecional para la fuente Pericles.  
  
 ![Texto que usa ligaduras discrecionales OpenType](./media/opentype-font-features/opentype-discretionary-ligatures.gif "Texto que usa ligaduras discrecionales OpenType")  
  
 En el siguiente ejemplo de marcado se muestra cómo definir glifos de ligadura discrecional para la fuente Pericles, utilizando las propiedades del <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xaml[OpenTypeFontSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#5)]  
  
 De forma predeterminada, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] las fuentes OpenType en habilitar ligaduras estándar. Por ejemplo, si usa la fuente Palatino Linotype, las ligaduras estándar "fi", "ff" y "fl" aparecen como un glifo de caracteres combinados. Observe que el par de caracteres de cada ligadura estándar se tocan entre sí.  
  
 ![Texto con ligaduras estándar OpenType con Palatino Linotype](./media/opentype-font-features/opentype-standard-ligatures-palatino.gif "Texto con ligaduras estándar OpenType con Palatino Linotype")

 Sin embargo, puede deshabilitar las características de ligadura estándar para que una ligadura estándar, como "ff", se muestre como dos glifos independientes, en lugar de un glifo de caracteres combinados.  
  
 ![Texto que usa ligaduras estándar OpenType deshabilitadas](./media/opentype-font-features/disabled-opentype-standard-ligatures.gif "Texto que usa ligaduras estándar OpenType deshabilitadas")  

 En el ejemplo de marcado siguiente se muestra cómo deshabilitar los glifos de <xref:System.Windows.Documents.Typography> ligadura estándar para la fuente Palatino Linotype, utilizando las propiedades del objeto.  
  
 [!code-xaml[OpenTypeFontSamples#6](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#6)]  
  
<a name="swashes"></a>
## <a name="swashes"></a>Caracteres floreados  
 Los caracteres floreados son glifos decorativos que usan adornos elaborados que suelen asociarse a la caligrafía. El texto siguiente muestra glifos estándar y swash para la fuente Pescadero.  
  
 ![Texto que usa glifos OpenType estándar y floreados](./media/opentype-font-features/opentype-standard-swash-glyphs.gif "Texto que usa glifos OpenType estándar y floreados")  

 Los caracteres floreados se usan a menudo como elementos decorativos en frases cortas, como anuncios de eventos. El texto siguiente utiliza swashes para enfatizar las letras mayúsculas del nombre del evento.  
  
 ![Texto que usa swash OpenType](./media/opentype-font-features/opentype-swashes.gif "Texto que usa swash OpenType")  
  
 En el ejemplo de marcado siguiente se muestra cómo definir <xref:System.Windows.Documents.Typography> swashes para una fuente, utilizando las propiedades del objeto.  
  
 [!code-xaml[OpenTypeFontSamples#7](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#7)]  
  
### <a name="contextual-swashes"></a>Caracteres floreados contextuales  
 Algunas combinaciones de glifos floreados pueden producir un aspecto poco atractivo, como trazos superpuestos descendentes en letras adyacentes. El uso de un swash contextual le permite utilizar un glifo de lavado sustituto que produce una mejor apariencia. El texto siguiente muestra la misma palabra antes y después de aplicar un swash contextual.  
  
 ![Texto que usa un carácter floreado contextual OpenType](./media/opentype-font-features/opentype-contextual-swashes.gif "Texto que usa swash contextual OpenType")  
  
 En el ejemplo de marcado siguiente se muestra cómo definir un swash contextual para la fuente Pescadero, utilizando las propiedades del <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet16](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet16)]  
  
<a name="alternates"></a>
## <a name="alternates"></a>Alternativas  
 Las alternativas son glifos que se pueden sustituir por un glifo estándar. Las fuentes OpenType, como la fuente Pericles utilizada en los ejemplos siguientes, pueden contener glifos alternativos que puede utilizar para crear diferentes apariencias para el texto. En el texto siguiente se muestran glifos estándar para la fuente Pericles.  
  
 ![Texto que usa glifos estándar OpenType](./media/opentype-font-features/opentype-standard-glyphs.gif "Texto que usa glifos estándar OpenType")  

 La fuente Pericles OpenType contiene glifos adicionales que proporcionan alternativas estilísticas al conjunto estándar de pictogramas. En el texto siguiente se muestran glifos alternativos de estilo.  
  
 ![Texto que usa glifos alternativos de estilo OpenType](./media/opentype-font-features/opentype-stylistic-alternate-glyphs.gif "Texto que usa glifos alternativos de estilo OpenType")  
  
 En el siguiente ejemplo de marcado se muestra cómo definir glifos alternativos estilísticos para la fuente Pericles, utilizando las propiedades del <xref:System.Windows.Documents.Typography> objeto.  
  
 [!code-xaml[OpenTypeFontSamples#2](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#2)]  
  
 El texto siguiente muestra varios otros glifos alternativos estilísticos para la fuente Pericles.  
  
 ![Texto con glifos alternativos estilísticos OpenType para la fuente Pericles](./media/opentype-font-features/opentype-stylistic-alternate-glyphs-pericles.gif "Texto con glifos alternativos estilísticos OpenType para la fuente Pericles")

 En el ejemplo de marcación siguiente se muestra cómo se definen estos otros glifos alternativos de estilo.  
  
 [!code-xaml[OpenTypeFontSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#3)]  
  
### <a name="random-contextual-alternates"></a>Alternativas contextuales aleatorias  
 Las alternativas contextuales aleatorias proporcionan varios glifos sustitutos para un único carácter. Cuando se implementa con fuentes de tipo script, esta característica puede simular la escritura a mano mediante el uso de un conjunto de glifos elegidos aleatoriamente con ligeras diferencias de apariencia. El texto siguiente utiliza alternativas contextuales aleatorias para la fuente Lindsey. Observe que la letra "a" varía ligeramente en apariencia  
  
 ![Texto que usa alternativas contextuales aleatorias OpenType](./media/opentype-font-features/opentype-random-contextual-alternates.gif "Texto que usa alternativas contextuales aleatorias OpenType")  
  
 En el siguiente ejemplo de marcado se muestra cómo definir alternativas <xref:System.Windows.Documents.Typography> contextuales aleatorias para la fuente Lindsey, utilizando las propiedades del objeto.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet20](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet20)]  
  
### <a name="historical-forms"></a>Formas históricas  
 Las formas históricas son convenciones tipográficas usadas comúnmente en el pasado. El texto siguiente muestra la frase, "Boston, Massachusetts", utilizando una forma histórica de glifos para la fuente Palatino Linotype.  
  
 ![Texto que usa formas históricas OpenType](./media/opentype-font-features/opentype-historical-forms.gif "Texto que usa formas históricas OpenType")  

 En el ejemplo de marcado siguiente se muestra cómo definir formularios <xref:System.Windows.Documents.Typography> históricos para la fuente Palatino Linotype, utilizando las propiedades del objeto.  
  
 [!code-xaml[OpenTypeFontSamples#8](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#8)]  
  
<a name="numerical_styles"></a>
## <a name="numerical-styles"></a>Estilos numéricos  
 Las fuentes OpenType admiten un gran número de características que se pueden usar con valores numéricos en texto.  
  
### <a name="fractions"></a>Fracciones  
 Las fuentes OpenType admiten estilos para fracciones, incluidas las barras diagonales y apiladas.  
  
 En el texto siguiente se muestran estilos de fracciones para la fuente Palatino Linotype.  
  
 ![Texto que usa fracciones verticales y con barra diagonal OpenType](./media/opentype-font-features/opentype-slashed-stacked-fractions.gif "Texto que usa fracciones verticales y con barra diagonal OpenType")  

 En el ejemplo de marcado siguiente se muestra cómo definir estilos <xref:System.Windows.Documents.Typography> de fracción para la fuente Palatino Linotype, utilizando las propiedades del objeto.  
  
 [!code-xaml[OpenTypeFontSamples#10](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#10)]  
  
### <a name="old-style-numerals"></a>Números de estilo antiguo  
 Las fuentes OpenType admiten un formato numérico de estilo antiguo. Este formato es útil para mostrar números en estilos que ya no son estándar. El texto siguiente muestra una fecha del siglo XVIII en formatos numéricos de estilo estándar y antiguo para la fuente Palatino Linotype.  
  
 ![Texto que usa números de estilo antiguo OpenType](./media/opentype-font-features/opentype-old-style-numerals.gif "Texto que usa números de estilo antiguo OpenType")  

 En el texto siguiente se muestran números estándar para la fuente Palatino Linotype, seguidos de números de estilo antiguo.  
  
 ![Texto que usa conjuntos de números de estilo antiguo OpenType](./media/opentype-font-features/opentype-old-style-numeral-sets.gif "Texto que usa conjuntos de números de estilo antiguo OpenType")  
  
 En el ejemplo de marcado siguiente se muestra cómo definir números de <xref:System.Windows.Documents.Typography> estilo antiguos para la fuente Palatino Linotype, utilizando las propiedades del objeto.  
  
 [!code-xaml[OpenTypeFontSamples#11](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#11)]  
  
### <a name="proportional-and-tabular-figures"></a>Cifras proporcionales y tabulares  
 Las fuentes OpenType admiten una función de figura proporcional y tabular para controlar la alineación de los anchos cuando se utilizan números. Las cifras proporcionales tratan los números como si tuvieran un ancho diferente: "1" es más estrecho que "5". Las cifras tabulares se tratan como números de igual ancho para que se alineen verticalmente, lo que aumenta la legibilidad de la información de tipo financiero.  
  
 El texto siguiente muestra dos figuras proporcionales en la primera columna utilizando la fuente Miramonte. Observe la diferencia de anchura entre los números "5" y "1". La segunda columna muestra los mismos dos valores numéricos con los anchos ajustados mediante la función de figura tabular.  
  
 ![Texto que usa cifras tabulares y proporcionales OpenType](./media/opentype-font-features/opentype-proportional-tabular-figures.gif "Texto que usa cifras tabulares y proporcionales OpenType")  

 En el ejemplo de marcado siguiente se muestra cómo definir figuras <xref:System.Windows.Documents.Typography> proporcionales y tabulares para la fuente Miramonte, utilizando las propiedades del objeto.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet19](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet19)]  
  
### <a name="slashed-zero"></a>Cero con barra diagonal  
 Las fuentes OpenType admiten un formato numérico cero con barra para enfatizar la diferencia entre la letra "O" y el número "0". El número cero con barra diagonal se usa a menudo para identificadores en información financiera y comercial.  
  
 El texto siguiente muestra un identificador de pedido de ejemplo mediante la fuente Miramonte. La primera línea utiliza números estándar. La segunda línea utilizaba números cero cortados para proporcionar un mejor contraste con la letra "O" mayúscula.  
  
 ![Texto que usa números cero con barra diagonal OpenType](./media/opentype-font-features/opentype-slashed-zero-numerals.gif "Texto que usa números cero con barra diagonal OpenType")  

 En el ejemplo de marcado siguiente se muestra cómo definir números cero <xref:System.Windows.Documents.Typography> con barras diagonales para la fuente Miramonte, utilizando las propiedades del objeto.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet15](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet15)]  
  
<a name="typography_class"></a>
## <a name="typography-class"></a>Clase de tipografía  
 El <xref:System.Windows.Documents.Typography> objeto expone el conjunto de características que admite una fuente OpenType. Al establecer las <xref:System.Windows.Documents.Typography> propiedades de en el marcado, puede crear fácilmente documentos que aprovechan las características de OpenType.  
  
 En el texto siguiente se muestran letras en mayúsculas estándar para la fuente Pescadero, seguidas de letras con estilo "SmallCaps" y "AllSmallCaps". En este caso, se utiliza el mismo tamaño de fuente para las tres palabras.  
  
 ![Texto que usa mayúsculas OpenType](./media/opentype-font-features/opentype-capitals.gif "Texto que usa mayúsculas OpenType")  

 En el ejemplo de marcado siguiente se muestra cómo definir mayúsculas para la fuente Pescadero, utilizando las propiedades del <xref:System.Windows.Documents.Typography> objeto. Cuando se usa el formato "SmallCaps", se omite cualquier letra mayúscula inicial.  
  
 [!code-xaml[OpenTypeFontSamples#9](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
 En el ejemplo de código siguiente se realiza la misma tarea que en el ejemplo anterior de marcación.  
  
 [!code-csharp[TypographyCodeSnippets#TypographyCodeSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TypographyCodeSnippets/CSharp/Page1.xaml.cs#typographycodesnippet1)]
 [!code-vb[TypographyCodeSnippets#TypographyCodeSnippet1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TypographyCodeSnippets/visualbasic/page1.xaml.vb#typographycodesnippet1)]  
  
### <a name="typography-class-properties"></a>Propiedades de la clase de tipografía  
 En la tabla siguiente se enumeran las <xref:System.Windows.Documents.Typography> propiedades, los valores y la configuración predeterminada del objeto.  
  
|Propiedad|Valor(s)|Valor predeterminado|  
|--------------|----------------|-------------------|  
|<xref:System.Windows.Documents.Typography.AnnotationAlternates%2A>|Valor numérico: byte|0|  
|<xref:System.Windows.Documents.Typography.Capitals%2A>|<xref:System.Windows.FontCapitals.AllPetiteCaps>&#124; <xref:System.Windows.FontCapitals.AllSmallCaps> <xref:System.Windows.FontCapitals.Normal> &#124; <xref:System.Windows.FontCapitals.PetiteCaps> <xref:System.Windows.FontCapitals.SmallCaps> de <xref:System.Windows.FontCapitals.Titling> &#124; &#124; &#124; &#124; &#124; &#124;<xref:System.Windows.FontCapitals.Unicase>|<xref:System.Windows.FontCapitals.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.CapitalSpacing%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.CaseSensitiveForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.ContextualAlternates%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualSwashes%2A>|Valor numérico: byte|0|  
|<xref:System.Windows.Documents.Typography.DiscretionaryLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianExpertForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianLanguage%2A>|<xref:System.Windows.FontEastAsianLanguage.HojoKanji>&#124; <xref:System.Windows.FontEastAsianLanguage.Jis04> <xref:System.Windows.FontEastAsianLanguage.Jis78> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis83> <xref:System.Windows.FontEastAsianLanguage.Jis90> &#124; <xref:System.Windows.FontEastAsianLanguage.NlcKanji> <xref:System.Windows.FontEastAsianLanguage.Normal> &#124; <xref:System.Windows.FontEastAsianLanguage.Simplified> <xref:System.Windows.FontEastAsianLanguage.Traditional> &#124; &#124; &#124; &#124; &#124; &#124; &#124; &#124; &#124; &#124; &#124; &#124; &#124; &#124; &#124; &#124; &#124; &#124; &#124; &#124; &#124; &#124; &#124; &#124; de &#124; &#124; &#124; &#124; &#124;<xref:System.Windows.FontEastAsianLanguage.TraditionalNames>|<xref:System.Windows.FontEastAsianLanguage.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.EastAsianWidths%2A>|<xref:System.Windows.FontEastAsianWidths.Full>&#124; <xref:System.Windows.FontEastAsianWidths.Half> <xref:System.Windows.FontEastAsianWidths.Normal> &#124; <xref:System.Windows.FontEastAsianWidths.Proportional> <xref:System.Windows.FontEastAsianWidths.Quarter> &#124; &#124; &#124; &#124;<xref:System.Windows.FontEastAsianWidths.Third>|<xref:System.Windows.FontEastAsianWidths.Normal?displayProperty=nameWithType>|  
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
|<xref:System.Windows.Documents.Typography.Variants%2A>|<xref:System.Windows.FontVariants.Inferior>&#124; <xref:System.Windows.FontVariants.Normal> <xref:System.Windows.FontVariants.Ordinal> &#124; <xref:System.Windows.FontVariants.Ruby> <xref:System.Windows.FontVariants.Subscript> &#124; &#124; &#124; &#124;<xref:System.Windows.FontVariants.Superscript>|<xref:System.Windows.FontVariants.Normal?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Documents.Typography>
- [Especificación OpenType](https://docs.microsoft.com/typography/opentype/spec/)
- [Tipografía en WPF](typography-in-wpf.md)
- [Paquete de fuentes OpenType de ejemplo](sample-opentype-font-pack.md)
- [Empaquetar fuentes con aplicaciones](packaging-fonts-with-applications.md)

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
ms.openlocfilehash: 65ecfc4269ff894d45c9b4ee15e349b1a7ddbb73
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094519"
---
# <a name="opentype-font-features"></a>Características de las fuentes OpenType

En este tema se proporciona información general sobre algunas de las características clave de la tecnología de fuentes OpenType en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
<a name="overview"></a>   
## <a name="opentype-font-format"></a>Formato de fuente OpenType  
 El formato de fuente OpenType es una extensión del formato de fuente TrueType®, lo que agrega compatibilidad con los datos de fuentes PostScript. Microsoft y Adobe Corporation desarrollaron conjuntamente el formato de fuente OpenType. Las fuentes OpenType y los servicios del sistema operativo que admiten fuentes OpenType proporcionan a los usuarios una forma sencilla de instalar y usar fuentes, independientemente de si las fuentes contienen contornos TrueType o CFF (PostScript).  
  
 El formato de fuente OpenType aborda los siguientes desafíos para desarrolladores:  
  
- Más compatibilidad con varias plataformas.  
  
- Más compatibilidad con juegos de caracteres internacionales.  
  
- Mejor protección para los datos de fuente.  
  
- Tamaños de archivo más pequeños para hacer más eficaz la distribución de la fuente.  
  
- Más compatibilidad con el control tipográfico avanzado.  
  
> [!NOTE]
> El Windows SDK contiene un conjunto de fuentes OpenType de ejemplo que puede usar con las aplicaciones de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Estas fuentes proporcionan la mayoría de las características ilustradas en el resto de este tema. Para obtener más información, vea [Paquete de fuentes OpenType de ejemplo](sample-opentype-font-pack.md).  
  
Para obtener información detallada sobre el formato de fuente OpenType, vea la [especificación OpenType](https://docs.microsoft.com/typography/opentype/spec/).  
  
### <a name="advanced-typographic-extensions"></a>Extensiones tipográficas avanzadas  
 Las tablas tipográficas avanzadas (tablas de diseño OpenType) amplían la funcionalidad de las fuentes con esquemas TrueType o CFF. Las fuentes de diseño OpenType contienen información adicional que amplía las capacidades de las fuentes para admitir la tipografía internacional de alta calidad. La mayoría de las fuentes OpenType exponen solo un subconjunto de las características de OpenType totales disponibles. Las fuentes OpenType proporcionan las siguientes características.  
  
- Asignación enriquecida entre caracteres y glifos que admiten ligaduras, formas posicionales, alternativas y otras sustituciones de fuentes.  
  
- Compatibilidad con datos adjuntos de glifo y posicionamiento en dos dimensiones.  
  
- Información explícita de script y lenguaje que contiene la fuente, para que una aplicación de procesamiento de textos pueda ajustar su comportamiento en consecuencia.  
  
 Las tablas de diseño OpenType se describen con más detalle en la sección ["tablas de archivos de fuentes"](https://www.microsoft.com/typography/otspec/otff.htm) de la especificación OpenType.  
  
 El resto de esta información general presenta la amplitud y flexibilidad de algunas de las características OpenType visualmente interesantes que se exponen mediante las propiedades del objeto <xref:System.Windows.Documents.Typography>. Para obtener más información sobre este objeto, consulte [Clase de tipografía](#typography_class).  
  
<a name="variants"></a>   
## <a name="variants"></a>Variantes  
 Las variantes se usan para representar varios estilos tipográficos, como superíndices y subíndices.  
  
### <a name="superscripts-and-subscripts"></a>Superíndices y subíndices  
 La propiedad <xref:System.Windows.Documents.Typography.Variants%2A> permite establecer los valores de superíndice y subíndice para una fuente OpenType.  
  
 En el texto siguiente se muestran superíndices para la fuente Palatino Linotype.  
  
 ![Texto que usa superíndices OpenType](./media/opentype-font-features/opentype-superscripts.gif "Texto que usa superíndices OpenType")  
  
 En el ejemplo de marcación siguiente se muestra cómo definir superíndices para la fuente Palatino Linotype mediante las propiedades del objeto <xref:System.Windows.Documents.Typography>.  
  
 [!code-xaml[OpenTypeFontSamples#12](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#12)]  
  
 En el texto siguiente se muestran los subíndices de la fuente Palatino Linotype.  
  
 ![Texto que usa subíndices OpenType](./media/opentype-font-features/opentype-subscripts.gif "Texto que usa subíndices OpenType")  
  
 En el ejemplo de marcación siguiente se muestra cómo definir los subíndices para la fuente Palatino Linotype mediante las propiedades del objeto <xref:System.Windows.Documents.Typography>.  
  
 [!code-xaml[OpenTypeFontSamples#13](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#13)]  
  
### <a name="decorative-uses-of-superscripts-and-subscripts"></a>Usos decorativos de superíndices y subíndices  
 También puede usar superíndices y subíndices para crear efectos decorativos con texto en mayúsculas y minúsculas. En el texto siguiente se muestra texto con superíndices y subíndices para la fuente Palatino Linotype. Tenga en cuenta que las mayúsculas no se ven afectadas.  
  
 ![Texto que usa superíndices y subíndices OpenType](./media/opentype-font-features/opentype-superscripts-subscripts.gif "Texto que usa superíndices y subíndices OpenType")  

 En el ejemplo de marcación siguiente se muestra cómo se definen los superíndices y subíndices de una fuente mediante las propiedades del objeto <xref:System.Windows.Documents.Typography>.  
  
 [!code-xaml[OpenTypeFontSamples#14](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#14)]  
  
<a name="capitals"></a>   
## <a name="capitals"></a>Mayúsculas  
 Las mayúsculas son un conjunto de formatos tipográficos que representan el texto en glifos con estilo de mayúscula. Normalmente, cuando se representa todo un texto en mayúsculas, el espaciado entre las letras puede parecer demasiado estrecho y el espesor y la proporción de las letras, demasiado anchos. OpenType admite varios formatos de estilo para las mayúsculas, incluidas las pequeñas mayúsculas, las mayúsculas mayúsculas pequeñas, los títulos y el espaciado de mayúsculas. Estos formatos de estilo le permiten controlar el aspecto de las mayúsculas.  
  
 En el texto siguiente se muestran letras en mayúsculas estándar para la fuente Pescadero, seguidas de letras con estilo "SmallCaps" y "AllSmallCaps". En este caso, se usa el mismo tamaño de fuente para las tres palabras.  
  
 ![Texto que usa mayúsculas OpenType](./media/opentype-font-features/opentype-capitals.gif "Texto que usa mayúsculas OpenType")  
  
 En el ejemplo de marcación siguiente se muestra cómo se definen las mayúsculas para la fuente pescadero mediante las propiedades del objeto <xref:System.Windows.Documents.Typography>. Cuando se usa el formato "SmallCaps", se omite cualquier letra mayúscula inicial.  
  
 [!code-xaml[OpenTypeFontSamples#9](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
### <a name="titling-capitals"></a>Mayúsculas de título  
 Las mayúsculas de título son más estrechas en espesor y proporción y están diseñadas para dar un aspecto más elegante que las mayúsculas corrientes. Las mayúsculas de título se suelen usar en tamaños de fuente mayores como encabezados. En el texto siguiente se muestran mayúsculas normales y de título para la fuente pescadero. Observe los anchos de tallo más estrechos del texto en la segunda línea.  
  
 ![Texto que usa mayúsculas de título OpenType](./media/opentype-font-features/opentype-titling-capitals.gif "Texto que usa mayúsculas titling OpenType")  
  
 En el ejemplo de marcación siguiente se muestra cómo definir mayúsculas de título para la fuente pescadero mediante las propiedades del objeto <xref:System.Windows.Documents.Typography>.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet17](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet17)]  
  
### <a name="capital-spacing"></a>Espaciado de mayúsculas  
 El espaciado de mayúsculas es una característica que le permite proporcionar más espacio al usar las mayúsculas en un texto. Las letras mayúsculas se diseñan normalmente para combinarlas con letras minúsculas. El espaciado que parece atractivo entre y una letra mayúscula y una minúscula puede parecer demasiado estrecho cuando se utilizan todas las letras mayúsculas. En el texto siguiente se muestra el espaciado normal y de mayúsculas para la fuente pescadero.  
  
 ![Texto que usa espaciado de mayúsculas OpenType](./media/opentype-font-features/opentype-capital-spacing.gif "Texto que usa espaciado de mayúsculas OpenType")  
 
 En el ejemplo de marcación siguiente se muestra cómo definir el espaciado de mayúsculas para la fuente pescadero mediante las propiedades del objeto <xref:System.Windows.Documents.Typography>.  
  
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
  
 En el ejemplo de marcación siguiente se muestra cómo se definen los glifos de ligadura estándar para la fuente Pericles mediante las propiedades del objeto <xref:System.Windows.Documents.Typography>.  
  
 [!code-xaml[OpenTypeFontSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#4)]  
  
 En el texto siguiente se muestran los glifos de ligadura discrecional para la fuente Pericles.  
  
 ![Texto que usa ligaduras discrecionales OpenType](./media/opentype-font-features/opentype-discretionary-ligatures.gif "Texto que usa ligaduras discrecionales OpenType")  
  
 En el ejemplo de marcación siguiente se muestra cómo se definen los glifos de ligadura discrecional para la fuente Pericles mediante las propiedades del objeto <xref:System.Windows.Documents.Typography>.  
  
 [!code-xaml[OpenTypeFontSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#5)]  
  
 De forma predeterminada, las fuentes OpenType en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] habilitar las ligaduras estándar. Por ejemplo, si usa la fuente Palatino Linotype, las ligaduras estándar "fi", "ff" y "fl" aparecen como un glifo de caracteres combinados. Observe que el par de caracteres de cada ligadura estándar se toca entre sí.  
  
 ![Texto que usa ligaduras estándar OpenType con Palatino Linotype](./media/opentype-font-features/opentype-standard-ligatures-palatino.gif "Texto que usa ligaduras estándar OpenType con Palatino Linotype")    
   
 Sin embargo, puede deshabilitar las características de ligadura estándar para que una ligadura estándar, como "ff", se muestre como dos glifos independientes, en lugar de un glifo de caracteres combinados.  
  
 ![Texto que usa ligaduras estándar OpenType deshabilitadas](./media/opentype-font-features/disabled-opentype-standard-ligatures.gif "Texto que usa ligaduras estándar OpenType deshabilitadas")  
    
 En el ejemplo de marcación siguiente se muestra cómo deshabilitar los glifos de ligadura estándar para la fuente Palatino Linotype mediante las propiedades del objeto <xref:System.Windows.Documents.Typography>.  
  
 [!code-xaml[OpenTypeFontSamples#6](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#6)]  
  
<a name="swashes"></a>   
## <a name="swashes"></a>Caracteres floreados  
 Los caracteres floreados son glifos decorativos que usan adornos elaborados que suelen asociarse a la caligrafía. En el texto siguiente se muestran glifos estándar y floreados para la fuente pescadero.  
  
 ![Texto que usa glifos OpenType estándar y floreados](./media/opentype-font-features/opentype-standard-swash-glyphs.gif "Texto que usa glifos OpenType estándar y floreados")  

 Los caracteres floreados se usan a menudo como elementos decorativos en frases cortas, como anuncios de eventos. En el texto siguiente se usan caracteres floreados para resaltar las letras mayúsculas del nombre del evento.  
  
 ![Texto que usa caracteres floreados OpenType](./media/opentype-font-features/opentype-swashes.gif "Texto que usa swash OpenType")  
  
 En el ejemplo de marcación siguiente se muestra cómo se definen los caracteres floreados para una fuente mediante las propiedades del objeto <xref:System.Windows.Documents.Typography>.  
  
 [!code-xaml[OpenTypeFontSamples#7](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#7)]  
  
### <a name="contextual-swashes"></a>Caracteres floreados contextuales  
 Algunas combinaciones de glifos floreados pueden producir un aspecto poco atractivo, como trazos superpuestos descendentes en letras adyacentes. El uso de un floreados contextual le permite utilizar un glifo de sustitutivas de sustitución que produce una apariencia mejor. En el texto siguiente se muestra la misma palabra antes y después de aplicar un floreados contextual.  
  
 ![Texto que usa un carácter floreado contextual OpenType](./media/opentype-font-features/opentype-contextual-swashes.gif "Texto que usa swash contextual OpenType")  
  
 En el ejemplo de marcación siguiente se muestra cómo definir un carácter decorativo contextual para la fuente pescadero mediante las propiedades del objeto <xref:System.Windows.Documents.Typography>.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet16](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet16)]  
  
<a name="alternates"></a>   
## <a name="alternates"></a>Alternativas  
 Las alternativas son glifos que se pueden sustituir por un glifo estándar. Las fuentes OpenType, como la fuente Pericles utilizada en los ejemplos siguientes, pueden contener glifos alternativos que se pueden usar para crear diferentes aspectos del texto. En el texto siguiente se muestran glifos estándar para la fuente Pericles.  
  
 ![Texto que usa glifos estándar OpenType](./media/opentype-font-features/opentype-standard-glyphs.gif "Texto que usa glifos estándar OpenType")  

 La fuente de OpenType Pericles contiene glifos adicionales que proporcionan alternativas estilísticas al conjunto estándar de glifos. En el texto siguiente se muestran glifos alternativos de estilo.  
  
 ![Texto que usa glifos alternativos de estilo OpenType](./media/opentype-font-features/opentype-stylistic-alternate-glyphs.gif "Texto que usa glifos alternativos de estilo OpenType")  
  
 En el ejemplo de marcación siguiente se muestra cómo se definen los glifos alternativos de estilo para la fuente Pericles mediante las propiedades del objeto <xref:System.Windows.Documents.Typography>.  
  
 [!code-xaml[OpenTypeFontSamples#2](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#2)]  
  
 En el texto siguiente se muestran otros glifos alternativos de estilo para la fuente Pericles.  
  
 ![Texto que usa glifos alternativos de estilo OpenType para la fuente Pericles](./media/opentype-font-features/opentype-stylistic-alternate-glyphs-pericles.gif "Texto que usa glifos alternativos de estilo OpenType para la fuente Pericles")

 En el ejemplo de marcación siguiente se muestra cómo se definen estos otros glifos alternativos de estilo.  
  
 [!code-xaml[OpenTypeFontSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#3)]  
  
### <a name="random-contextual-alternates"></a>Alternativas contextuales aleatorias  
 Las alternativas contextuales aleatorias proporcionan varios glifos sustitutos para un único carácter. Cuando se implementa con fuentes de tipo script, esta característica puede simular la escritura a mano mediante un conjunto de glifos elegidos aleatoriamente con ligeras diferencias de apariencia. El siguiente texto usa alternativas contextuales aleatorias para la fuente Lindsey. Tenga en cuenta que la letra "a" varía ligeramente en apariencia  
  
 ![Texto que usa alternativas contextuales aleatorias OpenType](./media/opentype-font-features/opentype-random-contextual-alternates.gif "Texto que usa alternativas contextuales aleatorias OpenType")  
  
 En el ejemplo de marcación siguiente se muestra cómo definir alternativas contextuales aleatorias para la fuente Lindsey mediante las propiedades del objeto <xref:System.Windows.Documents.Typography>.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet20](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet20)]  
  
### <a name="historical-forms"></a>Formas históricas  
 Las formas históricas son convenciones tipográficas usadas comúnmente en el pasado. En el texto siguiente se muestra la frase "Boston, Massachusetts" con una forma histórica de glifos para la fuente Palatino Linotype.  
  
 ![Texto que usa formas históricas OpenType](./media/opentype-font-features/opentype-historical-forms.gif "Texto que usa formas históricas OpenType")  
   
 En el ejemplo de marcación siguiente se muestra cómo definir los formatos históricos de la fuente Palatino Linotype mediante las propiedades del objeto <xref:System.Windows.Documents.Typography>.  
  
 [!code-xaml[OpenTypeFontSamples#8](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#8)]  
  
<a name="numerical_styles"></a>   
## <a name="numerical-styles"></a>Estilos numéricos  
 Las fuentes OpenType admiten un gran número de características que se pueden usar con valores numéricos en texto.  
  
### <a name="fractions"></a>Fracciones  
 Las fuentes OpenType admiten estilos para fracciones, entre las que se incluyen barras diagonales y apiladas.  
  
 En el texto siguiente se muestran estilos de fracciones para la fuente Palatino Linotype.  
  
 ![Texto que usa fracciones verticales y con barra diagonal OpenType](./media/opentype-font-features/opentype-slashed-stacked-fractions.gif "Texto que usa fracciones verticales y con barra diagonal OpenType")  
   
 En el ejemplo de marcación siguiente se muestra cómo se definen los estilos de fracción para la fuente Palatino Linotype mediante las propiedades del objeto <xref:System.Windows.Documents.Typography>.  
  
 [!code-xaml[OpenTypeFontSamples#10](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#10)]  
  
### <a name="old-style-numerals"></a>Números de estilo antiguo  
 Las fuentes OpenType admiten un formato de números de estilo antiguo. Este formato es útil para mostrar números en estilos que ya no son estándar. En el texto siguiente se muestra una fecha del siglo XVIII en formatos de números de estilo estándar y antiguo para la fuente Palatino Linotype.  
  
 ![Texto que usa números de estilo antiguo OpenType](./media/opentype-font-features/opentype-old-style-numerals.gif "Texto que usa números de estilo antiguo OpenType")  
    
 En el texto siguiente se muestran números estándar para la fuente Palatino Linotype, seguidos de números de estilo antiguo.  
  
 ![Texto que usa conjuntos de números de estilo antiguo OpenType](./media/opentype-font-features/opentype-old-style-numeral-sets.gif "Texto que usa conjuntos de números de estilo antiguo OpenType")  
  
 En el ejemplo de marcación siguiente se muestra cómo se definen los números de estilo antiguo para la fuente Palatino Linotype mediante las propiedades del objeto <xref:System.Windows.Documents.Typography>.  
  
 [!code-xaml[OpenTypeFontSamples#11](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#11)]  
  
### <a name="proportional-and-tabular-figures"></a>Cifras proporcionales y tabulares  
 Las fuentes OpenType admiten una característica de figura proporcional y tabular para controlar la alineación de los anchos cuando se utilizan números. Las cifras proporcionales tratan los números como si tuvieran un ancho diferente: "1" es más estrecho que "5". Las figuras tabulares se tratan como números de igual ancho para que se alineen verticalmente, lo que aumenta la legibilidad de la información de tipo financiero.  
  
 En el texto siguiente se muestran dos figuras proporcionales en la primera columna con la fuente Miramonte. Observe la diferencia en el ancho entre los números "5" y "1". La segunda columna muestra los mismos dos valores numéricos con los anchos ajustados mediante la característica de la ilustración tabular.  
  
 ![Texto que usa cifras tabulares y proporcionales OpenType](./media/opentype-font-features/opentype-proportional-tabular-figures.gif "Texto que usa cifras tabulares y proporcionales OpenType")  
    
 En el ejemplo de marcación siguiente se muestra cómo definir figuras proporcionales y tabulares para la fuente Miramonte mediante las propiedades del objeto <xref:System.Windows.Documents.Typography>.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet19](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet19)]  
  
### <a name="slashed-zero"></a>Cero con barra diagonal  
 Las fuentes OpenType admiten un formato de números cero con barra diagonal para resaltar la diferencia entre la letra "O" y el número "0". El número cero con barra diagonal se usa a menudo para identificadores en información financiera y comercial.  
  
 En el texto siguiente se muestra un identificador de orden de ejemplo con la fuente Miramonte. La primera línea usa números estándar. La segunda línea usó números cero con barra diagonal para proporcionar un mejor contraste con la letra "O" mayúscula.  
  
 ![Texto que usa números cero con barra diagonal OpenType](./media/opentype-font-features/opentype-slashed-zero-numerals.gif "Texto que usa números cero con barra diagonal OpenType")  
    
 En el ejemplo de marcación siguiente se muestra cómo se definen números cero con barra diagonal para la fuente Miramonte mediante las propiedades del objeto <xref:System.Windows.Documents.Typography>.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet15](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet15)]  
  
<a name="typography_class"></a>   
## <a name="typography-class"></a>Clase de tipografía  
 El objeto <xref:System.Windows.Documents.Typography> expone el conjunto de características que admite una fuente OpenType. Al establecer las propiedades de <xref:System.Windows.Documents.Typography> en el marcado, puede crear fácilmente documentos que aprovechen las características de OpenType.  
  
 En el texto siguiente se muestran letras en mayúsculas estándar para la fuente Pescadero, seguidas de letras con estilo "SmallCaps" y "AllSmallCaps". En este caso, se usa el mismo tamaño de fuente para las tres palabras.  
  
 ![Texto que usa mayúsculas OpenType](./media/opentype-font-features/opentype-capitals.gif "Texto que usa mayúsculas OpenType")  
    
 En el ejemplo de marcación siguiente se muestra cómo se definen las mayúsculas para la fuente pescadero mediante las propiedades del objeto <xref:System.Windows.Documents.Typography>. Cuando se usa el formato "SmallCaps", se omite cualquier letra mayúscula inicial.  
  
 [!code-xaml[OpenTypeFontSamples#9](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
 En el ejemplo de código siguiente se realiza la misma tarea que en el ejemplo anterior de marcación.  
  
 [!code-csharp[TypographyCodeSnippets#TypographyCodeSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TypographyCodeSnippets/CSharp/Page1.xaml.cs#typographycodesnippet1)]
 [!code-vb[TypographyCodeSnippets#TypographyCodeSnippet1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TypographyCodeSnippets/visualbasic/page1.xaml.vb#typographycodesnippet1)]  
  
### <a name="typography-class-properties"></a>Propiedades de la clase de tipografía  
 En la tabla siguiente se enumeran las propiedades, los valores y la configuración predeterminada del objeto <xref:System.Windows.Documents.Typography>.  
  
|Propiedad|Valores|Valor predeterminado|  
|--------------|----------------|-------------------|  
|<xref:System.Windows.Documents.Typography.AnnotationAlternates%2A>|Valor numérico: byte|0|  
|<xref:System.Windows.Documents.Typography.Capitals%2A>|<xref:System.Windows.FontCapitals.AllPetiteCaps> &#124; <xref:System.Windows.FontCapitals.AllSmallCaps> &#124; <xref:System.Windows.FontCapitals.Normal> &#124; <xref:System.Windows.FontCapitals.PetiteCaps> &#124; <xref:System.Windows.FontCapitals.SmallCaps> &#124; &#124; <xref:System.Windows.FontCapitals.Titling> <xref:System.Windows.FontCapitals.Unicase>|<xref:System.Windows.FontCapitals.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.CapitalSpacing%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.CaseSensitiveForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.ContextualAlternates%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualSwashes%2A>|Valor numérico: byte|0|  
|<xref:System.Windows.Documents.Typography.DiscretionaryLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianExpertForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianLanguage%2A>|<xref:System.Windows.FontEastAsianLanguage.HojoKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis04> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis78> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis83> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis90> &#124; &#124; &#124; <xref:System.Windows.FontEastAsianLanguage.NlcKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Simplified> &#124; <xref:System.Windows.FontEastAsianLanguage.Traditional> <xref:System.Windows.FontEastAsianLanguage.TraditionalNames><xref:System.Windows.FontEastAsianLanguage.Normal>|<xref:System.Windows.FontEastAsianLanguage.Normal?displayProperty=nameWithType>|  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Documents.Typography>
- [Especificación OpenType](https://docs.microsoft.com/typography/opentype/spec/)
- [Tipografía en WPF](typography-in-wpf.md)
- [Paquete de fuentes OpenType de ejemplo](sample-opentype-font-pack.md)
- [Empaquetar fuentes con aplicaciones](packaging-fonts-with-applications.md)

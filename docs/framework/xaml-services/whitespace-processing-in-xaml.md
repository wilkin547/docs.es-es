---
title: Espacio en blanco en XAML de procesamiento
ms.date: 03/30/2017
helpviewer_keywords:
- East Asian characters [XAML Services]
- XAML [XAML Services], white-space processing
- white-space processing in XAML [XAML Services]
- characters [XAML Services], East Asian
ms.assetid: cc9cc377-7544-4fd0-b65b-117b90bb0b23
ms.openlocfilehash: 89f8a4675b3edc23913549bc24f0d9ae16917519
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43870242"
---
# <a name="white-space-processing-in-xaml"></a>Espacio en blanco en XAML de procesamiento
Las reglas de lenguaje de XAML indican que espacio en blanco significativo debe ser procesada por una [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] implementación del procesador. En este tema se documentan estas reglas del lenguaje XAML. También se documenta el control de espacio en blanco adicional definida por el [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] implementación del procesador XAML y el escritor XAML para la serialización.  
  
<a name="whitespace_definition"></a>   
## <a name="white-space-definition"></a>Definición de espacio en blanco  
 Coherente con [!INCLUDE[TLA2#tla_xml](../../../includes/tla2sharptla-xml-md.md)], caracteres de espacio en blanco en [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] son espacio, avance de línea y tabulación. que corresponden a los valores 0020, 000A y 0009 de [!INCLUDE[TLA#tla_unicode](../../../includes/tlasharptla-unicode-md.md)], respectivamente.  
  
<a name="whitespace_normalization"></a>   
## <a name="white-space-normalization"></a>Normalización del espacio en blanco  
 De forma predeterminada la normalización del espacio en blanco siguiente se produce cuando un [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] procesos procesador un [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] archivo:  
  
1.  Se quitan los caracteres de avance de línea entre los caracteres de Asia oriental. Consulte la sección "Caracteres de Asia oriental" más adelante en este tema para obtener una definición de este término.  
  
2.  Todos los caracteres de espacio en blanco (espacio, avance de línea, pestaña) se convierten en espacios.  
  
3.  Todos los espacios consecutivos se eliminan y reemplazan por un espacio.  
  
4.  Se elimina el espacio que sigue inmediatamente a la etiqueta inicial.  
  
5.  Se elimina el espacio situado inmediatamente antes de la etiqueta de cierre.  
  
 El "valor predeterminado" corresponde al estado indicado por el valor predeterminado del atributo [xml:space](../../../docs/framework/xaml-services/xml-space-handling-in-xaml.md) .  
  
<a name="whitespace_in_inner_text_and_string_primitives"></a>   
## <a name="white-space-in-inner-text-and-string-primitives"></a>Espacio en blanco en texto interno y primitivas de cadena  
 Las reglas de normalización anteriores se aplican al texto interno que se encuentra dentro de los elementos XAML. Después de la normalización, un procesador XAML convierte cualquier texto interno en un tipo adecuado, como se indica debajo:  
  
-   Si el tipo de la propiedad no es una colección, pero no es directamente un tipo <xref:System.Object> , el procesador XAML intenta convertirlo a ese tipo con su convertidor de tipos. Una conversión incorrecta aquí producirá un error en tiempo de compilación.  
  
-   Si el tipo de la propiedad es una colección y el texto interno es contiguo (sin etiquetas de elementos intermedias), el texto interno se analiza como una sola <xref:System.String>. Si el tipo de colección no puede aceptar <xref:System.String>, esto también provoca un error en tiempo de compilación.  
  
-   Si el tipo de la propiedad es <xref:System.Object>, el texto interno se analiza como una sola <xref:System.String>. Si hay etiquetas de elemento intermedias, se produce un error en tiempo de compilación porque el tipo <xref:System.Object> implica que hay un objeto único (de tipo<xref:System.String> u otro).  
  
-   Si el tipo de la propiedad es una colección y el texto interno no es contiguo, la primera subcadena se convierte en <xref:System.String> y se agrega como un elemento de colección, el elemento intermedio se agrega como un elemento de colección y, por último, la subcadena final (si la hay) se agrega a la colección como un tercer elemento de tipo <xref:System.String> .  
  
<a name="preserving_whitespace"></a>   
## <a name="preserving-white-space"></a>Conservar espacio en blanco  
 Existen varias técnicas para conservar espacio en blanco en el origen de [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] para la presentación, que no se ven afectados por [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] normalización de espacio en blanco del procesador.  
  
 **XML: space = "preserve"**: especifique este atributo en el nivel del elemento donde desee conservar el espacio en blanco. De esta manera, se conserva todo los espacios en blanco, incluidos los espacios que las aplicaciones de edición de código puedan agregar a los elementos de alineación de "impresión con sangría" como anidamiento visualmente intuitivo. Pero es el modelo de contenido del elemento contenedor el que determina si esos espacios se presentan. Evite la especificación de `xml:space="preserve"` en el nivel raíz porque la mayoría de los modelos de objetos no considera el blancos espacio como significativo independientemente de cómo establecer el atributo. La configuración global de `xml:space` puede tener consecuencias en el rendimiento del procesamiento XAML (en especial la serialización) en algunas implementaciones. Es mejor establecer sólo el atributo específicamente en el nivel de elementos que representan el espacio en blanco dentro de las cadenas, o son colecciones de espacio en blanco significativo.  
  
 **Entidades y espacios de no separación**: [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] permite colocar cualquier entidad [!INCLUDE[TLA#tla_unicode](../../../includes/tlasharptla-unicode-md.md)] dentro de un modelo de objetos de texto. Puede usar entidades dedicadas, como espacio de no separación (&\#160; en codificación UTF-8). También puede usar controles de texto enriquecido que sean compatibles con caracteres de espacio de no separación. Debe tener cuidado si usa entidades para simular características de diseño tales como la sangría porque la generación de las entidades en tiempo de ejecución dependerá de muchos más factores que los que afectan a la capacidad para aplicar una sangría en un sistema de diseño típico, como el uso correcto de los paneles y los márgenes. Por ejemplo, las entidades se asignan a las fuentes y pueden cambiar el tamaño en respuesta a la selección de fuente del usuario.  
  
<a name="east_asian_characters"></a>   
## <a name="east-asian-characters"></a>Caracteres de Asia oriental  
 Los "caracteres de Asia Oriental" se definen como un conjunto de intervalos de caracteres de [!INCLUDE[TLA2#tla_unicode](../../../includes/tla2sharptla-unicode-md.md)] : de U+20000 a U+2FFFD y de U+30000 a U+3FFFD. En ocasiones, este subconjunto también se denomina "ideogramas CJK". Para obtener más información, vea [http://www.unicode.org](http://www.unicode.org/).  
  
<a name="whitespace_and_text_content_models"></a>   
## <a name="white-space-and-text-content-models"></a>Modelos de contenido de texto y de espacio en blanco  
 En la práctica, conserva los espacios en blanco es solo de preocupación para un subconjunto de todos los posibles modelos de contenido. Ese subconjunto está compuesto por modelos de contenido que pueden aceptar alguna forma del tipo <xref:System.String> singleton, una colección de <xref:System.String> dedicada o una mezcla de <xref:System.String> y otros tipos en una colección de <xref:System.Collections.IList> o <xref:System.Collections.Generic.ICollection%601> .  
  
### <a name="white-space-and-text-content-models-in-wpf"></a>Modelos de contenido de texto y de espacio en blanco en WPF  
 Para que sirva de ejemplo, en el resto de esta sección se hace referencia a tipos concretos definidos por WPF. Las características de control de espacio en blanco que se describen en este tema son generalmente guardan relación con los servicios XAML de .NET Framework y WPF. Para ver este comportamiento en acción, puede experimentar con el marcado XAML de WPF, ver los resultados en un gráfico de objeto y, después, serializar el marcado de nuevo.  
  
 Incluso para los modelos de contenido que pueden aceptar cadenas, el comportamiento predeterminado dentro de estos modelos de contenido es que los espacios en blanco que queda no es tratar como significativo. Por ejemplo, <xref:System.Windows.Controls.ListBox> toma un <xref:System.Collections.IList>, pero el espacio en blanco (como saltos de línea entre cada <xref:System.Windows.Controls.ListBoxItem>) no se conserva ni no representan. Si intenta usar avances de línea como separadores entre las cadenas de elementos de <xref:System.Windows.Controls.ListBoxItem> , no funcionará en absoluto; las cadenas que están separadas por los avances de línea se tratan como una cadena y un elemento.  
  
 Esas colecciones que tratan los espacios en blanco como significativos normalmente forman parte del modelo de documentos dinámicos. La colección principal que admite el comportamiento de conservación de espacio en blanco es <xref:System.Windows.Documents.InlineCollection>. Esta clase de colección se declara con el <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>; cuando se encuentra este atributo, el [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] procesador trata el espacio en blanco dentro de la colección como significativo. La combinación de `xml:space="preserve"` y espacio en blanco dentro de un <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> colección indicada que todo el espacio en blanco se conservan y se presentan. La combinación de `xml:space="default"` y espacio en blanco dentro de un <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> produce la normalización del espacio en blanco inicial descrita anteriormente, que deja un espacio en ciertas posiciones y esos espacios se conservan y se presentan. El comportamiento deseable depende del usuario, por lo que debe usar `xml:space` para habilitar el comportamiento que quiera.  
  
 Además, algunos elementos insertados que incluyen un avance en un modelo de documentos dinámicos no deben introducir deliberadamente un espacio adicional, incluso en una colección con espacio en blanco significativo. Por ejemplo, el <xref:System.Windows.Documents.LineBreak> elemento tiene el mismo propósito que la \<BR / > etiqueta en [!INCLUDE[TLA2#tla_html](../../../includes/tla2sharptla-html-md.md)]y para mejorar la legibilidad en el marcado, normalmente un <xref:System.Windows.Documents.LineBreak> está separado del texto posterior mediante un avance de línea creado. Ese avance de línea no se debe normalizar para convertirlo en un espacio inicial en la línea posterior. Para habilitar ese comportamiento, la definición de clase el <xref:System.Windows.Documents.LineBreak> elemento se aplica el <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>, lo que, a continuación, se interpreta por el [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] procesador ese espacio en blanco que rodea a <xref:System.Windows.Documents.LineBreak> siempre se recorta.  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Entidades de caracteres XML y XAML](../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)  
 [XML: space en XAML de control](../../../docs/framework/xaml-services/xml-space-handling-in-xaml.md)

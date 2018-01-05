---
title: Procesamiento de espacios en blanco en XAML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- East Asian characters [XAML Services]
- XAML [XAML Services], whitespace processing
- whitespace processing in XAML [XAML Services]
- characters [XAML Services], East Asian
ms.assetid: cc9cc377-7544-4fd0-b65b-117b90bb0b23
caps.latest.revision: "20"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c382be7dabca90ef201fa24cfb79472955347eef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="whitespace-processing-in-xaml"></a>Procesamiento de espacios en blanco en XAML
Las reglas de lenguaje de XAML indican que los espacios en blanco significativos debe ser procesados por una implementación de procesador [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] . En este tema se documentan estas reglas del lenguaje XAML. También se documenta el control adicional del espacio en blanco que está definido por la implementación de [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] del procesador XAML y el sistema de escritura XAML para la serialización.  
  
<a name="whitespace_definition"></a>   
## <a name="whitespace-definition"></a>Definición del espacio en blanco  
 De modo coherente con [!INCLUDE[TLA2#tla_xml](../../../includes/tla2sharptla-xml-md.md)], los caracteres de espacio en blanco de [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] son el espacio, el avance de línea y la tabulación, que corresponden a los valores 0020, 000A y 0009 de [!INCLUDE[TLA#tla_unicode](../../../includes/tlasharptla-unicode-md.md)], respectivamente.  
  
<a name="whitespace_normalization"></a>   
## <a name="whitespace-normalization"></a>Normalización del espacio en blanco  
 De manera predeterminada, la normalización del espacio en blanco siguiente se produce cuando un procesador [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] procesa un archivo [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] :  
  
1.  Se quitan los caracteres de avance de línea entre los caracteres de Asia oriental. Consulte la sección "Caracteres de Asia oriental" más adelante en este tema para obtener una definición de este término.  
  
2.  Todos los caracteres de espacio en blanco (espacio, avance de línea, tabulación) se convierten en espacios.  
  
3.  Todos los espacios consecutivos se eliminan y reemplazan por un espacio.  
  
4.  Se elimina el espacio que sigue inmediatamente a la etiqueta inicial.  
  
5.  Se elimina el espacio situado inmediatamente antes de la etiqueta de cierre.  
  
 El "valor predeterminado" corresponde al estado indicado por el valor predeterminado del atributo [xml:space](../../../docs/framework/xaml-services/xml-space-handling-in-xaml.md) .  
  
<a name="whitespace_in_inner_text_and_string_primitives"></a>   
## <a name="whitespace-in-inner-text-and-string-primitives"></a>Espacio en blanco en texto interno y primitivas de cadena  
 Las reglas de normalización anteriores se aplican al texto interno que se encuentra dentro de los elementos XAML. Después de la normalización, un procesador XAML convierte cualquier texto interno en un tipo adecuado, como se indica debajo:  
  
-   Si el tipo de la propiedad no es una colección, pero no es directamente un tipo <xref:System.Object> , el procesador XAML intenta convertirlo a ese tipo con su convertidor de tipos. Una conversión incorrecta aquí producirá un error en tiempo de compilación.  
  
-   Si el tipo de la propiedad es una colección y el texto interno es contiguo (sin etiquetas de elementos intermedias), el texto interno se analiza como una sola <xref:System.String>. Si el tipo de colección no puede aceptar <xref:System.String>, esto también provoca un error en tiempo de compilación.  
  
-   Si el tipo de la propiedad es <xref:System.Object>, el texto interno se analiza como una sola <xref:System.String>. Si hay etiquetas de elemento intermedias, se produce un error en tiempo de compilación porque el tipo <xref:System.Object> implica que hay un objeto único (de tipo<xref:System.String> u otro).  
  
-   Si el tipo de la propiedad es una colección y el texto interno no es contiguo, la primera subcadena se convierte en <xref:System.String> y se agrega como un elemento de colección, el elemento intermedio se agrega como un elemento de colección y, por último, la subcadena final (si la hay) se agrega a la colección como un tercer elemento de tipo <xref:System.String> .  
  
<a name="preserving_whitespace"></a>   
## <a name="preserving-whitespace"></a>Conservar el espacio en blanco  
 Hay varias técnicas para conservar el espacio en blanco para la presentación final en el [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] de origen a las que no afecta la normalización del espacio en blanco del procesador [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] .  
  
 **XML: space = "preserve"**: especifique este atributo en el nivel del elemento donde desee conservar el espacio en blanco. De esta manera, se conserva todo los espacios en blanco, incluidos los espacios que las aplicaciones de edición de código puedan agregar a los elementos de alineación de "impresión con sangría" como anidamiento visualmente intuitivo. Pero es el modelo de contenido del elemento contenedor el que determina si esos espacios se presentan. Procure no especificar `xml:space="preserve"` en el nivel raíz, porque la mayoría de los modelos de objetos no considera el espacio en blanco como significativo independientemente de cómo se establezca el atributo La configuración global de `xml:space` puede tener consecuencias en el rendimiento del procesamiento XAML (en especial la serialización) en algunas implementaciones. Se recomienda limitarse a establecer el atributo específicamente en el nivel de los elementos que presentan el espacio en blanco contenido en las cadenas o que son colecciones con espacio en blanco significativo.  
  
 **Entidades y espacios de no separación**: [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] permite colocar cualquier entidad [!INCLUDE[TLA#tla_unicode](../../../includes/tlasharptla-unicode-md.md)] dentro de un modelo de objetos de texto. Puede usar entidades dedicadas, como espacio de no separación (&\#160; en la codificación UTF-8). También puede usar controles de texto enriquecido que sean compatibles con caracteres de espacio de no separación. Debe tener cuidado si usa entidades para simular características de diseño tales como la sangría porque la generación de las entidades en tiempo de ejecución dependerá de muchos más factores que los que afectan a la capacidad para aplicar una sangría en un sistema de diseño típico, como el uso correcto de los paneles y los márgenes. Por ejemplo, las entidades se asignan a las fuentes y pueden cambiar el tamaño en respuesta a la selección de fuente del usuario.  
  
<a name="east_asian_characters"></a>   
## <a name="east-asian-characters"></a>Caracteres de Asia oriental  
 Los "caracteres de Asia Oriental" se definen como un conjunto de intervalos de caracteres de [!INCLUDE[TLA2#tla_unicode](../../../includes/tla2sharptla-unicode-md.md)] : de U+20000 a U+2FFFD y de U+30000 a U+3FFFD. En ocasiones, este subconjunto también se denomina "ideogramas CJK". Para más información, vea [http://www.unicode.org](http://www.unicode.org/).  
  
<a name="whitespace_and_text_content_models"></a>   
## <a name="whitespace-and-text-content-models"></a>Modelos de contenido de texto y de espacio en blanco  
 A efectos prácticos, conservar el espacio en blanco solo afecta a un subconjunto de todos los posibles modelos de contenido. Ese subconjunto está compuesto por modelos de contenido que pueden aceptar alguna forma del tipo <xref:System.String> singleton, una colección de <xref:System.String> dedicada o una mezcla de <xref:System.String> y otros tipos en una colección de <xref:System.Collections.IList> o <xref:System.Collections.Generic.ICollection%601> .  
  
### <a name="whitespace-and-text-content-models-in-wpf"></a>Modelos de contenido de texto y de espacio en blanco en WPF  
 Para que sirva de ejemplo, en el resto de esta sección se hace referencia a tipos concretos definidos por WPF. Las características de control de espacios en blanco que se describen en este tema generalmente guardan relación con los servicios XAML de .NET Framework y WPF. Para ver este comportamiento en acción, puede experimentar con el marcado XAML de WPF, ver los resultados en un gráfico de objeto y, después, serializar el marcado de nuevo.  
  
 Incluso para los modelos de contenido que pueden aceptar cadenas, el comportamiento predeterminado dentro de estos modelos de contenido consiste en no tratar como significativo el espacio en blanco restante. Por ejemplo, <xref:System.Windows.Controls.ListBox> toma <xref:System.Collections.IList>, pero el espacio en blanco (como por ejemplo los avances de línea entre cada <xref:System.Windows.Controls.ListBoxItem>) no se conserva ni se presenta. Si intenta usar avances de línea como separadores entre las cadenas de elementos de <xref:System.Windows.Controls.ListBoxItem> , no funcionará en absoluto; las cadenas que están separadas por los avances de línea se tratan como una cadena y un elemento.  
  
 Esas colecciones que tratan los espacios en blanco como significativos normalmente forman parte del modelo de documentos dinámicos. La colección principal que es compatible con el comportamiento de conservación de espacio en blanco es <xref:System.Windows.Documents.InlineCollection>. Esta clase de colección se declara con <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>; cuando se encuentra este atributo, el procesador [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] trata el espacio en blanco de la colección como significativo. La combinación de `xml:space="preserve"` y de espacio en blanco dentro de una colección indicada con <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> da lugar a que todo el espacio en blanco se conserve y se presente. La combinación de `xml:space="default"` y de espacio en blanco dentro de <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> produce la normalización del espacio en blanco inicial descrita anteriormente, que deja un espacio en ciertas posiciones, y esos espacios se conservan y se presentan. El comportamiento deseable depende del usuario, por lo que debe usar `xml:space` para habilitar el comportamiento que quiera.  
  
 Asimismo, algunos elementos en línea que incluyen un avance de línea en un modelo de documentos dinámicos no deben introducir deliberadamente un espacio adicional ni siquiera en una colección con espacio en blanco significativo. Por ejemplo, el <xref:System.Windows.Documents.LineBreak> elemento tiene el mismo propósito que la \<BR / > etiqueta en [!INCLUDE[TLA2#tla_html](../../../includes/tla2sharptla-html-md.md)]y para mejorar la legibilidad del marcado, normalmente un <xref:System.Windows.Documents.LineBreak> suele separarse del texto posterior con un avance de línea creado. Ese avance de línea no se debe normalizar para convertirlo en un espacio inicial en la línea posterior. Para habilitar ese comportamiento, la definición de clase del elemento <xref:System.Windows.Documents.LineBreak> aplica <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>, que el procesador [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] interpreta como una indicación de que siempre se recorta el espacio en blanco que rodea a <xref:System.Windows.Documents.LineBreak> .  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Entidades de caracteres XML y XAML](../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)  
 [Control de xml:space en XAML](../../../docs/framework/xaml-services/xml-space-handling-in-xaml.md)

---
title: Procesamiento de espacios en blanco en XAML
ms.date: 03/30/2017
helpviewer_keywords:
- East Asian characters [XAML Services]
- XAML [XAML Services], white-space processing
- white-space processing in XAML [XAML Services]
- characters [XAML Services], East Asian
ms.assetid: cc9cc377-7544-4fd0-b65b-117b90bb0b23
ms.openlocfilehash: 930e8a0013dd601aaafcd81340b3b9b8b69f8fdd
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458501"
---
# <a name="white-space-processing-in-xaml"></a>Procesamiento de espacios en blanco en XAML
Las reglas de lenguaje para el estado XAML que un espacio en blanco significativo debe ser procesado por una implementación de procesador [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]. En este tema se documentan estas reglas del lenguaje XAML. También documenta el control de espacios en blanco adicional definido por la implementación de [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] del procesador XAML y del escritor XAML para la serialización.  
  
<a name="whitespace_definition"></a>   
## <a name="white-space-definition"></a>Definición de espacio en blanco  
 Coherente con [!INCLUDE[TLA2#tla_xml](../../../includes/tla2sharptla-xml-md.md)], los caracteres de espacio en blanco en [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] son el espacio, el avance de barra y la tabulación. Se corresponden con los valores Unicode 0020, 000A y 0009, respectivamente.  
  
<a name="whitespace_normalization"></a>   
## <a name="white-space-normalization"></a>Normalización de espacio en blanco  
 De forma predeterminada, la normalización de espacio en blanco siguiente se produce cuando un procesador [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] procesa un archivo [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]:  
  
1. Se quitan los caracteres de avance de línea entre los caracteres de Asia oriental. Consulte la sección "Caracteres de Asia oriental" más adelante en este tema para obtener una definición de este término.  
  
2. Todos los caracteres de espacio en blanco (espacio, avance de barra de bits, tabulación) se convierten en espacios.  
  
3. Todos los espacios consecutivos se eliminan y reemplazan por un espacio.  
  
4. Se elimina el espacio que sigue inmediatamente a la etiqueta inicial.  
  
5. Se elimina el espacio situado inmediatamente antes de la etiqueta de cierre.  
  
 El "valor predeterminado" corresponde al estado indicado por el valor predeterminado del atributo [xml:space](xml-space-handling-in-xaml.md) .  
  
<a name="whitespace_in_inner_text_and_string_primitives"></a>   
## <a name="white-space-in-inner-text-and-string-primitives"></a>Espacio en blanco en texto interno y primitivas de cadena  
 Las reglas de normalización anteriores se aplican al texto interno que se encuentra dentro de los elementos XAML. Después de la normalización, un procesador XAML convierte cualquier texto interno en un tipo adecuado, como se indica debajo:  
  
- Si el tipo de la propiedad no es una colección, pero no es directamente un tipo <xref:System.Object> , el procesador XAML intenta convertirlo a ese tipo con su convertidor de tipos. Una conversión incorrecta aquí producirá un error en tiempo de compilación.  
  
- Si el tipo de la propiedad es una colección y el texto interno es contiguo (sin etiquetas de elementos intermedias), el texto interno se analiza como una sola <xref:System.String>. Si el tipo de colección no puede aceptar <xref:System.String>, esto también provoca un error en tiempo de compilación.  
  
- Si el tipo de la propiedad es <xref:System.Object>, el texto interno se analiza como una sola <xref:System.String>. Si hay etiquetas de elemento intermedias, se produce un error en tiempo de compilación porque el tipo <xref:System.Object> implica que hay un objeto único (de tipo<xref:System.String> u otro).  
  
- Si el tipo de la propiedad es una colección y el texto interno no es contiguo, la primera subcadena se convierte en <xref:System.String> y se agrega como un elemento de colección, el elemento intermedio se agrega como un elemento de colección y, por último, la subcadena final (si la hay) se agrega a la colección como un tercer elemento de tipo <xref:System.String> .  
  
<a name="preserving_whitespace"></a>   
## <a name="preserving-white-space"></a>Conservar espacios en blanco  
 Hay varias técnicas para conservar el espacio en blanco en el [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] de origen para la presentación eventual que no se ven afectadas por la normalización de espacio en blanco del procesador de [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)].  
  
 **xml: Space = "preserve"** : especifique este atributo en el nivel del elemento donde desee conservar el espacio en blanco. De esta manera, se conserva todo los espacios en blanco, incluidos los espacios que las aplicaciones de edición de código puedan agregar a los elementos de alineación de "impresión con sangría" como anidamiento visualmente intuitivo. Pero es el modelo de contenido del elemento contenedor el que determina si esos espacios se presentan. Evite especificar `xml:space="preserve"` en el nivel raíz, ya que la mayoría de los modelos de objetos no consideran el espacio en blanco como significativo independientemente de cómo establezca el atributo. La configuración global de `xml:space` puede tener consecuencias en el rendimiento del procesamiento XAML (en especial la serialización) en algunas implementaciones. Es aconsejable establecer solo el atributo específicamente en el nivel de elementos que representan el espacio en blanco dentro de las cadenas o que son colecciones significativas de espacio en blanco.  
  
 **Entidades y espacios de no separación**: [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] admite la colocación de cualquier entidad Unicode dentro de un modelo de objetos de texto. Puede usar entidades dedicadas, como el espacio de no separación (& \#160; en la codificación UTF-8). También puede usar controles de texto enriquecido que sean compatibles con caracteres de espacio de no separación. Debe tener cuidado si usa entidades para simular características de diseño tales como la sangría porque la generación de las entidades en tiempo de ejecución dependerá de muchos más factores que los que afectan a la capacidad para aplicar una sangría en un sistema de diseño típico, como el uso correcto de los paneles y los márgenes. Por ejemplo, las entidades se asignan a las fuentes y pueden cambiar el tamaño en respuesta a la selección de fuente del usuario.  
  
<a name="east_asian_characters"></a>   
## <a name="east-asian-characters"></a>Caracteres de Asia oriental  
 Los "caracteres de Asia oriental" se definen como un conjunto de intervalos de caracteres Unicode de U + 20000 a U + 2FFFD y de U + 30000 a U + 3FFFD. En ocasiones, este subconjunto también se denomina "ideogramas CJK". Para obtener más información, vea <https://www.unicode.org>.  
  
<a name="whitespace_and_text_content_models"></a>   
## <a name="white-space-and-text-content-models"></a>Modelos de contenido de texto y de espacio en blanco  
 En la práctica, conservar el espacio en blanco solo afecta a un subconjunto de todos los modelos de contenido posibles. Ese subconjunto está compuesto por modelos de contenido que pueden aceptar alguna forma del tipo <xref:System.String> singleton, una colección de <xref:System.String> dedicada o una mezcla de <xref:System.String> y otros tipos en una colección de <xref:System.Collections.IList> o <xref:System.Collections.Generic.ICollection%601> .  
  
### <a name="white-space-and-text-content-models-in-wpf"></a>Modelos de contenido de texto y espacios en blanco en WPF  
 Para que sirva de ejemplo, en el resto de esta sección se hace referencia a tipos concretos definidos por WPF. Las características de control de espacios en blanco que se describen en este tema suelen ser pertinentes para .NET Framework servicios XAML y WPF. Para ver este comportamiento en acción, puede experimentar con el marcado XAML de WPF, ver los resultados en un gráfico de objeto y, después, serializar el marcado de nuevo.  
  
 Incluso en el caso de los modelos de contenido que pueden tomar cadenas, el comportamiento predeterminado dentro de estos modelos de contenido es que cualquier espacio en blanco que quede no se trata como significativo. Por ejemplo, <xref:System.Windows.Controls.ListBox> toma <xref:System.Collections.IList>, pero el espacio en blanco (como los saltos de barra entre <xref:System.Windows.Controls.ListBoxItem>) no se conserva y no se representa. Si intenta usar avances de línea como separadores entre las cadenas de elementos de <xref:System.Windows.Controls.ListBoxItem> , no funcionará en absoluto; las cadenas que están separadas por los avances de línea se tratan como una cadena y un elemento.  
  
 Las colecciones que tratan los espacios en blanco como significativos normalmente forman parte del modelo de documentos dinámicos. La colección principal que admite el comportamiento de conservación de espacio en blanco es <xref:System.Windows.Documents.InlineCollection>. Esta clase de colección se declara con el <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>; Cuando se encuentra este atributo, el procesador de [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] tratará el espacio en blanco dentro de la colección como significativo. La combinación de `xml:space="preserve"` y el espacio en blanco dentro de una colección detenida <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> es que todos los espacios en blanco se conservan y se representan. La combinación de `xml:space="default"` y el espacio en blanco dentro de un <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> provoca la normalización del espacio en blanco inicial descrita anteriormente, que deja un espacio en ciertas posiciones, y esos espacios se conservan y representan. El comportamiento deseable depende del usuario, por lo que debe usar `xml:space` para habilitar el comportamiento que quiera.  
  
 Además, algunos elementos insertados que indican un LineBreak en un modelo de documento dinámico no deben introducir deliberadamente un espacio adicional ni siquiera en una colección de espacio en blanco significativa. Por ejemplo, el elemento <xref:System.Windows.Documents.LineBreak> tiene el mismo propósito que la etiqueta \<BR/> en HTML y para mejorar la legibilidad en el marcado, normalmente un <xref:System.Windows.Documents.LineBreak> se separa de cualquier texto subsiguiente mediante un avance de carro creado. Ese avance de línea no se debe normalizar para convertirlo en un espacio inicial en la línea posterior. Para habilitar ese comportamiento, la definición de clase para el elemento <xref:System.Windows.Documents.LineBreak> aplica el <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>, que el procesador de [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] interpreta para indicar que el espacio en blanco que rodea a <xref:System.Windows.Documents.LineBreak> siempre se recorta.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md)
- [Entidades de caracteres XML y XAML](xml-character-entities-and-xaml.md)
- [control de XML: Space en XAML](xml-space-handling-in-xaml.md)

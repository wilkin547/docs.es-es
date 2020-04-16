---
title: Procesamiento de espacios en blanco en XAML
ms.date: 03/30/2017
helpviewer_keywords:
- East Asian characters [XAML Services]
- XAML [XAML Services], white-space processing
- white-space processing in XAML [XAML Services]
- characters [XAML Services], East Asian
ms.assetid: cc9cc377-7544-4fd0-b65b-117b90bb0b23
ms.openlocfilehash: 05f28c9115326424164b92e1b704c52bba31cf35
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432849"
---
# <a name="white-space-processing-in-xaml"></a>Procesamiento de espacios en blanco en XAML

Las reglas de lenguaje para XAML establecen [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] que una implementación de procesador debe procesar un espacio en blanco significativo. En este artículo se documentan estas reglas de lenguaje XAML. También documenta el control de espacio [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] en blanco adicional definido por la implementación del procesador XAML y el escritor XAML para la serialización.

## <a name="white-space-definition"></a>Definición de espacio en blanco

Coherentes con XML, los [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] caracteres de espacio en blanco en son espacio, salto de línea y tabulación. Estos corresponden a los valores Unicode 0020, 000A y 0009 respectivamente.

## <a name="white-space-normalization"></a>Normalización de espacios en blanco

De forma predeterminada, la siguiente normalización de espacios en blanco se produce cuando un [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] procesador procesa un [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] archivo:

1. Se quitan los caracteres de avance de línea entre los caracteres de Este de Asia. Consulte la sección "Caracteres de Asia oriental" más adelante en este tema para obtener una definición de este término.

2. Todos los caracteres de espacio en blanco (espacio, salto de línea, tabulación) se convierten en espacios.

3. Todos los espacios consecutivos se eliminan y reemplazan por un espacio.

4. Se elimina el espacio que sigue inmediatamente a la etiqueta inicial.

5. Se elimina el espacio situado inmediatamente antes de la etiqueta de cierre.

El "valor predeterminado" corresponde al estado indicado por el valor predeterminado del atributo [xml:space](xml-space-handling.md) .

## <a name="white-space-in-inner-text-and-string-primitives"></a>Espacio en blanco en texto interno y primitivas de cadena

Las reglas de normalización anteriores se aplican al texto interno que se encuentra dentro de los elementos XAML. Después de la normalización, un procesador XAML convierte cualquier texto interno en un tipo adecuado, como se indica debajo:

- Si el tipo de la propiedad no es una colección, pero no es directamente un tipo <xref:System.Object> , el procesador XAML intenta convertirlo a ese tipo con su convertidor de tipos. Una conversión incorrecta aquí producirá un error en tiempo de compilación.

- Si el tipo de la propiedad es una colección y el texto interno es contiguo (sin etiquetas de elementos intermedias), el texto interno se analiza como una sola <xref:System.String>. Si el tipo de colección no puede aceptar <xref:System.String>, esto también provoca un error en tiempo de compilación.

- Si el tipo de la propiedad es <xref:System.Object>, el texto interno se analiza como una sola <xref:System.String>. Si hay etiquetas de elemento intermedias, se produce un error en tiempo de compilación porque el tipo <xref:System.Object> implica que hay un objeto único (de tipo<xref:System.String> u otro).

- Si el tipo de la propiedad es una colección y el texto interno no es contiguo, la primera subcadena se convierte en <xref:System.String> y se agrega como un elemento de colección, el elemento intermedio se agrega como un elemento de colección y, por último, la subcadena final (si la hay) se agrega a la colección como un tercer elemento de tipo <xref:System.String> .

## <a name="preserving-white-space"></a>Preservar el espacio en blanco

Existen varias técnicas para conservar el [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] espacio en blanco en [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] el origen para la presentación final que no se ven afectadas por la normalización del espacio en blanco del procesador.

**xml:space-"preserve"**: especifique este atributo en el nivel del elemento donde se desea la conservación del espacio en blanco. De esta manera, se conserva todo los espacios en blanco, incluidos los espacios que las aplicaciones de edición de código puedan agregar a los elementos de alineación de "impresión con sangría" como anidamiento visualmente intuitivo. Pero es el modelo de contenido del elemento contenedor el que determina si esos espacios se presentan. Evite especificar `xml:space="preserve"` en el nivel raíz porque la mayoría de los modelos de objetos no consideran el espacio en blanco como significativo independientemente de cómo establezca el atributo. La configuración global de `xml:space` puede tener consecuencias en el rendimiento del procesamiento XAML (en especial la serialización) en algunas implementaciones. Es una mejor práctica establecer solo el atributo específicamente en el nivel de elementos que representan espacios en blanco dentro de cadenas o son colecciones significativas de espacio en blanco.

**Entidades y espacios sin separación:** [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] admite la colocación de cualquier entidad Unicode dentro de un modelo de objetos de texto. Puede utilizar entidades dedicadas como el \#espacio de no separación (&160; en la codificación UTF-8). También puede usar controles de texto enriquecido que sean compatibles con caracteres de espacio de no separación. Debe tener cuidado si usa entidades para simular características de diseño tales como la sangría porque la generación de las entidades en tiempo de ejecución dependerá de muchos más factores que los que afectan a la capacidad para aplicar una sangría en un sistema de diseño típico, como el uso correcto de los paneles y los márgenes. Por ejemplo, las entidades se asignan a las fuentes y pueden cambiar el tamaño en respuesta a la selección de fuente del usuario.

## <a name="east-asian-characters"></a>Personajes de Asia Oriental

"Caracteres asiáticos orientales" se define como un conjunto de rangos de caracteres Unicode U+20000 a U+2FFFD y U+30000 a U+3FFFD. En ocasiones, este subconjunto también se denomina "ideogramas CJK". Para obtener más información, vea <https://www.unicode.org>.

## <a name="white-space-and-text-content-models"></a>Modelos de espacio en blanco y contenido de texto

En la práctica, la conservación del espacio en blanco solo es motivo de preocupación para un subconjunto de todos los modelos de contenido posibles. Ese subconjunto está compuesto por modelos de contenido que pueden aceptar alguna forma del tipo <xref:System.String> singleton, una colección de <xref:System.String> dedicada o una mezcla de <xref:System.String> y otros tipos en una colección de <xref:System.Collections.IList> o <xref:System.Collections.Generic.ICollection%601> .

### <a name="white-space-and-text-content-models-in-wpf"></a>Modelos de espacio en blanco y contenido de texto en WPFWPF

Para que sirva de ejemplo, en el resto de esta sección se hace referencia a tipos concretos definidos por WPF. Las características de control de espacio en blanco que se describen en este artículo son pertinentes para los servicios XAML de .NET y WPFWPF. Para ver este comportamiento en acción, puede experimentar con el marcado XAML de WPF, ver los resultados en un gráfico de objeto y, después, serializar el marcado de nuevo.

Incluso para los modelos de contenido que pueden tomar cadenas, el comportamiento predeterminado dentro de estos modelos de contenido es que cualquier espacio en blanco que queda no se trata como significativo. Por ejemplo, <xref:System.Windows.Controls.ListBox> <xref:System.Collections.IList>toma un , pero el espacio en <xref:System.Windows.Controls.ListBoxItem>blanco (como los sellos de línea entre cada uno) no se conserva ni se representa. Si intenta usar avances de línea como separadores entre las cadenas de elementos de <xref:System.Windows.Controls.ListBoxItem> , no funcionará en absoluto; las cadenas que están separadas por los avances de línea se tratan como una cadena y un elemento.

Las colecciones que tratan el espacio en blanco como significativo suelen formar parte del modelo de documento de flujo. La colección principal que admite <xref:System.Windows.Documents.InlineCollection>el comportamiento de conservación de espacios en blanco es . Esta clase de colección se declara con el <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>; cuando se encuentra este [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] atributo, el procesador tratará el espacio en blanco dentro de la colección como significativo. La combinación de espacio en blanco dentro de `xml:space="preserve"` una <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> colección denotada es que todo el espacio en blanco se conserva y se representa. La combinación de y el espacio en blanco dentro de `xml:space="default"` un <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> provoca la normalización inicial del espacio en blanco descrita anteriormente, que deja un espacio en ciertas posiciones, y esos espacios se conservan y se representan. El comportamiento deseable depende del usuario, por lo que debe usar `xml:space` para habilitar el comportamiento que quiera.

Además, ciertos elementos en línea que connotan un salto de línea en un modelo de documento de flujo no deben introducir deliberadamente un espacio adicional incluso en una colección significativa de espacio en blanco. Por ejemplo, <xref:System.Windows.Documents.LineBreak> el elemento tiene \<el mismo propósito que la etiqueta BR/> en <xref:System.Windows.Documents.LineBreak> HTML y para la legibilidad en el marcado, normalmente a está separado de cualquier texto posterior por un salto de línea creado. Ese avance de línea no se debe normalizar para convertirlo en un espacio inicial en la línea posterior. Para habilitar ese comportamiento, la <xref:System.Windows.Documents.LineBreak> definición <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>de clase para el [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] elemento aplica el <xref:System.Windows.Documents.LineBreak> , que luego es interpretado por el procesador para significar que el espacio en blanco que rodea siempre se recorta.

## <a name="see-also"></a>Consulte también

- [Información general de XAML (WPF)](../fundamentals/xaml.md)
- [Entidades de caracteres XML y XAML](xml-character-entities.md)
- [xml:control de espacio en XAML](xml-space-handling.md)

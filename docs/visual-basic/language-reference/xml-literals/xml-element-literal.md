---
title: Literal de elemento XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
ms.openlocfilehash: d6a91de4e279816bafd29f46bb4f5422cbd934ff
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400194"
---
# <a name="xml-element-literal-visual-basic"></a>Literal de elemento XML (Visual Basic)

Literal que representa un <xref:System.Xml.Linq.XElement> objeto.

## <a name="syntax"></a>Sintaxis

```xml
<name [ attributeList ] />
-or-
<name [ attributeList ] > [ elementContents ] </[ name ]>
```

## <a name="parts"></a>Partes

- `<`

  Necesario. Abre la etiqueta del elemento de inicio.

- `name`

  Necesario. Nombre del elemento. El formato es uno de los siguientes:

  - Texto literal del nombre del elemento, con el formato `[ePrefix:]eName` , donde:

    |Parte|Descripción|
    |---|---|
    |`ePrefix`|Opcional. Prefijo de espacio de nombres XML para el elemento. Debe ser un espacio de nombres XML global que se define con una `Imports` instrucción en el archivo o en el nivel de proyecto, o un espacio de nombres XML local que se define en este elemento o en un elemento primario.|
    |`eName`|Necesario. Nombre del elemento. El formato es uno de los siguientes:<br /><br /> : Texto literal. Vea [nombres de atributos y elementos XML declarados](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />-Expresión insertada con el formato `<%= eNameExp %>` . El tipo de `eNameExp` debe ser `String` o un tipo que se pueda convertir implícitamente en <xref:System.Xml.Linq.XName> .|

  - Expresión insertada con el formato `<%= nameExp %>` . El tipo de `nameExp` debe ser `String` o un tipo que se pueda convertir implícitamente a <xref:System.Xml.Linq.XName> . No se permite una expresión incrustada en una etiqueta de cierre de un elemento.

- `attributeList`

  Opcional. Lista de atributos declarados en el literal.

  `attribute [ attribute ... ]`

  Cada `attribute` una de ellas tiene una de las siguientes sintaxis:

  - Asignación de atributos, con el formato `[aPrefix:]aName=aValue` , donde:

    |Parte|Descripción|
    |---|---|
    |`aPrefix`|Opcional. Prefijo de espacio de nombres XML para el atributo. Debe ser un espacio de nombres XML global que se define con una `Imports` instrucción o un espacio de nombres XML local que se define en este elemento o en un elemento primario.|
    |`aName`|Necesario. Nombre del atributo. El formato es uno de los siguientes:<br /><br /> : Texto literal. Vea [nombres de atributos y elementos XML declarados](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />-Expresión insertada con el formato `<%= aNameExp %>` . El tipo de `aNameExp` debe ser `String` o un tipo que se pueda convertir implícitamente en <xref:System.Xml.Linq.XName> .|
    |`aValue`|Opcional. Valor del atributo. El formato es uno de los siguientes:<br /><br /> -Texto literal, entre comillas.<br />-Expresión insertada con el formato `<%= aValueExp %>` . Se permite cualquier tipo.|

  - Expresión insertada con el formato `<%= aExp %>` .

- `/>`

  Opcional. Indica que el elemento es un elemento vacío, sin contenido.

- `>`

  Necesario. Finaliza la etiqueta de elemento inicial o vacía.

- `elementContents`

  Opcional. Contenido del elemento.

  `content [ content ... ]`

  Cada `content` puede ser uno de los siguientes:

  - Texto literal. Todos los espacios en blanco de `elementContents` se convierten en significativos si hay texto literal.

  - Expresión insertada con el formato `<%= contentExp %>` .

  - Literal de elemento XML.

  - Literal de comentario XML. Vea [literal de comentario XML](xml-comment-literal.md).

  - Literal de instrucción de procesamiento XML. Vea [literal de instrucción de procesamiento XML](xml-processing-instruction-literal.md).

  - Literal de CDATA XML. Vea [literal CDATA XML](xml-cdata-literal.md).

- `</[name]>`

  Opcional. Representa la etiqueta de cierre del elemento. `name`No se permite el parámetro opcional cuando es el resultado de una expresión incrustada.

## <a name="return-value"></a>Valor devuelto

Objeto <xref:System.Xml.Linq.XElement>.

## <a name="remarks"></a>Observaciones

Puede usar la sintaxis de literales del elemento XML para crear <xref:System.Xml.Linq.XElement> objetos en el código.

> [!NOTE]
> Un literal XML puede abarcar varias líneas sin utilizar caracteres de continuación de línea. Esta característica permite copiar contenido de un documento XML y pegarlo directamente en un programa Visual Basic.

Las expresiones incrustadas del formulario `<%= exp %>` permiten agregar información dinámica a un literal de elemento XML. Para obtener más información, vea [expresiones incrustadas en XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md).

El compilador Visual Basic convierte el literal de elemento XML en llamadas al <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor y, si es necesario, el <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.

## <a name="xml-namespaces"></a>Espacios de nombres XML

Los prefijos de espacios de nombres XML son útiles cuando es necesario crear literales XML con elementos del mismo espacio de nombres muchas veces en el código. Puede usar prefijos globales de espacio de nombres XML, que se definen mediante la `Imports` instrucción, o prefijos locales, que se definen mediante la `xmlns:xmlPrefix="xmlNamespace"` Sintaxis de atributo. Para obtener más información, vea [instrucción Imports (espacio de nombres XML)](../statements/imports-statement-xml-namespace.md).

De acuerdo con las reglas de ámbito de los espacios de nombres XML, los prefijos locales tienen prioridad sobre los prefijos globales. Sin embargo, si un literal XML define un espacio de nombres XML, ese espacio de nombres no está disponible para las expresiones que aparecen en una expresión incrustada. La expresión incrustada solo puede tener acceso al espacio de nombres XML global.

El compilador Visual Basic convierte cada espacio de nombres XML global utilizado por un literal XML en una definición de espacio de nombres local en el código generado. Los espacios de nombres XML globales que no se utilizan no aparecen en el código generado.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo crear un elemento XML simple que tiene dos elementos vacíos anidados.

[!code-vb[VbXMLSamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#20)]

En el ejemplo se muestra el texto siguiente. Observe que el literal conserva la estructura de los elementos vacíos.

```xml
<outer>
  <inner1></inner1>
  <inner2 />
</outer>
```

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo utilizar expresiones incrustadas para asignar un nombre a un elemento y crear atributos.

[!code-vb[VbXMLSamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#21)]

Este código muestra el siguiente texto:

```xml
<book isbn="1234" author="My Author" year="1999" title="My Book" />
```

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se declara `ns` como un prefijo de espacio de nombres XML. A continuación, usa el prefijo del espacio de nombres para crear un literal XML y muestra el formulario final del elemento.

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

Este código muestra el siguiente texto:

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

Observe que el compilador ha convertido el prefijo del espacio de nombres XML global en una definición de prefijo para el espacio de nombres XML. El \<ns:middle> elemento redefine el prefijo del espacio de nombres XML para el \<ns:inner1> elemento. Sin embargo, el \<ns:inner2> elemento utiliza el espacio de nombres definido por la `Imports` instrucción.

## <a name="see-also"></a>Consulte también

- <xref:System.Xml.Linq.XElement>
- [Nombres de atributos y elementos XML declarados](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [Literal de comentario XML](xml-comment-literal.md)
- [Literal de CDATA XML](xml-cdata-literal.md)
- [Literales XML](index.md)
- [Crear XML en Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
- [Expresiones insertadas en XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [Imports (Instrucción, Espacio de nombres XML)](../statements/imports-statement-xml-namespace.md)

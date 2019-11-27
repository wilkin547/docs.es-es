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
ms.openlocfilehash: d6d900ca6868cfffe6b0e5b349321a79c5716c46
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347026"
---
# <a name="xml-element-literal-visual-basic"></a>Literal de elemento XML (Visual Basic)

Literal que representa un objeto <xref:System.Xml.Linq.XElement>.

## <a name="syntax"></a>Sintaxis

```xml
<name [ attributeList ] />
-or-
<name [ attributeList ] > [ elementContents ] </[ name ]>
```

## <a name="parts"></a>Elementos

- `<`

  Obligatorio. Abre la etiqueta del elemento de inicio.

- `name`

  Obligatorio. Nombre del elemento. El formato es uno de los siguientes:

  - Texto literal del nombre del elemento, con el formato `[ePrefix:]eName`, donde:

    |Parte|Descripción|
    |---|---|
    |`ePrefix`|Opcional. Prefijo de espacio de nombres XML para el elemento. Debe ser un espacio de nombres XML global que se define con una instrucción `Imports` en el archivo o en el nivel de proyecto, o un espacio de nombres XML local que se define en este elemento o en un elemento primario.|
    |`eName`|Obligatorio. Nombre del elemento. El formato es uno de los siguientes:<br /><br /> : Texto literal. Vea [nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />-Expresión insertada con el formato `<%= eNameExp %>`. El tipo de `eNameExp` debe ser `String` o un tipo que se pueda convertir implícitamente a <xref:System.Xml.Linq.XName>.|

  - Expresión incrustada con el formato `<%= nameExp %>`. El tipo de `nameExp` debe ser `String` o un tipo que se pueda convertir implícitamente en <xref:System.Xml.Linq.XName>. No se permite una expresión incrustada en una etiqueta de cierre de un elemento.

- `attributeList`

  Opcional. Lista de atributos declarados en el literal.

  `attribute [ attribute ... ]`

  Cada `attribute` tiene una de las siguientes sintaxis:

  - Asignación de atributos, con el formato `[aPrefix:]aName=aValue`, donde:

    |Parte|Descripción|
    |---|---|
    |`aPrefix`|Opcional. Prefijo de espacio de nombres XML para el atributo. Debe ser un espacio de nombres XML global que se define con una instrucción `Imports` o un espacio de nombres XML local que se define en este elemento o en un elemento primario.|
    |`aName`|Obligatorio. Nombre del atributo. El formato es uno de los siguientes:<br /><br /> : Texto literal. Vea [nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />-Expresión insertada con el formato `<%= aNameExp %>`. El tipo de `aNameExp` debe ser `String` o un tipo que se pueda convertir implícitamente a <xref:System.Xml.Linq.XName>.|
    |`aValue`|Opcional. Valor del atributo. El formato es uno de los siguientes:<br /><br /> -Texto literal, entre comillas.<br />-Expresión insertada con el formato `<%= aValueExp %>`. Se permite cualquier tipo.|

  - Expresión incrustada con el formato `<%= aExp %>`.

- `/>`

  Opcional. Indica que el elemento es un elemento vacío, sin contenido.

- `>`

  Obligatorio. Finaliza la etiqueta de elemento inicial o vacía.

- `elementContents`

  Opcional. Contenido del elemento.

  `content [ content ... ]`

  Cada `content` puede ser una de las siguientes:

  - Texto literal. Todo el espacio en blanco de `elementContents` se convierte en significativo si hay texto literal.

  - Expresión incrustada con el formato `<%= contentExp %>`.

  - Literal de elemento XML.

  - Literal de comentario XML. Vea [literal de comentario XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).

  - Literal de instrucción de procesamiento XML. Vea [literal de instrucción de procesamiento XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).

  - Literal de CDATA XML. Vea [literal CDATA XML](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).

- `</[name]>`

  Opcional. Representa la etiqueta de cierre del elemento. No se permite el parámetro opcional `name` cuando es el resultado de una expresión incrustada.

## <a name="return-value"></a>Valor devuelto

Un objeto <xref:System.Xml.Linq.XElement>.

## <a name="remarks"></a>Comentarios

Puede usar la sintaxis de literales del elemento XML para crear <xref:System.Xml.Linq.XElement> objetos en el código.

> [!NOTE]
> Un literal XML puede abarcar varias líneas sin utilizar caracteres de continuación de línea. Esta característica permite copiar contenido de un documento XML y pegarlo directamente en un programa Visual Basic.

Las expresiones incrustadas del formulario `<%= exp %>` permiten agregar información dinámica a un literal de elemento XML. Para obtener más información, vea [expresiones incrustadas en XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).

El compilador Visual Basic convierte el literal de elemento XML en llamadas al constructor <xref:System.Xml.Linq.XElement.%23ctor%2A> y, si es necesario, el constructor <xref:System.Xml.Linq.XAttribute.%23ctor%2A>.

## <a name="xml-namespaces"></a>Espacios de nombres XML

Los prefijos de espacios de nombres XML son útiles cuando es necesario crear literales XML con elementos del mismo espacio de nombres muchas veces en el código. Puede usar prefijos globales de espacio de nombres XML, que se definen mediante la instrucción `Imports`, o prefijos locales, que se definen mediante la sintaxis del atributo `xmlns:xmlPrefix="xmlNamespace"`. Para obtener más información, vea [instrucción Imports (espacio de nombres XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).

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

Observe que el compilador ha convertido el prefijo del espacio de nombres XML global en una definición de prefijo para el espacio de nombres XML. El elemento \<NS: Middle > vuelve a definir el prefijo de espacio de nombres XML para el elemento de > \<NS: inner1. Sin embargo, el elemento \<NS: inner2 > utiliza el espacio de nombres definido por la instrucción `Imports`.

## <a name="see-also"></a>Vea también

- <xref:System.Xml.Linq.XElement>
- [Nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [Literal de comentario XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [Literal de CDATA XML](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)
- [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Expresiones incrustadas en XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [Imports (instrucción), espacio de nombres XML](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)

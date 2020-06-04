---
title: 'Instrucción Imports: espacio de nombres XML'
ms.date: 07/20/2015
f1_keywords:
- vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
ms.openlocfilehash: a3184d68b0e4cdff5d4296a5a638e22b4e83bcde
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404542"
---
# <a name="imports-statement-xml-namespace"></a>Imports (Instrucción, Espacio de nombres XML)

Importa prefijos de espacios de nombres XML para su uso en literales XML y propiedades de eje XML.

## <a name="syntax"></a>Sintaxis

```vb
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">
```

## <a name="parts"></a>Partes

`xmlNamespacePrefix`  
Opcional. Cadena por la que pueden hacer referencia los elementos y atributos XML `xmlNamespaceName` . Si no `xmlNamespacePrefix` se proporciona ningún valor, el espacio de nombres XML importado es el espacio de nombres XML predeterminado. Debe ser un identificador XML válido. Para obtener más información, vea [nombres de elementos y atributos XML declarados](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).

`xmlNamespaceName`  
Necesario. Cadena que identifica el espacio de nombres XML que se va a importar.

## <a name="remarks"></a>Observaciones

Puede utilizar la `Imports` instrucción para definir espacios de nombres XML globales que puede usar con literales XML y propiedades de eje XML, o como parámetros pasados al `GetXmlNamespace` operador. (Para obtener información sobre el uso de la `Imports` instrucción para importar un alias que se puede usar donde se usan los nombres de tipo en el código, vea [instrucción Imports (espacio de nombres y tipo de .net)](imports-statement-net-namespace-and-type.md)). La sintaxis para declarar un espacio de nombres XML mediante la `Imports` instrucción es idéntica a la sintaxis utilizada en XML. Por lo tanto, puede copiar una declaración de espacio de nombres de un archivo XML y utilizarla en una `Imports` instrucción.

Los prefijos de espacios de nombres XML son útiles cuando se desea crear repetidamente elementos XML que son del mismo espacio de nombres. El prefijo de espacio de nombres XML declarado con la `Imports` instrucción es global en el sentido de que está disponible para todo el código del archivo. Se puede utilizar al crear literales de elemento XML y al tener acceso a las propiedades del eje XML. Para obtener más información, vea [XML ELEMENT literal](../xml-literals/xml-element-literal.md) and [XML AXIS Properties](../xml-axis/index.md).

Si define un espacio de nombres XML global sin un prefijo de espacio de nombres (por ejemplo, `Imports <xmlns="http://SomeNameSpace>"` ), ese espacio de nombres se considera el espacio de nombres XML predeterminado. El espacio de nombres XML predeterminado se utiliza para los literales de elemento XML o las propiedades de eje de atributo XML que no especifican explícitamente un espacio de nombres. También se utiliza el espacio de nombres predeterminado si el espacio de nombres especificado es el espacio de nombres vacío (es decir, `xmlns=""` ). El espacio de nombres XML predeterminado no se aplica a los atributos XML en los literales XML ni a las propiedades del eje de atributo XML que no tienen un espacio de nombres.

Los espacios de nombres XML que se definen en un literal XML, que se denominan *espacios de nombres XML locales*, tienen prioridad sobre los espacios de nombres XML definidos por la `Imports` instrucción como globales. Los espacios de nombres XML definidos por la `Imports` instrucción tienen prioridad sobre los espacios de nombres XML importados para un proyecto Visual Basic. Si un literal XML define un espacio de nombres XML, ese espacio de nombres local no se aplica a las expresiones incrustadas.

Los espacios de nombres XML globales siguen las mismas reglas de ámbito y definición que .NET Framework espacios de nombres. Como resultado, puede incluir una `Imports` instrucción para definir un espacio de nombres XML global en cualquier lugar en el que pueda importar un espacio de nombres de .NET Framework. Esto incluye los archivos de código y los espacios de nombres importados en el nivel de proyecto. Para obtener información sobre los espacios de nombres importados en el nivel de proyecto, vea [Página referencias, diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).

Cada archivo de código fuente puede contener cualquier número de `Imports` instrucciones. Estos deben seguir las declaraciones de opciones, como la `Option Strict` instrucción, y deben preceder a las declaraciones de elementos de programación, como las `Module` `Class` instrucciones o.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se importa un espacio de nombres XML predeterminado y un espacio de nombres XML identificado con el prefijo `ns` . A continuación, crea literales XML que usan ambos espacios de nombres.

[!code-vb[VbXMLSamples#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/Module1.vb#45)]

Este código muestra el siguiente texto:

```xml
<ns:outer xmlns="http://DefaultNamespace"
          xmlns:ns="http://NewNamespace">
  <ns:innerElement></ns:innerElement>
  <siblingElement></siblingElement>
  <innerElement />
</ns:outer>
```

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se importa el prefijo del espacio de nombres XML `ns` . A continuación, crea un literal XML que utiliza el prefijo de espacio de nombres y muestra el formulario final del elemento.

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

Observe que el compilador ha convertido el prefijo de espacio de nombres XML de un prefijo global a una definición de prefijo local.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se importa el prefijo del espacio de nombres XML `ns` . A continuación, se usa el prefijo del espacio de nombres para crear un literal XML y obtener acceso al primer nodo secundario con el nombre completo `ns:name`.

[!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]

Este código muestra el siguiente texto:

`Patrick Hines`

## <a name="see-also"></a>Consulte también

- [Literal de elemento XML](../xml-literals/xml-element-literal.md)
- [Propiedades de eje XML](../xml-axis/index.md)
- [Nombres de atributos y elementos XML declarados](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [Operador GetXmlNamespace](../operators/getxmlnamespace-operator.md)

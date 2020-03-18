---
title: 'Procesamiento del archivo XML: guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- XML processing [C#]
- XML [C#], processing
ms.assetid: 60c71193-9dac-4cd3-98c5-100bd0edcc42
ms.openlocfilehash: bc72cade9ce6edddb88d741a3424405bba0a7ad8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "76793390"
---
# <a name="processing-the-xml-file-c-programming-guide"></a>Procesamiento del archivo XML (guía de programación de C#)

El compilador genera una cadena de identificador para cada construcción del código que se etiqueta para generar documentación. (Para más información sobre cómo etiquetar el código, vea [Etiquetas recomendadas para comentarios de documentación](./recommended-tags-for-documentation-comments.md)). La cadena de identificador identifica la construcción de forma exclusiva. Los programas que procesan el archivo XML pueden usar la cadena de identificador para identificar el elemento de reflexión o de metadatos correspondiente de .NET Framework al que se aplica la documentación.

El archivo XML no es una representación jerárquica del código; se trata de una lista plana que tiene un identificador generado para cada elemento.

El compilador cumple las siguientes reglas cuando genera las cadenas de identificador:

- No hay ningún espacio en blanco en la cadena.

- La primera parte de la cadena de identificador identifica el tipo de miembro identificado, mediante un carácter único seguido de dos puntos. Se utilizan los siguientes tipos de miembros:

    |Carácter|Descripción|
    |---------------|-----------------|
    |N|namespace<br /><br /> No puede agregar comentarios de documentación a un espacio de nombres, pero sí puede hacer referencias cruzadas a ellos, en caso de que se admitan.|
    |T|tipo: clase, interfaz, estructura, enumeración o delegado|
    |F|campo|
    |P|propiedad (incluidos indizadores u otras propiedades indizadas)|
    |M|método (incluidos métodos especiales como constructores, operadores, etc.)|
    |E|event|
    |!|cadena de error<br /><br /> El resto de la cadena proporciona información sobre el error. El compilador de C# genera información de error para vínculos que no se puede resolver.|

- La segunda parte de la cadena es el nombre completo del elemento, que empieza por la raíz del espacio de nombres. El nombre del elemento, sus tipos envolventes y el espacio de nombres están separados por puntos. Si el nombre del elemento ya contiene puntos, estos se reemplazan por el signo hash ("#"). Se supone que ningún elemento tiene un signo hash directamente en su nombre. Por ejemplo, el nombre completo del constructor de String sería "System.String.#ctor".

- Para propiedades y métodos, si hay argumentos para el método, sigue la lista de argumentos entre paréntesis. Si no hay ningún argumento, tampoco habrá paréntesis. Los argumentos están separados por comas. La codificación de cada argumento indica directamente cómo se codifica en una firma de .NET Framework:

  - Tipos base. Los tipos habituales (ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE) se representan como el nombre completo del tipo.

  - Los tipos intrínsecos (por ejemplo, ELEMENT_TYPE_I4, ELEMENT_TYPE_OBJECT, ELEMENT_TYPE_STRING, ELEMENT_TYPE_TYPEDBYREF y ELEMENT_TYPE_VOID) se representan como el nombre completo del tipo completo correspondiente. Por ejemplo, System.Int32 o System.TypedReference.

  - ELEMENT_TYPE_PTR se representa como un "\*" después del tipo modificado.

  - ELEMENT_TYPE_BYREF se representa como un "\@" después del tipo modificado.

  - ELEMENT_TYPE_PINNED se representa como "^" después del tipo modificado. El compilador de C# nunca genera este resultado.

  - ELEMENT_TYPE_CMOD_REQ se representa como "&#124;" y el nombre completo de la clase modificadora, después del tipo modificado. El compilador de C# nunca genera este resultado.

  - ELEMENT_TYPE_CMOD_OPT se representa como "!" y el nombre completo de la clase modificadora, después del tipo modificado.

  - ELEMENT_TYPE_SZARRAY se representa como "[]" después del tipo de elemento de la matriz.

  - ELEMENT_TYPE_GENERICARRAY se representa como "[?]" después del tipo de elemento de la matriz. El compilador de C# nunca genera este resultado.

  - ELEMENT_TYPE_ARRAY se representa como [*límite inferior*:`size`,*límite inferior*:`size`], donde el número de comas es la clasificación - 1, y los límites inferiores y el tamaño de cada dimensión, si se conocen, se representan en decimales. Si no se especifican un límite inferior ni un tamaño, simplemente se omiten. Si se omiten el límite inferior y el tamaño de una dimensión determinada, también se omite ":". Por ejemplo, una matriz de dos dimensiones con 1 como los límites inferiores y tamaños no especificados es [1:,1:].

  - ELEMENT_TYPE_FNPTR se representa como "=FUNC:`type`(*signature*)", donde `type` es el tipo de valor devuelto y *signature* se corresponde con los argumentos del método. Si no hay ningún argumento, se omiten los paréntesis. El compilador de C# nunca genera este resultado.

    Los siguientes componentes de la firma no se representan porque nunca se usan para diferenciar métodos sobrecargados:

  - Convención de llamada

  - Tipo de valor devuelto

  - ELEMENT_TYPE_SENTINEL

- Solo para los operadores de conversión (op_Implicit y op_Explicit), el valor devuelto del método se codifica como "~" seguido de un tipo de valor devuelto, como se ha codificado anteriormente.

- Para tipos genéricos, el nombre del tipo está seguido de una tilde aguda y después de un número que indica el número de parámetros de tipo genérico. Por ejemplo:

     ``<member name="T:SampleClass`2">`` es la etiqueta de un tipo que se define como `public class SampleClass<T, U>`.

     Para los métodos que usan tipos genéricos como parámetros, los parámetros de tipo genérico se especifican como números precedidos por tildes agudas (por ejemplo, \`0,\`1). Cada número representa una notación de matriz de base cero para los parámetros genéricos del tipo.

## <a name="examples"></a>Ejemplos

En los ejemplos siguientes se muestra cómo se generarían las cadenas de identificador para una clase y sus miembros:

[!code-csharp[csProgGuidePointers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#21)]

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [-doc (opciones del compilador de C#)](../../language-reference/compiler-options/doc-compiler-option.md)
- [Comentarios de documentación XML](./index.md)

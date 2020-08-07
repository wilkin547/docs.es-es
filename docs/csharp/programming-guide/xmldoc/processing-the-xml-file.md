---
title: 'Procesamiento del archivo XML: guía de programación de C#'
description: Aprenda a procesar el archivo XML en programación de C#. Vea ejemplos de código y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
helpviewer_keywords:
- XML processing [C#]
- XML [C#], processing
ms.assetid: 60c71193-9dac-4cd3-98c5-100bd0edcc42
ms.openlocfilehash: 6f8a278ed842cd9c4176f3efff423ee048f7e9b9
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381546"
---
# <a name="process-the-xml-file-c-programming-guide"></a>Procesamiento del archivo XML (guía de programación de C#)

El compilador genera una cadena de identificador para cada construcción del código que se etiqueta para generar documentación. (Para más información sobre cómo etiquetar el código, vea [Etiquetas recomendadas para comentarios de documentación](./recommended-tags-for-documentation-comments.md)). La cadena de identificador identifica la construcción de forma exclusiva. Los programas que procesan el archivo XML pueden usar la cadena de identificador para identificar el elemento de reflexión o de metadatos correspondiente de .NET al que se aplica la documentación.

## <a name="id-strings"></a>Cadenas de identificador

El archivo XML no es una representación jerárquica del código. Es una lista plana que tiene un identificador generado para cada elemento.

El compilador cumple las siguientes reglas cuando genera las cadenas de identificador:

- No hay ningún espacio en blanco en la cadena.

- La primera parte de la cadena identifica el tipo de miembro mediante un carácter único seguido de dos puntos. Se utilizan los siguientes tipos de miembros:

    |Carácter|Tipo de miembro|Notas|
    |---------------|-----------------|-|
    |N|namespace|No puede agregar comentarios de documentación a un espacio de nombres, pero sí puede hacer referencias cruzadas a ellos, en caso de que se admitan.|
    |T|type|Un tipo puede ser una clase, una interfaz, una estructura, una enumeración o un delegado.|
    |F|campo|
    |P|propiedad|Incluye indizadores u otras propiedades indizadas.|
    |M|método|Incluye métodos especiales, como constructores y operadores.|
    |E|event|
    |!|cadena de error|El resto de la cadena proporciona información sobre el error. El compilador de C# genera información de error para vínculos que no se puede resolver.|

- La segunda parte de la cadena es el nombre completo del elemento, que empieza por la raíz del espacio de nombres. El nombre del elemento, sus tipos envolventes y el espacio de nombres están separados por puntos. Si el nombre del elemento ya contiene puntos, estos se reemplazan por el signo hash ("#"). Se supone que ningún elemento tiene un signo hash directamente en su nombre. Por ejemplo, el nombre completo del constructor de String es "System.String.#ctor".

- Para las propiedades y los métodos, se indica la lista de parámetros entre paréntesis. Si no hay ningún parámetro, tampoco habrá paréntesis. Los parámetros se separan mediante comas. La codificación de cada parámetro indica directamente cómo se codifica en una firma de .NET:

  - Tipos base. Los tipos habituales (ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE) se representan como el nombre completo del tipo.

  - Los tipos intrínsecos (por ejemplo, ELEMENT_TYPE_I4, ELEMENT_TYPE_OBJECT, ELEMENT_TYPE_STRING, ELEMENT_TYPE_TYPEDBYREF y ELEMENT_TYPE_VOID) se representan como el nombre completo del tipo completo correspondiente. Por ejemplo, System.Int32 o System.TypedReference.

  - ELEMENT_TYPE_PTR se representa como un "\*" después del tipo modificado.

  - ELEMENT_TYPE_BYREF se representa como un "\@" después del tipo modificado.

  - ELEMENT_TYPE_PINNED se representa como "^" después del tipo modificado. El compilador de C# nunca genera este resultado.

  - ELEMENT_TYPE_CMOD_REQ se representa como "&#124;" y el nombre completo de la clase modificadora, después del tipo modificado. El compilador de C# nunca genera este resultado.

  - ELEMENT_TYPE_CMOD_OPT se representa como "!" y el nombre completo de la clase modificadora, después del tipo modificado.

  - ELEMENT_TYPE_SZARRAY se representa como "[]" después del tipo de elemento de la matriz.

  - ELEMENT_TYPE_GENERICARRAY se representa como "[?]" después del tipo de elemento de la matriz. El compilador de C# nunca genera este resultado.

  - ELEMENT_TYPE_ARRAY se representa como [*límite inferior*:`size`,*límite inferior*:`size`], donde el número de comas es la clasificación - 1, y los límites inferiores y el tamaño de cada dimensión, si se conocen, se representan en decimales. Si no se especifican un límite inferior ni un tamaño, se omiten. Si se omiten el límite inferior y el tamaño de una dimensión determinada, también se omite ":". Por ejemplo, una matriz de dos dimensiones con 1 como los límites inferiores y tamaños no especificados es [1:,1:].

  - ELEMENT_TYPE_FNPTR se representa como "=FUNC:`type`(*signature*)", donde `type` es el tipo de valor devuelto y *signature* se corresponde con los argumentos del método. Si no hay ningún argumento, se omiten los paréntesis. El compilador de C# nunca genera este resultado.

  Los siguientes componentes de la firma no se representan porque nunca se usan para diferenciar métodos sobrecargados:

  - Convención de llamada

  - Tipo de valor devuelto

  - ELEMENT_TYPE_SENTINEL

- Solo para los operadores de conversión (`op_Implicit` y`op_Explicit`), el valor devuelto del método se codifica como "~" seguido por el tipo de valor devuelto.

- Para tipos genéricos, el nombre del tipo está seguido de una tilde aguda y después de un número que indica el número de parámetros de tipo genérico. Por ejemplo:

     ``<member name="T:SampleClass`2">`` es la etiqueta de un tipo que se define como `public class SampleClass<T, U>`.

     Para los métodos que toman tipos genéricos como parámetros, los parámetros de tipo genérico se especifican como números precedidos por tildes graves (por ejemplo, \`0,\`1). Cada número representa una notación de matriz de base cero para los parámetros genéricos del tipo.

## <a name="examples"></a>Ejemplos

En los ejemplos siguientes, se muestra cómo se generan las cadenas de identificador para una clase y sus miembros:

[!code-csharp[csProgGuidePointers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#21)]

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [-doc (opciones del compilador de C#)](../../language-reference/compiler-options/doc-compiler-option.md)
- [Comentarios de documentación XML](./index.md)

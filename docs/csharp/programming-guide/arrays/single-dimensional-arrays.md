---
title: 'Matrices unidimensionales: Guía de programación de C#'
description: Cree una matriz unidimensional en C# mediante el operador new; para ello, especifique el tipo de elemento de matriz y el número de elementos.
ms.date: 06/03/2020
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: ada01262d57cbfebc8bfa1a5fee0639a10db5a4b
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474597"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a>Matrices unidimensionales (Guía de programación de C#)

Cree una matriz unidimensional mediante el operador [new](../../language-reference/operators/new-operator.md); para ello, especifique el tipo de elemento de matriz y el número de elementos. En el ejemplo siguiente se declara una matriz de cinco enteros:

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="IntDeclaration":::

Esta matriz contiene los elementos de `array[0]` a `array[4]`. Los elementos de la matriz se inicializan en el valor predeterminado del tipo de elemento, `0` para los enteros.

Las matrices pueden almacenar cualquier tipo de elemento que se especifique, como en el ejemplo siguiente, en el que se declara una matriz de cadenas:

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="StringDeclaration":::

## <a name="array-initialization"></a>Inicialización de matriz

Puede inicializar los elementos de una matriz al declararla. El especificador de longitud no es necesario porque la medida se infiere a partir del número de elementos de la lista de inicialización. Por ejemplo:

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="IntInitialization":::

En el código siguiente se muestra una declaración de una matriz de cadenas donde cada elemento de la matriz se inicializa mediante el nombre de un día:

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="StringInitialization":::
  
Puede evitar la expresión `new` y el tipo de matriz al inicializar una matriz en la declaración, tal como se muestra en el código siguiente. Esto se conoce como [matriz con tipo implícito](implicitly-typed-arrays.md):

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="ShorthandInitialization":::

Puede declarar una variable de matriz sin crearla, pero debe usar el operador `new` cuando asigne una nueva matriz a esta variable. Por ejemplo:

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="DeclareAllocate":::

## <a name="value-type-and-reference-type-arrays"></a>Matrices de tipo de valor y tipo de referencia

Tenga en cuenta la siguiente declaración de matriz:  

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="FinalInstantiation":::

El resultado de esta instrucción depende de si `SomeType` es un tipo de valor o un tipo de referencia. Si es un tipo de valor, la instrucción crea una matriz de 10 elementos, y cada uno de ellos tiene el tipo `SomeType`. Si `SomeType` es un tipo de referencia, la instrucción crea una matriz de 10 elementos y cada uno de ellos se inicializa en una referencia nula. En ambas instancias, los elementos se inicializan en el valor predeterminado para el tipo de elemento. Para obtener más información sobre los tipos de valor y de referencia, consulte [Tipos de valor ](../../language-reference/builtin-types/value-types.md) y [Tipos de referencia](../../language-reference/keywords/reference-types.md).
  
## <a name="see-also"></a>Vea también

- <xref:System.Array>
- [Matrices](./index.md)
- [Matrices multidimensionales](./multidimensional-arrays.md)
- [Matrices escalonadas](./jagged-arrays.md)

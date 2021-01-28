---
title: 'Matrices: Guía de programación de C#'
description: Puede almacenar varias variables del mismo tipo en una estructura de datos de matriz de C#. Declare una matriz especificando un tipo o especifique un objeto para almacenar cualquier tipo.
ms.date: 01/22/2021
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: 203d8b86da4e74d8c5397132a0ba68618eedf348
ms.sourcegitcommit: 4d5e25a46aa7cd0d29b4b9227b92987354d444c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98794764"
---
# <a name="arrays-c-programming-guide"></a>Matrices (Guía de programación de C#)

Puede almacenar varias variables del mismo tipo en una estructura de datos de matriz. Puede declarar una matriz mediante la especificación del tipo de sus elementos. Si quiere que la matriz almacene elementos de cualquier tipo, puede especificar `object` como su tipo. En el sistema de tipos unificado de C#, todos los tipos, los predefinidos y los definidos por el usuario, los tipos de referencia y los tipos de valores, heredan directa o indirectamente de <xref:System.Object>.

```csharp
type[] arrayName;
```

## <a name="example"></a>Ejemplo

Los ejemplos siguientes crean matrices unidimensionales, multidimensionales y escalonadas:

[!code-csharp[csProgGuideArrays#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#1)]

## <a name="array-overview"></a>Información general sobre la matriz

Una matriz tiene las propiedades siguientes:

- Puede ser una matriz [unidimensional](single-dimensional-arrays.md), [multidimensional](multidimensional-arrays.md) o [escalonada](jagged-arrays.md).
- El número de dimensiones y la longitud de cada dimensión se establecen al crear la instancia de matriz. No se pueden cambiar estos valores durante la vigencia de la instancia.
- Los valores predeterminados de los elementos numéricos de matriz se establecen en cero y los elementos de referencia se establecen en null.
- Una matriz escalonada es una matriz de matrices y, por consiguiente, sus elementos son tipos de referencia y se inicializan en `null`.
- Las matrices se indexan con cero: una matriz con `n` elementos se indexa de `0` a `n-1`.
- Los elementos de una matriz puede ser cualquier tipo, incluido un tipo de matriz.
- Los tipos de matriz son [tipos de referencia](../../language-reference/keywords/reference-types.md) que proceden del tipo base abstracto <xref:System.Array>. Como este tipo implementa <xref:System.Collections.IEnumerable> y <xref:System.Collections.Generic.IEnumerable%601>, puede usar la iteración [foreach](../../language-reference/keywords/foreach-in.md) en todas las matrices de C#.

### <a name="arrays-as-objects"></a>Matrices como objetos

En C#, las matrices son actualmente objetos, y no simplemente regiones direccionables de memoria contigua como en C y C++. <xref:System.Array> es el tipo base abstracto de todos los tipos de matriz. Puede usar las propiedades, y otros miembros de clase, que tiene <xref:System.Array>. Un ejemplo de esto sería usar la propiedad <xref:System.Array.Length%2A> para obtener la longitud de una matriz. El código siguiente asigna la longitud de la matriz `numbers`, que es `5`, a una variable denominada `lengthOfNumbers`:

[!code-csharp[csProgGuideArrays#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#3)]

La clase <xref:System.Array> proporciona muchos otros métodos útiles y propiedades para ordenar, buscar y copiar matrices. En los ejemplos siguientes se usa la propiedad <xref:System.Array.Rank%2A> para mostrar el número de dimensiones de una matriz.

[!code-csharp[csProgGuideArrays#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#2)]

## <a name="see-also"></a>Vea también

- [Uso de matrices unidimensionales](single-dimensional-arrays.md)
- [Uso de matrices multidimensionales](multidimensional-arrays.md)
- [Uso de matrices escalonadas](jagged-arrays.md)
- [Utilizar foreach con matrices](using-foreach-with-arrays.md)
- [Pasar matrices como argumentos](passing-arrays-as-arguments.md)
- [Matrices con tipo implícito](implicitly-typed-arrays.md)
- [Guía de programación de C#](../index.md)
- [Colecciones](../concepts/collections.md)

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

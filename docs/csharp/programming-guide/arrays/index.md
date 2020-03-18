---
title: 'Matrices: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: bbabc84c144e5b3415c19f346b890782e251662c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "75715058"
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

## <a name="related-sections"></a>Secciones relacionadas

- [Matrices como objetos](arrays-as-objects.md)
- [Utilizar foreach con matrices](using-foreach-with-arrays.md)
- [Pasar matrices como argumentos](passing-arrays-as-arguments.md)

## <a name="c-language-specification"></a>especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Colecciones](../concepts/collections.md)

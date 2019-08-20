---
title: 'Matrices: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: 24c6d54c3fe92ada661e732adec582e87ab62417
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69597532"
---
# <a name="arrays-c-programming-guide"></a>Matrices (Guía de programación de C#)

Puede almacenar varias variables del mismo tipo en una estructura de datos de matriz. Puede declarar una matriz mediante la especificación del tipo de sus elementos.  
  
 `type[] arrayName;`  
  
 Los ejemplos siguientes crean matrices unidimensionales, multidimensionales y escalonadas:  
  
 [!code-csharp[csProgGuideArrays#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#1)]  
  
## <a name="array-overview"></a>Información general de las matrices

 Una matriz tiene las propiedades siguientes:  
  
- Puede ser una matriz [unidimensional](./single-dimensional-arrays.md), [multidimensional](./multidimensional-arrays.md) o [escalonada](./jagged-arrays.md).  
  
- El número de dimensiones y la longitud de cada dimensión se establecen al crear la instancia de matriz. No se pueden cambiar estos valores durante la vigencia de la instancia.  
  
- Los valores predeterminados de los elementos numéricos de matriz se establecen en cero y los elementos de referencia se establecen en null.  
  
- Una matriz escalonada es una matriz de matrices y, por consiguiente, sus elementos son tipos de referencia y se inicializan en `null`.  
  
- Las matrices se indexan con cero: una matriz con `n` elementos se indexa de `0` a `n-1`.  
  
- Los elementos de una matriz puede ser cualquier tipo, incluido un tipo de matriz.  
  
- Los tipos de matriz son [tipos de referencia](../../language-reference/keywords/reference-types.md) que proceden del tipo base abstracto <xref:System.Array>. Como este tipo implementa <xref:System.Collections.IEnumerable> y <xref:System.Collections.Generic.IEnumerable%601>, puede usar la iteración [foreach](../../language-reference/keywords/foreach-in.md) en todas las matrices de C#.  
  
## <a name="related-sections"></a>Secciones relacionadas  
  
- [Matrices como objetos](./arrays-as-objects.md)  
  
- [Utilizar foreach con matrices](./using-foreach-with-arrays.md)  
  
- [Pasar matrices como argumentos](./passing-arrays-as-arguments.md)  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Colecciones](../concepts/collections.md)

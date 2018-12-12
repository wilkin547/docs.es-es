---
title: 'Matrices: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: cf684d2ec7ae7282b1ab68817357773f0f96c9ae
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245657"
---
# <a name="arrays-c-programming-guide"></a>Matrices (Guía de programación de C#)

Puede almacenar varias variables del mismo tipo en una estructura de datos de matriz. Puede declarar una matriz mediante la especificación del tipo de sus elementos.  
  
 `type[] arrayName;`  
  
 Los ejemplos siguientes crean matrices unidimensionales, multidimensionales y escalonadas:  
  
 [!code-csharp[csProgGuideArrays#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/index_1.cs)]  
  
## <a name="array-overview"></a>Información general de las matrices

 Una matriz tiene las propiedades siguientes:  
  
-   Puede ser una matriz [unidimensional](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [multidimensional](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) o [escalonada](../../../csharp/programming-guide/arrays/jagged-arrays.md).  
  
-   El número de dimensiones y la longitud de cada dimensión se establecen al crear la instancia de matriz. No se pueden cambiar estos valores durante la vigencia de la instancia.  
  
-   Los valores predeterminados de los elementos numéricos de matriz se establecen en cero y los elementos de referencia se establecen en null.  
  
-   Una matriz escalonada es una matriz de matrices y, por consiguiente, sus elementos son tipos de referencia y se inicializan en `null`.  
  
-   Las matrices se indexan con cero: una matriz con `n` elementos se indexa de `0` a `n-1`.  
  
-   Los elementos de una matriz puede ser cualquier tipo, incluido un tipo de matriz.  
  
-   Los tipos de matriz son [tipos de referencia](../../../csharp/language-reference/keywords/reference-types.md) que proceden del tipo base abstracto <xref:System.Array>. Como este tipo implementa <xref:System.Collections.IEnumerable> y <xref:System.Collections.Generic.IEnumerable%601>, puede usar la iteración [foreach](../../../csharp/language-reference/keywords/foreach-in.md) en todas las matrices de C#.  
  
## <a name="related-sections"></a>Secciones relacionadas  
  
-   [Matrices como objetos](../../../csharp/programming-guide/arrays/arrays-as-objects.md)  
  
-   [Utilizar foreach con matrices](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
-   [Pasar matrices como argumentos](../../../csharp/programming-guide/arrays/passing-arrays-as-arguments.md)  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Colecciones](../../../csharp/programming-guide/concepts/collections.md)

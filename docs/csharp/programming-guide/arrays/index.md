---
title: "Matrices (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
caps.latest.revision: 33
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1035caae15b64d1311305cfe4c1f1a74c80ed19a
ms.contentlocale: es-es
ms.lasthandoff: 09/25/2017

---
# <a name="arrays-c-programming-guide"></a>Matrices (Guía de programación de C#)
Puede almacenar varias variables del mismo tipo en una estructura de datos de matriz. Puede declarar una matriz mediante la especificación del tipo de sus elementos.  
  
 `type[] arrayName;`  
  
 Los ejemplos siguientes crean matrices unidimensionales, multidimensionales y escalonadas:  
  
 [!code-cs[csProgGuideArrays#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/index_1.cs)]  
  
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
  
-   [Pasar matrices mediante Ref y Out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)   
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Colecciones](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)   
 [Tipo de colección de matrices](http://msdn.microsoft.com/en-us/8a9964de-8941-47b1-a3cf-a01bc88db9e8)


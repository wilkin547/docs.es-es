---
title: 'Matrices como objetos: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
ms.openlocfilehash: 8500cf508b77a0fa7e348ce0fe6b1f16fd2bab25
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977188"
---
# <a name="arrays-as-objects-c-programming-guide"></a>Utilizar matrices como objetos (Guía de programación de C#)

En C#, las matrices son actualmente objetos, y no simplemente regiones direccionables de memoria contigua como en C y C++. <xref:System.Array> es el tipo base abstracto de todos los tipos de matriz. Puede usar las propiedades, y otros miembros de clase, que tiene <xref:System.Array>. Un ejemplo de esto sería usar la propiedad <xref:System.Array.Length%2A> para obtener la longitud de una matriz. El código siguiente asigna la longitud de la matriz `numbers`, que es `5`, a una variable denominada `lengthOfNumbers`:  
  
 [!code-csharp[csProgGuideArrays#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#3)]  
  
 La clase <xref:System.Array> proporciona muchos otros métodos útiles y propiedades para ordenar, buscar y copiar matrices.  
  
## <a name="example"></a>Ejemplo

 Este ejemplo usa la propiedad <xref:System.Array.Rank%2A> para mostrar el número de dimensiones de una matriz.  
  
 [!code-csharp[csProgGuideArrays#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#2)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Matrices](../../../csharp/programming-guide/arrays/index.md)
- [Matrices unidimensionales](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)
- [Matrices multidimensionales](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)
- [Matrices escalonadas](../../../csharp/programming-guide/arrays/jagged-arrays.md)

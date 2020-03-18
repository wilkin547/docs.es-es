---
title: 'Matrices como objetos: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
ms.openlocfilehash: d8b929eccf9be259874d03dd93f49a49798bb349
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75715093"
---
# <a name="arrays-as-objects-c-programming-guide"></a>Utilizar matrices como objetos (Guía de programación de C#)

En C#, las matrices son actualmente objetos, y no simplemente regiones direccionables de memoria contigua como en C y C++. <xref:System.Array> es el tipo base abstracto de todos los tipos de matriz. Puede usar las propiedades, y otros miembros de clase, que tiene <xref:System.Array>. Un ejemplo de esto sería usar la propiedad <xref:System.Array.Length%2A> para obtener la longitud de una matriz. El código siguiente asigna la longitud de la matriz `numbers`, que es `5`, a una variable denominada `lengthOfNumbers`:

[!code-csharp[csProgGuideArrays#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#3)]

La clase <xref:System.Array> proporciona muchos otros métodos útiles y propiedades para ordenar, buscar y copiar matrices.

## <a name="example"></a>Ejemplo

Este ejemplo usa la propiedad <xref:System.Array.Rank%2A> para mostrar el número de dimensiones de una matriz.

[!code-csharp[csProgGuideArrays#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#2)]

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Matrices](./index.md)
- [Matrices unidimensionales](./single-dimensional-arrays.md)
- [Matrices multidimensionales](./multidimensional-arrays.md)
- [Matrices escalonadas](./jagged-arrays.md)

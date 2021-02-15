---
description: 'Más información acerca de cómo: ordenar una matriz en Visual Basic'
title: Procedimiento para ordenar una matriz
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: ea030b63dbbb5f5ea1d6160757afe2e9b58f7c21
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100462768"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a><span data-ttu-id="bd5e1-103">Cómo: ordenar una matriz en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bd5e1-103">How to: sort an array in Visual Basic</span></span>

<span data-ttu-id="bd5e1-104">En este artículo se muestra un ejemplo de cómo ordenar una matriz de cadenas en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="bd5e1-104">This article shows an example of how to sort an array of strings in Visual Basic.</span></span>

## <a name="example"></a><span data-ttu-id="bd5e1-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bd5e1-105">Example</span></span>

<span data-ttu-id="bd5e1-106">En este ejemplo se declara una matriz de `String` objetos denominada `zooAnimals` , se rellena y, a continuación, se ordena alfabéticamente:</span><span class="sxs-lookup"><span data-stu-id="bd5e1-106">This example declares an array of `String` objects named `zooAnimals`, populates it, and then sorts it alphabetically:</span></span>
  
```vb
Private Sub SortAnimals()
    Dim zooAnimals(2) As String
    zooAnimals(0) = "lion"
    zooAnimals(1) = "turtle"
    zooAnimals(2) = "ostrich"
    Array.Sort(zooAnimals)
End Sub
```

## <a name="robust-programming"></a><span data-ttu-id="bd5e1-107">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="bd5e1-107">Robust programming</span></span>

<span data-ttu-id="bd5e1-108">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="bd5e1-108">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="bd5e1-109">La matriz está vacía ( <xref:System.ArgumentNullException> clase).</span><span class="sxs-lookup"><span data-stu-id="bd5e1-109">Array is empty (<xref:System.ArgumentNullException> class).</span></span>
- <span data-ttu-id="bd5e1-110">La matriz es multidimensional ( <xref:System.RankException> clase).</span><span class="sxs-lookup"><span data-stu-id="bd5e1-110">Array is multidimensional (<xref:System.RankException> class).</span></span>
- <span data-ttu-id="bd5e1-111">Uno o varios elementos de la matriz no implementan la <xref:System.IComparable> interfaz ( <xref:System.InvalidOperationException> clase).</span><span class="sxs-lookup"><span data-stu-id="bd5e1-111">One or more elements of the array don't implement the <xref:System.IComparable> interface (<xref:System.InvalidOperationException> class).</span></span>

## <a name="see-also"></a><span data-ttu-id="bd5e1-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd5e1-112">See also</span></span>

- <xref:System.Array.Sort%2A?displayProperty=nameWithType>
- [<span data-ttu-id="bd5e1-113">Matrices</span><span class="sxs-lookup"><span data-stu-id="bd5e1-113">Arrays</span></span>](index.md)
- [<span data-ttu-id="bd5e1-114">Solución de problemas de matrices</span><span class="sxs-lookup"><span data-stu-id="bd5e1-114">Troubleshooting Arrays</span></span>](troubleshooting-arrays.md)
- [<span data-ttu-id="bd5e1-115">Colecciones</span><span class="sxs-lookup"><span data-stu-id="bd5e1-115">Collections</span></span>](../../concepts/collections.md)
- [<span data-ttu-id="bd5e1-116">Instrucción For Each...Next</span><span class="sxs-lookup"><span data-stu-id="bd5e1-116">For Each...Next Statement</span></span>](../../../language-reference/statements/for-each-next-statement.md)

---
title: Procedimiento Ordenar una matriz en Visual Basic
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: 467d1bcce6bda2feb5a8e59c152cb292d753e79b
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700976"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a><span data-ttu-id="bed85-102">Cómo: ordenar una matriz en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bed85-102">How to: sort an array in Visual Basic</span></span>

<span data-ttu-id="bed85-103">En este artículo se muestra un ejemplo de cómo ordenar una matriz de cadenas en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="bed85-103">This article shows an example of how to sort an array of strings in Visual Basic.</span></span>

## <a name="example"></a><span data-ttu-id="bed85-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bed85-104">Example</span></span>

<span data-ttu-id="bed85-105">En este ejemplo se declara una matriz de objetos `String` denominada `zooAnimals`, se rellena y, a continuación, se ordena alfabéticamente:</span><span class="sxs-lookup"><span data-stu-id="bed85-105">This example declares an array of `String` objects named `zooAnimals`, populates it, and then sorts it alphabetically:</span></span>
  
```vb
Private Sub SortAnimals()
    Dim zooAnimals(2) As String
    zooAnimals(0) = "lion"
    zooAnimals(1) = "turtle"
    zooAnimals(2) = "ostrich"
    Array.Sort(zooAnimals)
End Sub
```

## <a name="robust-programming"></a><span data-ttu-id="bed85-106">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="bed85-106">Robust programming</span></span>

<span data-ttu-id="bed85-107">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="bed85-107">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="bed85-108">La matriz está vacía (clase <xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="bed85-108">Array is empty (<xref:System.ArgumentNullException> class).</span></span>
- <span data-ttu-id="bed85-109">La matriz es multidimensional (clase <xref:System.RankException>).</span><span class="sxs-lookup"><span data-stu-id="bed85-109">Array is multidimensional (<xref:System.RankException> class).</span></span>
- <span data-ttu-id="bed85-110">Uno o varios elementos de la matriz no implementan la interfaz <xref:System.IComparable> (clase <xref:System.InvalidOperationException>).</span><span class="sxs-lookup"><span data-stu-id="bed85-110">One or more elements of the array don't implement the <xref:System.IComparable> interface (<xref:System.InvalidOperationException> class).</span></span>

## <a name="see-also"></a><span data-ttu-id="bed85-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="bed85-111">See also</span></span>

- <xref:System.Array.Sort%2A?displayProperty=nameWithType>
- [<span data-ttu-id="bed85-112">Matrices</span><span class="sxs-lookup"><span data-stu-id="bed85-112">Arrays</span></span>](index.md)
- [<span data-ttu-id="bed85-113">Solución de problemas de matrices</span><span class="sxs-lookup"><span data-stu-id="bed85-113">Troubleshooting Arrays</span></span>](troubleshooting-arrays.md)
- [<span data-ttu-id="bed85-114">Colecciones</span><span class="sxs-lookup"><span data-stu-id="bed85-114">Collections</span></span>](../../concepts/collections.md)
- [<span data-ttu-id="bed85-115">For Each...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="bed85-115">For Each...Next Statement</span></span>](../../../language-reference/statements/for-each-next-statement.md)

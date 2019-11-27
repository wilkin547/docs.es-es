---
title: 'Cómo: ordenar una matriz'
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: 3fb9af8de0fc86075fdccd64506c855c1c720660
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351851"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a><span data-ttu-id="60598-102">Cómo: ordenar una matriz en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="60598-102">How to: sort an array in Visual Basic</span></span>

<span data-ttu-id="60598-103">En este artículo se muestra un ejemplo de cómo ordenar una matriz de cadenas en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="60598-103">This article shows an example of how to sort an array of strings in Visual Basic.</span></span>

## <a name="example"></a><span data-ttu-id="60598-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="60598-104">Example</span></span>

<span data-ttu-id="60598-105">En este ejemplo se declara una matriz de objetos de `String` denominada `zooAnimals`, se rellena y, a continuación, se ordena alfabéticamente:</span><span class="sxs-lookup"><span data-stu-id="60598-105">This example declares an array of `String` objects named `zooAnimals`, populates it, and then sorts it alphabetically:</span></span>
  
```vb
Private Sub SortAnimals()
    Dim zooAnimals(2) As String
    zooAnimals(0) = "lion"
    zooAnimals(1) = "turtle"
    zooAnimals(2) = "ostrich"
    Array.Sort(zooAnimals)
End Sub
```

## <a name="robust-programming"></a><span data-ttu-id="60598-106">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="60598-106">Robust programming</span></span>

<span data-ttu-id="60598-107">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="60598-107">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="60598-108">La matriz está vacía (clase<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="60598-108">Array is empty (<xref:System.ArgumentNullException> class).</span></span>
- <span data-ttu-id="60598-109">La matriz es multidimensional (clase<xref:System.RankException>).</span><span class="sxs-lookup"><span data-stu-id="60598-109">Array is multidimensional (<xref:System.RankException> class).</span></span>
- <span data-ttu-id="60598-110">Uno o varios elementos de la matriz no implementan la interfaz <xref:System.IComparable> (clase<xref:System.InvalidOperationException>).</span><span class="sxs-lookup"><span data-stu-id="60598-110">One or more elements of the array don't implement the <xref:System.IComparable> interface (<xref:System.InvalidOperationException> class).</span></span>

## <a name="see-also"></a><span data-ttu-id="60598-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="60598-111">See also</span></span>

- <xref:System.Array.Sort%2A?displayProperty=nameWithType>
- [<span data-ttu-id="60598-112">Matrices</span><span class="sxs-lookup"><span data-stu-id="60598-112">Arrays</span></span>](index.md)
- [<span data-ttu-id="60598-113">Solución de problemas de matrices</span><span class="sxs-lookup"><span data-stu-id="60598-113">Troubleshooting Arrays</span></span>](troubleshooting-arrays.md)
- [<span data-ttu-id="60598-114">Colecciones</span><span class="sxs-lookup"><span data-stu-id="60598-114">Collections</span></span>](../../concepts/collections.md)
- [<span data-ttu-id="60598-115">For Each...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="60598-115">For Each...Next Statement</span></span>](../../../language-reference/statements/for-each-next-statement.md)

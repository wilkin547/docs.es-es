---
title: Procedimiento Ordenar una matriz en Visual Basic
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: 0b04bfbedf9d7266d1b2e190fa85b8a64cf6efbf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558441"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a><span data-ttu-id="e18fc-102">Procedimiento Ordenar una matriz en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e18fc-102">How to: Sort An Array in Visual Basic</span></span>
<span data-ttu-id="e18fc-103">En este ejemplo declara una matriz de `String` objetos denominados `zooAnimals`, lo rellena y, a continuación, ordena alfabéticamente.</span><span class="sxs-lookup"><span data-stu-id="e18fc-103">This example declares an array of `String` objects named `zooAnimals`, populates it, and then sorts it alphabetically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e18fc-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e18fc-104">Example</span></span>  
  
```  
Private Sub sortAnimals()  
    Dim zooAnimals(2) As String  
    zooAnimals(0) = "lion"  
    zooAnimals(1) = "turtle"  
    zooAnimals(2) = "ostrich"  
    Array.Sort(zooAnimals)  
End Sub  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e18fc-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="e18fc-105">Compiling the Code</span></span>  
 <span data-ttu-id="e18fc-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="e18fc-106">This example requires:</span></span>  
  
-   <span data-ttu-id="e18fc-107">Acceso a Mscorlib.dll y <xref:System> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e18fc-107">Access to Mscorlib.dll and the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e18fc-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="e18fc-108">Robust Programming</span></span>  
 <span data-ttu-id="e18fc-109">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="e18fc-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="e18fc-110">Matriz está vacía (<xref:System.ArgumentNullException> clase)</span><span class="sxs-lookup"><span data-stu-id="e18fc-110">Array is empty (<xref:System.ArgumentNullException> class)</span></span>  
  
-   <span data-ttu-id="e18fc-111">La matriz es multidimensional (<xref:System.RankException> clase)</span><span class="sxs-lookup"><span data-stu-id="e18fc-111">Array is multidimensional (<xref:System.RankException> class)</span></span>  
  
-   <span data-ttu-id="e18fc-112">Uno o más elementos de la matriz no implementan la <xref:System.IComparable> interfaz (<xref:System.InvalidOperationException> clase)</span><span class="sxs-lookup"><span data-stu-id="e18fc-112">One or more elements of the array do not implement the <xref:System.IComparable> interface (<xref:System.InvalidOperationException> class)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e18fc-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e18fc-113">See also</span></span>
- <xref:System.Array.Sort%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e18fc-114">Matrices</span><span class="sxs-lookup"><span data-stu-id="e18fc-114">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="e18fc-115">Solución de problemas de matrices</span><span class="sxs-lookup"><span data-stu-id="e18fc-115">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
- [<span data-ttu-id="e18fc-116">Colecciones</span><span class="sxs-lookup"><span data-stu-id="e18fc-116">Collections</span></span>](../../concepts/collections.md)
- [<span data-ttu-id="e18fc-117">For Each...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e18fc-117">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)

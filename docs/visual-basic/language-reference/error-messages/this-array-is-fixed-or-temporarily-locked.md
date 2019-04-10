---
title: Esta matriz es fija o está bloqueada temporalmente (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: c74d9524ff64101ba6002e133b93c9b80e8f50a9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59337973"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a><span data-ttu-id="c52d3-102">Esta matriz es fija o está bloqueada temporalmente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c52d3-102">This array is fixed or temporarily locked (Visual Basic)</span></span>
<span data-ttu-id="c52d3-103">Este error tiene las siguientes causas posibles:</span><span class="sxs-lookup"><span data-stu-id="c52d3-103">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="c52d3-104">Uso de `ReDim` para cambiar el número de elementos de una matriz de tamaño fijo.</span><span class="sxs-lookup"><span data-stu-id="c52d3-104">Using `ReDim` to change the number of elements of a fixed-size array.</span></span>  
  
-   <span data-ttu-id="c52d3-105">Cambiar el tamaño de una matriz dinámica de nivel de módulo, en el que se ha pasado un elemento como un argumento a un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c52d3-105">Redimensioning a module-level dynamic array, in which one element has been passed as an argument to a procedure.</span></span> <span data-ttu-id="c52d3-106">Si se pasa un elemento, la matriz está bloqueada para evitar la desasignación de memoria para el parámetro de referencia dentro del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c52d3-106">If an element is passed, the array is locked to prevent deallocating memory for the reference parameter within the procedure.</span></span>  
  
-   <span data-ttu-id="c52d3-107">Al intentar asignar un valor a un `Variant` variable que contiene una matriz, pero la `Variant` está bloqueada actualmente.</span><span class="sxs-lookup"><span data-stu-id="c52d3-107">Attempting to assign a value to a `Variant` variable containing an array, but the `Variant` is currently locked.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c52d3-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="c52d3-108">To correct this error</span></span>  
  
1. <span data-ttu-id="c52d3-109">Convertir la matriz original dinámico en lugar de fija declarándola con `ReDim` (si la matriz se declara dentro de un procedimiento,) o declarando sin especificar el número de elementos (si la matriz se declara en el nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="c52d3-109">Make the original array dynamic rather than fixed by declaring it with `ReDim` (if the array is declared within a procedure), or by declaring it without specifying the number of elements (if the array is declared at the module level.</span></span>  
  
2. <span data-ttu-id="c52d3-110">Determinar si realmente necesita pasar el elemento, ya que es visible dentro de todos los procedimientos en el módulo.</span><span class="sxs-lookup"><span data-stu-id="c52d3-110">Determine whether you really need to pass the element, since it is visible within all procedures in the module.</span></span>  
  
3. <span data-ttu-id="c52d3-111">Determinar la causa del bloqueo del `Variant` y soluciónelo.</span><span class="sxs-lookup"><span data-stu-id="c52d3-111">Determine what is locking the `Variant` and remedy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c52d3-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="c52d3-112">See also</span></span>

- [<span data-ttu-id="c52d3-113">Matrices</span><span class="sxs-lookup"><span data-stu-id="c52d3-113">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)

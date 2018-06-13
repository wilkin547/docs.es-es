---
title: Esta matriz es fija o está bloqueada temporalmente (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: e912bd202603d9a0f427418708ad584c7d6203e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593569"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a><span data-ttu-id="e4635-102">Esta matriz es fija o está bloqueada temporalmente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e4635-102">This array is fixed or temporarily locked (Visual Basic)</span></span>
<span data-ttu-id="e4635-103">Este error tiene las siguientes causas posibles:</span><span class="sxs-lookup"><span data-stu-id="e4635-103">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="e4635-104">Usar `ReDim` para cambiar el número de elementos de una matriz de tamaño fijo.</span><span class="sxs-lookup"><span data-stu-id="e4635-104">Using `ReDim` to change the number of elements of a fixed-size array.</span></span>  
  
-   <span data-ttu-id="e4635-105">Cambiar el tamaño de una matriz dinámica de nivel de módulo, en el que se ha pasado un elemento como un argumento a un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e4635-105">Redimensioning a module-level dynamic array, in which one element has been passed as an argument to a procedure.</span></span> <span data-ttu-id="e4635-106">Si se pasa un elemento, la matriz está bloqueada para evitar la desasignación de memoria para el parámetro de referencia dentro del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e4635-106">If an element is passed, the array is locked to prevent deallocating memory for the reference parameter within the procedure.</span></span>  
  
-   <span data-ttu-id="e4635-107">Intenta asignar un valor a un `Variant` variable que contiene una matriz, pero la `Variant` está bloqueado actualmente.</span><span class="sxs-lookup"><span data-stu-id="e4635-107">Attempting to assign a value to a `Variant` variable containing an array, but the `Variant` is currently locked.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e4635-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="e4635-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="e4635-109">Hacer que la matriz original dinámica en lugar de fija declarándola con `ReDim` (si la matriz se declara dentro de un procedimiento), o mediante la declaración sin especificar el número de elementos (si la matriz se declara en el nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="e4635-109">Make the original array dynamic rather than fixed by declaring it with `ReDim` (if the array is declared within a procedure), or by declaring it without specifying the number of elements (if the array is declared at the module level.</span></span>  
  
2.  <span data-ttu-id="e4635-110">Determine si realmente necesita pasar el elemento, ya que es visible dentro de todos los procedimientos en el módulo.</span><span class="sxs-lookup"><span data-stu-id="e4635-110">Determine whether you really need to pass the element, since it is visible within all procedures in the module.</span></span>  
  
3.  <span data-ttu-id="e4635-111">Determinar la causa del bloqueo del `Variant` y soluciónelo.</span><span class="sxs-lookup"><span data-stu-id="e4635-111">Determine what is locking the `Variant` and remedy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4635-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4635-112">See Also</span></span>  
 [<span data-ttu-id="e4635-113">Matrices</span><span class="sxs-lookup"><span data-stu-id="e4635-113">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)

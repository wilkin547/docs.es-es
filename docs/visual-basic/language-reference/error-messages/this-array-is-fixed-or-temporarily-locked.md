---
title: Matriz fija o bloqueada temporalmente
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: 8d5e4add2d92a575126fb934ac3874a2e37685f5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350785"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a><span data-ttu-id="1a2c0-102">Esta matriz es fija o está bloqueada temporalmente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a2c0-102">This array is fixed or temporarily locked (Visual Basic)</span></span>
<span data-ttu-id="1a2c0-103">Este error tiene las siguientes causas posibles:</span><span class="sxs-lookup"><span data-stu-id="1a2c0-103">This error has the following possible causes:</span></span>  
  
- <span data-ttu-id="1a2c0-104">Usar `ReDim` para cambiar el número de elementos de una matriz de tamaño fijo.</span><span class="sxs-lookup"><span data-stu-id="1a2c0-104">Using `ReDim` to change the number of elements of a fixed-size array.</span></span>  
  
- <span data-ttu-id="1a2c0-105">Redimensionar una matriz dinámica de nivel de módulo, en la que se ha pasado un elemento como argumento a un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="1a2c0-105">Redimensioning a module-level dynamic array, in which one element has been passed as an argument to a procedure.</span></span> <span data-ttu-id="1a2c0-106">Si se pasa un elemento, la matriz está bloqueada para evitar la desasignación de memoria para el parámetro de referencia dentro del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="1a2c0-106">If an element is passed, the array is locked to prevent deallocating memory for the reference parameter within the procedure.</span></span>  
  
- <span data-ttu-id="1a2c0-107">Se intentó asignar un valor a una variable `Variant` que contiene una matriz, pero el `Variant` está bloqueado actualmente.</span><span class="sxs-lookup"><span data-stu-id="1a2c0-107">Attempting to assign a value to a `Variant` variable containing an array, but the `Variant` is currently locked.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1a2c0-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="1a2c0-108">To correct this error</span></span>  
  
1. <span data-ttu-id="1a2c0-109">Haga que la matriz original sea dinámica en lugar de fija declarándola con `ReDim` (si la matriz se declara dentro de un procedimiento) o declarándolo sin especificar el número de elementos (si la matriz se declara en el nivel de módulo).</span><span class="sxs-lookup"><span data-stu-id="1a2c0-109">Make the original array dynamic rather than fixed by declaring it with `ReDim` (if the array is declared within a procedure), or by declaring it without specifying the number of elements (if the array is declared at the module level.</span></span>  
  
2. <span data-ttu-id="1a2c0-110">Determine si realmente necesita pasar el elemento, ya que es visible en todos los procedimientos del módulo.</span><span class="sxs-lookup"><span data-stu-id="1a2c0-110">Determine whether you really need to pass the element, since it is visible within all procedures in the module.</span></span>  
  
3. <span data-ttu-id="1a2c0-111">Determine qué está bloqueando el `Variant` y Remedy.</span><span class="sxs-lookup"><span data-stu-id="1a2c0-111">Determine what is locking the `Variant` and remedy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a2c0-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a2c0-112">See also</span></span>

- [<span data-ttu-id="1a2c0-113">Matrices</span><span class="sxs-lookup"><span data-stu-id="1a2c0-113">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)

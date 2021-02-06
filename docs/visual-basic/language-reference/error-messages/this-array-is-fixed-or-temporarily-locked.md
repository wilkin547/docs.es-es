---
description: 'Más información acerca de: esta matriz es fija o está bloqueada temporalmente (Visual Basic)'
title: Matriz fija o bloqueada temporalmente
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: 034bcc23055f7fb3f707e1105589a4526e6f9009
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641218"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a><span data-ttu-id="4902e-103">Esta matriz es fija o está bloqueada temporalmente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4902e-103">This array is fixed or temporarily locked (Visual Basic)</span></span>

<span data-ttu-id="4902e-104">Este error tiene las siguientes causas posibles:</span><span class="sxs-lookup"><span data-stu-id="4902e-104">This error has the following possible causes:</span></span>  
  
- <span data-ttu-id="4902e-105">Usar `ReDim` para cambiar el número de elementos de una matriz de tamaño fijo.</span><span class="sxs-lookup"><span data-stu-id="4902e-105">Using `ReDim` to change the number of elements of a fixed-size array.</span></span>  
  
- <span data-ttu-id="4902e-106">Redimensionar una matriz dinámica de nivel de módulo, en la que se ha pasado un elemento como argumento a un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4902e-106">Redimensioning a module-level dynamic array, in which one element has been passed as an argument to a procedure.</span></span> <span data-ttu-id="4902e-107">Si se pasa un elemento, la matriz está bloqueada para evitar la desasignación de memoria para el parámetro de referencia dentro del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4902e-107">If an element is passed, the array is locked to prevent deallocating memory for the reference parameter within the procedure.</span></span>  
  
- <span data-ttu-id="4902e-108">Se está intentando asignar un valor a una `Variant` variable que contiene una matriz, pero `Variant` está bloqueado actualmente.</span><span class="sxs-lookup"><span data-stu-id="4902e-108">Attempting to assign a value to a `Variant` variable containing an array, but the `Variant` is currently locked.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4902e-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="4902e-109">To correct this error</span></span>  
  
1. <span data-ttu-id="4902e-110">Haga que la matriz original sea dinámica en lugar de fija declarándola con `ReDim` (si la matriz se declara dentro de un procedimiento) o declarándolo sin especificar el número de elementos (si la matriz se declara en el nivel de módulo).</span><span class="sxs-lookup"><span data-stu-id="4902e-110">Make the original array dynamic rather than fixed by declaring it with `ReDim` (if the array is declared within a procedure), or by declaring it without specifying the number of elements (if the array is declared at the module level.</span></span>  
  
2. <span data-ttu-id="4902e-111">Determine si realmente necesita pasar el elemento, ya que es visible en todos los procedimientos del módulo.</span><span class="sxs-lookup"><span data-stu-id="4902e-111">Determine whether you really need to pass the element, since it is visible within all procedures in the module.</span></span>  
  
3. <span data-ttu-id="4902e-112">Determine qué está bloqueando `Variant` y soluciónelo.</span><span class="sxs-lookup"><span data-stu-id="4902e-112">Determine what is locking the `Variant` and remedy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4902e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="4902e-113">See also</span></span>

- [<span data-ttu-id="4902e-114">Matrices</span><span class="sxs-lookup"><span data-stu-id="4902e-114">Arrays</span></span>](../../programming-guide/language-features/arrays/index.md)

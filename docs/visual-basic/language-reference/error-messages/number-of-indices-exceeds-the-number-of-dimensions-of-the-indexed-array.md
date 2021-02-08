---
description: 'Más información acerca de: BC30106: el número de índices supera el número de dimensiones de la matriz indizada'
title: El número de índices sobrepasa el número de dimensiones de la matriz indizada
ms.date: 07/20/2015
f1_keywords:
- bc30106
- vbc30106
helpviewer_keywords:
- BC30106
ms.assetid: 2c5363e1-62c2-4f5a-b675-c7337aeb363d
ms.openlocfilehash: 35ec1ea106e67022046179412b142cd92712c822
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795616"
---
# <a name="bc30106-number-of-indices-exceeds-the-number-of-dimensions-of-the-indexed-array"></a><span data-ttu-id="7eeb1-103">BC30106: el número de índices supera el número de dimensiones de la matriz indizada</span><span class="sxs-lookup"><span data-stu-id="7eeb1-103">BC30106: Number of indices exceeds the number of dimensions of the indexed array</span></span>

<span data-ttu-id="7eeb1-104">El número de índices usado para obtener acceso a un elemento de matriz debe ser exactamente igual al rango de la matriz, es decir, el número de dimensiones que tiene declaradas.</span><span class="sxs-lookup"><span data-stu-id="7eeb1-104">The number of indices used to access an array element must be exactly the same as the rank of the array, that is, the number of dimensions declared for it.</span></span>

 <span data-ttu-id="7eeb1-105">**Identificador de error:** BC30106</span><span class="sxs-lookup"><span data-stu-id="7eeb1-105">**Error ID:** BC30106</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="7eeb1-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="7eeb1-106">To correct this error</span></span>

- <span data-ttu-id="7eeb1-107">Quite los subíndices de la referencia de la matriz hasta que el número total de subíndices sea igual al rango de la matriz.</span><span class="sxs-lookup"><span data-stu-id="7eeb1-107">Remove subscripts from the array reference until the total number of subscripts equals the rank of the array.</span></span> <span data-ttu-id="7eeb1-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7eeb1-108">For example:</span></span>

    ```vb
    Dim gameBoard(3, 3) As String

    ' Incorrect code. The array has two dimensions.
    gameBoard(1, 1, 1) = "X"
    gameBoard(2, 1, 1) = "O"

    ' Correct code.
    gameBoard(0, 0) = "X"
    gameBoard(1, 0) = "O"
    ```

## <a name="see-also"></a><span data-ttu-id="7eeb1-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="7eeb1-109">See also</span></span>

- [<span data-ttu-id="7eeb1-110">Matrices</span><span class="sxs-lookup"><span data-stu-id="7eeb1-110">Arrays</span></span>](../../programming-guide/language-features/arrays/index.md)

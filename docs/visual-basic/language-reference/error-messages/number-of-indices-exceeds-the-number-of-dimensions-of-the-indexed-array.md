---
title: El número de índices sobrepasa el número de dimensiones de la matriz indizada
ms.date: 07/20/2015
f1_keywords:
- bc30106
- vbc30106
helpviewer_keywords:
- BC30106
ms.assetid: 2c5363e1-62c2-4f5a-b675-c7337aeb363d
ms.openlocfilehash: 01659205f271b089fe4e8aa87cf7a8c44e7a4000
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58837999"
---
# <a name="number-of-indices-exceeds-the-number-of-dimensions-of-the-indexed-array"></a><span data-ttu-id="b8d2f-102">El número de índices sobrepasa el número de dimensiones de la matriz indizada</span><span class="sxs-lookup"><span data-stu-id="b8d2f-102">Number of indices exceeds the number of dimensions of the indexed array</span></span>
<span data-ttu-id="b8d2f-103">El número de índices usado para obtener acceso a un elemento de matriz debe ser exactamente igual al rango de la matriz, es decir, el número de dimensiones que tiene declaradas.</span><span class="sxs-lookup"><span data-stu-id="b8d2f-103">The number of indices used to access an array element must be exactly the same as the rank of the array, that is, the number of dimensions declared for it.</span></span>  
  
 <span data-ttu-id="b8d2f-104">**Identificador de error:** BC30106</span><span class="sxs-lookup"><span data-stu-id="b8d2f-104">**Error ID:** BC30106</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b8d2f-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="b8d2f-105">To correct this error</span></span>  
  
-   <span data-ttu-id="b8d2f-106">Quite los subíndices de la referencia de la matriz hasta que el número total de subíndices sea igual al rango de la matriz.</span><span class="sxs-lookup"><span data-stu-id="b8d2f-106">Remove subscripts from the array reference until the total number of subscripts equals the rank of the array.</span></span> <span data-ttu-id="b8d2f-107">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b8d2f-107">For example:</span></span>  
  
    ```vb  
    Dim gameBoard(3, 3) As String  
  
    ' Incorrect code. The array has two dimensions.  
    gameBoard(1, 1, 1) = "X"  
    gameBoard(2, 1, 1) = "O"  
  
    ' Correct code.  
    gameBoard(0, 0) = "X"  
    gameBoard(1, 0) = "O"  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b8d2f-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8d2f-108">See also</span></span>

- [<span data-ttu-id="b8d2f-109">Matrices</span><span class="sxs-lookup"><span data-stu-id="b8d2f-109">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)

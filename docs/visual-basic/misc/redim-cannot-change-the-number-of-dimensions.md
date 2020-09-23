---
title: "'ReDim' no puede cambiar el número de dimensiones."
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: 8d80af7682f27b403e0f463fdbebbcac71f18b01
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077376"
---
# <a name="redim-cannot-change-the-number-of-dimensions"></a><span data-ttu-id="be0c6-102">'ReDim' no puede cambiar el número de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="be0c6-102">'ReDim' cannot change the number of dimensions</span></span>

<span data-ttu-id="be0c6-103">Una operación intenta usar la instrucción `ReDim` para cambiar el rango (número de dimensiones) de una matriz.</span><span class="sxs-lookup"><span data-stu-id="be0c6-103">An operation attempts to use the `ReDim` statement to change the rank (number of dimensions) of an array.</span></span> <span data-ttu-id="be0c6-104">`ReDim` puede cambiar el tamaño de una o más dimensiones de una matriz que ya se ha declarado formalmente, pero no puede cambiar el rango de la matriz.</span><span class="sxs-lookup"><span data-stu-id="be0c6-104">`ReDim` can change the size of one or more dimensions of an array that has already been formally declared, but it cannot change an array's rank.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="be0c6-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="be0c6-105">To correct this error</span></span>  
  
- <span data-ttu-id="be0c6-106">Asegúrese de que intenta cambiar el rango de la matriz y no los tamaños de sus dimensiones y, si es posible, use `Dim` para declarar una nueva matriz con el rango deseado.</span><span class="sxs-lookup"><span data-stu-id="be0c6-106">Ensure that you intend to change the array's rank and not the sizes of its dimensions, and if possible, use `Dim` to declare a new array with the desired rank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be0c6-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="be0c6-107">See also</span></span>

- [<span data-ttu-id="be0c6-108">Matrices en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="be0c6-108">Arrays in Visual Basic</span></span>](../programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="be0c6-109">Dimensiones de matriz en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="be0c6-109">Array dimensions in Visual Basic</span></span>](../programming-guide/language-features/arrays/array-dimensions.md)
- [<span data-ttu-id="be0c6-110">Instrucción ReDim</span><span class="sxs-lookup"><span data-stu-id="be0c6-110">ReDim Statement</span></span>](../language-reference/statements/redim-statement.md)
- [<span data-ttu-id="be0c6-111">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="be0c6-111">Dim Statement</span></span>](../language-reference/statements/dim-statement.md)

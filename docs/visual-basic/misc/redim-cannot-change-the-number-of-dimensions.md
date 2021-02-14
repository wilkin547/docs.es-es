---
description: "Más información acerca de: ' ReDim ' no puede cambiar el número de dimensiones"
title: "'ReDim' no puede cambiar el número de dimensiones."
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: 4552dd6b1cce54813b57e5b8c76a3580b81b8def
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100454643"
---
# <a name="redim-cannot-change-the-number-of-dimensions"></a><span data-ttu-id="b3411-103">'ReDim' no puede cambiar el número de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="b3411-103">'ReDim' cannot change the number of dimensions</span></span>

<span data-ttu-id="b3411-104">Una operación intenta usar la instrucción `ReDim` para cambiar el rango (número de dimensiones) de una matriz.</span><span class="sxs-lookup"><span data-stu-id="b3411-104">An operation attempts to use the `ReDim` statement to change the rank (number of dimensions) of an array.</span></span> <span data-ttu-id="b3411-105">`ReDim` puede cambiar el tamaño de una o más dimensiones de una matriz que ya se ha declarado formalmente, pero no puede cambiar el rango de la matriz.</span><span class="sxs-lookup"><span data-stu-id="b3411-105">`ReDim` can change the size of one or more dimensions of an array that has already been formally declared, but it cannot change an array's rank.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b3411-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="b3411-106">To correct this error</span></span>  
  
- <span data-ttu-id="b3411-107">Asegúrese de que intenta cambiar el rango de la matriz y no los tamaños de sus dimensiones y, si es posible, use `Dim` para declarar una nueva matriz con el rango deseado.</span><span class="sxs-lookup"><span data-stu-id="b3411-107">Ensure that you intend to change the array's rank and not the sizes of its dimensions, and if possible, use `Dim` to declare a new array with the desired rank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3411-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b3411-108">See also</span></span>

- [<span data-ttu-id="b3411-109">Matrices en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b3411-109">Arrays in Visual Basic</span></span>](../programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="b3411-110">Dimensiones de matriz en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b3411-110">Array dimensions in Visual Basic</span></span>](../programming-guide/language-features/arrays/array-dimensions.md)
- [<span data-ttu-id="b3411-111">Instrucción ReDim</span><span class="sxs-lookup"><span data-stu-id="b3411-111">ReDim Statement</span></span>](../language-reference/statements/redim-statement.md)
- [<span data-ttu-id="b3411-112">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="b3411-112">Dim Statement</span></span>](../language-reference/statements/dim-statement.md)

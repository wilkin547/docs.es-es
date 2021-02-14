---
description: "Más información sobre: ' ReDim ' solo puede cambiar la dimensión situada más a la derecha"
title: "'ReDim' solo puede cambiar la dimensión situada más a la derecha"
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: 6816e5b2e9c7c079b78ce53e168f46b337831512
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100454695"
---
# <a name="redim-can-only-change-the-right-most-dimension"></a><span data-ttu-id="8bd6f-103">'ReDim' solo puede cambiar la dimensión situada más a la derecha</span><span class="sxs-lookup"><span data-stu-id="8bd6f-103">'ReDim' can only change the right-most dimension</span></span>

<span data-ttu-id="8bd6f-104">Una instrucción `ReDim` intentó usar la palabra clave `Preserve` para cambiar una dimensión de una matriz que no es la última dimensión.</span><span class="sxs-lookup"><span data-stu-id="8bd6f-104">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="8bd6f-105">Si usa `Preserve`, solo puede cambiar el tamaño de la última dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="8bd6f-105">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="8bd6f-106">Para todas las demás dimensiones, debe especificar el mismo tamaño que la matriz existente.</span><span class="sxs-lookup"><span data-stu-id="8bd6f-106">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8bd6f-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="8bd6f-107">To correct this error</span></span>  
  
- <span data-ttu-id="8bd6f-108">Quite la palabra clave `Preserve` .</span><span class="sxs-lookup"><span data-stu-id="8bd6f-108">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bd6f-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8bd6f-109">See also</span></span>

- [<span data-ttu-id="8bd6f-110">Matrices en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8bd6f-110">Arrays in Visual Basic</span></span>](../programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="8bd6f-111">Dimensiones de matriz en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8bd6f-111">Array dimensions in Visual Basic</span></span>](../programming-guide/language-features/arrays/array-dimensions.md)
- [<span data-ttu-id="8bd6f-112">Instrucción ReDim</span><span class="sxs-lookup"><span data-stu-id="8bd6f-112">ReDim Statement</span></span>](../language-reference/statements/redim-statement.md)
- [<span data-ttu-id="8bd6f-113">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="8bd6f-113">Dim Statement</span></span>](../language-reference/statements/dim-statement.md)

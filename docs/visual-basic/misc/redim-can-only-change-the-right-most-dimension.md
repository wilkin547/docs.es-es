---
title: "'ReDim' solo puede cambiar la dimensión situada más a la derecha"
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: 584370f356180fe8b1710a9e145018be7f2d8a0f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592305"
---
# <a name="redim-can-only-change-the-right-most-dimension"></a><span data-ttu-id="96dc1-102">'ReDim' solo puede cambiar la dimensión situada más a la derecha</span><span class="sxs-lookup"><span data-stu-id="96dc1-102">'ReDim' can only change the right-most dimension</span></span>
<span data-ttu-id="96dc1-103">Una instrucción `ReDim` intentó usar la palabra clave `Preserve` para cambiar una dimensión de una matriz que no es la última dimensión.</span><span class="sxs-lookup"><span data-stu-id="96dc1-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="96dc1-104">Si usa `Preserve`, solo puede cambiar el tamaño de la última dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="96dc1-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="96dc1-105">Para todas las demás dimensiones, debe especificar el mismo tamaño que la matriz existente.</span><span class="sxs-lookup"><span data-stu-id="96dc1-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="96dc1-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="96dc1-106">To correct this error</span></span>  
  
- <span data-ttu-id="96dc1-107">Quite la palabra clave `Preserve` .</span><span class="sxs-lookup"><span data-stu-id="96dc1-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96dc1-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="96dc1-108">See also</span></span>

- [<span data-ttu-id="96dc1-109">Matrices en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="96dc1-109">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="96dc1-110">Dimensiones de la matriz en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="96dc1-110">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)
- [<span data-ttu-id="96dc1-111">ReDim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="96dc1-111">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="96dc1-112">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="96dc1-112">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)

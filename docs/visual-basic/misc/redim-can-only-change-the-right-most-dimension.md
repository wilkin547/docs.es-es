---
title: "'ReDim' solo puede cambiar la dimensión situada más a la derecha"
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: 5b4f054c5d1dfad52ce19e1a9f9d246945866703
ms.sourcegitcommit: 0888d7b24f475c346a3f444de8d83ec1ca7cd234
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2018
ms.locfileid: "53767404"
---
# <a name="redim-can-only-change-the-right-most-dimension"></a><span data-ttu-id="45c0e-102">'ReDim' solo puede cambiar la dimensión situada más a la derecha</span><span class="sxs-lookup"><span data-stu-id="45c0e-102">'ReDim' can only change the right-most dimension</span></span>
<span data-ttu-id="45c0e-103">Una instrucción `ReDim` intentó usar la palabra clave `Preserve` para cambiar una dimensión de una matriz que no es la última dimensión.</span><span class="sxs-lookup"><span data-stu-id="45c0e-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="45c0e-104">Si usa `Preserve`, solo puede cambiar el tamaño de la última dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="45c0e-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="45c0e-105">Para todas las demás dimensiones, debe especificar el mismo tamaño que la matriz existente.</span><span class="sxs-lookup"><span data-stu-id="45c0e-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="45c0e-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="45c0e-106">To correct this error</span></span>  
  
-   <span data-ttu-id="45c0e-107">Quite la palabra clave `Preserve` .</span><span class="sxs-lookup"><span data-stu-id="45c0e-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45c0e-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="45c0e-108">See Also</span></span>  
 [<span data-ttu-id="45c0e-109">Matrices en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="45c0e-109">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="45c0e-110">Dimensiones de la matriz en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="45c0e-110">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [<span data-ttu-id="45c0e-111">ReDim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="45c0e-111">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="45c0e-112">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="45c0e-112">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="45c0e-113">Preserve - delete</span><span class="sxs-lookup"><span data-stu-id="45c0e-113">Preserve - delete</span></span>](https://msdn.microsoft.com/library/91badeab-b4e0-48b6-92c9-9f0c8f995d81)

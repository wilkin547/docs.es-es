---
title: '&#39;ReDim&#39; solo se puede cambiar la dimensión más a la derecha'
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: efb98df13a7e3e378347b30b6fc00b90030ec194
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33641188"
---
# <a name="39redim39-can-only-change-the-right-most-dimension"></a><span data-ttu-id="c88c5-102">&#39;ReDim&#39; solo se puede cambiar la dimensión más a la derecha</span><span class="sxs-lookup"><span data-stu-id="c88c5-102">&#39;ReDim&#39; can only change the right-most dimension</span></span>
<span data-ttu-id="c88c5-103">Una instrucción `ReDim` intentó usar la palabra clave `Preserve` para cambiar una dimensión de una matriz que no es la última dimensión.</span><span class="sxs-lookup"><span data-stu-id="c88c5-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="c88c5-104">Si usa `Preserve`, solo puede cambiar el tamaño de la última dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="c88c5-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="c88c5-105">Para todas las demás dimensiones, debe especificar el mismo tamaño que la matriz existente.</span><span class="sxs-lookup"><span data-stu-id="c88c5-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c88c5-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="c88c5-106">To correct this error</span></span>  
  
-   <span data-ttu-id="c88c5-107">Quite la palabra clave `Preserve` .</span><span class="sxs-lookup"><span data-stu-id="c88c5-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c88c5-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="c88c5-108">See Also</span></span>  
 [<span data-ttu-id="c88c5-109">Matrices en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c88c5-109">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="c88c5-110">Dimensiones de la matriz en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c88c5-110">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [<span data-ttu-id="c88c5-111">ReDim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c88c5-111">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="c88c5-112">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c88c5-112">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="c88c5-113">Conservar: eliminar</span><span class="sxs-lookup"><span data-stu-id="c88c5-113">Preserve - delete</span></span>](http://msdn.microsoft.com/library/91badeab-b4e0-48b6-92c9-9f0c8f995d81)

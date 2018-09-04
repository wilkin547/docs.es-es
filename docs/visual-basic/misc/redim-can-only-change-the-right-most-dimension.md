---
title: '&#39;ReDim&#39; solo se puede cambiar la dimensión más a la derecha'
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: 94e0fe81f7e750a67943b68f2db700e3a7831da1
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43502591"
---
# <a name="39redim39-can-only-change-the-right-most-dimension"></a><span data-ttu-id="26504-102">&#39;ReDim&#39; solo se puede cambiar la dimensión más a la derecha</span><span class="sxs-lookup"><span data-stu-id="26504-102">&#39;ReDim&#39; can only change the right-most dimension</span></span>
<span data-ttu-id="26504-103">Una instrucción `ReDim` intentó usar la palabra clave `Preserve` para cambiar una dimensión de una matriz que no es la última dimensión.</span><span class="sxs-lookup"><span data-stu-id="26504-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="26504-104">Si usa `Preserve`, solo puede cambiar el tamaño de la última dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="26504-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="26504-105">Para todas las demás dimensiones, debe especificar el mismo tamaño que la matriz existente.</span><span class="sxs-lookup"><span data-stu-id="26504-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="26504-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="26504-106">To correct this error</span></span>  
  
-   <span data-ttu-id="26504-107">Quite la palabra clave `Preserve` .</span><span class="sxs-lookup"><span data-stu-id="26504-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26504-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="26504-108">See Also</span></span>  
 [<span data-ttu-id="26504-109">Matrices en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="26504-109">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="26504-110">Dimensiones de la matriz en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="26504-110">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [<span data-ttu-id="26504-111">ReDim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="26504-111">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="26504-112">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="26504-112">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="26504-113">Conservar: eliminar</span><span class="sxs-lookup"><span data-stu-id="26504-113">Preserve - delete</span></span>](https://msdn.microsoft.com/library/91badeab-b4e0-48b6-92c9-9f0c8f995d81)

---
title: "'ReDim' solo puede cambiar la dimensión situada más a la derecha"
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: 8e42e0df7b97fb96f468ce37dd4cfc52fad8c596
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84358301"
---
# <a name="redim-can-only-change-the-right-most-dimension"></a><span data-ttu-id="39d96-102">'ReDim' solo puede cambiar la dimensión situada más a la derecha</span><span class="sxs-lookup"><span data-stu-id="39d96-102">'ReDim' can only change the right-most dimension</span></span>
<span data-ttu-id="39d96-103">Una instrucción `ReDim` intentó usar la palabra clave `Preserve` para cambiar una dimensión de una matriz que no es la última dimensión.</span><span class="sxs-lookup"><span data-stu-id="39d96-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="39d96-104">Si usa `Preserve`, solo puede cambiar el tamaño de la última dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="39d96-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="39d96-105">Para todas las demás dimensiones, debe especificar el mismo tamaño que la matriz existente.</span><span class="sxs-lookup"><span data-stu-id="39d96-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="39d96-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="39d96-106">To correct this error</span></span>  
  
- <span data-ttu-id="39d96-107">Quite la palabra clave `Preserve` .</span><span class="sxs-lookup"><span data-stu-id="39d96-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39d96-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="39d96-108">See also</span></span>

- [<span data-ttu-id="39d96-109">Matrices en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="39d96-109">Arrays in Visual Basic</span></span>](../programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="39d96-110">Dimensiones de matriz en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="39d96-110">Array dimensions in Visual Basic</span></span>](../programming-guide/language-features/arrays/array-dimensions.md)
- [<span data-ttu-id="39d96-111">Instrucción ReDim</span><span class="sxs-lookup"><span data-stu-id="39d96-111">ReDim Statement</span></span>](../language-reference/statements/redim-statement.md)
- [<span data-ttu-id="39d96-112">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="39d96-112">Dim Statement</span></span>](../language-reference/statements/dim-statement.md)

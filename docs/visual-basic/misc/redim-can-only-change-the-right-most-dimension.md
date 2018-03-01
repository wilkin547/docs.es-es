---
title: "&#39; ReDim &#39; solo se puede cambiar la dimensión más a la derecha"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 752e0e54c48b3b348a477787e5e911f1b1777667
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="39redim39-can-only-change-the-right-most-dimension"></a><span data-ttu-id="1f704-102">&#39; ReDim &#39; solo se puede cambiar la dimensión más a la derecha</span><span class="sxs-lookup"><span data-stu-id="1f704-102">&#39;ReDim&#39; can only change the right-most dimension</span></span>
<span data-ttu-id="1f704-103">Una instrucción `ReDim` intentó usar la palabra clave `Preserve` para cambiar una dimensión de una matriz que no es la última dimensión.</span><span class="sxs-lookup"><span data-stu-id="1f704-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="1f704-104">Si usa `Preserve`, solo puede cambiar el tamaño de la última dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="1f704-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="1f704-105">Para todas las demás dimensiones, debe especificar el mismo tamaño que la matriz existente.</span><span class="sxs-lookup"><span data-stu-id="1f704-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1f704-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="1f704-106">To correct this error</span></span>  
  
-   <span data-ttu-id="1f704-107">Quite la palabra clave `Preserve` .</span><span class="sxs-lookup"><span data-stu-id="1f704-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f704-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f704-108">See Also</span></span>  
 [<span data-ttu-id="1f704-109">Matrices en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1f704-109">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="1f704-110">Dimensiones de la matriz en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1f704-110">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [<span data-ttu-id="1f704-111">ReDim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="1f704-111">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="1f704-112">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="1f704-112">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="1f704-113">Conservar: eliminar</span><span class="sxs-lookup"><span data-stu-id="1f704-113">Preserve - delete</span></span>](http://msdn.microsoft.com/library/91badeab-b4e0-48b6-92c9-9f0c8f995d81)

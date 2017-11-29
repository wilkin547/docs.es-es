---
title: "&#39; ReDim &#39; solo se puede cambiar la dimensión más a la derecha"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 989a06f94824dfd051d1a7d2e7749dbb8c8e11a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="39redim39-can-only-change-the-right-most-dimension"></a><span data-ttu-id="93723-102">&#39; ReDim &#39; solo se puede cambiar la dimensión más a la derecha</span><span class="sxs-lookup"><span data-stu-id="93723-102">&#39;ReDim&#39; can only change the right-most dimension</span></span>
<span data-ttu-id="93723-103">Una instrucción `ReDim` intentó usar la palabra clave `Preserve` para cambiar una dimensión de una matriz que no es la última dimensión.</span><span class="sxs-lookup"><span data-stu-id="93723-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="93723-104">Si usa `Preserve`, solo puede cambiar el tamaño de la última dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="93723-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="93723-105">Para todas las demás dimensiones, debe especificar el mismo tamaño que la matriz existente.</span><span class="sxs-lookup"><span data-stu-id="93723-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="93723-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="93723-106">To correct this error</span></span>  
  
-   <span data-ttu-id="93723-107">Quite la palabra clave `Preserve` .</span><span class="sxs-lookup"><span data-stu-id="93723-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93723-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="93723-108">See Also</span></span>  
 [<span data-ttu-id="93723-109">Matrices en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="93723-109">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="93723-110">Dimensiones de la matriz en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="93723-110">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [<span data-ttu-id="93723-111">ReDim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="93723-111">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="93723-112">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="93723-112">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="93723-113">Conservar: eliminar</span><span class="sxs-lookup"><span data-stu-id="93723-113">Preserve - delete</span></span>](http://msdn.microsoft.com/en-us/91badeab-b4e0-48b6-92c9-9f0c8f995d81)

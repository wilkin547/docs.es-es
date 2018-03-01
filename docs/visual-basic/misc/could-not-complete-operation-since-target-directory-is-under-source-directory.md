---
title: "No se pudo completar la operación porque el directorio de destino se encuentra bajo el directorio de origen"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0a17877b2335ee010a97f0b522bd4c399867cd7d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="5de69-102">No se pudo completar la operación porque el directorio de destino se encuentra bajo el directorio de origen</span><span class="sxs-lookup"><span data-stu-id="5de69-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="5de69-103">No se pudo realizar una operación cíclica.</span><span class="sxs-lookup"><span data-stu-id="5de69-103">A cyclic operation has failed.</span></span> <span data-ttu-id="5de69-104">Las operaciones cíclicas se realizan cíclicamente y, por tanto, no se pueden completar.</span><span class="sxs-lookup"><span data-stu-id="5de69-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="5de69-105">Por ejemplo, el objeto A puede intentar heredar del objeto B, que a su vez hereda del objeto A.</span><span class="sxs-lookup"><span data-stu-id="5de69-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5de69-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="5de69-106">To correct this error</span></span>  
  
-   <span data-ttu-id="5de69-107">Durante la herencia, asegúrese de que no existe ninguna referencia cíclica.</span><span class="sxs-lookup"><span data-stu-id="5de69-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5de69-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="5de69-108">See Also</span></span>  
 [<span data-ttu-id="5de69-109">Tipos de error</span><span class="sxs-lookup"><span data-stu-id="5de69-109">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)  
 [<span data-ttu-id="5de69-110">Fundamentos de la depuración: puntos de interrupción</span><span class="sxs-lookup"><span data-stu-id="5de69-110">Debugging Basics: Breakpoints</span></span>](http://msdn.microsoft.com/library/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e)

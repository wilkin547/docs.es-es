---
title: No se puede llamar a una función friend de un objeto que no sea una instancia de una clase
ms.date: 07/20/2015
f1_keywords:
- vbrID97
ms.assetid: b9d821f0-8565-4f15-bb35-184789c69662
ms.openlocfilehash: c18c04470c4c49113e8195b92185326c5c4197c1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400853"
---
# <a name="cannot-call-friend-function-on-object-which-is-not-an-instance-of-defining-class"></a><span data-ttu-id="93121-102">No se puede llamar a una función friend de un objeto que no sea una instancia de una clase</span><span class="sxs-lookup"><span data-stu-id="93121-102">Cannot call friend function on object which is not an instance of defining class</span></span>
<span data-ttu-id="93121-103">Intentó llamar al procedimiento `Friend` de una clase, o bien acceder a una propiedad o un método `Friend` entre procesos o a través de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="93121-103">Either you tried to call the `Friend` procedure of a class, or you tried to access a `Friend` property or method either cross-process or cross-thread.</span></span> <span data-ttu-id="93121-104">Un procedimiento `Friend` se puede llamar desde un módulo fuera de la clase, pero forma parte del proyecto en el que está definida la clase.</span><span class="sxs-lookup"><span data-stu-id="93121-104">A `Friend` procedure is callable from a module outside the class, but is part of the project in which the class is defined.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="93121-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="93121-105">To correct this error</span></span>  
  
- <span data-ttu-id="93121-106">Asegúrese de que llama o accede al procedimiento desde un módulo que forma parte del proyecto en el que está definida la clase.</span><span class="sxs-lookup"><span data-stu-id="93121-106">Ensure that you are calling or accessing the procedure from a module that is part of the project in which the class is defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93121-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="93121-107">See also</span></span>

- [<span data-ttu-id="93121-108">Respecto</span><span class="sxs-lookup"><span data-stu-id="93121-108">Friend</span></span>](../language-reference/modifiers/friend.md)

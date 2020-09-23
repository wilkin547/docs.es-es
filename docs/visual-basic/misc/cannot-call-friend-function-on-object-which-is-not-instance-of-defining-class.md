---
title: No se puede llamar a una función friend de un objeto que no sea una instancia de una clase
ms.date: 07/20/2015
f1_keywords:
- vbrID97
ms.assetid: b9d821f0-8565-4f15-bb35-184789c69662
ms.openlocfilehash: fe95f80d42fc12ab2829db899fe295e32f358db6
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059813"
---
# <a name="cannot-call-friend-function-on-object-which-is-not-an-instance-of-defining-class"></a><span data-ttu-id="4cbdf-102">No se puede llamar a una función friend de un objeto que no sea una instancia de una clase</span><span class="sxs-lookup"><span data-stu-id="4cbdf-102">Cannot call friend function on object which is not an instance of defining class</span></span>

<span data-ttu-id="4cbdf-103">Intentó llamar al procedimiento `Friend` de una clase, o bien acceder a una propiedad o un método `Friend` entre procesos o a través de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-103">Either you tried to call the `Friend` procedure of a class, or you tried to access a `Friend` property or method either cross-process or cross-thread.</span></span> <span data-ttu-id="4cbdf-104">Un procedimiento `Friend` se puede llamar desde un módulo fuera de la clase, pero forma parte del proyecto en el que está definida la clase.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-104">A `Friend` procedure is callable from a module outside the class, but is part of the project in which the class is defined.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4cbdf-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="4cbdf-105">To correct this error</span></span>  
  
- <span data-ttu-id="4cbdf-106">Asegúrese de que llama o accede al procedimiento desde un módulo que forma parte del proyecto en el que está definida la clase.</span><span class="sxs-lookup"><span data-stu-id="4cbdf-106">Ensure that you are calling or accessing the procedure from a module that is part of the project in which the class is defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cbdf-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="4cbdf-107">See also</span></span>

- [<span data-ttu-id="4cbdf-108">Friend</span><span class="sxs-lookup"><span data-stu-id="4cbdf-108">Friend</span></span>](../language-reference/modifiers/friend.md)

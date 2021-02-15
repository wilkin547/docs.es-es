---
description: 'Más información acerca de: no se puede llamar a una función Friend en el objeto, que no es una instancia de la clase de definición'
title: No se puede llamar a una función friend de un objeto que no sea una instancia de una clase
ms.date: 07/20/2015
f1_keywords:
- vbrID97
ms.assetid: b9d821f0-8565-4f15-bb35-184789c69662
ms.openlocfilehash: 612a169cf976881b82cb0bb0c44ac6c6e7f91755
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100478703"
---
# <a name="cannot-call-friend-function-on-object-which-is-not-an-instance-of-defining-class"></a><span data-ttu-id="ed13e-103">No se puede llamar a una función friend de un objeto que no sea una instancia de una clase</span><span class="sxs-lookup"><span data-stu-id="ed13e-103">Cannot call friend function on object which is not an instance of defining class</span></span>

<span data-ttu-id="ed13e-104">Intentó llamar al procedimiento `Friend` de una clase, o bien acceder a una propiedad o un método `Friend` entre procesos o a través de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="ed13e-104">Either you tried to call the `Friend` procedure of a class, or you tried to access a `Friend` property or method either cross-process or cross-thread.</span></span> <span data-ttu-id="ed13e-105">Un procedimiento `Friend` se puede llamar desde un módulo fuera de la clase, pero forma parte del proyecto en el que está definida la clase.</span><span class="sxs-lookup"><span data-stu-id="ed13e-105">A `Friend` procedure is callable from a module outside the class, but is part of the project in which the class is defined.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ed13e-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="ed13e-106">To correct this error</span></span>  
  
- <span data-ttu-id="ed13e-107">Asegúrese de que llama o accede al procedimiento desde un módulo que forma parte del proyecto en el que está definida la clase.</span><span class="sxs-lookup"><span data-stu-id="ed13e-107">Ensure that you are calling or accessing the procedure from a module that is part of the project in which the class is defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed13e-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ed13e-108">See also</span></span>

- [<span data-ttu-id="ed13e-109">Friend</span><span class="sxs-lookup"><span data-stu-id="ed13e-109">Friend</span></span>](../language-reference/modifiers/friend.md)

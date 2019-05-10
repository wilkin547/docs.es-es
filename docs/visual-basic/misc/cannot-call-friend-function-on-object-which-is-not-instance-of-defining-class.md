---
title: No se puede llamar a una función friend de un objeto que no sea una instancia de una clase
ms.date: 07/20/2015
f1_keywords:
- vbrID97
ms.assetid: b9d821f0-8565-4f15-bb35-184789c69662
ms.openlocfilehash: a227e5761bacc36c0682844a833e70c34582a5d3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64622605"
---
# <a name="cannot-call-friend-function-on-object-which-is-not-an-instance-of-defining-class"></a><span data-ttu-id="a8050-102">No se puede llamar a una función friend de un objeto que no sea una instancia de una clase</span><span class="sxs-lookup"><span data-stu-id="a8050-102">Cannot call friend function on object which is not an instance of defining class</span></span>
<span data-ttu-id="a8050-103">Intentó llamar al procedimiento `Friend` de una clase, o bien acceder a una propiedad o un método `Friend` entre procesos o a través de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="a8050-103">Either you tried to call the `Friend` procedure of a class, or you tried to access a `Friend` property or method either cross-process or cross-thread.</span></span> <span data-ttu-id="a8050-104">Un procedimiento `Friend` se puede llamar desde un módulo fuera de la clase, pero forma parte del proyecto en el que está definida la clase.</span><span class="sxs-lookup"><span data-stu-id="a8050-104">A `Friend` procedure is callable from a module outside the class, but is part of the project in which the class is defined.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a8050-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="a8050-105">To correct this error</span></span>  
  
- <span data-ttu-id="a8050-106">Asegúrese de que llama o accede al procedimiento desde un módulo que forma parte del proyecto en el que está definida la clase.</span><span class="sxs-lookup"><span data-stu-id="a8050-106">Ensure that you are calling or accessing the procedure from a module that is part of the project in which the class is defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8050-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8050-107">See also</span></span>

- [<span data-ttu-id="a8050-108">Friend</span><span class="sxs-lookup"><span data-stu-id="a8050-108">Friend</span></span>](../../visual-basic/language-reference/modifiers/friend.md)

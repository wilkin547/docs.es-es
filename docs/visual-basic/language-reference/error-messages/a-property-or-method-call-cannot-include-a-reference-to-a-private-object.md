---
title: Una llamada a una propiedad o un método no puede incluir una referencia a un objeto privado como un argumento o un valor de retorno
ms.date: 07/20/2015
f1_keywords:
- vbrID98
ms.assetid: 059b43e1-202d-4fa2-806b-7bad63c1e7ca
ms.openlocfilehash: 00237d795fb62fbae426e0015d8e64d5fabb4c32
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162679"
---
# <a name="a-property-or-method-call-cannot-include-a-reference-to-a-private-object-either-as-an-argument-or-as-a-return-value"></a><span data-ttu-id="e0b60-102">Una llamada a una propiedad o un método no puede incluir una referencia a un objeto privado como un argumento o un valor de retorno</span><span class="sxs-lookup"><span data-stu-id="e0b60-102">A property or method call cannot include a reference to a private object, either as an argument or as a return value</span></span>

<span data-ttu-id="e0b60-103">Entre las causas posibles de este error se incluyen:</span><span class="sxs-lookup"><span data-stu-id="e0b60-103">Among the possible causes of this error are:</span></span>

- <span data-ttu-id="e0b60-104">Un cliente invocó una propiedad o un método de un componente fuera de proceso e intentó pasar una referencia a un objeto privado como uno de los argumentos.</span><span class="sxs-lookup"><span data-stu-id="e0b60-104">A client invoked a property or method of an out-of-process component and attempted to pass a reference to a private object as one of the arguments.</span></span>

- <span data-ttu-id="e0b60-105">Un componente fuera de proceso invocó un método de devolución de llamada en su cliente e intentó pasar una referencia a un objeto privado.</span><span class="sxs-lookup"><span data-stu-id="e0b60-105">An out-of-process component invoked a call-back method on its client and attempted to pass a reference to a private object.</span></span>

- <span data-ttu-id="e0b60-106">Un componente fuera de proceso intentó pasar una referencia a un objeto privado como un argumento de un evento que estaba generando.</span><span class="sxs-lookup"><span data-stu-id="e0b60-106">An out-of-process component attempted to pass a reference to a private object as an argument of an event it was raising.</span></span>

- <span data-ttu-id="e0b60-107">Un cliente intentó asignar una referencia de objeto privado a un argumento `ByRef` de un evento que estaba controlando.</span><span class="sxs-lookup"><span data-stu-id="e0b60-107">A client attempted to assign a private object reference to a `ByRef` argument of an event it was handling.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="e0b60-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="e0b60-108">To correct this error</span></span>

- <span data-ttu-id="e0b60-109">Quite la referencia.</span><span class="sxs-lookup"><span data-stu-id="e0b60-109">Remove the reference.</span></span>

## <a name="see-also"></a><span data-ttu-id="e0b60-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0b60-110">See also</span></span>

- [<span data-ttu-id="e0b60-111">Privado</span><span class="sxs-lookup"><span data-stu-id="e0b60-111">Private</span></span>](../modifiers/private.md)

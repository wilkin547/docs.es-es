---
description: 'Más información sobre: una llamada a una propiedad o un método no puede incluir una referencia a un objeto privado, ya sea como argumento o como valor devuelto'
title: Una llamada a una propiedad o un método no puede incluir una referencia a un objeto privado como un argumento o un valor de retorno
ms.date: 07/20/2015
f1_keywords:
- vbrID98
ms.assetid: 059b43e1-202d-4fa2-806b-7bad63c1e7ca
ms.openlocfilehash: 8fe570c9ed789a5bac36aafa9b1ec2f507a55d51
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797203"
---
# <a name="a-property-or-method-call-cannot-include-a-reference-to-a-private-object-either-as-an-argument-or-as-a-return-value"></a><span data-ttu-id="6c556-103">Una llamada a una propiedad o un método no puede incluir una referencia a un objeto privado como un argumento o un valor de retorno</span><span class="sxs-lookup"><span data-stu-id="6c556-103">A property or method call cannot include a reference to a private object, either as an argument or as a return value</span></span>

<span data-ttu-id="6c556-104">Entre las causas posibles de este error se incluyen:</span><span class="sxs-lookup"><span data-stu-id="6c556-104">Among the possible causes of this error are:</span></span>

- <span data-ttu-id="6c556-105">Un cliente invocó una propiedad o un método de un componente fuera de proceso e intentó pasar una referencia a un objeto privado como uno de los argumentos.</span><span class="sxs-lookup"><span data-stu-id="6c556-105">A client invoked a property or method of an out-of-process component and attempted to pass a reference to a private object as one of the arguments.</span></span>

- <span data-ttu-id="6c556-106">Un componente fuera de proceso invocó un método de devolución de llamada en su cliente e intentó pasar una referencia a un objeto privado.</span><span class="sxs-lookup"><span data-stu-id="6c556-106">An out-of-process component invoked a call-back method on its client and attempted to pass a reference to a private object.</span></span>

- <span data-ttu-id="6c556-107">Un componente fuera de proceso intentó pasar una referencia a un objeto privado como un argumento de un evento que estaba generando.</span><span class="sxs-lookup"><span data-stu-id="6c556-107">An out-of-process component attempted to pass a reference to a private object as an argument of an event it was raising.</span></span>

- <span data-ttu-id="6c556-108">Un cliente intentó asignar una referencia de objeto privado a un argumento `ByRef` de un evento que estaba controlando.</span><span class="sxs-lookup"><span data-stu-id="6c556-108">A client attempted to assign a private object reference to a `ByRef` argument of an event it was handling.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="6c556-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="6c556-109">To correct this error</span></span>

- <span data-ttu-id="6c556-110">Quite la referencia.</span><span class="sxs-lookup"><span data-stu-id="6c556-110">Remove the reference.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c556-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c556-111">See also</span></span>

- [<span data-ttu-id="6c556-112">Privado</span><span class="sxs-lookup"><span data-stu-id="6c556-112">Private</span></span>](../modifiers/private.md)

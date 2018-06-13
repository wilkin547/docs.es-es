---
title: Una llamada a una propiedad o un método no puede incluir una referencia a un objeto privado como un argumento o un valor de retorno
ms.date: 07/20/2015
f1_keywords:
- vbrID98
ms.assetid: 059b43e1-202d-4fa2-806b-7bad63c1e7ca
ms.openlocfilehash: 1f36526eab1bc0964bf89398b6e0f3e74d09fdc6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583830"
---
# <a name="a-property-or-method-call-cannot-include-a-reference-to-a-private-object-either-as-an-argument-or-as-a-return-value"></a><span data-ttu-id="60110-102">Una llamada a una propiedad o un método no puede incluir una referencia a un objeto privado como un argumento o un valor de retorno</span><span class="sxs-lookup"><span data-stu-id="60110-102">A property or method call cannot include a reference to a private object, either as an argument or as a return value</span></span>
<span data-ttu-id="60110-103">Entre las causas posibles de este error se incluyen:</span><span class="sxs-lookup"><span data-stu-id="60110-103">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="60110-104">Un cliente invocó una propiedad o un método de un componente fuera de proceso e intentó pasar una referencia a un objeto privado como uno de los argumentos.</span><span class="sxs-lookup"><span data-stu-id="60110-104">A client invoked a property or method of an out-of-process component and attempted to pass a reference to a private object as one of the arguments.</span></span>  
  
-   <span data-ttu-id="60110-105">Un componente fuera de proceso invocó un método de devolución de llamada en su cliente e intentó pasar una referencia a un objeto privado.</span><span class="sxs-lookup"><span data-stu-id="60110-105">An out-of-process component invoked a call-back method on its client and attempted to pass a reference to a private object.</span></span>  
  
-   <span data-ttu-id="60110-106">Un componente fuera de proceso intentó pasar una referencia a un objeto privado como un argumento de un evento que estaba generando.</span><span class="sxs-lookup"><span data-stu-id="60110-106">An out-of-process component attempted to pass a reference to a private object as an argument of an event it was raising.</span></span>  
  
-   <span data-ttu-id="60110-107">Un cliente intentó asignar una referencia de objeto privado a un argumento `ByRef` de un evento que estaba controlando.</span><span class="sxs-lookup"><span data-stu-id="60110-107">A client attempted to assign a private object reference to a `ByRef` argument of an event it was handling.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="60110-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="60110-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="60110-109">Quite la referencia.</span><span class="sxs-lookup"><span data-stu-id="60110-109">Remove the reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60110-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="60110-110">See Also</span></span>  
 [<span data-ttu-id="60110-111">Private</span><span class="sxs-lookup"><span data-stu-id="60110-111">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)

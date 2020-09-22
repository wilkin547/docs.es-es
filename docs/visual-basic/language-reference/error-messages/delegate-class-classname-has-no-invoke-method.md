---
title: La clase delegada '<classname>' no tiene ningún método Invoke y, por tanto, una expresión de este tipo no puede ser el destino de una llamada a método
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: e6ad06262806088347c94b3040b743618a3b3695
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874498"
---
# <a name="delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a><span data-ttu-id="e07e0-102">La clase delegada '\<classname>' no tiene ningún método Invoke y, por tanto, una expresión de este tipo no puede ser el destino de una llamada a método</span><span class="sxs-lookup"><span data-stu-id="e07e0-102">Delegate class '\<classname>' has no Invoke method, so an expression of this type cannot be the target of a method call</span></span>

<span data-ttu-id="e07e0-103">No se pudo realizar una llamada a `Invoke` a través de un delegado porque `Invoke` no está implementado en la clase de delegado.</span><span class="sxs-lookup"><span data-stu-id="e07e0-103">A call to `Invoke` through a delegate has failed because `Invoke` is not implemented on the delegate class.</span></span>  
  
 <span data-ttu-id="e07e0-104">**Identificador de error:** BC30220</span><span class="sxs-lookup"><span data-stu-id="e07e0-104">**Error ID:** BC30220</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e07e0-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="e07e0-105">To correct this error</span></span>  
  
1. <span data-ttu-id="e07e0-106">Asegúrese de que se ha creado una instancia de la clase delegada con una `Dim` instrucción y que se ha asignado un procedimiento a la instancia de delegado con el `AddressOf` operador.</span><span class="sxs-lookup"><span data-stu-id="e07e0-106">Ensure that an instance of the delegate class has been created with a `Dim` statement and that a procedure has been assigned to the delegate instance with the `AddressOf` operator.</span></span>  
  
2. <span data-ttu-id="e07e0-107">Busque el código que implementa la clase delegada y asegúrese de que implementa el `Invoke` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e07e0-107">Locate the code that implements the delegate class and make sure it implements the `Invoke` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e07e0-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e07e0-108">See also</span></span>

- [<span data-ttu-id="e07e0-109">Delegados</span><span class="sxs-lookup"><span data-stu-id="e07e0-109">Delegates</span></span>](../../programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="e07e0-110">Delegate (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="e07e0-110">Delegate Statement</span></span>](../statements/delegate-statement.md)
- [<span data-ttu-id="e07e0-111">Operador AddressOf</span><span class="sxs-lookup"><span data-stu-id="e07e0-111">AddressOf Operator</span></span>](../operators/addressof-operator.md)
- [<span data-ttu-id="e07e0-112">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="e07e0-112">Dim Statement</span></span>](../statements/dim-statement.md)

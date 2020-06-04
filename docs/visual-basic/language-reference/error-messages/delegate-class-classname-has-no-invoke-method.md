---
title: La clase delegada '<classname>' no tiene ningún método Invoke y, por tanto, una expresión de este tipo no puede ser el destino de una llamada a método
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: 27be97ba2930791bcb9012c824bc418a0089b037
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409717"
---
# <a name="delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a><span data-ttu-id="2e09f-102">La clase delegada '\<classname>' no tiene ningún método Invoke y, por tanto, una expresión de este tipo no puede ser el destino de una llamada a método</span><span class="sxs-lookup"><span data-stu-id="2e09f-102">Delegate class '\<classname>' has no Invoke method, so an expression of this type cannot be the target of a method call</span></span>
<span data-ttu-id="2e09f-103">No se pudo realizar una llamada a `Invoke` a través de un delegado porque `Invoke` no está implementado en la clase de delegado.</span><span class="sxs-lookup"><span data-stu-id="2e09f-103">A call to `Invoke` through a delegate has failed because `Invoke` is not implemented on the delegate class.</span></span>  
  
 <span data-ttu-id="2e09f-104">**Identificador de error:** BC30220</span><span class="sxs-lookup"><span data-stu-id="2e09f-104">**Error ID:** BC30220</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2e09f-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="2e09f-105">To correct this error</span></span>  
  
1. <span data-ttu-id="2e09f-106">Asegúrese de que se ha creado una instancia de la clase delegada con una `Dim` instrucción y que se ha asignado un procedimiento a la instancia de delegado con el `AddressOf` operador.</span><span class="sxs-lookup"><span data-stu-id="2e09f-106">Ensure that an instance of the delegate class has been created with a `Dim` statement and that a procedure has been assigned to the delegate instance with the `AddressOf` operator.</span></span>  
  
2. <span data-ttu-id="2e09f-107">Busque el código que implementa la clase delegada y asegúrese de que implementa el `Invoke` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2e09f-107">Locate the code that implements the delegate class and make sure it implements the `Invoke` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e09f-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2e09f-108">See also</span></span>

- [<span data-ttu-id="2e09f-109">Delegados</span><span class="sxs-lookup"><span data-stu-id="2e09f-109">Delegates</span></span>](../../programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="2e09f-110">Delegate (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="2e09f-110">Delegate Statement</span></span>](../statements/delegate-statement.md)
- [<span data-ttu-id="2e09f-111">AddressOf (operador)</span><span class="sxs-lookup"><span data-stu-id="2e09f-111">AddressOf Operator</span></span>](../operators/addressof-operator.md)
- [<span data-ttu-id="2e09f-112">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="2e09f-112">Dim Statement</span></span>](../statements/dim-statement.md)

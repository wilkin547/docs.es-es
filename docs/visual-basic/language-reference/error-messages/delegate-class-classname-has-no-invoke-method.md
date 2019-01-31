---
title: La clase delegada '<classname>' no tiene ningún método Invoke y, por tanto, una expresión de este tipo no puede ser el destino de una llamada a método
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: 8339d038f845b8568f31f3068a98ccccf580aeae
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55286655"
---
# <a name="delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a><span data-ttu-id="2e79c-102">Clase delegada\<classname >' no tiene ningún método Invoke, por lo que una expresión de este tipo no puede ser el destino de una llamada al método</span><span class="sxs-lookup"><span data-stu-id="2e79c-102">Delegate class '\<classname>' has no Invoke method, so an expression of this type cannot be the target of a method call</span></span>
<span data-ttu-id="2e79c-103">Una llamada a `Invoke` a través de un delegado ha fallado porque `Invoke` no está implementado en la clase de delegado.</span><span class="sxs-lookup"><span data-stu-id="2e79c-103">A call to `Invoke` through a delegate has failed because `Invoke` is not implemented on the delegate class.</span></span>  
  
 <span data-ttu-id="2e79c-104">**Identificador de error:** BC30220</span><span class="sxs-lookup"><span data-stu-id="2e79c-104">**Error ID:** BC30220</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2e79c-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="2e79c-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="2e79c-106">Asegúrese de que se ha creado una instancia de la clase de delegado con una `Dim` instrucción y que se ha asignado un procedimiento a la instancia de delegado con el `AddressOf` operador.</span><span class="sxs-lookup"><span data-stu-id="2e79c-106">Ensure that an instance of the delegate class has been created with a `Dim` statement and that a procedure has been assigned to the delegate instance with the `AddressOf` operator.</span></span>  
  
2.  <span data-ttu-id="2e79c-107">Busque el código que implementa la clase de delegado y asegúrese de que implementa el `Invoke` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2e79c-107">Locate the code that implements the delegate class and make sure it implements the `Invoke` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e79c-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e79c-108">See also</span></span>
- [<span data-ttu-id="2e79c-109">Delegados</span><span class="sxs-lookup"><span data-stu-id="2e79c-109">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="2e79c-110">Delegate (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2e79c-110">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="2e79c-111">AddressOf (operador)</span><span class="sxs-lookup"><span data-stu-id="2e79c-111">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="2e79c-112">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2e79c-112">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)

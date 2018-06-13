---
title: Clase delegada &#39; &lt;classname&gt; &#39; no tiene ningún método Invoke y, por lo que una expresión de este tipo no puede ser el destino de una llamada a método
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: cc1abba46224772e733780800dd104dfc7ebe9ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588835"
---
# <a name="delegate-class-39ltclassnamegt39-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a><span data-ttu-id="280d1-102">Clase delegada &#39; &lt;classname&gt; &#39; no tiene ningún método Invoke y, por lo que una expresión de este tipo no puede ser el destino de una llamada a método</span><span class="sxs-lookup"><span data-stu-id="280d1-102">Delegate class &#39;&lt;classname&gt;&#39; has no Invoke method, so an expression of this type cannot be the target of a method call</span></span>
<span data-ttu-id="280d1-103">Una llamada a `Invoke` a través de un delegado error porque `Invoke` no está implementada en la clase de delegado.</span><span class="sxs-lookup"><span data-stu-id="280d1-103">A call to `Invoke` through a delegate has failed because `Invoke` is not implemented on the delegate class.</span></span>  
  
 <span data-ttu-id="280d1-104">**Id. de error:** BC30220</span><span class="sxs-lookup"><span data-stu-id="280d1-104">**Error ID:** BC30220</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="280d1-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="280d1-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="280d1-106">Asegúrese de que se ha creado una instancia de la clase de delegado con una `Dim` instrucción y que se ha asignado un procedimiento a la instancia de delegado con el `AddressOf` operador.</span><span class="sxs-lookup"><span data-stu-id="280d1-106">Ensure that an instance of the delegate class has been created with a `Dim` statement and that a procedure has been assigned to the delegate instance with the `AddressOf` operator.</span></span>  
  
2.  <span data-ttu-id="280d1-107">Busque el código que implementa la clase de delegado y asegúrese de que implementa el `Invoke` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="280d1-107">Locate the code that implements the delegate class and make sure it implements the `Invoke` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="280d1-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="280d1-108">See Also</span></span>  
 [<span data-ttu-id="280d1-109">Delegados</span><span class="sxs-lookup"><span data-stu-id="280d1-109">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="280d1-110">Delegate (instrucción)</span><span class="sxs-lookup"><span data-stu-id="280d1-110">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="280d1-111">AddressOf (operador)</span><span class="sxs-lookup"><span data-stu-id="280d1-111">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="280d1-112">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="280d1-112">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)

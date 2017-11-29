---
title: "Clase de delegado &#39; &lt;classname&gt;&#39; no tiene ningún método Invoke y, por lo que una expresión de este tipo no puede ser el destino de una llamada a método"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords: BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 55d0e2442807e25737d90ac4b45a59b9d3e73037
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="delegate-class-39ltclassnamegt39-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a><span data-ttu-id="54b13-102">Clase de delegado &#39; &lt;classname&gt;&#39; no tiene ningún método Invoke y, por lo que una expresión de este tipo no puede ser el destino de una llamada a método</span><span class="sxs-lookup"><span data-stu-id="54b13-102">Delegate class &#39;&lt;classname&gt;&#39; has no Invoke method, so an expression of this type cannot be the target of a method call</span></span>
<span data-ttu-id="54b13-103">Una llamada a `Invoke` a través de un delegado error porque `Invoke` no está implementada en la clase de delegado.</span><span class="sxs-lookup"><span data-stu-id="54b13-103">A call to `Invoke` through a delegate has failed because `Invoke` is not implemented on the delegate class.</span></span>  
  
 <span data-ttu-id="54b13-104">**Id. de error:** BC30220</span><span class="sxs-lookup"><span data-stu-id="54b13-104">**Error ID:** BC30220</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="54b13-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="54b13-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="54b13-106">Asegúrese de que se ha creado una instancia de la clase de delegado con una `Dim` instrucción y que se ha asignado un procedimiento a la instancia de delegado con el `AddressOf` operador.</span><span class="sxs-lookup"><span data-stu-id="54b13-106">Ensure that an instance of the delegate class has been created with a `Dim` statement and that a procedure has been assigned to the delegate instance with the `AddressOf` operator.</span></span>  
  
2.  <span data-ttu-id="54b13-107">Busque el código que implementa la clase de delegado y asegúrese de que implementa el `Invoke` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="54b13-107">Locate the code that implements the delegate class and make sure it implements the `Invoke` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54b13-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="54b13-108">See Also</span></span>  
 [<span data-ttu-id="54b13-109">Delegados</span><span class="sxs-lookup"><span data-stu-id="54b13-109">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="54b13-110">Delegate (instrucción)</span><span class="sxs-lookup"><span data-stu-id="54b13-110">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="54b13-111">AddressOf (operador)</span><span class="sxs-lookup"><span data-stu-id="54b13-111">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="54b13-112">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="54b13-112">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)

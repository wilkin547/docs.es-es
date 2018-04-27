---
title: 'Cómo: Pasar procedimientos a otro procedimiento en Visual Basic'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 30264e0480b603b21f8f71893af0fd742af40286
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a><span data-ttu-id="d6e16-102">Cómo: Pasar procedimientos a otro procedimiento en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d6e16-102">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>
<span data-ttu-id="d6e16-103">En este ejemplo se muestra cómo utilizar a los delegados para pasar un procedimiento a otro procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d6e16-103">This example shows how to use delegates to pass a procedure to another procedure.</span></span>  
  
 <span data-ttu-id="d6e16-104">Un delegado es un tipo que puede usar como cualquier otro tipo en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d6e16-104">A delegate is a type that you can use like any other type in Visual Basic.</span></span> <span data-ttu-id="d6e16-105">El `AddressOf` operador devuelve un objeto de delegado cuando se aplica a un nombre de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d6e16-105">The `AddressOf` operator returns a delegate object when applied to a procedure name.</span></span>  
  
 <span data-ttu-id="d6e16-106">Este ejemplo tiene un procedimiento con un parámetro de delegado que puede tomar una referencia a otro procedimiento obtenido con la `AddressOf` operador.</span><span class="sxs-lookup"><span data-stu-id="d6e16-106">This example has a procedure with a delegate parameter that can take a reference to another procedure, obtained with the `AddressOf` operator.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="d6e16-107">Crear el delegado y los procedimientos correspondientes</span><span class="sxs-lookup"><span data-stu-id="d6e16-107">Create the delegate and matching procedures</span></span>  
  
1.  <span data-ttu-id="d6e16-108">Cree un delegado denominado `MathOperator`.</span><span class="sxs-lookup"><span data-stu-id="d6e16-108">Create a delegate named `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]  
  
2.  <span data-ttu-id="d6e16-109">Cree un procedimiento denominado `AddNumbers` con parámetros y el valor devuelto que coinciden con los de `MathOperator`, de modo que coincidan con las firmas.</span><span class="sxs-lookup"><span data-stu-id="d6e16-109">Create a procedure named `AddNumbers` with parameters and return value that match those of `MathOperator`, so that the signatures match.</span></span>  
  
     [!code-vb[VbVbalrDelegates#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]  
  
3.  <span data-ttu-id="d6e16-110">Cree un procedimiento denominado `SubtractNumbers` con una firma que coincida con `MathOperator`.</span><span class="sxs-lookup"><span data-stu-id="d6e16-110">Create a procedure named `SubtractNumbers` with a signature that matches `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]  
  
4.  <span data-ttu-id="d6e16-111">Cree un procedimiento denominado `DelegateTest` que toma un delegado como parámetro.</span><span class="sxs-lookup"><span data-stu-id="d6e16-111">Create a procedure named `DelegateTest` that takes a delegate as a parameter.</span></span>  
  
     <span data-ttu-id="d6e16-112">Este procedimiento puede aceptar una referencia a `AddNumbers` o `SubtractNumbers`, porque sus firmas coinciden con la `MathOperator` firma.</span><span class="sxs-lookup"><span data-stu-id="d6e16-112">This procedure can accept a reference to `AddNumbers` or `SubtractNumbers`, because their signatures match the `MathOperator` signature.</span></span>  
  
     [!code-vb[VbVbalrDelegates#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]  
  
5.  <span data-ttu-id="d6e16-113">Cree un procedimiento denominado `Test` que llama `DelegateTest` una vez con el delegado para `AddNumbers` como un parámetro y otra con el delegado para `SubtractNumbers` como un parámetro.</span><span class="sxs-lookup"><span data-stu-id="d6e16-113">Create a procedure named `Test` that calls `DelegateTest` once with the delegate for `AddNumbers` as a parameter, and again with the delegate for `SubtractNumbers` as a parameter.</span></span>  
  
     [!code-vb[VbVbalrDelegates#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]  
  
     <span data-ttu-id="d6e16-114">Cuando `Test` es llama, primero muestra el resultado de `AddNumbers` funciona en `5` y `3`, que es 8.</span><span class="sxs-lookup"><span data-stu-id="d6e16-114">When `Test` is called, it first displays the result of `AddNumbers` acting on `5` and `3`, which is 8.</span></span> <span data-ttu-id="d6e16-115">A continuación, el resultado de `SubtractNumbers` actúa en `9` y `3` se muestra, que es 6.</span><span class="sxs-lookup"><span data-stu-id="d6e16-115">Then the result of `SubtractNumbers` acting on `9` and `3` is displayed, which is 6.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6e16-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6e16-116">See Also</span></span>  
 [<span data-ttu-id="d6e16-117">Delegados</span><span class="sxs-lookup"><span data-stu-id="d6e16-117">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="d6e16-118">AddressOf (operador)</span><span class="sxs-lookup"><span data-stu-id="d6e16-118">AddressOf Operator</span></span>](../../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="d6e16-119">Delegate (instrucción)</span><span class="sxs-lookup"><span data-stu-id="d6e16-119">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="d6e16-120">Invocar un método delegado</span><span class="sxs-lookup"><span data-stu-id="d6e16-120">How to: Invoke a Delegate Method</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)

---
title: Procedimiento para pasar procedimientos a otro procedimiento
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: 3a7a653bbf238b50e3c7339da76df0f68ab9b59f
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085794"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a><span data-ttu-id="4026e-102">Cómo: Pasar procedimientos a otro procedimiento en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4026e-102">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>

<span data-ttu-id="4026e-103">En este ejemplo se muestra cómo usar delegados para pasar un procedimiento a otro procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4026e-103">This example shows how to use delegates to pass a procedure to another procedure.</span></span>  
  
 <span data-ttu-id="4026e-104">Un delegado es un tipo que puede usar como cualquier otro tipo en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4026e-104">A delegate is a type that you can use like any other type in Visual Basic.</span></span> <span data-ttu-id="4026e-105">El `AddressOf` operador devuelve un objeto delegado cuando se aplica a un nombre de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4026e-105">The `AddressOf` operator returns a delegate object when applied to a procedure name.</span></span>  
  
 <span data-ttu-id="4026e-106">Este ejemplo tiene un procedimiento con un parámetro de delegado que puede tomar una referencia a otro procedimiento, obtenido con el `AddressOf` operador.</span><span class="sxs-lookup"><span data-stu-id="4026e-106">This example has a procedure with a delegate parameter that can take a reference to another procedure, obtained with the `AddressOf` operator.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="4026e-107">Crear el delegado y los procedimientos coincidentes</span><span class="sxs-lookup"><span data-stu-id="4026e-107">Create the delegate and matching procedures</span></span>  
  
1. <span data-ttu-id="4026e-108">Cree un delegado denominado `MathOperator` .</span><span class="sxs-lookup"><span data-stu-id="4026e-108">Create a delegate named `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#1)]  
  
2. <span data-ttu-id="4026e-109">Cree un procedimiento denominado `AddNumbers` con parámetros y un valor devuelto que coincida con `MathOperator` el de, para que las firmas coincidan.</span><span class="sxs-lookup"><span data-stu-id="4026e-109">Create a procedure named `AddNumbers` with parameters and return value that match those of `MathOperator`, so that the signatures match.</span></span>  
  
     [!code-vb[VbVbalrDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#2)]  
  
3. <span data-ttu-id="4026e-110">Cree un procedimiento denominado `SubtractNumbers` con una firma que coincida con `MathOperator` .</span><span class="sxs-lookup"><span data-stu-id="4026e-110">Create a procedure named `SubtractNumbers` with a signature that matches `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#3)]  
  
4. <span data-ttu-id="4026e-111">Cree un procedimiento denominado `DelegateTest` que tome un delegado como parámetro.</span><span class="sxs-lookup"><span data-stu-id="4026e-111">Create a procedure named `DelegateTest` that takes a delegate as a parameter.</span></span>  
  
     <span data-ttu-id="4026e-112">Este procedimiento puede aceptar una referencia a `AddNumbers` o `SubtractNumbers` , ya que sus firmas coinciden con la `MathOperator` firma.</span><span class="sxs-lookup"><span data-stu-id="4026e-112">This procedure can accept a reference to `AddNumbers` or `SubtractNumbers`, because their signatures match the `MathOperator` signature.</span></span>  
  
     [!code-vb[VbVbalrDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#4)]  
  
5. <span data-ttu-id="4026e-113">Cree un procedimiento denominado `Test` que llame `DelegateTest` una vez con el delegado de `AddNumbers` como parámetro y de nuevo con el delegado de `SubtractNumbers` como parámetro.</span><span class="sxs-lookup"><span data-stu-id="4026e-113">Create a procedure named `Test` that calls `DelegateTest` once with the delegate for `AddNumbers` as a parameter, and again with the delegate for `SubtractNumbers` as a parameter.</span></span>  
  
     [!code-vb[VbVbalrDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#5)]  
  
     <span data-ttu-id="4026e-114">Cuando `Test` se llama a, primero se muestra el resultado de `AddNumbers` actuar en `5` y `3` , que es 8.</span><span class="sxs-lookup"><span data-stu-id="4026e-114">When `Test` is called, it first displays the result of `AddNumbers` acting on `5` and `3`, which is 8.</span></span> <span data-ttu-id="4026e-115">A continuación `SubtractNumbers` , se muestra el resultado de actuar en `9` y `3` , que es 6.</span><span class="sxs-lookup"><span data-stu-id="4026e-115">Then the result of `SubtractNumbers` acting on `9` and `3` is displayed, which is 6.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4026e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="4026e-116">See also</span></span>

- [<span data-ttu-id="4026e-117">Delegados</span><span class="sxs-lookup"><span data-stu-id="4026e-117">Delegates</span></span>](index.md)
- [<span data-ttu-id="4026e-118">Operador AddressOf</span><span class="sxs-lookup"><span data-stu-id="4026e-118">AddressOf Operator</span></span>](../../../language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="4026e-119">Delegate (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="4026e-119">Delegate Statement</span></span>](../../../language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="4026e-120">Procedimiento para invocar un método delegado</span><span class="sxs-lookup"><span data-stu-id="4026e-120">How to: Invoke a Delegate Method</span></span>](how-to-invoke-a-delegate-method.md)

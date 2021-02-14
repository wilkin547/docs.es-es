---
description: 'Más información acerca de cómo: pasar procedimientos a otro procedimiento en Visual Basic'
title: Procedimiento para pasar procedimientos a otro procedimiento
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: dfd75d1f58519365bfb6ac59892238b5322743f3
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434451"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a><span data-ttu-id="7061b-103">Cómo: Pasar procedimientos a otro procedimiento en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7061b-103">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>

<span data-ttu-id="7061b-104">En este ejemplo se muestra cómo usar delegados para pasar un procedimiento a otro procedimiento.</span><span class="sxs-lookup"><span data-stu-id="7061b-104">This example shows how to use delegates to pass a procedure to another procedure.</span></span>  
  
 <span data-ttu-id="7061b-105">Un delegado es un tipo que puede usar como cualquier otro tipo en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7061b-105">A delegate is a type that you can use like any other type in Visual Basic.</span></span> <span data-ttu-id="7061b-106">El `AddressOf` operador devuelve un objeto delegado cuando se aplica a un nombre de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="7061b-106">The `AddressOf` operator returns a delegate object when applied to a procedure name.</span></span>  
  
 <span data-ttu-id="7061b-107">Este ejemplo tiene un procedimiento con un parámetro de delegado que puede tomar una referencia a otro procedimiento, obtenido con el `AddressOf` operador.</span><span class="sxs-lookup"><span data-stu-id="7061b-107">This example has a procedure with a delegate parameter that can take a reference to another procedure, obtained with the `AddressOf` operator.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="7061b-108">Crear el delegado y los procedimientos coincidentes</span><span class="sxs-lookup"><span data-stu-id="7061b-108">Create the delegate and matching procedures</span></span>  
  
1. <span data-ttu-id="7061b-109">Cree un delegado denominado `MathOperator` .</span><span class="sxs-lookup"><span data-stu-id="7061b-109">Create a delegate named `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#1)]  
  
2. <span data-ttu-id="7061b-110">Cree un procedimiento denominado `AddNumbers` con parámetros y un valor devuelto que coincida con `MathOperator` el de, para que las firmas coincidan.</span><span class="sxs-lookup"><span data-stu-id="7061b-110">Create a procedure named `AddNumbers` with parameters and return value that match those of `MathOperator`, so that the signatures match.</span></span>  
  
     [!code-vb[VbVbalrDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#2)]  
  
3. <span data-ttu-id="7061b-111">Cree un procedimiento denominado `SubtractNumbers` con una firma que coincida con `MathOperator` .</span><span class="sxs-lookup"><span data-stu-id="7061b-111">Create a procedure named `SubtractNumbers` with a signature that matches `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#3)]  
  
4. <span data-ttu-id="7061b-112">Cree un procedimiento denominado `DelegateTest` que tome un delegado como parámetro.</span><span class="sxs-lookup"><span data-stu-id="7061b-112">Create a procedure named `DelegateTest` that takes a delegate as a parameter.</span></span>  
  
     <span data-ttu-id="7061b-113">Este procedimiento puede aceptar una referencia a `AddNumbers` o `SubtractNumbers` , ya que sus firmas coinciden con la `MathOperator` firma.</span><span class="sxs-lookup"><span data-stu-id="7061b-113">This procedure can accept a reference to `AddNumbers` or `SubtractNumbers`, because their signatures match the `MathOperator` signature.</span></span>  
  
     [!code-vb[VbVbalrDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#4)]  
  
5. <span data-ttu-id="7061b-114">Cree un procedimiento denominado `Test` que llame `DelegateTest` una vez con el delegado de `AddNumbers` como parámetro y de nuevo con el delegado de `SubtractNumbers` como parámetro.</span><span class="sxs-lookup"><span data-stu-id="7061b-114">Create a procedure named `Test` that calls `DelegateTest` once with the delegate for `AddNumbers` as a parameter, and again with the delegate for `SubtractNumbers` as a parameter.</span></span>  
  
     [!code-vb[VbVbalrDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#5)]  
  
     <span data-ttu-id="7061b-115">Cuando `Test` se llama a, primero se muestra el resultado de `AddNumbers` actuar en `5` y `3` , que es 8.</span><span class="sxs-lookup"><span data-stu-id="7061b-115">When `Test` is called, it first displays the result of `AddNumbers` acting on `5` and `3`, which is 8.</span></span> <span data-ttu-id="7061b-116">A continuación `SubtractNumbers` , se muestra el resultado de actuar en `9` y `3` , que es 6.</span><span class="sxs-lookup"><span data-stu-id="7061b-116">Then the result of `SubtractNumbers` acting on `9` and `3` is displayed, which is 6.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7061b-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7061b-117">See also</span></span>

- [<span data-ttu-id="7061b-118">Delegados</span><span class="sxs-lookup"><span data-stu-id="7061b-118">Delegates</span></span>](index.md)
- [<span data-ttu-id="7061b-119">Operador AddressOf</span><span class="sxs-lookup"><span data-stu-id="7061b-119">AddressOf Operator</span></span>](../../../language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="7061b-120">Delegate (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="7061b-120">Delegate Statement</span></span>](../../../language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="7061b-121">Procedimiento para invocar un método delegado</span><span class="sxs-lookup"><span data-stu-id="7061b-121">How to: Invoke a Delegate Method</span></span>](how-to-invoke-a-delegate-method.md)

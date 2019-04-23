---
title: Procedimiento Pasar procedimientos a otro procedimiento en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: 312c0e0f100e85256ad4ca856ccf7f35dbaa36dc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59305252"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a><span data-ttu-id="08880-102">Procedimiento Pasar procedimientos a otro procedimiento en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="08880-102">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>
<span data-ttu-id="08880-103">En este ejemplo se muestra cómo utilizar a delegados para pasar un procedimiento a otro procedimiento.</span><span class="sxs-lookup"><span data-stu-id="08880-103">This example shows how to use delegates to pass a procedure to another procedure.</span></span>  
  
 <span data-ttu-id="08880-104">Un delegado es un tipo que puede usar como cualquier otro tipo en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="08880-104">A delegate is a type that you can use like any other type in Visual Basic.</span></span> <span data-ttu-id="08880-105">El `AddressOf` operador devuelve un objeto de delegado cuando se aplica a un nombre de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="08880-105">The `AddressOf` operator returns a delegate object when applied to a procedure name.</span></span>  
  
 <span data-ttu-id="08880-106">Este ejemplo tiene un procedimiento con un parámetro de delegado que puede hacer referencia a otro procedimiento obtenido con el `AddressOf` operador.</span><span class="sxs-lookup"><span data-stu-id="08880-106">This example has a procedure with a delegate parameter that can take a reference to another procedure, obtained with the `AddressOf` operator.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="08880-107">Crear el delegado y los procedimientos correspondientes</span><span class="sxs-lookup"><span data-stu-id="08880-107">Create the delegate and matching procedures</span></span>  
  
1. <span data-ttu-id="08880-108">Cree un delegado denominado `MathOperator`.</span><span class="sxs-lookup"><span data-stu-id="08880-108">Create a delegate named `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#1)]  
  
2. <span data-ttu-id="08880-109">Cree un procedimiento denominado `AddNumbers` con parámetros y el valor devuelto que coincidan con los de `MathOperator`, de modo que coincidan con las firmas.</span><span class="sxs-lookup"><span data-stu-id="08880-109">Create a procedure named `AddNumbers` with parameters and return value that match those of `MathOperator`, so that the signatures match.</span></span>  
  
     [!code-vb[VbVbalrDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#2)]  
  
3. <span data-ttu-id="08880-110">Cree un procedimiento denominado `SubtractNumbers` con una firma que coincida con `MathOperator`.</span><span class="sxs-lookup"><span data-stu-id="08880-110">Create a procedure named `SubtractNumbers` with a signature that matches `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#3)]  
  
4. <span data-ttu-id="08880-111">Cree un procedimiento denominado `DelegateTest` que toma un delegado como parámetro.</span><span class="sxs-lookup"><span data-stu-id="08880-111">Create a procedure named `DelegateTest` that takes a delegate as a parameter.</span></span>  
  
     <span data-ttu-id="08880-112">Este procedimiento puede aceptar una referencia a `AddNumbers` o `SubtractNumbers`, porque sus firmas coinciden el `MathOperator` firma.</span><span class="sxs-lookup"><span data-stu-id="08880-112">This procedure can accept a reference to `AddNumbers` or `SubtractNumbers`, because their signatures match the `MathOperator` signature.</span></span>  
  
     [!code-vb[VbVbalrDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#4)]  
  
5. <span data-ttu-id="08880-113">Cree un procedimiento denominado `Test` que llama a `DelegateTest` una vez con el delegado para `AddNumbers` como un parámetro y otra con el delegado para `SubtractNumbers` como un parámetro.</span><span class="sxs-lookup"><span data-stu-id="08880-113">Create a procedure named `Test` that calls `DelegateTest` once with the delegate for `AddNumbers` as a parameter, and again with the delegate for `SubtractNumbers` as a parameter.</span></span>  
  
     [!code-vb[VbVbalrDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#5)]  
  
     <span data-ttu-id="08880-114">Cuando `Test` es llama, primero muestra el resultado de `AddNumbers` que actúa en `5` y `3`, que es 8.</span><span class="sxs-lookup"><span data-stu-id="08880-114">When `Test` is called, it first displays the result of `AddNumbers` acting on `5` and `3`, which is 8.</span></span> <span data-ttu-id="08880-115">A continuación, el resultado de `SubtractNumbers` que actúan en `9` y `3` se muestra, que es 6.</span><span class="sxs-lookup"><span data-stu-id="08880-115">Then the result of `SubtractNumbers` acting on `9` and `3` is displayed, which is 6.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08880-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="08880-116">See also</span></span>

- [<span data-ttu-id="08880-117">Delegados</span><span class="sxs-lookup"><span data-stu-id="08880-117">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="08880-118">AddressOf (operador)</span><span class="sxs-lookup"><span data-stu-id="08880-118">AddressOf Operator</span></span>](../../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="08880-119">Delegate (instrucción)</span><span class="sxs-lookup"><span data-stu-id="08880-119">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="08880-120">Cómo: Invocar un método delegado</span><span class="sxs-lookup"><span data-stu-id="08880-120">How to: Invoke a Delegate Method</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)

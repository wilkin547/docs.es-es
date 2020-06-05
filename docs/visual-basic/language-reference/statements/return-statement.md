---
title: Instrucción Return
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: cdb58e32c30c8e6c1662fb698ac5576c3f71258c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404205"
---
# <a name="return-statement-visual-basic"></a><span data-ttu-id="6c845-102">Return (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6c845-102">Return Statement (Visual Basic)</span></span>
<span data-ttu-id="6c845-103">Devuelve el control al código que llamó a `Function` un `Sub` procedimiento,, `Get` , `Set` o `Operator` .</span><span class="sxs-lookup"><span data-stu-id="6c845-103">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c845-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6c845-104">Syntax</span></span>  
  
```vb  
Return  
' -or-  
Return expression  
```  
  
## <a name="part"></a><span data-ttu-id="6c845-105">Parte</span><span class="sxs-lookup"><span data-stu-id="6c845-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="6c845-106">Requerido en un `Function` `Get` procedimiento, o `Operator` .</span><span class="sxs-lookup"><span data-stu-id="6c845-106">Required in a `Function`, `Get`, or `Operator` procedure.</span></span> <span data-ttu-id="6c845-107">Expresión que representa el valor que se va a devolver al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="6c845-107">Expression that represents the value to be returned to the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c845-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6c845-108">Remarks</span></span>  
 <span data-ttu-id="6c845-109">En un `Sub` `Set` procedimiento o, la `Return` instrucción es equivalente a una `Exit Sub` `Exit Property` instrucción o, y `expression` no se debe proporcionar.</span><span class="sxs-lookup"><span data-stu-id="6c845-109">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span></span>  
  
 <span data-ttu-id="6c845-110">En un `Function` `Get` procedimiento, o `Operator` , la `Return` instrucción debe incluir `expression` y `expression` debe evaluarse como un tipo de datos que se pueda convertir al tipo de valor devuelto del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6c845-110">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span></span> <span data-ttu-id="6c845-111">En un `Function` `Get` procedimiento o, también tiene la alternativa de asignar una expresión al nombre del procedimiento para que sirva como valor devuelto y, a continuación, ejecutar una `Exit Function` instrucción o `Exit Property` .</span><span class="sxs-lookup"><span data-stu-id="6c845-111">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span></span> <span data-ttu-id="6c845-112">En un `Operator` procedimiento, debe usar `Return expression` .</span><span class="sxs-lookup"><span data-stu-id="6c845-112">In an `Operator` procedure, you must use `Return expression`.</span></span>  
  
 <span data-ttu-id="6c845-113">Puede incluir tantas `Return` instrucciones como corresponda en el mismo procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6c845-113">You can include as many `Return` statements as appropriate in the same procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6c845-114">El código de un `Finally` bloque se ejecuta después de `Return` que se encuentre una instrucción en un `Try` `Catch` bloque o, pero antes de que se `Return` ejecute la instrucción.</span><span class="sxs-lookup"><span data-stu-id="6c845-114">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span></span> <span data-ttu-id="6c845-115">`Return`No se puede incluir una instrucción en un `Finally` bloque.</span><span class="sxs-lookup"><span data-stu-id="6c845-115">A `Return` statement cannot be included in a `Finally` block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c845-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6c845-116">Example</span></span>  
 <span data-ttu-id="6c845-117">En el ejemplo siguiente se utiliza la `Return` instrucción varias veces para volver al código de llamada cuando el procedimiento no tiene que hacer nada más.</span><span class="sxs-lookup"><span data-stu-id="6c845-117">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span></span>  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a><span data-ttu-id="6c845-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6c845-118">See also</span></span>

- [<span data-ttu-id="6c845-119">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="6c845-119">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="6c845-120">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="6c845-120">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="6c845-121">Get (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="6c845-121">Get Statement</span></span>](get-statement.md)
- [<span data-ttu-id="6c845-122">Set (instrucción)</span><span class="sxs-lookup"><span data-stu-id="6c845-122">Set Statement</span></span>](set-statement.md)
- [<span data-ttu-id="6c845-123">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="6c845-123">Operator Statement</span></span>](operator-statement.md)
- [<span data-ttu-id="6c845-124">Property Statement</span><span class="sxs-lookup"><span data-stu-id="6c845-124">Property Statement</span></span>](property-statement.md)
- [<span data-ttu-id="6c845-125">Instrucción Exit</span><span class="sxs-lookup"><span data-stu-id="6c845-125">Exit Statement</span></span>](exit-statement.md)
- [<span data-ttu-id="6c845-126">Instrucción Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="6c845-126">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)

---
title: Return (Instrucción, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: af49ea95d7f9d01072190ac3ccf6ba2f1041347e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957673"
---
# <a name="return-statement-visual-basic"></a><span data-ttu-id="7b1e1-102">Return (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b1e1-102">Return Statement (Visual Basic)</span></span>
<span data-ttu-id="7b1e1-103">Devuelve el control al código que llamó a `Function`un `Sub`procedimiento `Get`, `Set`,, `Operator` o.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-103">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b1e1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b1e1-104">Syntax</span></span>  
  
```  
Return  
-or-  
Return expression  
```  
  
## <a name="part"></a><span data-ttu-id="7b1e1-105">Parte</span><span class="sxs-lookup"><span data-stu-id="7b1e1-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="7b1e1-106">Requerido en un `Function`procedimiento `Get`, o `Operator` .</span><span class="sxs-lookup"><span data-stu-id="7b1e1-106">Required in a `Function`, `Get`, or `Operator` procedure.</span></span> <span data-ttu-id="7b1e1-107">Expresión que representa el valor que se va a devolver al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-107">Expression that represents the value to be returned to the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b1e1-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7b1e1-108">Remarks</span></span>  
 <span data-ttu-id="7b1e1-109">En un `Sub` procedimiento `Set` o, la `Return` instrucción es equivalente a una `Exit Sub` instrucción `Exit Property` o, y `expression` no se debe proporcionar.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-109">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span></span>  
  
 <span data-ttu-id="7b1e1-110">En un `Function`procedimiento `Get`, o `Operator` , la `Return` instrucción debe incluir `expression`y `expression` debe evaluarse como un tipo de datos que se pueda convertir al tipo de valor devuelto del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-110">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span></span> <span data-ttu-id="7b1e1-111">En un `Function` procedimiento `Get` o, también tiene la alternativa de asignar una expresión al nombre del procedimiento para que sirva como valor devuelto y, a continuación, ejecutar una `Exit Function` instrucción o `Exit Property` .</span><span class="sxs-lookup"><span data-stu-id="7b1e1-111">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span></span> <span data-ttu-id="7b1e1-112">En un `Operator` procedimiento, debe usar `Return expression`.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-112">In an `Operator` procedure, you must use `Return expression`.</span></span>  
  
 <span data-ttu-id="7b1e1-113">Puede incluir tantas `Return` instrucciones como corresponda en el mismo procedimiento.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-113">You can include as many `Return` statements as appropriate in the same procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7b1e1-114">El código de un `Finally` bloque se ejecuta después de que se `Try` encuentre `Catch` una instrucción en un bloque o, `Return` pero antes de que se ejecute la `Return` instrucción.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-114">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span></span> <span data-ttu-id="7b1e1-115">No `Return` se puede incluir una instrucción en `Finally` un bloque.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-115">A `Return` statement cannot be included in a `Finally` block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b1e1-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7b1e1-116">Example</span></span>  
 <span data-ttu-id="7b1e1-117">En el ejemplo siguiente se `Return` utiliza la instrucción varias veces para volver al código de llamada cuando el procedimiento no tiene que hacer nada más.</span><span class="sxs-lookup"><span data-stu-id="7b1e1-117">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span></span>  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a><span data-ttu-id="7b1e1-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b1e1-118">See also</span></span>

- [<span data-ttu-id="7b1e1-119">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="7b1e1-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="7b1e1-120">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="7b1e1-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="7b1e1-121">Get (instrucción)</span><span class="sxs-lookup"><span data-stu-id="7b1e1-121">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="7b1e1-122">Set (instrucción)</span><span class="sxs-lookup"><span data-stu-id="7b1e1-122">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
- [<span data-ttu-id="7b1e1-123">Operator (instrucción)</span><span class="sxs-lookup"><span data-stu-id="7b1e1-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="7b1e1-124">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="7b1e1-124">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="7b1e1-125">Exit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="7b1e1-125">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="7b1e1-126">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="7b1e1-126">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)

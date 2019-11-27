---
title: Return (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: efc85a3a844898345aa2d16926ba0e35d7346d1b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333011"
---
# <a name="return-statement-visual-basic"></a><span data-ttu-id="96464-102">Return (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96464-102">Return Statement (Visual Basic)</span></span>
<span data-ttu-id="96464-103">Devuelve el control al código que llamó a un procedimiento `Function`, `Sub`, `Get`, `Set`o `Operator`.</span><span class="sxs-lookup"><span data-stu-id="96464-103">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96464-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="96464-104">Syntax</span></span>  
  
```vb  
Return  
' -or-  
Return expression  
```  
  
## <a name="part"></a><span data-ttu-id="96464-105">Parte</span><span class="sxs-lookup"><span data-stu-id="96464-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="96464-106">Obligatorio en un procedimiento `Function`, `Get`o `Operator`.</span><span class="sxs-lookup"><span data-stu-id="96464-106">Required in a `Function`, `Get`, or `Operator` procedure.</span></span> <span data-ttu-id="96464-107">Expresión que representa el valor que se va a devolver al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="96464-107">Expression that represents the value to be returned to the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96464-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="96464-108">Remarks</span></span>  
 <span data-ttu-id="96464-109">En un procedimiento `Sub` o `Set`, la instrucción `Return` es equivalente a una instrucción `Exit Sub` o `Exit Property` y no se debe proporcionar `expression`.</span><span class="sxs-lookup"><span data-stu-id="96464-109">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span></span>  
  
 <span data-ttu-id="96464-110">En un procedimiento `Function`, `Get`o `Operator`, la instrucción `Return` debe incluir `expression`y `expression` debe evaluarse como un tipo de datos que se pueda convertir al tipo de valor devuelto del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="96464-110">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span></span> <span data-ttu-id="96464-111">En un procedimiento `Function` o `Get`, también tiene la alternativa de asignar una expresión al nombre del procedimiento para que sirva como valor devuelto y, a continuación, ejecutar una instrucción `Exit Function` o `Exit Property`.</span><span class="sxs-lookup"><span data-stu-id="96464-111">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span></span> <span data-ttu-id="96464-112">En un procedimiento `Operator`, debe utilizar `Return expression`.</span><span class="sxs-lookup"><span data-stu-id="96464-112">In an `Operator` procedure, you must use `Return expression`.</span></span>  
  
 <span data-ttu-id="96464-113">Puede incluir tantas instrucciones `Return` como corresponda en el mismo procedimiento.</span><span class="sxs-lookup"><span data-stu-id="96464-113">You can include as many `Return` statements as appropriate in the same procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="96464-114">El código de un bloque de `Finally` se ejecuta después de que se encuentre una instrucción de `Return` en un bloque de `Try` o `Catch`, pero antes de que se ejecute la instrucción `Return`.</span><span class="sxs-lookup"><span data-stu-id="96464-114">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span></span> <span data-ttu-id="96464-115">No se puede incluir una instrucción `Return` en un bloque de `Finally`.</span><span class="sxs-lookup"><span data-stu-id="96464-115">A `Return` statement cannot be included in a `Finally` block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96464-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="96464-116">Example</span></span>  
 <span data-ttu-id="96464-117">En el ejemplo siguiente se utiliza la instrucción `Return` varias veces para volver al código de llamada cuando el procedimiento no tiene que hacer nada más.</span><span class="sxs-lookup"><span data-stu-id="96464-117">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span></span>  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a><span data-ttu-id="96464-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="96464-118">See also</span></span>

- [<span data-ttu-id="96464-119">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="96464-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="96464-120">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="96464-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="96464-121">Get (instrucción)</span><span class="sxs-lookup"><span data-stu-id="96464-121">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="96464-122">Set (instrucción)</span><span class="sxs-lookup"><span data-stu-id="96464-122">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
- [<span data-ttu-id="96464-123">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="96464-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="96464-124">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="96464-124">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="96464-125">Exit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="96464-125">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="96464-126">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="96464-126">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)

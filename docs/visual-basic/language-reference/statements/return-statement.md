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
ms.openlocfilehash: 00d9f09bed513199d579c9e1c3f831b729e68839
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977141"
---
# <a name="return-statement-visual-basic"></a><span data-ttu-id="01687-102">Return (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01687-102">Return Statement (Visual Basic)</span></span>
<span data-ttu-id="01687-103">Devuelve el control al código que llama a un `Function`, `Sub`, `Get`, `Set`, o `Operator` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="01687-103">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01687-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="01687-104">Syntax</span></span>  
  
```  
Return  
-or-  
Return expression  
```  
  
## <a name="part"></a><span data-ttu-id="01687-105">Parte</span><span class="sxs-lookup"><span data-stu-id="01687-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="01687-106">Necesario en un `Function`, `Get`, o `Operator` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="01687-106">Required in a `Function`, `Get`, or `Operator` procedure.</span></span> <span data-ttu-id="01687-107">Expresión que representa el valor que se devolverá al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="01687-107">Expression that represents the value to be returned to the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01687-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="01687-108">Remarks</span></span>  
 <span data-ttu-id="01687-109">En un `Sub` o `Set` procedimiento, el `Return` instrucción es equivalente a un `Exit Sub` o `Exit Property` instrucción, y `expression` no se debe proporcionar.</span><span class="sxs-lookup"><span data-stu-id="01687-109">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span></span>  
  
 <span data-ttu-id="01687-110">En un `Function`, `Get`, o `Operator` procedimiento, el `Return` debe incluir la instrucción `expression`, y `expression` debe evaluarse como un tipo de datos que se pueda convertir al tipo de valor devuelto del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="01687-110">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span></span> <span data-ttu-id="01687-111">En un `Function` o `Get` procedimiento, también tiene la alternativa de asignación de una expresión para el nombre del procedimiento para que actúe como el valor devuelto y, a continuación, ejecutando un `Exit Function` o `Exit Property` instrucción.</span><span class="sxs-lookup"><span data-stu-id="01687-111">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span></span> <span data-ttu-id="01687-112">En un `Operator` procedimiento, debe usar `Return expression`.</span><span class="sxs-lookup"><span data-stu-id="01687-112">In an `Operator` procedure, you must use `Return expression`.</span></span>  
  
 <span data-ttu-id="01687-113">Puede incluir tantos `Return` instrucciones según corresponda en el mismo procedimiento.</span><span class="sxs-lookup"><span data-stu-id="01687-113">You can include as many `Return` statements as appropriate in the same procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="01687-114">El código en un `Finally` bloque se ejecuta después de un `Return` instrucción en un `Try` o `Catch` bloque es se ha encontrado, pero antes de que `Return` ejecuta la instrucción.</span><span class="sxs-lookup"><span data-stu-id="01687-114">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span></span> <span data-ttu-id="01687-115">Un `Return` instrucción no puede incluirse en un `Finally` bloque.</span><span class="sxs-lookup"><span data-stu-id="01687-115">A `Return` statement cannot be included in a `Finally` block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01687-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="01687-116">Example</span></span>  
 <span data-ttu-id="01687-117">En el ejemplo siguiente se usa el `Return` instrucción varias veces para volver al código de llamada cuando el procedimiento no tiene que hacer nada más.</span><span class="sxs-lookup"><span data-stu-id="01687-117">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span></span>  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a><span data-ttu-id="01687-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="01687-118">See also</span></span>
- [<span data-ttu-id="01687-119">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="01687-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="01687-120">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="01687-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="01687-121">Get (instrucción)</span><span class="sxs-lookup"><span data-stu-id="01687-121">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="01687-122">Set (instrucción)</span><span class="sxs-lookup"><span data-stu-id="01687-122">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
- [<span data-ttu-id="01687-123">Operator (instrucción)</span><span class="sxs-lookup"><span data-stu-id="01687-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="01687-124">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="01687-124">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="01687-125">Exit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="01687-125">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="01687-126">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="01687-126">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)

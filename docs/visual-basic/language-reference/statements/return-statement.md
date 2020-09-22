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
ms.openlocfilehash: 3ca705409bc8233bc2562c64b8e7704f08dd7641
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871800"
---
# <a name="return-statement-visual-basic"></a><span data-ttu-id="c67a6-102">Return (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c67a6-102">Return Statement (Visual Basic)</span></span>

<span data-ttu-id="c67a6-103">Devuelve el control al código que llamó a `Function` un `Sub` procedimiento,, `Get` , `Set` o `Operator` .</span><span class="sxs-lookup"><span data-stu-id="c67a6-103">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c67a6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c67a6-104">Syntax</span></span>  
  
```vb  
Return  
' -or-  
Return expression  
```  
  
## <a name="part"></a><span data-ttu-id="c67a6-105">Parte</span><span class="sxs-lookup"><span data-stu-id="c67a6-105">Part</span></span>  

 `expression`  
 <span data-ttu-id="c67a6-106">Requerido en un `Function` `Get` procedimiento, o `Operator` .</span><span class="sxs-lookup"><span data-stu-id="c67a6-106">Required in a `Function`, `Get`, or `Operator` procedure.</span></span> <span data-ttu-id="c67a6-107">Expresión que representa el valor que se va a devolver al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="c67a6-107">Expression that represents the value to be returned to the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c67a6-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c67a6-108">Remarks</span></span>  

 <span data-ttu-id="c67a6-109">En un `Sub` `Set` procedimiento o, la `Return` instrucción es equivalente a una `Exit Sub` `Exit Property` instrucción o, y `expression` no se debe proporcionar.</span><span class="sxs-lookup"><span data-stu-id="c67a6-109">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span></span>  
  
 <span data-ttu-id="c67a6-110">En un `Function` `Get` procedimiento, o `Operator` , la `Return` instrucción debe incluir `expression` y `expression` debe evaluarse como un tipo de datos que se pueda convertir al tipo de valor devuelto del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c67a6-110">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span></span> <span data-ttu-id="c67a6-111">En un `Function` `Get` procedimiento o, también tiene la alternativa de asignar una expresión al nombre del procedimiento para que sirva como valor devuelto y, a continuación, ejecutar una `Exit Function` instrucción o `Exit Property` .</span><span class="sxs-lookup"><span data-stu-id="c67a6-111">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span></span> <span data-ttu-id="c67a6-112">En un `Operator` procedimiento, debe usar `Return expression` .</span><span class="sxs-lookup"><span data-stu-id="c67a6-112">In an `Operator` procedure, you must use `Return expression`.</span></span>  
  
 <span data-ttu-id="c67a6-113">Puede incluir tantas `Return` instrucciones como corresponda en el mismo procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c67a6-113">You can include as many `Return` statements as appropriate in the same procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c67a6-114">El código de un `Finally` bloque se ejecuta después de `Return` que se encuentre una instrucción en un `Try` `Catch` bloque o, pero antes de que se `Return` ejecute la instrucción.</span><span class="sxs-lookup"><span data-stu-id="c67a6-114">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span></span> <span data-ttu-id="c67a6-115">`Return`No se puede incluir una instrucción en un `Finally` bloque.</span><span class="sxs-lookup"><span data-stu-id="c67a6-115">A `Return` statement cannot be included in a `Finally` block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c67a6-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c67a6-116">Example</span></span>  

 <span data-ttu-id="c67a6-117">En el ejemplo siguiente se utiliza la `Return` instrucción varias veces para volver al código de llamada cuando el procedimiento no tiene que hacer nada más.</span><span class="sxs-lookup"><span data-stu-id="c67a6-117">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span></span>  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a><span data-ttu-id="c67a6-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c67a6-118">See also</span></span>

- [<span data-ttu-id="c67a6-119">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="c67a6-119">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="c67a6-120">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="c67a6-120">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="c67a6-121">Get (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="c67a6-121">Get Statement</span></span>](get-statement.md)
- [<span data-ttu-id="c67a6-122">Set (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c67a6-122">Set Statement</span></span>](set-statement.md)
- [<span data-ttu-id="c67a6-123">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="c67a6-123">Operator Statement</span></span>](operator-statement.md)
- [<span data-ttu-id="c67a6-124">Property Statement</span><span class="sxs-lookup"><span data-stu-id="c67a6-124">Property Statement</span></span>](property-statement.md)
- [<span data-ttu-id="c67a6-125">Instrucción Exit</span><span class="sxs-lookup"><span data-stu-id="c67a6-125">Exit Statement</span></span>](exit-statement.md)
- [<span data-ttu-id="c67a6-126">Try... Detectar... Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c67a6-126">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)

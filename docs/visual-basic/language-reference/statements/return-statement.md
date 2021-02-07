---
description: 'Más información sobre: Return (instrucción) (Visual Basic)'
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
ms.openlocfilehash: 62086090ede7e634b09d3edc3dc42feb28d15793
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741203"
---
# <a name="return-statement-visual-basic"></a><span data-ttu-id="c7909-103">Return (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7909-103">Return Statement (Visual Basic)</span></span>

<span data-ttu-id="c7909-104">Devuelve el control al código que llamó a `Function` un `Sub` procedimiento,, `Get` , `Set` o `Operator` .</span><span class="sxs-lookup"><span data-stu-id="c7909-104">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7909-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c7909-105">Syntax</span></span>  
  
```vb  
Return  
' -or-  
Return expression  
```  
  
## <a name="part"></a><span data-ttu-id="c7909-106">Parte</span><span class="sxs-lookup"><span data-stu-id="c7909-106">Part</span></span>  

 `expression`  
 <span data-ttu-id="c7909-107">Requerido en un `Function` `Get` procedimiento, o `Operator` .</span><span class="sxs-lookup"><span data-stu-id="c7909-107">Required in a `Function`, `Get`, or `Operator` procedure.</span></span> <span data-ttu-id="c7909-108">Expresión que representa el valor que se va a devolver al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="c7909-108">Expression that represents the value to be returned to the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7909-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c7909-109">Remarks</span></span>  

 <span data-ttu-id="c7909-110">En un `Sub` `Set` procedimiento o, la `Return` instrucción es equivalente a una `Exit Sub` `Exit Property` instrucción o, y `expression` no se debe proporcionar.</span><span class="sxs-lookup"><span data-stu-id="c7909-110">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span></span>  
  
 <span data-ttu-id="c7909-111">En un `Function` `Get` procedimiento, o `Operator` , la `Return` instrucción debe incluir `expression` y `expression` debe evaluarse como un tipo de datos que se pueda convertir al tipo de valor devuelto del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c7909-111">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span></span> <span data-ttu-id="c7909-112">En un `Function` `Get` procedimiento o, también tiene la alternativa de asignar una expresión al nombre del procedimiento para que sirva como valor devuelto y, a continuación, ejecutar una `Exit Function` instrucción o `Exit Property` .</span><span class="sxs-lookup"><span data-stu-id="c7909-112">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span></span> <span data-ttu-id="c7909-113">En un `Operator` procedimiento, debe usar `Return expression` .</span><span class="sxs-lookup"><span data-stu-id="c7909-113">In an `Operator` procedure, you must use `Return expression`.</span></span>  
  
 <span data-ttu-id="c7909-114">Puede incluir tantas `Return` instrucciones como corresponda en el mismo procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c7909-114">You can include as many `Return` statements as appropriate in the same procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c7909-115">El código de un `Finally` bloque se ejecuta después de `Return` que se encuentre una instrucción en un `Try` `Catch` bloque o, pero antes de que se `Return` ejecute la instrucción.</span><span class="sxs-lookup"><span data-stu-id="c7909-115">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span></span> <span data-ttu-id="c7909-116">`Return`No se puede incluir una instrucción en un `Finally` bloque.</span><span class="sxs-lookup"><span data-stu-id="c7909-116">A `Return` statement cannot be included in a `Finally` block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7909-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c7909-117">Example</span></span>  

 <span data-ttu-id="c7909-118">En el ejemplo siguiente se utiliza la `Return` instrucción varias veces para volver al código de llamada cuando el procedimiento no tiene que hacer nada más.</span><span class="sxs-lookup"><span data-stu-id="c7909-118">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span></span>  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a><span data-ttu-id="c7909-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7909-119">See also</span></span>

- [<span data-ttu-id="c7909-120">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="c7909-120">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="c7909-121">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="c7909-121">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="c7909-122">Get (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="c7909-122">Get Statement</span></span>](get-statement.md)
- [<span data-ttu-id="c7909-123">Set (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c7909-123">Set Statement</span></span>](set-statement.md)
- [<span data-ttu-id="c7909-124">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="c7909-124">Operator Statement</span></span>](operator-statement.md)
- [<span data-ttu-id="c7909-125">Property Statement</span><span class="sxs-lookup"><span data-stu-id="c7909-125">Property Statement</span></span>](property-statement.md)
- [<span data-ttu-id="c7909-126">Instrucción Exit</span><span class="sxs-lookup"><span data-stu-id="c7909-126">Exit Statement</span></span>](exit-statement.md)
- [<span data-ttu-id="c7909-127">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c7909-127">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)

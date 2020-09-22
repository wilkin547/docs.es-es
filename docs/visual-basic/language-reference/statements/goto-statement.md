---
title: GoTo (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.GoTo
helpviewer_keywords:
- GoTo statement [Visual Basic]
- control flow [Visual Basic], branching
- unconditional branching [Visual Basic]
- branching [Visual Basic]
- branching [Visual Basic], unconditional
- branching [Visual Basic], conditional
- conditional statements [Visual Basic], GoTo statement
- GoTo statement [Visual Basic], syntax
ms.assetid: 313274c2-8ab3-4b9c-9ba3-0fd6798e4f6d
ms.openlocfilehash: 000f6754575bcce6b2d79d85541e755219aca956
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866614"
---
# <a name="goto-statement"></a><span data-ttu-id="33f80-102">GoTo (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="33f80-102">GoTo Statement</span></span>

<span data-ttu-id="33f80-103">Bifurca incondicionalmente a una línea especificada en un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="33f80-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33f80-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33f80-104">Syntax</span></span>  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="33f80-105">Parte</span><span class="sxs-lookup"><span data-stu-id="33f80-105">Part</span></span>  

 `line`  
 <span data-ttu-id="33f80-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="33f80-106">Required.</span></span> <span data-ttu-id="33f80-107">Cualquier etiqueta de línea.</span><span class="sxs-lookup"><span data-stu-id="33f80-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33f80-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="33f80-108">Remarks</span></span>  

 <span data-ttu-id="33f80-109">La `GoTo` instrucción solo puede bifurcar a las líneas del procedimiento en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="33f80-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="33f80-110">La línea debe tener una etiqueta de línea que `GoTo` pueda hacer referencia a.</span><span class="sxs-lookup"><span data-stu-id="33f80-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="33f80-111">Para obtener más información, vea [Cómo: etiquetar instrucciones](../../programming-guide/program-structure/how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="33f80-111">For more information, see [How to: Label Statements](../../programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="33f80-112">`GoTo` las instrucciones pueden hacer que el código sea difícil de leer y mantener.</span><span class="sxs-lookup"><span data-stu-id="33f80-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="33f80-113">Siempre que sea posible, use una estructura de control en su lugar.</span><span class="sxs-lookup"><span data-stu-id="33f80-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="33f80-114">Para más información, consulte [Control Flow](../../programming-guide/language-features/control-flow/index.md).</span><span class="sxs-lookup"><span data-stu-id="33f80-114">For more information, see [Control Flow](../../programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="33f80-115">No se puede usar una `GoTo` instrucción para bifurcar desde fuera de `For` ... `Next` ,.. `For Each` . `Next` , `SyncLock` . `End SyncLock` . `Try` `Catch` .,... ... `Finally` , `With` ... `End With` o `Using` ... `End Using` en una etiqueta dentro de.</span><span class="sxs-lookup"><span data-stu-id="33f80-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="33f80-116">Bifurcación y construcciones try</span><span class="sxs-lookup"><span data-stu-id="33f80-116">Branching and Try Constructions</span></span>  

 <span data-ttu-id="33f80-117">Dentro de `Try` ... `Catch` ...`Finally` la construcción de, se aplican las siguientes reglas a la bifurcación con la `GoTo` instrucción.</span><span class="sxs-lookup"><span data-stu-id="33f80-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="33f80-118">Bloque o región</span><span class="sxs-lookup"><span data-stu-id="33f80-118">Block or region</span></span>|<span data-ttu-id="33f80-119">Bifurcación desde fuera</span><span class="sxs-lookup"><span data-stu-id="33f80-119">Branching in from outside</span></span>|<span data-ttu-id="33f80-120">Bifurcar desde dentro</span><span class="sxs-lookup"><span data-stu-id="33f80-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="33f80-121">`Try` sin</span><span class="sxs-lookup"><span data-stu-id="33f80-121">`Try` block</span></span>|<span data-ttu-id="33f80-122">Solo desde un `Catch` bloque de la misma construcción <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="33f80-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="33f80-123">Solo hacia fuera de la construcción completa</span><span class="sxs-lookup"><span data-stu-id="33f80-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="33f80-124">`Catch` sin</span><span class="sxs-lookup"><span data-stu-id="33f80-124">`Catch` block</span></span>|<span data-ttu-id="33f80-125">Nunca permitido</span><span class="sxs-lookup"><span data-stu-id="33f80-125">Never allowed</span></span>|<span data-ttu-id="33f80-126">Solo hacia fuera de la construcción completa o hasta el `Try` bloque de la misma construcción <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="33f80-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="33f80-127">`Finally` sin</span><span class="sxs-lookup"><span data-stu-id="33f80-127">`Finally` block</span></span>|<span data-ttu-id="33f80-128">Nunca permitido</span><span class="sxs-lookup"><span data-stu-id="33f80-128">Never allowed</span></span>|<span data-ttu-id="33f80-129">Nunca permitido</span><span class="sxs-lookup"><span data-stu-id="33f80-129">Never allowed</span></span>|  
  
 <span data-ttu-id="33f80-130"><sup>1</sup> si uno `Try` ... `Catch` ...`Finally` la construcción está anidada dentro de otra, un `Catch` bloque se puede bifurcar en el `Try` bloque en su propio nivel de anidamiento, pero no en ningún otro `Try` bloque.</span><span class="sxs-lookup"><span data-stu-id="33f80-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="33f80-131">Una instrucción anidada `Try` ... `Catch` ...`Finally` la construcción debe estar contenida completamente en un `Try` `Catch` bloque o de la construcción en la que está anidada.</span><span class="sxs-lookup"><span data-stu-id="33f80-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="33f80-132">En la ilustración siguiente se muestra una `Try` construcción anidada dentro de otra.</span><span class="sxs-lookup"><span data-stu-id="33f80-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="33f80-133">Varias ramas entre los bloques de las dos construcciones se indican como válidas o no válidas.</span><span class="sxs-lookup"><span data-stu-id="33f80-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 ![Diagrama gráfico de bifurcación en construcciones Try](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a><span data-ttu-id="33f80-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="33f80-135">Example</span></span>  

 <span data-ttu-id="33f80-136">En el ejemplo siguiente se usa la `GoTo` instrucción para bifurcar a las etiquetas de línea de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="33f80-136">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="33f80-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="33f80-137">See also</span></span>

- [<span data-ttu-id="33f80-138">Instrucción Do...Loop</span><span class="sxs-lookup"><span data-stu-id="33f80-138">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="33f80-139">Instrucción For...Next</span><span class="sxs-lookup"><span data-stu-id="33f80-139">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="33f80-140">Instrucción For Each...Next</span><span class="sxs-lookup"><span data-stu-id="33f80-140">For Each...Next Statement</span></span>](for-each-next-statement.md)
- [<span data-ttu-id="33f80-141">Instrucción If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="33f80-141">If...Then...Else Statement</span></span>](if-then-else-statement.md)
- [<span data-ttu-id="33f80-142">Instrucción Select...Case</span><span class="sxs-lookup"><span data-stu-id="33f80-142">Select...Case Statement</span></span>](select-case-statement.md)
- [<span data-ttu-id="33f80-143">Instrucción Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="33f80-143">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
- [<span data-ttu-id="33f80-144">Instrucción While...End While</span><span class="sxs-lookup"><span data-stu-id="33f80-144">While...End While Statement</span></span>](while-end-while-statement.md)
- [<span data-ttu-id="33f80-145">Instrucción With...End With</span><span class="sxs-lookup"><span data-stu-id="33f80-145">With...End With Statement</span></span>](with-end-with-statement.md)

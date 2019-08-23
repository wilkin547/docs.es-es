---
title: GoTo (instrucción) (Visual Basic)
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
ms.openlocfilehash: 3034c84684e94dfe8c334107a16df8cbd227c4d4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912448"
---
# <a name="goto-statement"></a><span data-ttu-id="5436d-102">GoTo (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="5436d-102">GoTo Statement</span></span>
<span data-ttu-id="5436d-103">Bifurca incondicionalmente a una línea especificada en un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="5436d-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5436d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5436d-104">Syntax</span></span>  
  
```  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="5436d-105">Parte</span><span class="sxs-lookup"><span data-stu-id="5436d-105">Part</span></span>  
 `line`  
 <span data-ttu-id="5436d-106">Necesario.</span><span class="sxs-lookup"><span data-stu-id="5436d-106">Required.</span></span> <span data-ttu-id="5436d-107">Cualquier etiqueta de línea.</span><span class="sxs-lookup"><span data-stu-id="5436d-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5436d-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5436d-108">Remarks</span></span>  
 <span data-ttu-id="5436d-109">La `GoTo` instrucción solo puede bifurcar a las líneas del procedimiento en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="5436d-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="5436d-110">La línea debe tener una etiqueta de línea `GoTo` que pueda hacer referencia a.</span><span class="sxs-lookup"><span data-stu-id="5436d-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="5436d-111">Para obtener más información, vea [Cómo: Instrucciones](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="5436d-111">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5436d-112">`GoTo`las instrucciones pueden hacer que el código sea difícil de leer y mantener.</span><span class="sxs-lookup"><span data-stu-id="5436d-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="5436d-113">Siempre que sea posible, use una estructura de control en su lugar.</span><span class="sxs-lookup"><span data-stu-id="5436d-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="5436d-114">Para obtener más información, consulte [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span><span class="sxs-lookup"><span data-stu-id="5436d-114">For more information, see [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="5436d-115">No se puede usar `GoTo` una instrucción para bifurcar desde `For`fuera de... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, `With`... `End With`, o`Using`... `End Using` construcción de una etiqueta dentro de.</span><span class="sxs-lookup"><span data-stu-id="5436d-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="5436d-116">Bifurcación y construcciones try</span><span class="sxs-lookup"><span data-stu-id="5436d-116">Branching and Try Constructions</span></span>  
 <span data-ttu-id="5436d-117">Dentro de `Try`... `Catch`... la construcción de, se aplican las siguientes reglas a `GoTo` la bifurcación con la instrucción. `Finally`</span><span class="sxs-lookup"><span data-stu-id="5436d-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="5436d-118">Bloque o región</span><span class="sxs-lookup"><span data-stu-id="5436d-118">Block or region</span></span>|<span data-ttu-id="5436d-119">Bifurcación desde fuera</span><span class="sxs-lookup"><span data-stu-id="5436d-119">Branching in from outside</span></span>|<span data-ttu-id="5436d-120">Bifurcar desde dentro</span><span class="sxs-lookup"><span data-stu-id="5436d-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="5436d-121">`Try`sin</span><span class="sxs-lookup"><span data-stu-id="5436d-121">`Try` block</span></span>|<span data-ttu-id="5436d-122">Solo desde un `Catch` bloque de la misma construcción <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5436d-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="5436d-123">Solo hacia fuera de la construcción completa</span><span class="sxs-lookup"><span data-stu-id="5436d-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="5436d-124">`Catch`sin</span><span class="sxs-lookup"><span data-stu-id="5436d-124">`Catch` block</span></span>|<span data-ttu-id="5436d-125">Nunca permitido</span><span class="sxs-lookup"><span data-stu-id="5436d-125">Never allowed</span></span>|<span data-ttu-id="5436d-126">Solo hacia fuera de la construcción completa o hasta el `Try` bloque de la misma construcción <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5436d-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="5436d-127">`Finally`sin</span><span class="sxs-lookup"><span data-stu-id="5436d-127">`Finally` block</span></span>|<span data-ttu-id="5436d-128">Nunca permitido</span><span class="sxs-lookup"><span data-stu-id="5436d-128">Never allowed</span></span>|<span data-ttu-id="5436d-129">Nunca permitido</span><span class="sxs-lookup"><span data-stu-id="5436d-129">Never allowed</span></span>|  
  
 <span data-ttu-id="5436d-130"><sup>1</sup> si uno `Try`... `Catch`... la construcción está anidada dentro de otra `Catch` , un bloque se puede `Try` bifurcar en el bloque en su propio nivel de anidamiento, pero `Try` no en ningún otro bloque. `Finally`</span><span class="sxs-lookup"><span data-stu-id="5436d-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="5436d-131">Una instrucción anidada `Try`... `Catch`... la construcción debe estar contenida completamente `Try` en `Catch` un bloque o de la construcción en la que está anidada. `Finally`</span><span class="sxs-lookup"><span data-stu-id="5436d-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="5436d-132">En la ilustración siguiente se `Try` muestra una construcción anidada dentro de otra.</span><span class="sxs-lookup"><span data-stu-id="5436d-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="5436d-133">Varias ramas entre los bloques de las dos construcciones se indican como válidas o no válidas.</span><span class="sxs-lookup"><span data-stu-id="5436d-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 ![Diagrama gráfico de bifurcación en construcciones Try](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a><span data-ttu-id="5436d-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5436d-135">Example</span></span>  
 <span data-ttu-id="5436d-136">En el ejemplo siguiente se `GoTo` usa la instrucción para bifurcar a las etiquetas de línea de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="5436d-136">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="5436d-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="5436d-137">See also</span></span>

- [<span data-ttu-id="5436d-138">Do...Loop (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5436d-138">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="5436d-139">For...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5436d-139">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="5436d-140">For Each...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5436d-140">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="5436d-141">If...Then...Else (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5436d-141">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="5436d-142">Select...Case (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5436d-142">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="5436d-143">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5436d-143">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="5436d-144">While...End While (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5436d-144">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="5436d-145">With...End With (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5436d-145">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)

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
ms.openlocfilehash: 5e7aa036f632b4c310c4978d0d684c1222d2b096
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2019
ms.locfileid: "58125569"
---
# <a name="goto-statement"></a><span data-ttu-id="8e1ca-102">GoTo (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="8e1ca-102">GoTo Statement</span></span>
<span data-ttu-id="8e1ca-103">Ramas incondicionalmente a una línea especificada en un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e1ca-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8e1ca-104">Syntax</span></span>  
  
```  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="8e1ca-105">Parte</span><span class="sxs-lookup"><span data-stu-id="8e1ca-105">Part</span></span>  
 `line`  
 <span data-ttu-id="8e1ca-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-106">Required.</span></span> <span data-ttu-id="8e1ca-107">Cualquier etiqueta de línea.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e1ca-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8e1ca-108">Remarks</span></span>  
 <span data-ttu-id="8e1ca-109">El `GoTo` instrucción solamente puede bifurcar a líneas en el procedimiento en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="8e1ca-110">La línea debe tener una línea en la etiqueta que `GoTo` puede hacer referencia a.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="8e1ca-111">Para obtener más información, vea [Cómo: Etiquetar instrucciones](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="8e1ca-111">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e1ca-112">`GoTo` las instrucciones pueden dificultar la lectura y el mantenimiento del código.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="8e1ca-113">Siempre que sea posible, use una estructura de control en su lugar.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="8e1ca-114">Para obtener más información, consulte [flujo de Control](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span><span class="sxs-lookup"><span data-stu-id="8e1ca-114">For more information, see [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="8e1ca-115">No puede usar un `GoTo` instrucción para bifurcar desde fuera de un `For`... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, `With`... `End With`, o `Using`... `End Using` construcción una etiqueta dentro.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="8e1ca-116">Bifurcación y construcciones Try</span><span class="sxs-lookup"><span data-stu-id="8e1ca-116">Branching and Try Constructions</span></span>  
 <span data-ttu-id="8e1ca-117">Dentro de un `Try`... `Catch`... `Finally` construcción, las reglas siguientes se aplican a la bifurcación con la `GoTo` instrucción.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="8e1ca-118">Bloque o región</span><span class="sxs-lookup"><span data-stu-id="8e1ca-118">Block or region</span></span>|<span data-ttu-id="8e1ca-119">Bifurcación en desde fuera de</span><span class="sxs-lookup"><span data-stu-id="8e1ca-119">Branching in from outside</span></span>|<span data-ttu-id="8e1ca-120">Bifurcación hacia fuera desde dentro de</span><span class="sxs-lookup"><span data-stu-id="8e1ca-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="8e1ca-121">`Try` Bloque</span><span class="sxs-lookup"><span data-stu-id="8e1ca-121">`Try` block</span></span>|<span data-ttu-id="8e1ca-122">Solo desde un `Catch` bloque de la misma construcción <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8e1ca-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="8e1ca-123">Solo fuera de la construcción toda</span><span class="sxs-lookup"><span data-stu-id="8e1ca-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="8e1ca-124">`Catch` Bloque</span><span class="sxs-lookup"><span data-stu-id="8e1ca-124">`Catch` block</span></span>|<span data-ttu-id="8e1ca-125">No permite nunca</span><span class="sxs-lookup"><span data-stu-id="8e1ca-125">Never allowed</span></span>|<span data-ttu-id="8e1ca-126">Solo fuera de la construcción toda, o la `Try` bloque de la misma construcción <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8e1ca-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="8e1ca-127">`Finally` Bloque</span><span class="sxs-lookup"><span data-stu-id="8e1ca-127">`Finally` block</span></span>|<span data-ttu-id="8e1ca-128">No permite nunca</span><span class="sxs-lookup"><span data-stu-id="8e1ca-128">Never allowed</span></span>|<span data-ttu-id="8e1ca-129">No permite nunca</span><span class="sxs-lookup"><span data-stu-id="8e1ca-129">Never allowed</span></span>|  
  
 <span data-ttu-id="8e1ca-130"><sup>1</sup> si uno `Try`... `Catch`... `Finally` está anidada dentro de otra, una `Catch` bloque puede bifurcar a la `Try` bloquear su propio nivel de anidamiento, pero no en cualquier otro `Try` bloque.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="8e1ca-131">Anidada `Try`... `Catch`... `Finally` debe estar contenida completamente en un `Try` o `Catch` bloque de la construcción en el que está anidada.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="8e1ca-132">La siguiente ilustración muestra una `Try` construcción anidada dentro de otra.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="8e1ca-133">Las distintas bifurcaciones entre los bloques de las dos construcciones se indican como válidos o no es válido.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 ![Diagrama gráfico de bifurcación en construcciones Try](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a><span data-ttu-id="8e1ca-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8e1ca-135">Example</span></span>  
 <span data-ttu-id="8e1ca-136">En el ejemplo siguiente se usa el `GoTo` instrucción para bifurcar a etiquetas de línea en un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-136">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="8e1ca-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e1ca-137">See also</span></span>
- [<span data-ttu-id="8e1ca-138">Do...Loop (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8e1ca-138">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="8e1ca-139">For...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8e1ca-139">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="8e1ca-140">For Each...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8e1ca-140">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="8e1ca-141">If...Then...Else (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8e1ca-141">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="8e1ca-142">Select...Case (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8e1ca-142">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="8e1ca-143">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8e1ca-143">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="8e1ca-144">While...End While (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8e1ca-144">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="8e1ca-145">With...End With (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8e1ca-145">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)

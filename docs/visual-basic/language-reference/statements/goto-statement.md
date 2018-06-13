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
ms.openlocfilehash: 27ebc677bab8b7f61a02408fddb30a6ec21c43cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604749"
---
# <a name="goto-statement"></a><span data-ttu-id="8b3cf-102">GoTo (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="8b3cf-102">GoTo Statement</span></span>
<span data-ttu-id="8b3cf-103">Realiza una bifurcación incondicional a una línea especificada en un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="8b3cf-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b3cf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8b3cf-104">Syntax</span></span>  
  
```  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="8b3cf-105">Parte</span><span class="sxs-lookup"><span data-stu-id="8b3cf-105">Part</span></span>  
 `line`  
 <span data-ttu-id="8b3cf-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="8b3cf-106">Required.</span></span> <span data-ttu-id="8b3cf-107">Cualquier etiqueta de línea.</span><span class="sxs-lookup"><span data-stu-id="8b3cf-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b3cf-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8b3cf-108">Remarks</span></span>  
 <span data-ttu-id="8b3cf-109">El `GoTo` instrucción puede crear una bifurcación únicamente a las líneas en el procedimiento en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="8b3cf-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="8b3cf-110">La línea debe tener una línea en la etiqueta que `GoTo` pueden hacer referencia a.</span><span class="sxs-lookup"><span data-stu-id="8b3cf-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="8b3cf-111">Para obtener más información, consulte [Cómo: instrucciones de la etiqueta](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="8b3cf-111">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b3cf-112">`GoTo` las instrucciones pueden dificultar la lectura y el mantenimiento del código.</span><span class="sxs-lookup"><span data-stu-id="8b3cf-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="8b3cf-113">Siempre que sea posible, utilice en su lugar una estructura de control.</span><span class="sxs-lookup"><span data-stu-id="8b3cf-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="8b3cf-114">Para obtener más información, consulte [flujo de Control](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span><span class="sxs-lookup"><span data-stu-id="8b3cf-114">For more information, see [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="8b3cf-115">No se puede utilizar un `GoTo` instrucción para bifurcar desde fuera de un `For`... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, `With`... `End With`, o `Using`... `End Using` construcción en una etiqueta dentro.</span><span class="sxs-lookup"><span data-stu-id="8b3cf-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="8b3cf-116">Bifurcación y construcciones Try</span><span class="sxs-lookup"><span data-stu-id="8b3cf-116">Branching and Try Constructions</span></span>  
 <span data-ttu-id="8b3cf-117">Dentro de un `Try`... `Catch`... `Finally` construcción, las reglas siguientes se aplican a la bifurcación con la `GoTo` instrucción.</span><span class="sxs-lookup"><span data-stu-id="8b3cf-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="8b3cf-118">Bloque o región</span><span class="sxs-lookup"><span data-stu-id="8b3cf-118">Block or region</span></span>|<span data-ttu-id="8b3cf-119">Bifurcación hacia dentro desde fuera</span><span class="sxs-lookup"><span data-stu-id="8b3cf-119">Branching in from outside</span></span>|<span data-ttu-id="8b3cf-120">Bifurcación hacia fuera desde dentro de</span><span class="sxs-lookup"><span data-stu-id="8b3cf-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="8b3cf-121">`Try` Bloque</span><span class="sxs-lookup"><span data-stu-id="8b3cf-121">`Try` block</span></span>|<span data-ttu-id="8b3cf-122">Sólo desde un `Catch` bloque de la misma construcción <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8b3cf-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="8b3cf-123">Solo fuera de la construcción completa</span><span class="sxs-lookup"><span data-stu-id="8b3cf-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="8b3cf-124">`Catch` Bloque</span><span class="sxs-lookup"><span data-stu-id="8b3cf-124">`Catch` block</span></span>|<span data-ttu-id="8b3cf-125">Nunca se permite</span><span class="sxs-lookup"><span data-stu-id="8b3cf-125">Never allowed</span></span>|<span data-ttu-id="8b3cf-126">Solo fuera de la construcción completa o a la `Try` bloque de la misma construcción <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8b3cf-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="8b3cf-127">`Finally` Bloque</span><span class="sxs-lookup"><span data-stu-id="8b3cf-127">`Finally` block</span></span>|<span data-ttu-id="8b3cf-128">Nunca se permite</span><span class="sxs-lookup"><span data-stu-id="8b3cf-128">Never allowed</span></span>|<span data-ttu-id="8b3cf-129">Nunca se permite</span><span class="sxs-lookup"><span data-stu-id="8b3cf-129">Never allowed</span></span>|  
  
 <span data-ttu-id="8b3cf-130"><sup>1</sup> si `Try`... `Catch`... `Finally` construcción está anidada dentro de otra, un `Catch` bloque puede crear una bifurcación en el `Try` bloque en su propio nivel de anidamiento, pero no en cualquier otro `Try` bloque.</span><span class="sxs-lookup"><span data-stu-id="8b3cf-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="8b3cf-131">Anidada `Try`... `Catch`... `Finally` construcción debe estar contenida completamente en un `Try` o `Catch` bloque de la construcción dentro del cual está anidado.</span><span class="sxs-lookup"><span data-stu-id="8b3cf-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="8b3cf-132">En la siguiente ilustración muestra una `Try` construcción anidada dentro de otra.</span><span class="sxs-lookup"><span data-stu-id="8b3cf-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="8b3cf-133">Las distintas bifurcaciones entre los bloques de las dos construcciones se indican como válidos o no es válido.</span><span class="sxs-lookup"><span data-stu-id="8b3cf-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 <span data-ttu-id="8b3cf-134">![Diagrama gráfico de bifurcación en construcciones Try](../../../visual-basic/language-reference/statements/media/trybranching.gif "TryBranching")</span><span class="sxs-lookup"><span data-stu-id="8b3cf-134">![Graphic diagram of branching in Try constructions](../../../visual-basic/language-reference/statements/media/trybranching.gif "TryBranching")</span></span>  
<span data-ttu-id="8b3cf-135">Bifurcaciones válidas como no válidas en construcciones Try</span><span class="sxs-lookup"><span data-stu-id="8b3cf-135">Valid and invalid branches in Try constructions</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b3cf-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8b3cf-136">Example</span></span>  
 <span data-ttu-id="8b3cf-137">En el ejemplo siguiente se usa el `GoTo` instrucción para bifurcar a etiquetas de línea en un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="8b3cf-137">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/goto-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8b3cf-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b3cf-138">See Also</span></span>  
 [<span data-ttu-id="8b3cf-139">Do...Loop (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8b3cf-139">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [<span data-ttu-id="8b3cf-140">For...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8b3cf-140">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="8b3cf-141">For Each...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8b3cf-141">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [<span data-ttu-id="8b3cf-142">If...Then...Else (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8b3cf-142">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="8b3cf-143">Select...Case (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8b3cf-143">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)  
 [<span data-ttu-id="8b3cf-144">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8b3cf-144">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="8b3cf-145">While...End While (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8b3cf-145">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [<span data-ttu-id="8b3cf-146">With...End With (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8b3cf-146">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)

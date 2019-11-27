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
ms.openlocfilehash: d5cdcd214c9679e245645505fe11cb5d521ce085
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351086"
---
# <a name="goto-statement"></a><span data-ttu-id="91e71-102">GoTo (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="91e71-102">GoTo Statement</span></span>
<span data-ttu-id="91e71-103">Bifurca incondicionalmente a una línea especificada en un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="91e71-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91e71-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91e71-104">Syntax</span></span>  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="91e71-105">Parte</span><span class="sxs-lookup"><span data-stu-id="91e71-105">Part</span></span>  
 `line`  
 <span data-ttu-id="91e71-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="91e71-106">Required.</span></span> <span data-ttu-id="91e71-107">Cualquier etiqueta de línea.</span><span class="sxs-lookup"><span data-stu-id="91e71-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91e71-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="91e71-108">Remarks</span></span>  
 <span data-ttu-id="91e71-109">La instrucción `GoTo` solo puede bifurcar a las líneas del procedimiento en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="91e71-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="91e71-110">La línea debe tener una etiqueta de línea a la que `GoTo` pueda hacer referencia.</span><span class="sxs-lookup"><span data-stu-id="91e71-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="91e71-111">Para obtener más información, vea [Cómo: etiquetar instrucciones](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="91e71-111">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="91e71-112">`GoTo` instrucciones pueden hacer que el código sea difícil de leer y mantener.</span><span class="sxs-lookup"><span data-stu-id="91e71-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="91e71-113">Siempre que sea posible, use una estructura de control en su lugar.</span><span class="sxs-lookup"><span data-stu-id="91e71-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="91e71-114">Para obtener más información, consulte [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span><span class="sxs-lookup"><span data-stu-id="91e71-114">For more information, see [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="91e71-115">No se puede usar una instrucción `GoTo` para bifurcar desde fuera de una `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`o `Using`...`End Using` construcción a una etiqueta dentro de.</span><span class="sxs-lookup"><span data-stu-id="91e71-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="91e71-116">Bifurcación y construcciones try</span><span class="sxs-lookup"><span data-stu-id="91e71-116">Branching and Try Constructions</span></span>  
 <span data-ttu-id="91e71-117">Dentro de una construcción `Try`...`Catch`...`Finally`, se aplican las siguientes reglas a la bifurcación con la instrucción `GoTo`.</span><span class="sxs-lookup"><span data-stu-id="91e71-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="91e71-118">Bloque o región</span><span class="sxs-lookup"><span data-stu-id="91e71-118">Block or region</span></span>|<span data-ttu-id="91e71-119">Bifurcación desde fuera</span><span class="sxs-lookup"><span data-stu-id="91e71-119">Branching in from outside</span></span>|<span data-ttu-id="91e71-120">Bifurcar desde dentro</span><span class="sxs-lookup"><span data-stu-id="91e71-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="91e71-121">`Try` bloque)</span><span class="sxs-lookup"><span data-stu-id="91e71-121">`Try` block</span></span>|<span data-ttu-id="91e71-122">Solo desde un bloque de `Catch` de la misma construcción <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="91e71-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="91e71-123">Solo hacia fuera de la construcción completa</span><span class="sxs-lookup"><span data-stu-id="91e71-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="91e71-124">`Catch` bloque)</span><span class="sxs-lookup"><span data-stu-id="91e71-124">`Catch` block</span></span>|<span data-ttu-id="91e71-125">Nunca permitido</span><span class="sxs-lookup"><span data-stu-id="91e71-125">Never allowed</span></span>|<span data-ttu-id="91e71-126">Solo hacia fuera de la construcción completa o hasta el `Try` bloque de la misma construcción <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="91e71-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="91e71-127">`Finally` bloque)</span><span class="sxs-lookup"><span data-stu-id="91e71-127">`Finally` block</span></span>|<span data-ttu-id="91e71-128">Nunca permitido</span><span class="sxs-lookup"><span data-stu-id="91e71-128">Never allowed</span></span>|<span data-ttu-id="91e71-129">Nunca permitido</span><span class="sxs-lookup"><span data-stu-id="91e71-129">Never allowed</span></span>|  
  
 <span data-ttu-id="91e71-130"><sup>1</sup> si una construcción `Try`...`Catch`...`Finally` está anidada dentro de otra, un bloque de `Catch` se puede bifurcar en el bloque de `Try` en su propio nivel de anidamiento, pero no en otro bloque de `Try`.</span><span class="sxs-lookup"><span data-stu-id="91e71-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="91e71-131">Una construcción `Try`anidada...`Catch`...`Finally` debe estar contenida completamente en un bloque `Try` o `Catch` de la construcción en la que está anidada.</span><span class="sxs-lookup"><span data-stu-id="91e71-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="91e71-132">En la ilustración siguiente se muestra una construcción `Try` anidada dentro de otra.</span><span class="sxs-lookup"><span data-stu-id="91e71-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="91e71-133">Varias ramas entre los bloques de las dos construcciones se indican como válidas o no válidas.</span><span class="sxs-lookup"><span data-stu-id="91e71-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 ![Diagrama gráfico de bifurcación en construcciones Try](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a><span data-ttu-id="91e71-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="91e71-135">Example</span></span>  
 <span data-ttu-id="91e71-136">En el ejemplo siguiente se usa la instrucción `GoTo` para bifurcar a las etiquetas de línea de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="91e71-136">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="91e71-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="91e71-137">See also</span></span>

- [<span data-ttu-id="91e71-138">Do...Loop (instrucción)</span><span class="sxs-lookup"><span data-stu-id="91e71-138">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="91e71-139">For...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="91e71-139">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="91e71-140">For Each...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="91e71-140">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="91e71-141">If...Then...Else (instrucción)</span><span class="sxs-lookup"><span data-stu-id="91e71-141">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="91e71-142">Select...Case (instrucción)</span><span class="sxs-lookup"><span data-stu-id="91e71-142">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="91e71-143">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="91e71-143">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="91e71-144">While...End While (instrucción)</span><span class="sxs-lookup"><span data-stu-id="91e71-144">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="91e71-145">With...End With (instrucción)</span><span class="sxs-lookup"><span data-stu-id="91e71-145">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)

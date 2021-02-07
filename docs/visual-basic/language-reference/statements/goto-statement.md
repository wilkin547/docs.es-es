---
description: 'Más información sobre: GoTo (instrucción)'
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
ms.openlocfilehash: 804baec130111562225b09cbdc7b5fb2d73adba5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769057"
---
# <a name="goto-statement"></a><span data-ttu-id="69479-103">GoTo (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="69479-103">GoTo Statement</span></span>

<span data-ttu-id="69479-104">Bifurca incondicionalmente a una línea especificada en un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="69479-104">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69479-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69479-105">Syntax</span></span>  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="69479-106">Parte</span><span class="sxs-lookup"><span data-stu-id="69479-106">Part</span></span>  

 `line`  
 <span data-ttu-id="69479-107">Necesario.</span><span class="sxs-lookup"><span data-stu-id="69479-107">Required.</span></span> <span data-ttu-id="69479-108">Cualquier etiqueta de línea.</span><span class="sxs-lookup"><span data-stu-id="69479-108">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69479-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="69479-109">Remarks</span></span>  

 <span data-ttu-id="69479-110">La `GoTo` instrucción solo puede bifurcar a las líneas del procedimiento en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="69479-110">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="69479-111">La línea debe tener una etiqueta de línea que `GoTo` pueda hacer referencia a.</span><span class="sxs-lookup"><span data-stu-id="69479-111">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="69479-112">Para obtener más información, vea [Cómo: etiquetar instrucciones](../../programming-guide/program-structure/how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="69479-112">For more information, see [How to: Label Statements](../../programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="69479-113">`GoTo` las instrucciones pueden hacer que el código sea difícil de leer y mantener.</span><span class="sxs-lookup"><span data-stu-id="69479-113">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="69479-114">Siempre que sea posible, use una estructura de control en su lugar.</span><span class="sxs-lookup"><span data-stu-id="69479-114">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="69479-115">Para más información, consulte [Control Flow](../../programming-guide/language-features/control-flow/index.md).</span><span class="sxs-lookup"><span data-stu-id="69479-115">For more information, see [Control Flow](../../programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="69479-116">No se puede usar una `GoTo` instrucción para bifurcar desde fuera de `For` ... `Next` ,.. `For Each` . `Next` , `SyncLock` . `End SyncLock` . `Try` `Catch` .,... ... `Finally` , `With` ... `End With` o `Using` ... `End Using` en una etiqueta dentro de.</span><span class="sxs-lookup"><span data-stu-id="69479-116">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="69479-117">Bifurcación y construcciones try</span><span class="sxs-lookup"><span data-stu-id="69479-117">Branching and Try Constructions</span></span>  

 <span data-ttu-id="69479-118">Dentro de `Try` ... `Catch` ...`Finally` la construcción de, se aplican las siguientes reglas a la bifurcación con la `GoTo` instrucción.</span><span class="sxs-lookup"><span data-stu-id="69479-118">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="69479-119">Bloque o región</span><span class="sxs-lookup"><span data-stu-id="69479-119">Block or region</span></span>|<span data-ttu-id="69479-120">Bifurcación desde fuera</span><span class="sxs-lookup"><span data-stu-id="69479-120">Branching in from outside</span></span>|<span data-ttu-id="69479-121">Bifurcar desde dentro</span><span class="sxs-lookup"><span data-stu-id="69479-121">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="69479-122">`Try` sin</span><span class="sxs-lookup"><span data-stu-id="69479-122">`Try` block</span></span>|<span data-ttu-id="69479-123">Solo desde un `Catch` bloque de la misma construcción <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="69479-123">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="69479-124">Solo hacia fuera de la construcción completa</span><span class="sxs-lookup"><span data-stu-id="69479-124">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="69479-125">`Catch` sin</span><span class="sxs-lookup"><span data-stu-id="69479-125">`Catch` block</span></span>|<span data-ttu-id="69479-126">Nunca permitido</span><span class="sxs-lookup"><span data-stu-id="69479-126">Never allowed</span></span>|<span data-ttu-id="69479-127">Solo hacia fuera de la construcción completa o hasta el `Try` bloque de la misma construcción <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="69479-127">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="69479-128">`Finally` sin</span><span class="sxs-lookup"><span data-stu-id="69479-128">`Finally` block</span></span>|<span data-ttu-id="69479-129">Nunca permitido</span><span class="sxs-lookup"><span data-stu-id="69479-129">Never allowed</span></span>|<span data-ttu-id="69479-130">Nunca permitido</span><span class="sxs-lookup"><span data-stu-id="69479-130">Never allowed</span></span>|  
  
 <span data-ttu-id="69479-131"><sup>1</sup> si uno `Try` ... `Catch` ...`Finally` la construcción está anidada dentro de otra, un `Catch` bloque se puede bifurcar en el `Try` bloque en su propio nivel de anidamiento, pero no en ningún otro `Try` bloque.</span><span class="sxs-lookup"><span data-stu-id="69479-131"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="69479-132">Una instrucción anidada `Try` ... `Catch` ...`Finally` la construcción debe estar contenida completamente en un `Try` `Catch` bloque o de la construcción en la que está anidada.</span><span class="sxs-lookup"><span data-stu-id="69479-132">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="69479-133">En la ilustración siguiente se muestra una `Try` construcción anidada dentro de otra.</span><span class="sxs-lookup"><span data-stu-id="69479-133">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="69479-134">Varias ramas entre los bloques de las dos construcciones se indican como válidas o no válidas.</span><span class="sxs-lookup"><span data-stu-id="69479-134">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 ![Diagrama gráfico de bifurcación en construcciones Try](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a><span data-ttu-id="69479-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="69479-136">Example</span></span>  

 <span data-ttu-id="69479-137">En el ejemplo siguiente se usa la `GoTo` instrucción para bifurcar a las etiquetas de línea de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="69479-137">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="69479-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="69479-138">See also</span></span>

- [<span data-ttu-id="69479-139">Instrucción Do...Loop</span><span class="sxs-lookup"><span data-stu-id="69479-139">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="69479-140">Instrucción For...Next</span><span class="sxs-lookup"><span data-stu-id="69479-140">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="69479-141">Instrucción For Each...Next</span><span class="sxs-lookup"><span data-stu-id="69479-141">For Each...Next Statement</span></span>](for-each-next-statement.md)
- [<span data-ttu-id="69479-142">Instrucción If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="69479-142">If...Then...Else Statement</span></span>](if-then-else-statement.md)
- [<span data-ttu-id="69479-143">Instrucción Select...Case</span><span class="sxs-lookup"><span data-stu-id="69479-143">Select...Case Statement</span></span>](select-case-statement.md)
- [<span data-ttu-id="69479-144">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="69479-144">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
- [<span data-ttu-id="69479-145">Instrucción While...End While</span><span class="sxs-lookup"><span data-stu-id="69479-145">While...End While Statement</span></span>](while-end-while-statement.md)
- [<span data-ttu-id="69479-146">Instrucción With...End With</span><span class="sxs-lookup"><span data-stu-id="69479-146">With...End With Statement</span></span>](with-end-with-statement.md)

---
description: 'Más información acerca de: para... Instrucción Next (Visual Basic)'
title: Instrucción For...Next
ms.date: 07/20/2015
f1_keywords:
- vb.Step
- vb.Next
- vb.To
- vb.for
helpviewer_keywords:
- infinite loops
- Next keyword [Visual Basic], For...Next statements
- For keyword [Visual Basic], For...Next statements
- Step keyword [Visual Basic], For...Next statements
- operator overloading, For...Next statement
- To keyword [Visual Basic], For...Next statements
- endless loops
- loops, endless
- instructions, repeating
- Next statement [Visual Basic], For...Next
- For...Next statements
- loop structures [Visual Basic], For...Next
- loops, infinite
- Exit statement [Visual Basic], For...Next statements
- For statement [Visual Basic]
ms.assetid: f5fc0d51-67ce-4c36-9f09-31c9a91c94e9
ms.openlocfilehash: f26d9cb1885d9d22b96d622f44325aad64e34d1d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769083"
---
# <a name="fornext-statement-visual-basic"></a><span data-ttu-id="7c069-103">Instrucción For...Next (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7c069-103">For...Next Statement (Visual Basic)</span></span>

<span data-ttu-id="7c069-104">Repite un grupo de instrucciones un número especificado de veces.</span><span class="sxs-lookup"><span data-stu-id="7c069-104">Repeats a group of statements a specified number of times.</span></span>

## <a name="syntax"></a><span data-ttu-id="7c069-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7c069-105">Syntax</span></span>

```vb
For counter [ As datatype ] = start To end [ Step step ]
    [ statements ]
    [ Continue For ]
    [ statements ]
    [ Exit For ]
    [ statements ]
Next [ counter ]
```

## <a name="parts"></a><span data-ttu-id="7c069-106">Partes</span><span class="sxs-lookup"><span data-stu-id="7c069-106">Parts</span></span>

|<span data-ttu-id="7c069-107">Parte</span><span class="sxs-lookup"><span data-stu-id="7c069-107">Part</span></span>|<span data-ttu-id="7c069-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="7c069-108">Description</span></span>|
|----------|-----------------|
|`counter`|<span data-ttu-id="7c069-109">Obligatorio en la `For` instrucción.</span><span class="sxs-lookup"><span data-stu-id="7c069-109">Required in the `For` statement.</span></span> <span data-ttu-id="7c069-110">Variable numérica.</span><span class="sxs-lookup"><span data-stu-id="7c069-110">Numeric variable.</span></span> <span data-ttu-id="7c069-111">Variable de control del bucle.</span><span class="sxs-lookup"><span data-stu-id="7c069-111">The control variable for the loop.</span></span> <span data-ttu-id="7c069-112">Para obtener más información, vea el [argumento Counter](#BKMK_Counter) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="7c069-112">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|
|`datatype`|<span data-ttu-id="7c069-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="7c069-113">Optional.</span></span> <span data-ttu-id="7c069-114">Tipo de datos de `counter` .</span><span class="sxs-lookup"><span data-stu-id="7c069-114">Data type of `counter`.</span></span> <span data-ttu-id="7c069-115">Para obtener más información, vea el [argumento Counter](#BKMK_Counter) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="7c069-115">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|
|`start`|<span data-ttu-id="7c069-116">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="7c069-116">Required.</span></span> <span data-ttu-id="7c069-117">Expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="7c069-117">Numeric expression.</span></span> <span data-ttu-id="7c069-118">Valor inicial de `counter`.</span><span class="sxs-lookup"><span data-stu-id="7c069-118">The initial value of `counter`.</span></span>|
|`end`|<span data-ttu-id="7c069-119">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="7c069-119">Required.</span></span> <span data-ttu-id="7c069-120">Expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="7c069-120">Numeric expression.</span></span> <span data-ttu-id="7c069-121">Valor final de `counter` .</span><span class="sxs-lookup"><span data-stu-id="7c069-121">The final value of `counter`.</span></span>|
|`step`|<span data-ttu-id="7c069-122">Opcional.</span><span class="sxs-lookup"><span data-stu-id="7c069-122">Optional.</span></span> <span data-ttu-id="7c069-123">Expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="7c069-123">Numeric expression.</span></span> <span data-ttu-id="7c069-124">Cantidad que `counter` se incrementa cada vez a través del bucle.</span><span class="sxs-lookup"><span data-stu-id="7c069-124">The amount by which `counter` is incremented each time through the loop.</span></span>|
|`statements`|<span data-ttu-id="7c069-125">Opcional.</span><span class="sxs-lookup"><span data-stu-id="7c069-125">Optional.</span></span> <span data-ttu-id="7c069-126">Una o más instrucciones entre `For` y `Next` que ejecutan el número especificado de veces.</span><span class="sxs-lookup"><span data-stu-id="7c069-126">One or more statements between `For` and `Next` that run the specified number of times.</span></span>|
|`Continue For`|<span data-ttu-id="7c069-127">Opcional.</span><span class="sxs-lookup"><span data-stu-id="7c069-127">Optional.</span></span> <span data-ttu-id="7c069-128">Transfiere el control a la siguiente iteración del bucle.</span><span class="sxs-lookup"><span data-stu-id="7c069-128">Transfers control to the next loop iteration.</span></span>|
|`Exit For`|<span data-ttu-id="7c069-129">Opcional.</span><span class="sxs-lookup"><span data-stu-id="7c069-129">Optional.</span></span> <span data-ttu-id="7c069-130">Transfiere el control fuera del `For` bucle.</span><span class="sxs-lookup"><span data-stu-id="7c069-130">Transfers control out of the `For` loop.</span></span>|
|`Next`|<span data-ttu-id="7c069-131">Necesario.</span><span class="sxs-lookup"><span data-stu-id="7c069-131">Required.</span></span> <span data-ttu-id="7c069-132">Finaliza la definición del `For` bucle.</span><span class="sxs-lookup"><span data-stu-id="7c069-132">Terminates the definition of the `For` loop.</span></span>|

> [!NOTE]
> <span data-ttu-id="7c069-133">La `To` palabra clave se usa en esta instrucción para especificar el intervalo del contador.</span><span class="sxs-lookup"><span data-stu-id="7c069-133">The `To` keyword is used in this statement to specify the range for the counter.</span></span> <span data-ttu-id="7c069-134">También puede usar esta palabra clave [en la Instrucción Case](select-case-statement.md) y en declaraciones de matriz.</span><span class="sxs-lookup"><span data-stu-id="7c069-134">You can also use this keyword in the [Select...Case Statement](select-case-statement.md) and in array declarations.</span></span> <span data-ttu-id="7c069-135">Para obtener más información sobre las declaraciones de matriz, vea [instrucción Dim](dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7c069-135">For more information about array declarations, see [Dim Statement](dim-statement.md).</span></span>

## <a name="simple-examples"></a><span data-ttu-id="7c069-136"> Ejemplos sencillos</span><span class="sxs-lookup"><span data-stu-id="7c069-136">Simple Examples</span></span>

<span data-ttu-id="7c069-137">Use una `For` estructura... `Next` cuando desee repetir un conjunto de instrucciones un número de veces.</span><span class="sxs-lookup"><span data-stu-id="7c069-137">You use a `For`...`Next` structure when you want to repeat a set of statements a set number of times.</span></span>

<span data-ttu-id="7c069-138">En el ejemplo siguiente, la `index` variable empieza con un valor de 1 y se incrementa con cada iteración del bucle, finalizando después del valor de hasta `index` 5.</span><span class="sxs-lookup"><span data-stu-id="7c069-138">In the following example, the `index` variable starts with a value of 1 and is incremented with each iteration of the loop, ending after the value of `index` reaches 5.</span></span>

[!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]

<span data-ttu-id="7c069-139">En el ejemplo siguiente, la `number` variable empieza en 2 y se reduce por 0,25 en cada iteración del bucle, finalizando después del valor de hasta `number` 0.</span><span class="sxs-lookup"><span data-stu-id="7c069-139">In the following example, the `number` variable starts at 2 and is reduced by 0.25 on each iteration of the loop, ending after the value of `number` reaches 0.</span></span> <span data-ttu-id="7c069-140">El `Step` argumento de `-.25` reduce el valor en 0,25 en cada iteración del bucle.</span><span class="sxs-lookup"><span data-stu-id="7c069-140">The `Step` argument of `-.25` reduces the value by 0.25 on each iteration of the loop.</span></span>

[!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]

> [!TIP]
> <span data-ttu-id="7c069-141">[While... End while instrucción](while-end-while-statement.md) o [do... La instrucción de bucle](do-loop-statement.md) funciona bien cuando no se sabe de antemano cuántas veces ejecutar las instrucciones en el bucle.</span><span class="sxs-lookup"><span data-stu-id="7c069-141">A [While...End While Statement](while-end-while-statement.md) or [Do...Loop Statement](do-loop-statement.md) works well when you don't know in advance how many times to run the statements in the loop.</span></span> <span data-ttu-id="7c069-142">Sin embargo, cuando espera ejecutar el bucle un número determinado de veces, un `For` bucle... `Next` es una opción mejor.</span><span class="sxs-lookup"><span data-stu-id="7c069-142">However, when you expect to run the loop a specific number of times, a `For`...`Next` loop is a better choice.</span></span> <span data-ttu-id="7c069-143">El número de iteraciones se determina cuando se escribe el bucle por primera vez.</span><span class="sxs-lookup"><span data-stu-id="7c069-143">You determine the number of iterations when you first enter the loop.</span></span>

## <a name="nesting-loops"></a><span data-ttu-id="7c069-144">Anidar bucles</span><span class="sxs-lookup"><span data-stu-id="7c069-144">Nesting Loops</span></span>

<span data-ttu-id="7c069-145">Puede anidar `For` bucles colocando un bucle dentro de otro.</span><span class="sxs-lookup"><span data-stu-id="7c069-145">You can nest `For` loops by putting one loop within another.</span></span> <span data-ttu-id="7c069-146">En el ejemplo siguiente se muestran las estructuras anidadas `For` ... `Next` que tienen valores de pasos diferentes.</span><span class="sxs-lookup"><span data-stu-id="7c069-146">The following example demonstrates nested `For`...`Next` structures that have different step values.</span></span> <span data-ttu-id="7c069-147">El bucle exterior crea una cadena para cada iteración del bucle.</span><span class="sxs-lookup"><span data-stu-id="7c069-147">The outer loop creates a string for every iteration of the loop.</span></span> <span data-ttu-id="7c069-148">El bucle interno reduce una variable de contador de bucle para cada iteración del bucle.</span><span class="sxs-lookup"><span data-stu-id="7c069-148">The inner loop decrements a loop counter variable for every iteration of the loop.</span></span>

[!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]

<span data-ttu-id="7c069-149">Al anidar bucles, cada bucle debe tener una `counter` variable única.</span><span class="sxs-lookup"><span data-stu-id="7c069-149">When nesting loops, each loop must have a unique `counter` variable.</span></span>

<span data-ttu-id="7c069-150">También puede anidar distintos tipos de estructuras de control.</span><span class="sxs-lookup"><span data-stu-id="7c069-150">You can also nest different kinds control structures within each other.</span></span> <span data-ttu-id="7c069-151">Para obtener más información, vea [estructuras de control anidadas](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="7c069-151">For more information, see [Nested Control Structures](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>

## <a name="exit-for-and-continue-for"></a><span data-ttu-id="7c069-152">Salir de y continuar para</span><span class="sxs-lookup"><span data-stu-id="7c069-152">Exit For and Continue For</span></span>

<span data-ttu-id="7c069-153">La `Exit For` instrucción sale inmediatamente de `For` ...`Next`</span><span class="sxs-lookup"><span data-stu-id="7c069-153">The `Exit For` statement immediately exits the `For`…`Next`</span></span> <span data-ttu-id="7c069-154">bucle y transfiere el control a la instrucción que sigue a la `Next` instrucción.</span><span class="sxs-lookup"><span data-stu-id="7c069-154">loop and transfers control to the statement that follows the `Next` statement.</span></span>

<span data-ttu-id="7c069-155">La `Continue For` instrucción transfiere el control inmediatamente a la siguiente iteración del bucle.</span><span class="sxs-lookup"><span data-stu-id="7c069-155">The `Continue For` statement transfers control immediately to the next iteration of the loop.</span></span> <span data-ttu-id="7c069-156">Para obtener más información, vea [instrucción continue](continue-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7c069-156">For more information, see [Continue Statement](continue-statement.md).</span></span>

<span data-ttu-id="7c069-157">En el ejemplo siguiente se muestra el uso de `Continue For` las `Exit For` instrucciones y.</span><span class="sxs-lookup"><span data-stu-id="7c069-157">The following example illustrates the use of the `Continue For` and `Exit For` statements.</span></span>

[!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]

<span data-ttu-id="7c069-158">Puede incluir cualquier número de `Exit For` instrucciones en `For` ...`Next`</span><span class="sxs-lookup"><span data-stu-id="7c069-158">You can put any number of `Exit For` statements in a `For`…`Next`</span></span> <span data-ttu-id="7c069-159">bucle</span><span class="sxs-lookup"><span data-stu-id="7c069-159">loop.</span></span> <span data-ttu-id="7c069-160">Cuando se usa dentro de la instrucción anidada `For` ...`Next`</span><span class="sxs-lookup"><span data-stu-id="7c069-160">When used within nested `For`…`Next`</span></span> <span data-ttu-id="7c069-161">bucles, `Exit For` sale del bucle más interno y transfiere el control al siguiente nivel superior de anidamiento.</span><span class="sxs-lookup"><span data-stu-id="7c069-161">loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

<span data-ttu-id="7c069-162">`Exit For` se suele usar después de evaluar alguna condición (por ejemplo, en `If` ... `Then` ...`Else` estructura).</span><span class="sxs-lookup"><span data-stu-id="7c069-162">`Exit For` is often used after you evaluate some condition (for example, in an `If`...`Then`...`Else` structure).</span></span> <span data-ttu-id="7c069-163">Puede que desee usar `Exit For` para las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="7c069-163">You might want to use `Exit For` for the following conditions:</span></span>

- <span data-ttu-id="7c069-164">Continuar la iteración no es necesario o imposible.</span><span class="sxs-lookup"><span data-stu-id="7c069-164">Continuing to iterate is unnecessary or impossible.</span></span> <span data-ttu-id="7c069-165">Un valor erróneo o una solicitud de finalización podría crear esta condición.</span><span class="sxs-lookup"><span data-stu-id="7c069-165">An erroneous value or a termination request might create this condition.</span></span>

- <span data-ttu-id="7c069-166">.. `Try` . `Catch` ...`Finally` la instrucción detecta una excepción.</span><span class="sxs-lookup"><span data-stu-id="7c069-166">A `Try`...`Catch`...`Finally` statement catches an exception.</span></span> <span data-ttu-id="7c069-167">Puede usar `Exit For` al final del `Finally` bloque.</span><span class="sxs-lookup"><span data-stu-id="7c069-167">You might use `Exit For` at the end of the `Finally` block.</span></span>

- <span data-ttu-id="7c069-168">Tiene un bucle sin fin, que es un bucle que podría ejecutar un número de veces grande o incluso infinito.</span><span class="sxs-lookup"><span data-stu-id="7c069-168">You have an endless loop, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="7c069-169">Si detecta este tipo de condición, puede usar `Exit For` para escapar el bucle.</span><span class="sxs-lookup"><span data-stu-id="7c069-169">If you detect such a condition, you can use `Exit For` to escape the loop.</span></span> <span data-ttu-id="7c069-170">Para obtener más información, vea.. [. Instrucción Loop](do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7c069-170">For more information, see [Do...Loop Statement](do-loop-statement.md).</span></span>

## <a name="technical-implementation"></a><span data-ttu-id="7c069-171">Implementación técnica</span><span class="sxs-lookup"><span data-stu-id="7c069-171">Technical Implementation</span></span>

<span data-ttu-id="7c069-172">Cuando `For` se inicia un bucle... `Next` , Visual Basic evalúa `start` , `end` y `step` .</span><span class="sxs-lookup"><span data-stu-id="7c069-172">When a `For`...`Next` loop starts, Visual Basic evaluates `start`, `end`, and `step`.</span></span> <span data-ttu-id="7c069-173">Visual Basic evalúa estos valores solo en este momento y, a continuación, `start` se asigna a `counter` .</span><span class="sxs-lookup"><span data-stu-id="7c069-173">Visual Basic evaluates these values only at this time and then assigns `start` to `counter`.</span></span> <span data-ttu-id="7c069-174">Antes de que se ejecute el bloque de instrucciones, Visual Basic compara `counter` con `end` .</span><span class="sxs-lookup"><span data-stu-id="7c069-174">Before the statement block runs, Visual Basic compares `counter` to `end`.</span></span> <span data-ttu-id="7c069-175">Si `counter` ya es mayor que el `end` valor (o menor si `step` es negativo), el `For` bucle finaliza y el control pasa a la instrucción que sigue a la `Next` instrucción.</span><span class="sxs-lookup"><span data-stu-id="7c069-175">If `counter` is already larger than the `end` value (or smaller if `step` is negative), the `For` loop ends and control passes to the statement that follows the `Next` statement.</span></span> <span data-ttu-id="7c069-176">De lo contrario, se ejecuta el bloque de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="7c069-176">Otherwise, the statement block runs.</span></span>

<span data-ttu-id="7c069-177">Cada vez que Visual Basic encuentra la `Next` instrucción, se incrementa en `counter` `step` y vuelve a la `For` instrucción.</span><span class="sxs-lookup"><span data-stu-id="7c069-177">Each time Visual Basic encounters the `Next` statement, it increments `counter` by `step` and returns to the `For` statement.</span></span> <span data-ttu-id="7c069-178">Una vez más, se compara `counter` con `end` y, de nuevo, ejecuta el bloque o sale del bucle, en función del resultado.</span><span class="sxs-lookup"><span data-stu-id="7c069-178">Again it compares `counter` to `end`, and again it either runs the block or exits the loop, depending on the result.</span></span> <span data-ttu-id="7c069-179">Este proceso continúa hasta `counter` que `end` se encuentran las pasadas o una `Exit For` instrucción.</span><span class="sxs-lookup"><span data-stu-id="7c069-179">This process continues until `counter` passes `end` or an `Exit For` statement is encountered.</span></span>

<span data-ttu-id="7c069-180">El bucle no se detiene hasta que `counter` se ha pasado `end` .</span><span class="sxs-lookup"><span data-stu-id="7c069-180">The loop doesn't stop until `counter` has passed `end`.</span></span> <span data-ttu-id="7c069-181">Si `counter` es igual a `end` , el bucle continúa.</span><span class="sxs-lookup"><span data-stu-id="7c069-181">If `counter` is equal to `end`, the loop continues.</span></span> <span data-ttu-id="7c069-182">La comparación que determina si se debe ejecutar el bloque es `counter`  <=  `end` si `step` es positivo y `counter`  >=  `end` si `step` es negativo.</span><span class="sxs-lookup"><span data-stu-id="7c069-182">The comparison that determines whether to run the block is `counter` <= `end` if `step` is positive and `counter` >= `end` if `step` is negative.</span></span>

<span data-ttu-id="7c069-183">Si cambia el valor de `counter` mientras se encuentra dentro de un bucle, el código podría ser más difícil de leer y depurar.</span><span class="sxs-lookup"><span data-stu-id="7c069-183">If you change the value of `counter` while inside a loop, your code might be more difficult to read and debug.</span></span> <span data-ttu-id="7c069-184">Cambiar el valor de `start` , `end` o `step` no afecta a los valores de iteración que se determinaron cuando se escribió el bucle por primera vez.</span><span class="sxs-lookup"><span data-stu-id="7c069-184">Changing the value of `start`, `end`, or `step` doesn't affect the iteration values that were determined when the loop was first entered.</span></span>

<span data-ttu-id="7c069-185">Si anida bucles, el compilador indicará un error si encuentra la `Next` instrucción de un nivel de anidamiento externo antes de la `Next` instrucción de un nivel interno.</span><span class="sxs-lookup"><span data-stu-id="7c069-185">If you nest loops, the compiler signals an error if it encounters the `Next` statement of an outer nesting level before the `Next` statement of an inner level.</span></span> <span data-ttu-id="7c069-186">Sin embargo, el compilador puede detectar este error superpuesto solo si especifica `counter` en cada `Next` instrucción.</span><span class="sxs-lookup"><span data-stu-id="7c069-186">However, the compiler can detect this overlapping error only if you specify `counter` in every `Next` statement.</span></span>

### <a name="step-argument"></a><span data-ttu-id="7c069-187">Argumento Step</span><span class="sxs-lookup"><span data-stu-id="7c069-187">Step Argument</span></span>

<span data-ttu-id="7c069-188">El valor de `step` puede ser positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="7c069-188">The value of `step` can be either positive or negative.</span></span> <span data-ttu-id="7c069-189">Este parámetro determina el procesamiento de bucles según la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="7c069-189">This parameter determines loop processing according to the following table:</span></span>

|<span data-ttu-id="7c069-190">**Valor del paso**</span><span class="sxs-lookup"><span data-stu-id="7c069-190">**Step value**</span></span>|<span data-ttu-id="7c069-191">**El bucle se ejecuta si**</span><span class="sxs-lookup"><span data-stu-id="7c069-191">**Loop executes if**</span></span>|
|--------------------|--------------------------|
|<span data-ttu-id="7c069-192">Positivo o cero</span><span class="sxs-lookup"><span data-stu-id="7c069-192">Positive or zero</span></span>|`counter` <= `end`|
|<span data-ttu-id="7c069-193">Negativo</span><span class="sxs-lookup"><span data-stu-id="7c069-193">Negative</span></span>|`counter` >= `end`|

<span data-ttu-id="7c069-194">El valor predeterminado de `step` es 1.</span><span class="sxs-lookup"><span data-stu-id="7c069-194">The default value of `step` is 1.</span></span>

### <a name="counter-argument"></a><a name="BKMK_Counter"></a> <span data-ttu-id="7c069-195">Argumento Counter</span><span class="sxs-lookup"><span data-stu-id="7c069-195">Counter Argument</span></span>

<span data-ttu-id="7c069-196">En la tabla siguiente se indica si `counter` define una nueva variable local cuyo ámbito es el `For…Next` bucle completo.</span><span class="sxs-lookup"><span data-stu-id="7c069-196">The following table indicates whether `counter` defines a new local variable that’s scoped to the entire `For…Next` loop.</span></span> <span data-ttu-id="7c069-197">Esta determinación depende de si `datatype` está presente y si `counter` ya está definido.</span><span class="sxs-lookup"><span data-stu-id="7c069-197">This determination depends on whether `datatype` is present and whether `counter` is already defined.</span></span>

|<span data-ttu-id="7c069-198">`datatype`¿Está presente?</span><span class="sxs-lookup"><span data-stu-id="7c069-198">Is `datatype` present?</span></span>|<span data-ttu-id="7c069-199">`counter`¿Ya está definido?</span><span class="sxs-lookup"><span data-stu-id="7c069-199">Is `counter` already defined?</span></span>|<span data-ttu-id="7c069-200">Resultado (si `counter` define una nueva variable local cuyo ámbito es el `For...Next` bucle completo)</span><span class="sxs-lookup"><span data-stu-id="7c069-200">Result (whether `counter` defines a new local variable that’s scoped to the entire `For...Next` loop)</span></span>|
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="7c069-201">No</span><span class="sxs-lookup"><span data-stu-id="7c069-201">No</span></span>|<span data-ttu-id="7c069-202">Sí</span><span class="sxs-lookup"><span data-stu-id="7c069-202">Yes</span></span>|<span data-ttu-id="7c069-203">No, porque `counter` ya está definido.</span><span class="sxs-lookup"><span data-stu-id="7c069-203">No, because `counter` is already defined.</span></span> <span data-ttu-id="7c069-204">Si el ámbito de `counter` no es local para el procedimiento, se produce una advertencia en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="7c069-204">If the scope of `counter` isn't local to the procedure, a compile-time warning occurs.</span></span>|
|<span data-ttu-id="7c069-205">No</span><span class="sxs-lookup"><span data-stu-id="7c069-205">No</span></span>|<span data-ttu-id="7c069-206">No</span><span class="sxs-lookup"><span data-stu-id="7c069-206">No</span></span>|<span data-ttu-id="7c069-207">Sí.</span><span class="sxs-lookup"><span data-stu-id="7c069-207">Yes.</span></span> <span data-ttu-id="7c069-208">El tipo de datos se deduce de `start` las `end` expresiones, y `step` .</span><span class="sxs-lookup"><span data-stu-id="7c069-208">The data type is inferred from the `start`, `end`, and `step` expressions.</span></span> <span data-ttu-id="7c069-209">Para obtener información sobre la inferencia de tipos, vea [Option Infer Statement](option-infer-statement.md) e [inferencia de tipo local](../../programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="7c069-209">For information about type inference, see [Option Infer Statement](option-infer-statement.md) and [Local Type Inference](../../programming-guide/language-features/variables/local-type-inference.md).</span></span>|
|<span data-ttu-id="7c069-210">Sí</span><span class="sxs-lookup"><span data-stu-id="7c069-210">Yes</span></span>|<span data-ttu-id="7c069-211">Sí</span><span class="sxs-lookup"><span data-stu-id="7c069-211">Yes</span></span>|<span data-ttu-id="7c069-212">Sí, pero solo si la `counter` variable existente se define fuera del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="7c069-212">Yes, but only if the existing `counter` variable is defined outside the procedure.</span></span> <span data-ttu-id="7c069-213">Esa variable sigue siendo independiente.</span><span class="sxs-lookup"><span data-stu-id="7c069-213">That variable remains separate.</span></span> <span data-ttu-id="7c069-214">Si el ámbito de la `counter` variable existente es local para el procedimiento, se produce un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="7c069-214">If the scope of the existing `counter` variable is local to the procedure, a compile-time error occurs.</span></span>|
|<span data-ttu-id="7c069-215">Sí</span><span class="sxs-lookup"><span data-stu-id="7c069-215">Yes</span></span>|<span data-ttu-id="7c069-216">No</span><span class="sxs-lookup"><span data-stu-id="7c069-216">No</span></span>|<span data-ttu-id="7c069-217">Sí.</span><span class="sxs-lookup"><span data-stu-id="7c069-217">Yes.</span></span>|

<span data-ttu-id="7c069-218">El tipo de datos de `counter` determina el tipo de iteración, que debe ser uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="7c069-218">The data type of `counter` determines the type of the iteration, which must be one of the following types:</span></span>

- <span data-ttu-id="7c069-219">`Byte`, `SByte` , `UShort` , `Short` , `UInteger` , `Integer` , `ULong` , `Long` , `Decimal` , `Single` O `Double` .</span><span class="sxs-lookup"><span data-stu-id="7c069-219">A `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, or `Double`.</span></span>

- <span data-ttu-id="7c069-220">Una enumeración que se declara mediante una [instrucción enum](enum-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7c069-220">An enumeration that you declare by using an [Enum Statement](enum-statement.md).</span></span>

- <span data-ttu-id="7c069-221">Una clase `Object`.</span><span class="sxs-lookup"><span data-stu-id="7c069-221">An `Object`.</span></span>

- <span data-ttu-id="7c069-222">Tipo `T` que tiene los operadores siguientes, donde `B` es un tipo que se puede utilizar en una `Boolean` expresión.</span><span class="sxs-lookup"><span data-stu-id="7c069-222">A type `T` that has the following operators, where `B` is a type that can be used in a `Boolean` expression.</span></span>

  `Public Shared Operator >= (op1 As T, op2 As T) As B`

  `Public Shared Operator <= (op1 As T, op2 As T) As B`

  `Public Shared Operator - (op1 As T, op2 As T) As T`

  `Public Shared Operator + (op1 As T, op2 As T) As T`

<span data-ttu-id="7c069-223">Opcionalmente, puede especificar la `counter` variable en la `Next` instrucción.</span><span class="sxs-lookup"><span data-stu-id="7c069-223">You can optionally specify the `counter` variable in the `Next` statement.</span></span> <span data-ttu-id="7c069-224">Esta sintaxis mejora la legibilidad del programa, sobre todo si tiene `For` bucles anidados.</span><span class="sxs-lookup"><span data-stu-id="7c069-224">This syntax improves the readability of your program, especially if you have nested `For` loops.</span></span> <span data-ttu-id="7c069-225">Debe especificar la variable que aparece en la instrucción correspondiente `For` .</span><span class="sxs-lookup"><span data-stu-id="7c069-225">You must specify the variable that appears in the corresponding `For` statement.</span></span>

<span data-ttu-id="7c069-226">Las `start` `end` expresiones, y `step` se pueden evaluar como cualquier tipo de datos que se amplíe al tipo de `counter` .</span><span class="sxs-lookup"><span data-stu-id="7c069-226">The `start`, `end`, and `step` expressions can evaluate to any data type that widens to the type of `counter`.</span></span> <span data-ttu-id="7c069-227">Si usa un tipo definido por el usuario para `counter` , es posible que tenga que definir el `CType` operador de conversión para convertir los tipos de `start` , `end` o `step` al tipo de `counter` .</span><span class="sxs-lookup"><span data-stu-id="7c069-227">If you use a user-defined type for `counter`, you might have to define the `CType` conversion operator to convert the types of `start`, `end`, or `step` to the type of `counter`.</span></span>

## <a name="example"></a><span data-ttu-id="7c069-228">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7c069-228">Example</span></span>

<span data-ttu-id="7c069-229">En el ejemplo siguiente se quitan todos los elementos de una lista genérica.</span><span class="sxs-lookup"><span data-stu-id="7c069-229">The following example removes all elements from a generic list.</span></span> <span data-ttu-id="7c069-230">En lugar de [para cada... Instrucción siguiente](for-each-next-statement.md), en el ejemplo se muestra una `For` instrucción... `Next` que recorre en iteración en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="7c069-230">Instead of a [For Each...Next Statement](for-each-next-statement.md), the example shows a `For`...`Next` statement that iterates in descending order.</span></span> <span data-ttu-id="7c069-231">En el ejemplo se utiliza esta técnica porque el `removeAt` método hace que los elementos situados después del elemento quitado tengan un valor de índice inferior.</span><span class="sxs-lookup"><span data-stu-id="7c069-231">The example uses this technique because the `removeAt` method causes elements after the removed element to have a lower index value.</span></span>

[!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]

## <a name="example"></a><span data-ttu-id="7c069-232">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7c069-232">Example</span></span>

<span data-ttu-id="7c069-233">En el ejemplo siguiente se recorre en iteración una enumeración declarada mediante una [instrucción enum](enum-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7c069-233">The following example iterates through an enumeration that's declared by using an [Enum Statement](enum-statement.md).</span></span>

[!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]

## <a name="example"></a><span data-ttu-id="7c069-234">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7c069-234">Example</span></span>

<span data-ttu-id="7c069-235">En el ejemplo siguiente, los parámetros de instrucción usan una clase que tiene sobrecargas de operador para los `+` `-` operadores,, `>=` y `<=` .</span><span class="sxs-lookup"><span data-stu-id="7c069-235">In the following example, the statement parameters use a class that has operator overloads for the `+`, `-`, `>=`, and `<=` operators.</span></span>

[!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]

## <a name="see-also"></a><span data-ttu-id="7c069-236">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c069-236">See also</span></span>

- <xref:System.Collections.Generic.List%601>
- [<span data-ttu-id="7c069-237">Estructuras de bucle</span><span class="sxs-lookup"><span data-stu-id="7c069-237">Loop Structures</span></span>](../../programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="7c069-238">Instrucción While...End While</span><span class="sxs-lookup"><span data-stu-id="7c069-238">While...End While Statement</span></span>](while-end-while-statement.md)
- [<span data-ttu-id="7c069-239">Instrucción Do...Loop</span><span class="sxs-lookup"><span data-stu-id="7c069-239">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="7c069-240">Estructuras de control anidadas</span><span class="sxs-lookup"><span data-stu-id="7c069-240">Nested Control Structures</span></span>](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="7c069-241">Instrucción Exit</span><span class="sxs-lookup"><span data-stu-id="7c069-241">Exit Statement</span></span>](exit-statement.md)
- [<span data-ttu-id="7c069-242">Colecciones</span><span class="sxs-lookup"><span data-stu-id="7c069-242">Collections</span></span>](../../programming-guide/concepts/collections.md)

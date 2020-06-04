---
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
ms.openlocfilehash: 6896c6cfb4ec5d6207011e56b72639c459120e53
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404646"
---
# <a name="fornext-statement-visual-basic"></a><span data-ttu-id="be916-102">Instrucción For...Next (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be916-102">For...Next Statement (Visual Basic)</span></span>

<span data-ttu-id="be916-103">Repite un grupo de instrucciones un número especificado de veces.</span><span class="sxs-lookup"><span data-stu-id="be916-103">Repeats a group of statements a specified number of times.</span></span>

## <a name="syntax"></a><span data-ttu-id="be916-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="be916-104">Syntax</span></span>

```vb
For counter [ As datatype ] = start To end [ Step step ]
    [ statements ]
    [ Continue For ]
    [ statements ]
    [ Exit For ]
    [ statements ]
Next [ counter ]
```

## <a name="parts"></a><span data-ttu-id="be916-105">Partes</span><span class="sxs-lookup"><span data-stu-id="be916-105">Parts</span></span>

|<span data-ttu-id="be916-106">Parte</span><span class="sxs-lookup"><span data-stu-id="be916-106">Part</span></span>|<span data-ttu-id="be916-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="be916-107">Description</span></span>|
|----------|-----------------|
|`counter`|<span data-ttu-id="be916-108">Obligatorio en la `For` instrucción.</span><span class="sxs-lookup"><span data-stu-id="be916-108">Required in the `For` statement.</span></span> <span data-ttu-id="be916-109">Variable numérica.</span><span class="sxs-lookup"><span data-stu-id="be916-109">Numeric variable.</span></span> <span data-ttu-id="be916-110">Variable de control del bucle.</span><span class="sxs-lookup"><span data-stu-id="be916-110">The control variable for the loop.</span></span> <span data-ttu-id="be916-111">Para obtener más información, vea el [argumento Counter](#BKMK_Counter) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="be916-111">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|
|`datatype`|<span data-ttu-id="be916-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="be916-112">Optional.</span></span> <span data-ttu-id="be916-113">Tipo de datos de `counter` .</span><span class="sxs-lookup"><span data-stu-id="be916-113">Data type of `counter`.</span></span> <span data-ttu-id="be916-114">Para obtener más información, vea el [argumento Counter](#BKMK_Counter) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="be916-114">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|
|`start`|<span data-ttu-id="be916-115">Necesario.</span><span class="sxs-lookup"><span data-stu-id="be916-115">Required.</span></span> <span data-ttu-id="be916-116">Expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="be916-116">Numeric expression.</span></span> <span data-ttu-id="be916-117">Valor inicial de `counter`.</span><span class="sxs-lookup"><span data-stu-id="be916-117">The initial value of `counter`.</span></span>|
|`end`|<span data-ttu-id="be916-118">Necesario.</span><span class="sxs-lookup"><span data-stu-id="be916-118">Required.</span></span> <span data-ttu-id="be916-119">Expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="be916-119">Numeric expression.</span></span> <span data-ttu-id="be916-120">Valor final de `counter` .</span><span class="sxs-lookup"><span data-stu-id="be916-120">The final value of `counter`.</span></span>|
|`step`|<span data-ttu-id="be916-121">Opcional.</span><span class="sxs-lookup"><span data-stu-id="be916-121">Optional.</span></span> <span data-ttu-id="be916-122">Expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="be916-122">Numeric expression.</span></span> <span data-ttu-id="be916-123">Cantidad que `counter` se incrementa cada vez a través del bucle.</span><span class="sxs-lookup"><span data-stu-id="be916-123">The amount by which `counter` is incremented each time through the loop.</span></span>|
|`statements`|<span data-ttu-id="be916-124">Opcional.</span><span class="sxs-lookup"><span data-stu-id="be916-124">Optional.</span></span> <span data-ttu-id="be916-125">Una o más instrucciones entre `For` y `Next` que ejecutan el número especificado de veces.</span><span class="sxs-lookup"><span data-stu-id="be916-125">One or more statements between `For` and `Next` that run the specified number of times.</span></span>|
|`Continue For`|<span data-ttu-id="be916-126">Opcional.</span><span class="sxs-lookup"><span data-stu-id="be916-126">Optional.</span></span> <span data-ttu-id="be916-127">Transfiere el control a la siguiente iteración del bucle.</span><span class="sxs-lookup"><span data-stu-id="be916-127">Transfers control to the next loop iteration.</span></span>|
|`Exit For`|<span data-ttu-id="be916-128">Opcional.</span><span class="sxs-lookup"><span data-stu-id="be916-128">Optional.</span></span> <span data-ttu-id="be916-129">Transfiere el control fuera del `For` bucle.</span><span class="sxs-lookup"><span data-stu-id="be916-129">Transfers control out of the `For` loop.</span></span>|
|`Next`|<span data-ttu-id="be916-130">Necesario.</span><span class="sxs-lookup"><span data-stu-id="be916-130">Required.</span></span> <span data-ttu-id="be916-131">Finaliza la definición del `For` bucle.</span><span class="sxs-lookup"><span data-stu-id="be916-131">Terminates the definition of the `For` loop.</span></span>|

> [!NOTE]
> <span data-ttu-id="be916-132">La `To` palabra clave se usa en esta instrucción para especificar el intervalo del contador.</span><span class="sxs-lookup"><span data-stu-id="be916-132">The `To` keyword is used in this statement to specify the range for the counter.</span></span> <span data-ttu-id="be916-133">También puede usar esta palabra clave [en la Instrucción Case](select-case-statement.md) y en declaraciones de matriz.</span><span class="sxs-lookup"><span data-stu-id="be916-133">You can also use this keyword in the [Select...Case Statement](select-case-statement.md) and in array declarations.</span></span> <span data-ttu-id="be916-134">Para obtener más información sobre las declaraciones de matriz, vea [instrucción Dim](dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="be916-134">For more information about array declarations, see [Dim Statement](dim-statement.md).</span></span>

## <a name="simple-examples"></a><span data-ttu-id="be916-135"> Ejemplos sencillos</span><span class="sxs-lookup"><span data-stu-id="be916-135">Simple Examples</span></span>

<span data-ttu-id="be916-136">Use una `For` estructura... `Next` cuando desee repetir un conjunto de instrucciones un número de veces.</span><span class="sxs-lookup"><span data-stu-id="be916-136">You use a `For`...`Next` structure when you want to repeat a set of statements a set number of times.</span></span>

<span data-ttu-id="be916-137">En el ejemplo siguiente, la `index` variable empieza con un valor de 1 y se incrementa con cada iteración del bucle, finalizando después del valor de hasta `index` 5.</span><span class="sxs-lookup"><span data-stu-id="be916-137">In the following example, the `index` variable starts with a value of 1 and is incremented with each iteration of the loop, ending after the value of `index` reaches 5.</span></span>

[!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]

<span data-ttu-id="be916-138">En el ejemplo siguiente, la `number` variable empieza en 2 y se reduce por 0,25 en cada iteración del bucle, finalizando después del valor de hasta `number` 0.</span><span class="sxs-lookup"><span data-stu-id="be916-138">In the following example, the `number` variable starts at 2 and is reduced by 0.25 on each iteration of the loop, ending after the value of `number` reaches 0.</span></span> <span data-ttu-id="be916-139">El `Step` argumento de `-.25` reduce el valor en 0,25 en cada iteración del bucle.</span><span class="sxs-lookup"><span data-stu-id="be916-139">The `Step` argument of `-.25` reduces the value by 0.25 on each iteration of the loop.</span></span>

[!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]

> [!TIP]
> <span data-ttu-id="be916-140">[While... End while instrucción](while-end-while-statement.md) o [do... La instrucción de bucle](do-loop-statement.md) funciona bien cuando no se sabe de antemano cuántas veces ejecutar las instrucciones en el bucle.</span><span class="sxs-lookup"><span data-stu-id="be916-140">A [While...End While Statement](while-end-while-statement.md) or [Do...Loop Statement](do-loop-statement.md) works well when you don't know in advance how many times to run the statements in the loop.</span></span> <span data-ttu-id="be916-141">Sin embargo, cuando espera ejecutar el bucle un número determinado de veces, un `For` bucle... `Next` es una opción mejor.</span><span class="sxs-lookup"><span data-stu-id="be916-141">However, when you expect to run the loop a specific number of times, a `For`...`Next` loop is a better choice.</span></span> <span data-ttu-id="be916-142">El número de iteraciones se determina cuando se escribe el bucle por primera vez.</span><span class="sxs-lookup"><span data-stu-id="be916-142">You determine the number of iterations when you first enter the loop.</span></span>

## <a name="nesting-loops"></a><span data-ttu-id="be916-143">Anidar bucles</span><span class="sxs-lookup"><span data-stu-id="be916-143">Nesting Loops</span></span>

<span data-ttu-id="be916-144">Puede anidar `For` bucles colocando un bucle dentro de otro.</span><span class="sxs-lookup"><span data-stu-id="be916-144">You can nest `For` loops by putting one loop within another.</span></span> <span data-ttu-id="be916-145">En el ejemplo siguiente se muestran las estructuras anidadas `For` ... `Next` que tienen valores de pasos diferentes.</span><span class="sxs-lookup"><span data-stu-id="be916-145">The following example demonstrates nested `For`...`Next` structures that have different step values.</span></span> <span data-ttu-id="be916-146">El bucle exterior crea una cadena para cada iteración del bucle.</span><span class="sxs-lookup"><span data-stu-id="be916-146">The outer loop creates a string for every iteration of the loop.</span></span> <span data-ttu-id="be916-147">El bucle interno reduce una variable de contador de bucle para cada iteración del bucle.</span><span class="sxs-lookup"><span data-stu-id="be916-147">The inner loop decrements a loop counter variable for every iteration of the loop.</span></span>

[!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]

<span data-ttu-id="be916-148">Al anidar bucles, cada bucle debe tener una `counter` variable única.</span><span class="sxs-lookup"><span data-stu-id="be916-148">When nesting loops, each loop must have a unique `counter` variable.</span></span>

<span data-ttu-id="be916-149">También puede anidar distintos tipos de estructuras de control.</span><span class="sxs-lookup"><span data-stu-id="be916-149">You can also nest different kinds control structures within each other.</span></span> <span data-ttu-id="be916-150">Para obtener más información, vea [estructuras de control anidadas](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="be916-150">For more information, see [Nested Control Structures](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>

## <a name="exit-for-and-continue-for"></a><span data-ttu-id="be916-151">Salir de y continuar para</span><span class="sxs-lookup"><span data-stu-id="be916-151">Exit For and Continue For</span></span>

<span data-ttu-id="be916-152">La `Exit For` instrucción sale inmediatamente de `For` ...`Next`</span><span class="sxs-lookup"><span data-stu-id="be916-152">The `Exit For` statement immediately exits the `For`…`Next`</span></span> <span data-ttu-id="be916-153">bucle y transfiere el control a la instrucción que sigue a la `Next` instrucción.</span><span class="sxs-lookup"><span data-stu-id="be916-153">loop and transfers control to the statement that follows the `Next` statement.</span></span>

<span data-ttu-id="be916-154">La `Continue For` instrucción transfiere el control inmediatamente a la siguiente iteración del bucle.</span><span class="sxs-lookup"><span data-stu-id="be916-154">The `Continue For` statement transfers control immediately to the next iteration of the loop.</span></span> <span data-ttu-id="be916-155">Para obtener más información, vea [instrucción continue](continue-statement.md).</span><span class="sxs-lookup"><span data-stu-id="be916-155">For more information, see [Continue Statement](continue-statement.md).</span></span>

<span data-ttu-id="be916-156">En el ejemplo siguiente se muestra el uso de `Continue For` las `Exit For` instrucciones y.</span><span class="sxs-lookup"><span data-stu-id="be916-156">The following example illustrates the use of the `Continue For` and `Exit For` statements.</span></span>

[!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]

<span data-ttu-id="be916-157">Puede incluir cualquier número de `Exit For` instrucciones en `For` ...`Next`</span><span class="sxs-lookup"><span data-stu-id="be916-157">You can put any number of `Exit For` statements in a `For`…`Next`</span></span> <span data-ttu-id="be916-158">bucle</span><span class="sxs-lookup"><span data-stu-id="be916-158">loop.</span></span> <span data-ttu-id="be916-159">Cuando se usa dentro de la instrucción anidada `For` ...`Next`</span><span class="sxs-lookup"><span data-stu-id="be916-159">When used within nested `For`…`Next`</span></span> <span data-ttu-id="be916-160">bucles, `Exit For` sale del bucle más interno y transfiere el control al siguiente nivel superior de anidamiento.</span><span class="sxs-lookup"><span data-stu-id="be916-160">loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

<span data-ttu-id="be916-161">`Exit For`se suele usar después de evaluar alguna condición (por ejemplo, en `If` ... `Then` ...`Else` estructura).</span><span class="sxs-lookup"><span data-stu-id="be916-161">`Exit For` is often used after you evaluate some condition (for example, in an `If`...`Then`...`Else` structure).</span></span> <span data-ttu-id="be916-162">Puede que desee usar `Exit For` para las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="be916-162">You might want to use `Exit For` for the following conditions:</span></span>

- <span data-ttu-id="be916-163">Continuar la iteración no es necesario o imposible.</span><span class="sxs-lookup"><span data-stu-id="be916-163">Continuing to iterate is unnecessary or impossible.</span></span> <span data-ttu-id="be916-164">Un valor erróneo o una solicitud de finalización podría crear esta condición.</span><span class="sxs-lookup"><span data-stu-id="be916-164">An erroneous value or a termination request might create this condition.</span></span>

- <span data-ttu-id="be916-165">.. `Try` . `Catch` ...`Finally` la instrucción detecta una excepción.</span><span class="sxs-lookup"><span data-stu-id="be916-165">A `Try`...`Catch`...`Finally` statement catches an exception.</span></span> <span data-ttu-id="be916-166">Puede usar `Exit For` al final del `Finally` bloque.</span><span class="sxs-lookup"><span data-stu-id="be916-166">You might use `Exit For` at the end of the `Finally` block.</span></span>

- <span data-ttu-id="be916-167">Tiene un bucle sin fin, que es un bucle que podría ejecutar un número de veces grande o incluso infinito.</span><span class="sxs-lookup"><span data-stu-id="be916-167">You have an endless loop, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="be916-168">Si detecta este tipo de condición, puede usar `Exit For` para escapar el bucle.</span><span class="sxs-lookup"><span data-stu-id="be916-168">If you detect such a condition, you can use `Exit For` to escape the loop.</span></span> <span data-ttu-id="be916-169">Para obtener más información, vea.. [. Instrucción Loop](do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="be916-169">For more information, see [Do...Loop Statement](do-loop-statement.md).</span></span>

## <a name="technical-implementation"></a><span data-ttu-id="be916-170">Implementación técnica</span><span class="sxs-lookup"><span data-stu-id="be916-170">Technical Implementation</span></span>

<span data-ttu-id="be916-171">Cuando `For` se inicia un bucle... `Next` , Visual Basic evalúa `start` , `end` y `step` .</span><span class="sxs-lookup"><span data-stu-id="be916-171">When a `For`...`Next` loop starts, Visual Basic evaluates `start`, `end`, and `step`.</span></span> <span data-ttu-id="be916-172">Visual Basic evalúa estos valores solo en este momento y, a continuación, `start` se asigna a `counter` .</span><span class="sxs-lookup"><span data-stu-id="be916-172">Visual Basic evaluates these values only at this time and then assigns `start` to `counter`.</span></span> <span data-ttu-id="be916-173">Antes de que se ejecute el bloque de instrucciones, Visual Basic compara `counter` con `end` .</span><span class="sxs-lookup"><span data-stu-id="be916-173">Before the statement block runs, Visual Basic compares `counter` to `end`.</span></span> <span data-ttu-id="be916-174">Si `counter` ya es mayor que el `end` valor (o menor si `step` es negativo), el `For` bucle finaliza y el control pasa a la instrucción que sigue a la `Next` instrucción.</span><span class="sxs-lookup"><span data-stu-id="be916-174">If `counter` is already larger than the `end` value (or smaller if `step` is negative), the `For` loop ends and control passes to the statement that follows the `Next` statement.</span></span> <span data-ttu-id="be916-175">De lo contrario, se ejecuta el bloque de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="be916-175">Otherwise, the statement block runs.</span></span>

<span data-ttu-id="be916-176">Cada vez que Visual Basic encuentra la `Next` instrucción, se incrementa en `counter` `step` y vuelve a la `For` instrucción.</span><span class="sxs-lookup"><span data-stu-id="be916-176">Each time Visual Basic encounters the `Next` statement, it increments `counter` by `step` and returns to the `For` statement.</span></span> <span data-ttu-id="be916-177">Una vez más, se compara `counter` con `end` y, de nuevo, ejecuta el bloque o sale del bucle, en función del resultado.</span><span class="sxs-lookup"><span data-stu-id="be916-177">Again it compares `counter` to `end`, and again it either runs the block or exits the loop, depending on the result.</span></span> <span data-ttu-id="be916-178">Este proceso continúa hasta `counter` que `end` se encuentran las pasadas o una `Exit For` instrucción.</span><span class="sxs-lookup"><span data-stu-id="be916-178">This process continues until `counter` passes `end` or an `Exit For` statement is encountered.</span></span>

<span data-ttu-id="be916-179">El bucle no se detiene hasta que `counter` se ha pasado `end` .</span><span class="sxs-lookup"><span data-stu-id="be916-179">The loop doesn't stop until `counter` has passed `end`.</span></span> <span data-ttu-id="be916-180">Si `counter` es igual a `end` , el bucle continúa.</span><span class="sxs-lookup"><span data-stu-id="be916-180">If `counter` is equal to `end`, the loop continues.</span></span> <span data-ttu-id="be916-181">La comparación que determina si se debe ejecutar el bloque es `counter`  <=  `end` si `step` es positivo y `counter`  >=  `end` si `step` es negativo.</span><span class="sxs-lookup"><span data-stu-id="be916-181">The comparison that determines whether to run the block is `counter` <= `end` if `step` is positive and `counter` >= `end` if `step` is negative.</span></span>

<span data-ttu-id="be916-182">Si cambia el valor de `counter` mientras se encuentra dentro de un bucle, el código podría ser más difícil de leer y depurar.</span><span class="sxs-lookup"><span data-stu-id="be916-182">If you change the value of `counter` while inside a loop, your code might be more difficult to read and debug.</span></span> <span data-ttu-id="be916-183">Cambiar el valor de `start` , `end` o `step` no afecta a los valores de iteración que se determinaron cuando se escribió el bucle por primera vez.</span><span class="sxs-lookup"><span data-stu-id="be916-183">Changing the value of `start`, `end`, or `step` doesn't affect the iteration values that were determined when the loop was first entered.</span></span>

<span data-ttu-id="be916-184">Si anida bucles, el compilador indicará un error si encuentra la `Next` instrucción de un nivel de anidamiento externo antes de la `Next` instrucción de un nivel interno.</span><span class="sxs-lookup"><span data-stu-id="be916-184">If you nest loops, the compiler signals an error if it encounters the `Next` statement of an outer nesting level before the `Next` statement of an inner level.</span></span> <span data-ttu-id="be916-185">Sin embargo, el compilador puede detectar este error superpuesto solo si especifica `counter` en cada `Next` instrucción.</span><span class="sxs-lookup"><span data-stu-id="be916-185">However, the compiler can detect this overlapping error only if you specify `counter` in every `Next` statement.</span></span>

### <a name="step-argument"></a><span data-ttu-id="be916-186">Argumento Step</span><span class="sxs-lookup"><span data-stu-id="be916-186">Step Argument</span></span>

<span data-ttu-id="be916-187">El valor de `step` puede ser positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="be916-187">The value of `step` can be either positive or negative.</span></span> <span data-ttu-id="be916-188">Este parámetro determina el procesamiento de bucles según la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="be916-188">This parameter determines loop processing according to the following table:</span></span>

|<span data-ttu-id="be916-189">**Valor del paso**</span><span class="sxs-lookup"><span data-stu-id="be916-189">**Step value**</span></span>|<span data-ttu-id="be916-190">**El bucle se ejecuta si**</span><span class="sxs-lookup"><span data-stu-id="be916-190">**Loop executes if**</span></span>|
|--------------------|--------------------------|
|<span data-ttu-id="be916-191">Positivo o cero</span><span class="sxs-lookup"><span data-stu-id="be916-191">Positive or zero</span></span>|`counter` <= `end`|
|<span data-ttu-id="be916-192">Negative</span><span class="sxs-lookup"><span data-stu-id="be916-192">Negative</span></span>|`counter` >= `end`|

<span data-ttu-id="be916-193">El valor predeterminado de `step` es 1.</span><span class="sxs-lookup"><span data-stu-id="be916-193">The default value of `step` is 1.</span></span>

### <a name="counter-argument"></a><a name="BKMK_Counter"></a><span data-ttu-id="be916-194">Argumento Counter</span><span class="sxs-lookup"><span data-stu-id="be916-194">Counter Argument</span></span>

<span data-ttu-id="be916-195">En la tabla siguiente se indica si `counter` define una nueva variable local cuyo ámbito es el `For…Next` bucle completo.</span><span class="sxs-lookup"><span data-stu-id="be916-195">The following table indicates whether `counter` defines a new local variable that’s scoped to the entire `For…Next` loop.</span></span> <span data-ttu-id="be916-196">Esta determinación depende de si `datatype` está presente y si `counter` ya está definido.</span><span class="sxs-lookup"><span data-stu-id="be916-196">This determination depends on whether `datatype` is present and whether `counter` is already defined.</span></span>

|<span data-ttu-id="be916-197">`datatype`¿Está presente?</span><span class="sxs-lookup"><span data-stu-id="be916-197">Is `datatype` present?</span></span>|<span data-ttu-id="be916-198">`counter`¿Ya está definido?</span><span class="sxs-lookup"><span data-stu-id="be916-198">Is `counter` already defined?</span></span>|<span data-ttu-id="be916-199">Resultado (si `counter` define una nueva variable local cuyo ámbito es el `For...Next` bucle completo)</span><span class="sxs-lookup"><span data-stu-id="be916-199">Result (whether `counter` defines a new local variable that’s scoped to the entire `For...Next` loop)</span></span>|
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="be916-200">No</span><span class="sxs-lookup"><span data-stu-id="be916-200">No</span></span>|<span data-ttu-id="be916-201">Sí</span><span class="sxs-lookup"><span data-stu-id="be916-201">Yes</span></span>|<span data-ttu-id="be916-202">No, porque `counter` ya está definido.</span><span class="sxs-lookup"><span data-stu-id="be916-202">No, because `counter` is already defined.</span></span> <span data-ttu-id="be916-203">Si el ámbito de `counter` no es local para el procedimiento, se produce una advertencia en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="be916-203">If the scope of `counter` isn't local to the procedure, a compile-time warning occurs.</span></span>|
|<span data-ttu-id="be916-204">Sin</span><span class="sxs-lookup"><span data-stu-id="be916-204">No</span></span>|<span data-ttu-id="be916-205">No</span><span class="sxs-lookup"><span data-stu-id="be916-205">No</span></span>|<span data-ttu-id="be916-206">Sí.</span><span class="sxs-lookup"><span data-stu-id="be916-206">Yes.</span></span> <span data-ttu-id="be916-207">El tipo de datos se deduce de `start` las `end` expresiones, y `step` .</span><span class="sxs-lookup"><span data-stu-id="be916-207">The data type is inferred from the `start`, `end`, and `step` expressions.</span></span> <span data-ttu-id="be916-208">Para obtener información sobre la inferencia de tipos, vea [Option Infer Statement](option-infer-statement.md) e [inferencia de tipo local](../../programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="be916-208">For information about type inference, see [Option Infer Statement](option-infer-statement.md) and [Local Type Inference](../../programming-guide/language-features/variables/local-type-inference.md).</span></span>|
|<span data-ttu-id="be916-209">Sí</span><span class="sxs-lookup"><span data-stu-id="be916-209">Yes</span></span>|<span data-ttu-id="be916-210">Sí</span><span class="sxs-lookup"><span data-stu-id="be916-210">Yes</span></span>|<span data-ttu-id="be916-211">Sí, pero solo si la `counter` variable existente se define fuera del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="be916-211">Yes, but only if the existing `counter` variable is defined outside the procedure.</span></span> <span data-ttu-id="be916-212">Esa variable sigue siendo independiente.</span><span class="sxs-lookup"><span data-stu-id="be916-212">That variable remains separate.</span></span> <span data-ttu-id="be916-213">Si el ámbito de la `counter` variable existente es local para el procedimiento, se produce un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="be916-213">If the scope of the existing `counter` variable is local to the procedure, a compile-time error occurs.</span></span>|
|<span data-ttu-id="be916-214">Sí</span><span class="sxs-lookup"><span data-stu-id="be916-214">Yes</span></span>|<span data-ttu-id="be916-215">No</span><span class="sxs-lookup"><span data-stu-id="be916-215">No</span></span>|<span data-ttu-id="be916-216">Sí.</span><span class="sxs-lookup"><span data-stu-id="be916-216">Yes.</span></span>|

<span data-ttu-id="be916-217">El tipo de datos de `counter` determina el tipo de iteración, que debe ser uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="be916-217">The data type of `counter` determines the type of the iteration, which must be one of the following types:</span></span>

- <span data-ttu-id="be916-218">`Byte`, `SByte` , `UShort` , `Short` , `UInteger` , `Integer` , `ULong` , `Long` , `Decimal` , `Single` O `Double` .</span><span class="sxs-lookup"><span data-stu-id="be916-218">A `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, or `Double`.</span></span>

- <span data-ttu-id="be916-219">Una enumeración que se declara mediante una [instrucción enum](enum-statement.md).</span><span class="sxs-lookup"><span data-stu-id="be916-219">An enumeration that you declare by using an [Enum Statement](enum-statement.md).</span></span>

- <span data-ttu-id="be916-220">Un valor de tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="be916-220">An `Object`.</span></span>

- <span data-ttu-id="be916-221">Tipo `T` que tiene los operadores siguientes, donde `B` es un tipo que se puede utilizar en una `Boolean` expresión.</span><span class="sxs-lookup"><span data-stu-id="be916-221">A type `T` that has the following operators, where `B` is a type that can be used in a `Boolean` expression.</span></span>

  `Public Shared Operator >= (op1 As T, op2 As T) As B`

  `Public Shared Operator <= (op1 As T, op2 As T) As B`

  `Public Shared Operator - (op1 As T, op2 As T) As T`

  `Public Shared Operator + (op1 As T, op2 As T) As T`

<span data-ttu-id="be916-222">Opcionalmente, puede especificar la `counter` variable en la `Next` instrucción.</span><span class="sxs-lookup"><span data-stu-id="be916-222">You can optionally specify the `counter` variable in the `Next` statement.</span></span> <span data-ttu-id="be916-223">Esta sintaxis mejora la legibilidad del programa, sobre todo si tiene `For` bucles anidados.</span><span class="sxs-lookup"><span data-stu-id="be916-223">This syntax improves the readability of your program, especially if you have nested `For` loops.</span></span> <span data-ttu-id="be916-224">Debe especificar la variable que aparece en la instrucción correspondiente `For` .</span><span class="sxs-lookup"><span data-stu-id="be916-224">You must specify the variable that appears in the corresponding `For` statement.</span></span>

<span data-ttu-id="be916-225">Las `start` `end` expresiones, y `step` se pueden evaluar como cualquier tipo de datos que se amplíe al tipo de `counter` .</span><span class="sxs-lookup"><span data-stu-id="be916-225">The `start`, `end`, and `step` expressions can evaluate to any data type that widens to the type of `counter`.</span></span> <span data-ttu-id="be916-226">Si usa un tipo definido por el usuario para `counter` , es posible que tenga que definir el `CType` operador de conversión para convertir los tipos de `start` , `end` o `step` al tipo de `counter` .</span><span class="sxs-lookup"><span data-stu-id="be916-226">If you use a user-defined type for `counter`, you might have to define the `CType` conversion operator to convert the types of `start`, `end`, or `step` to the type of `counter`.</span></span>

## <a name="example"></a><span data-ttu-id="be916-227">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="be916-227">Example</span></span>

<span data-ttu-id="be916-228">En el ejemplo siguiente se quitan todos los elementos de una lista genérica.</span><span class="sxs-lookup"><span data-stu-id="be916-228">The following example removes all elements from a generic list.</span></span> <span data-ttu-id="be916-229">En lugar de [para cada... Instrucción siguiente](for-each-next-statement.md), en el ejemplo se muestra una `For` instrucción... `Next` que recorre en iteración en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="be916-229">Instead of a [For Each...Next Statement](for-each-next-statement.md), the example shows a `For`...`Next` statement that iterates in descending order.</span></span> <span data-ttu-id="be916-230">En el ejemplo se utiliza esta técnica porque el `removeAt` método hace que los elementos situados después del elemento quitado tengan un valor de índice inferior.</span><span class="sxs-lookup"><span data-stu-id="be916-230">The example uses this technique because the `removeAt` method causes elements after the removed element to have a lower index value.</span></span>

[!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]

## <a name="example"></a><span data-ttu-id="be916-231">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="be916-231">Example</span></span>

<span data-ttu-id="be916-232">En el ejemplo siguiente se recorre en iteración una enumeración declarada mediante una [instrucción enum](enum-statement.md).</span><span class="sxs-lookup"><span data-stu-id="be916-232">The following example iterates through an enumeration that's declared by using an [Enum Statement](enum-statement.md).</span></span>

[!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]

## <a name="example"></a><span data-ttu-id="be916-233">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="be916-233">Example</span></span>

<span data-ttu-id="be916-234">En el ejemplo siguiente, los parámetros de instrucción usan una clase que tiene sobrecargas de operador para los `+` `-` operadores,, `>=` y `<=` .</span><span class="sxs-lookup"><span data-stu-id="be916-234">In the following example, the statement parameters use a class that has operator overloads for the `+`, `-`, `>=`, and `<=` operators.</span></span>

[!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]

## <a name="see-also"></a><span data-ttu-id="be916-235">Consulte también</span><span class="sxs-lookup"><span data-stu-id="be916-235">See also</span></span>

- <xref:System.Collections.Generic.List%601>
- [<span data-ttu-id="be916-236">Estructuras de bucle</span><span class="sxs-lookup"><span data-stu-id="be916-236">Loop Structures</span></span>](../../programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="be916-237">Instrucción While...End While</span><span class="sxs-lookup"><span data-stu-id="be916-237">While...End While Statement</span></span>](while-end-while-statement.md)
- [<span data-ttu-id="be916-238">Instrucción Do...Loop</span><span class="sxs-lookup"><span data-stu-id="be916-238">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="be916-239">Estructuras de control anidadas</span><span class="sxs-lookup"><span data-stu-id="be916-239">Nested Control Structures</span></span>](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="be916-240">Instrucción Exit</span><span class="sxs-lookup"><span data-stu-id="be916-240">Exit Statement</span></span>](exit-statement.md)
- [<span data-ttu-id="be916-241">Colecciones</span><span class="sxs-lookup"><span data-stu-id="be916-241">Collections</span></span>](../../programming-guide/concepts/collections.md)

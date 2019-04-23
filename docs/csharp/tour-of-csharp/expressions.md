---
title: 'Expresiones de C#: un paseo por el lenguaje C#'
description: Las expresiones, los operandos y los operadores son bloques de construcción del lenguaje C#.
ms.date: 11/06/2016
ms.assetid: 20d5eb10-7381-47b9-ad90-f1cc895aa27e
ms.openlocfilehash: 4ffe947a4cb8c36a5925a4b3846486e44a9d8ec4
ms.sourcegitcommit: 859b2ba0c74a1a5a4ad0d59a3c3af23450995981
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2019
ms.locfileid: "59480760"
---
# <a name="expressions"></a><span data-ttu-id="6d246-103">Expresiones</span><span class="sxs-lookup"><span data-stu-id="6d246-103">Expressions</span></span>

<span data-ttu-id="6d246-104">Las *expresiones* se construyen con *operandos* y *operadores*.</span><span class="sxs-lookup"><span data-stu-id="6d246-104">*Expressions* are constructed from *operands* and *operators*.</span></span> <span data-ttu-id="6d246-105">Los operadores de una expresión indican qué operaciones se aplican a los operandos.</span><span class="sxs-lookup"><span data-stu-id="6d246-105">The operators of an expression indicate which operations to apply to the operands.</span></span> <span data-ttu-id="6d246-106">Ejemplos de operadores incluyen `+`, `-`, `*`, `/` y `new`.</span><span class="sxs-lookup"><span data-stu-id="6d246-106">Examples of operators include `+`, `-`, `*`, `/`, and `new`.</span></span> <span data-ttu-id="6d246-107">Algunos ejemplos de operandos son literales, campos, variables locales y expresiones.</span><span class="sxs-lookup"><span data-stu-id="6d246-107">Examples of operands include literals, fields, local variables, and expressions.</span></span>

<span data-ttu-id="6d246-108">Cuando una expresión contiene varios operadores, la *precedencia* de los operadores controla el orden en que se evalúan los operadores individuales.</span><span class="sxs-lookup"><span data-stu-id="6d246-108">When an expression contains multiple operators, the *precedence* of the operators controls the order in which the individual operators are evaluated.</span></span> <span data-ttu-id="6d246-109">Por ejemplo, la expresión `x + y * z` se evalúa como `x + (y * z)` porque el operador `*` tiene mayor precedencia que el operador `+`.</span><span class="sxs-lookup"><span data-stu-id="6d246-109">For example, the expression `x + y * z` is evaluated as `x + (y * z)` because the `*` operator has higher precedence than the `+` operator.</span></span>

<span data-ttu-id="6d246-110">Cuando un operando se encuentra entre dos operadores con la misma precedencia, la *asociatividad* de los operadores controla el orden en que se realizan las operaciones:</span><span class="sxs-lookup"><span data-stu-id="6d246-110">When an operand occurs between two operators with the same precedence, the *associativity* of the operators controls the order in which the operations are performed:</span></span>

* <span data-ttu-id="6d246-111">Excepto los operadores de asignación, todos los operadores binarios son *asociativos a la izquierda*, lo que significa que las operaciones se realizan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="6d246-111">Except for the assignment operators, all binary operators are *left-associative*, meaning that operations are performed from left to right.</span></span> <span data-ttu-id="6d246-112">Por ejemplo, `x + y + z` se evalúa como `(x + y) + z`.</span><span class="sxs-lookup"><span data-stu-id="6d246-112">For example, `x + y + z` is evaluated as `(x + y) + z`.</span></span>
* <span data-ttu-id="6d246-113">Los operadores de asignación y el operador condicional (`?:`) son *asociativos a la derecha*, lo que significa que las operaciones se realizan de derecha a izquierda.</span><span class="sxs-lookup"><span data-stu-id="6d246-113">The assignment operators and the conditional operator (`?:`) are *right-associative*, meaning that operations are performed from right to left.</span></span> <span data-ttu-id="6d246-114">Por ejemplo, `x = y = z` se evalúa como `x = (y = z)`.</span><span class="sxs-lookup"><span data-stu-id="6d246-114">For example, `x = y = z` is evaluated as `x = (y = z)`.</span></span>

<span data-ttu-id="6d246-115">La precedencia y la asociatividad pueden controlarse mediante paréntesis.</span><span class="sxs-lookup"><span data-stu-id="6d246-115">Precedence and associativity can be controlled using parentheses.</span></span> <span data-ttu-id="6d246-116">Por ejemplo, `x + y * z` primero multiplica `y` por `z` y luego suma el resultado a `x`, pero `(x + y) * z` primero suma `x` y `y` y luego multiplica el resultado por `z`.</span><span class="sxs-lookup"><span data-stu-id="6d246-116">For example, `x + y * z` first multiplies `y` by `z` and then adds the result to `x`, but `(x + y) * z` first adds `x` and `y` and then multiplies the result by `z`.</span></span>

<span data-ttu-id="6d246-117">La mayoría de los operadores se pueden *sobrecargar*.</span><span class="sxs-lookup"><span data-stu-id="6d246-117">Most operators can be *overloaded*.</span></span> <span data-ttu-id="6d246-118">La sobrecarga de operador permite la especificación de implementaciones de operadores definidas por el usuario para operaciones donde uno o ambos operandos son de un tipo de struct o una clase definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="6d246-118">Operator overloading permits user-defined operator implementations to be specified for operations where one or both of the operands are of a user-defined class or struct type.</span></span>

<span data-ttu-id="6d246-119">A continuación se resumen los operadores de C#, con las categorías de operador en orden de precedencia de mayor a menor.</span><span class="sxs-lookup"><span data-stu-id="6d246-119">The following summarizes C#’s operators, listing the operator categories in order of precedence from highest to lowest.</span></span> <span data-ttu-id="6d246-120">Los operadores de la misma categoría tienen la misma precedencia.</span><span class="sxs-lookup"><span data-stu-id="6d246-120">Operators in the same category have equal precedence.</span></span> <span data-ttu-id="6d246-121">En cada categoría, hay una lista de expresiones de esa categoría junto con la descripción de ese tipo de expresión.</span><span class="sxs-lookup"><span data-stu-id="6d246-121">Under each category is a list of expressions in that category along with the description of that expression type.</span></span>

* <span data-ttu-id="6d246-122">Principal</span><span class="sxs-lookup"><span data-stu-id="6d246-122">Primary</span></span>
  - `x.m`<span data-ttu-id="6d246-123">: Acceso a miembros</span><span class="sxs-lookup"><span data-stu-id="6d246-123">: Member access</span></span>
  - `x(...)`<span data-ttu-id="6d246-124">: Invocación de método y delegado</span><span class="sxs-lookup"><span data-stu-id="6d246-124">: Method and delegate invocation</span></span>
  - `x[...]`<span data-ttu-id="6d246-125">: Acceso a matriz e indizador</span><span class="sxs-lookup"><span data-stu-id="6d246-125">: Array and indexer access</span></span>
  - `x++`<span data-ttu-id="6d246-126">: Postincremento</span><span class="sxs-lookup"><span data-stu-id="6d246-126">: Post-increment</span></span>
  - `x--`<span data-ttu-id="6d246-127">: Postdecremento</span><span class="sxs-lookup"><span data-stu-id="6d246-127">: Post-decrement</span></span>
  - `new T(...)`<span data-ttu-id="6d246-128">: Creación de objetos y delegados</span><span class="sxs-lookup"><span data-stu-id="6d246-128">: Object and delegate creation</span></span>
  - `new T(...){...}`<span data-ttu-id="6d246-129">: creación de objetos con inicializador</span><span class="sxs-lookup"><span data-stu-id="6d246-129">: Object creation with initializer</span></span>
  - `new {...}`<span data-ttu-id="6d246-130">:  inicializador de objetos anónimos</span><span class="sxs-lookup"><span data-stu-id="6d246-130">:  Anonymous object initializer</span></span>
  - `new T[...]`<span data-ttu-id="6d246-131">: creación de matriz</span><span class="sxs-lookup"><span data-stu-id="6d246-131">: Array creation</span></span>
  - `typeof(T)`<span data-ttu-id="6d246-132">: obtener el objeto <xref:System.Type> para</span><span class="sxs-lookup"><span data-stu-id="6d246-132">: Obtain <xref:System.Type> object for</span></span> `T`
  - `checked(x)`<span data-ttu-id="6d246-133">: Evaluar expresión en contexto comprobado</span><span class="sxs-lookup"><span data-stu-id="6d246-133">: Evaluate expression in checked context</span></span>
  - `unchecked(x)`<span data-ttu-id="6d246-134">: Evaluar expresión en contexto no comprobado</span><span class="sxs-lookup"><span data-stu-id="6d246-134">: Evaluate expression in unchecked context</span></span>
  - `default(T)`<span data-ttu-id="6d246-135">: obtener valor predeterminado de tipo</span><span class="sxs-lookup"><span data-stu-id="6d246-135">: Obtain default value of type</span></span> `T`
  - `delegate {...}`<span data-ttu-id="6d246-136">: Función anónima (método anónimo)</span><span class="sxs-lookup"><span data-stu-id="6d246-136">: Anonymous function (anonymous method)</span></span>
* <span data-ttu-id="6d246-137">Unario</span><span class="sxs-lookup"><span data-stu-id="6d246-137">Unary</span></span>
  - `+x`<span data-ttu-id="6d246-138">: identidad</span><span class="sxs-lookup"><span data-stu-id="6d246-138">: Identity</span></span>
  - `-x`<span data-ttu-id="6d246-139">: Negación</span><span class="sxs-lookup"><span data-stu-id="6d246-139">: Negation</span></span>
  - `!x`<span data-ttu-id="6d246-140">: Negación lógica</span><span class="sxs-lookup"><span data-stu-id="6d246-140">: Logical negation</span></span>
  - `~x`<span data-ttu-id="6d246-141">: Negación bit a bit</span><span class="sxs-lookup"><span data-stu-id="6d246-141">: Bitwise negation</span></span>
  - `++x`<span data-ttu-id="6d246-142">: Preincremento</span><span class="sxs-lookup"><span data-stu-id="6d246-142">: Pre-increment</span></span>
  - `--x`<span data-ttu-id="6d246-143">: Predecremento</span><span class="sxs-lookup"><span data-stu-id="6d246-143">: Pre-decrement</span></span>
  - `(T)x`<span data-ttu-id="6d246-144">: convertir explícitamente `x` en el tipo</span><span class="sxs-lookup"><span data-stu-id="6d246-144">: Explicitly convert `x` to type</span></span> `T`
  - `await x`<span data-ttu-id="6d246-145">: esperar asincrónicamente a que finalice `x`</span><span class="sxs-lookup"><span data-stu-id="6d246-145">: Asynchronously wait for `x` to complete</span></span>
* <span data-ttu-id="6d246-146">Multiplicativo</span><span class="sxs-lookup"><span data-stu-id="6d246-146">Multiplicative</span></span>
  - `x * y`<span data-ttu-id="6d246-147">: Multiplicación</span><span class="sxs-lookup"><span data-stu-id="6d246-147">: Multiplication</span></span>
  - `x / y`<span data-ttu-id="6d246-148">: División</span><span class="sxs-lookup"><span data-stu-id="6d246-148">: Division</span></span>
  - `x % y`<span data-ttu-id="6d246-149">: Resto</span><span class="sxs-lookup"><span data-stu-id="6d246-149">: Remainder</span></span>
* <span data-ttu-id="6d246-150">Aditivo</span><span class="sxs-lookup"><span data-stu-id="6d246-150">Additive</span></span>
  - `x + y`<span data-ttu-id="6d246-151">: Suma, concatenación de cadenas, combinación de delegados</span><span class="sxs-lookup"><span data-stu-id="6d246-151">: Addition, string concatenation, delegate combination</span></span>
  - `x – y`<span data-ttu-id="6d246-152">: Resta, eliminación de delegados</span><span class="sxs-lookup"><span data-stu-id="6d246-152">: Subtraction, delegate removal</span></span>
* <span data-ttu-id="6d246-153">Shift</span><span class="sxs-lookup"><span data-stu-id="6d246-153">Shift</span></span>
  - `x << y`<span data-ttu-id="6d246-154">: Desplazamiento a la izquierda</span><span class="sxs-lookup"><span data-stu-id="6d246-154">: Shift left</span></span>
  - `x >> y`<span data-ttu-id="6d246-155">: Desplazamiento a la derecha</span><span class="sxs-lookup"><span data-stu-id="6d246-155">: Shift right</span></span>
* <span data-ttu-id="6d246-156">Comprobación de tipos y relacional</span><span class="sxs-lookup"><span data-stu-id="6d246-156">Relational and type testing</span></span>
  - `x < y`<span data-ttu-id="6d246-157">: Menor que</span><span class="sxs-lookup"><span data-stu-id="6d246-157">: Less than</span></span>
  - `x > y`<span data-ttu-id="6d246-158">: Mayor que</span><span class="sxs-lookup"><span data-stu-id="6d246-158">: Greater than</span></span>
  - `x <= y`<span data-ttu-id="6d246-159">: Menor o igual que</span><span class="sxs-lookup"><span data-stu-id="6d246-159">: Less than or equal</span></span>
  - `x >= y`<span data-ttu-id="6d246-160">: Mayor o igual que</span><span class="sxs-lookup"><span data-stu-id="6d246-160">: Greater than or equal</span></span>
  - `x is T`<span data-ttu-id="6d246-161">: volver a ejecutar `true` si `x` es una `T`, de lo contrario `false`</span><span class="sxs-lookup"><span data-stu-id="6d246-161">: Return `true` if `x` is a `T`, `false` otherwise</span></span>
  - `x as T`<span data-ttu-id="6d246-162">: volver a ejecutar `x` con tipo `T`, o `null` si `x` no es una</span><span class="sxs-lookup"><span data-stu-id="6d246-162">: Return `x` typed as `T`, or `null` if `x` is not a</span></span> `T`
* <span data-ttu-id="6d246-163">Igualdad</span><span class="sxs-lookup"><span data-stu-id="6d246-163">Equality</span></span>
  - `x == y`<span data-ttu-id="6d246-164">: Igual</span><span class="sxs-lookup"><span data-stu-id="6d246-164">: Equal</span></span>
  - `x != y`<span data-ttu-id="6d246-165">: No igual</span><span class="sxs-lookup"><span data-stu-id="6d246-165">: Not equal</span></span>
* <span data-ttu-id="6d246-166">AND lógico</span><span class="sxs-lookup"><span data-stu-id="6d246-166">Logical AND</span></span>
  - `x & y`<span data-ttu-id="6d246-167">: AND bit a bit entero, AND lógico booleano</span><span class="sxs-lookup"><span data-stu-id="6d246-167">: Integer bitwise AND, boolean logical AND</span></span>
* <span data-ttu-id="6d246-168">XOR lógico</span><span class="sxs-lookup"><span data-stu-id="6d246-168">Logical XOR</span></span>
  - `x ^ y`<span data-ttu-id="6d246-169">: XOR bit a bit entero, XOR lógico booleano</span><span class="sxs-lookup"><span data-stu-id="6d246-169">: Integer bitwise XOR, boolean logical XOR</span></span>
* <span data-ttu-id="6d246-170">OR lógico</span><span class="sxs-lookup"><span data-stu-id="6d246-170">Logical OR</span></span>
  - `x | y`<span data-ttu-id="6d246-171">: OR bit a bit entero, OR lógico booleano</span><span class="sxs-lookup"><span data-stu-id="6d246-171">: Integer bitwise OR, boolean logical OR</span></span>
* <span data-ttu-id="6d246-172">AND condicional</span><span class="sxs-lookup"><span data-stu-id="6d246-172">Conditional AND</span></span>
  - `x && y`<span data-ttu-id="6d246-173">: evalúa `y` solo si `x` no es</span><span class="sxs-lookup"><span data-stu-id="6d246-173">: Evaluates `y` only if `x` is not</span></span> `false`
* <span data-ttu-id="6d246-174">OR condicional</span><span class="sxs-lookup"><span data-stu-id="6d246-174">Conditional OR</span></span>
  - `x || y`<span data-ttu-id="6d246-175">: evalúa `y` solo si `x` no es</span><span class="sxs-lookup"><span data-stu-id="6d246-175">: Evaluates `y` only if `x` is not</span></span> `true`
* <span data-ttu-id="6d246-176">Uso combinado de NULL</span><span class="sxs-lookup"><span data-stu-id="6d246-176">Null coalescing</span></span>
  - `x ?? y`<span data-ttu-id="6d246-177">: se evalúa como `y` si `x` es NULL, de lo contrario, como `x`</span><span class="sxs-lookup"><span data-stu-id="6d246-177">: Evaluates to `y` if `x` is null, to `x` otherwise</span></span>
* <span data-ttu-id="6d246-178">Condicional</span><span class="sxs-lookup"><span data-stu-id="6d246-178">Conditional</span></span>
  - `x ? y : z`<span data-ttu-id="6d246-179">: se evalúa como `y` si `x` es `true` o `z` si `x` es</span><span class="sxs-lookup"><span data-stu-id="6d246-179">: Evaluates `y` if `x` is `true`, `z` if `x` is</span></span> `false`
* <span data-ttu-id="6d246-180">Asignación o función anónima</span><span class="sxs-lookup"><span data-stu-id="6d246-180">Assignment or anonymous function</span></span>
  - `x = y`<span data-ttu-id="6d246-181">: Asignación</span><span class="sxs-lookup"><span data-stu-id="6d246-181">: Assignment</span></span>
  - `x op= y`<span data-ttu-id="6d246-182">: asignación compuesta; los operadores admitidos son</span><span class="sxs-lookup"><span data-stu-id="6d246-182">: Compound assignment; supported operators are</span></span>
    - `*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`
  - `(T x) => y`<span data-ttu-id="6d246-183">: Función anónima (expresión lambda)</span><span class="sxs-lookup"><span data-stu-id="6d246-183">: Anonymous function (lambda expression)</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="6d246-184">[Anterior](types-and-variables.md)
> [Siguiente](statements.md)</span><span class="sxs-lookup"><span data-stu-id="6d246-184">[Previous](types-and-variables.md)
[Next](statements.md)</span></span>

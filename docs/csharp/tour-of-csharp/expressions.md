---
title: 'Expresiones de C#: un paseo por el lenguaje C#'
description: "Las expresiones, los operandos y los operadores son bloques de construcción del lenguaje C#."
keywords: ".NET, csharp, expresión, operador, operanddo"
author: BillWagner
ms.author: wiwagn
ms.date: 11/06/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 20d5eb10-7381-47b9-ad90-f1cc895aa27e
ms.openlocfilehash: 7b7e321e6554818924a8a2b68afa4c787807bcba
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2017
---
# <a name="expressions"></a><span data-ttu-id="c7d0b-104">Expresiones</span><span class="sxs-lookup"><span data-stu-id="c7d0b-104">Expressions</span></span>

<span data-ttu-id="c7d0b-105">Las *expresiones* se construyen con *operandos* y *operadores*.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-105">*Expressions* are constructed from *operands* and *operators*.</span></span> <span data-ttu-id="c7d0b-106">Los operadores de una expresión indican qué operaciones se aplican a los operandos.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-106">The operators of an expression indicate which operations to apply to the operands.</span></span> <span data-ttu-id="c7d0b-107">Ejemplos de operadores incluyen `+`, `-`, `*`, `/` y `new`.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-107">Examples of operators include `+`, `-`, `*`, `/`, and `new`.</span></span> <span data-ttu-id="c7d0b-108">Algunos ejemplos de operandos son literales, campos, variables locales y expresiones.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-108">Examples of operands include literals, fields, local variables, and expressions.</span></span>

<span data-ttu-id="c7d0b-109">Cuando una expresión contiene varios operadores, la *precedencia* de los operadores controla el orden en que se evalúan los operadores individuales.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-109">When an expression contains multiple operators, the *precedence* of the operators controls the order in which the individual operators are evaluated.</span></span> <span data-ttu-id="c7d0b-110">Por ejemplo, la expresión `x + y * z` se evalúa como `x + (y * z)` porque el operador `*` tiene mayor precedencia que el operador `+`.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-110">For example, the expression `x + y * z` is evaluated as `x + (y * z)` because the `*` operator has higher precedence than the `+` operator.</span></span>

<span data-ttu-id="c7d0b-111">Cuando un operando se encuentra entre dos operadores con la misma precedencia, la *asociatividad* de los operadores controla el orden en que se realizan las operaciones:</span><span class="sxs-lookup"><span data-stu-id="c7d0b-111">When an operand occurs between two operators with the same precedence, the *associativity* of the operators controls the order in which the operations are performed:</span></span>

*   <span data-ttu-id="c7d0b-112">Excepto los operadores de asignación, todos los operadores binarios son *asociativos a la izquierda*, lo que significa que las operaciones se realizan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-112">Except for the assignment operators, all binary operators are *left-associative*, meaning that operations are performed from left to right.</span></span> <span data-ttu-id="c7d0b-113">Por ejemplo, `x + y + z` se evalúa como `(x + y) + z`.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-113">For example, `x + y + z` is evaluated as `(x + y) + z`.</span></span>
*   <span data-ttu-id="c7d0b-114">Los operadores de asignación y el operador condicional (`?:`) son *asociativos a la derecha*, lo que significa que las operaciones se realizan de derecha a izquierda.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-114">The assignment operators and the conditional operator (`?:`) are *right-associative*, meaning that operations are performed from right to left.</span></span> <span data-ttu-id="c7d0b-115">Por ejemplo, `x = y = z` se evalúa como `x = (y = z)`.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-115">For example, `x = y = z` is evaluated as `x = (y = z)`.</span></span>

<span data-ttu-id="c7d0b-116">La precedencia y la asociatividad pueden controlarse mediante paréntesis.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-116">Precedence and associativity can be controlled using parentheses.</span></span> <span data-ttu-id="c7d0b-117">Por ejemplo, `x + y * z` primero multiplica `y` por `z` y luego suma el resultado a `x`, pero `(x + y) * z` primero suma `x` y `y` y luego multiplica el resultado por `z`.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-117">For example, `x + y * z` first multiplies `y` by `z` and then adds the result to `x`, but `(x + y) * z` first adds `x` and `y` and then multiplies the result by `z`.</span></span>

<span data-ttu-id="c7d0b-118">La mayoría de los operadores se pueden *sobrecargar*.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-118">Most operators can be *overloaded*.</span></span> <span data-ttu-id="c7d0b-119">La sobrecarga de operador permite la especificación de implementaciones de operadores definidas por el usuario para operaciones donde uno o ambos operandos son de un tipo de struct o una clase definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-119">Operator overloading permits user-defined operator implementations to be specified for operations where one or both of the operands are of a user-defined class or struct type.</span></span>

<span data-ttu-id="c7d0b-120">A continuación se resumen los operadores de C#, con las categorías de operador en orden de precedencia de mayor a menor.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-120">The following summarizes C#’s operators, listing the operator categories in order of precedence from highest to lowest.</span></span> <span data-ttu-id="c7d0b-121">Los operadores de la misma categoría tienen la misma precedencia.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-121">Operators in the same category have equal precedence.</span></span> <span data-ttu-id="c7d0b-122">En cada categoría, hay una lista de expresiones de esa categoría junto con la descripción de ese tipo de expresión.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-122">Under each category is a list of expressions in that category along with the description of that expression type.</span></span>

* <span data-ttu-id="c7d0b-123">Principal</span><span class="sxs-lookup"><span data-stu-id="c7d0b-123">Primary</span></span>
    - <span data-ttu-id="c7d0b-124">`x.m`: acceso a miembros.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-124">`x.m`: Member access</span></span>
    - <span data-ttu-id="c7d0b-125">`x(...)`: invocación de método y delegado.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-125">`x(...)`: Method and delegate invocation</span></span>
    - <span data-ttu-id="c7d0b-126">`x[...]`: acceso a matriz e indexador.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-126">`x[...]`: Array and indexer access</span></span>
    - <span data-ttu-id="c7d0b-127">`x++`: postincremento.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-127">`x++`: Post-increment</span></span>
    - <span data-ttu-id="c7d0b-128">`x--`: postdecremento.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-128">`x--`: Post-decrement</span></span>
    - <span data-ttu-id="c7d0b-129">`new T(...)`: creación de objetos y delegados.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-129">`new T(...)`: Object and delegate creation</span></span>
    - <span data-ttu-id="c7d0b-130">`new T(...){...}`: creación de objetos con inicializador.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-130">`new T(...){...}`: Object creation with initializer</span></span>
    - <span data-ttu-id="c7d0b-131">`new {...}`: inicializador de objetos anónimos.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-131">`new {...}`:  Anonymous object initializer</span></span>
    - <span data-ttu-id="c7d0b-132">`new T[...]`: creación de matriz.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-132">`new T[...]`: Array creation</span></span>
    - <span data-ttu-id="c7d0b-133">`typeof(T)`: obtener el objeto <xref:System.Type> para `T`.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-133">`typeof(T)`: Obtain <xref:System.Type> object for `T`</span></span>
    - <span data-ttu-id="c7d0b-134">`checked(x)`: evaluar expresión en contexto comprobado.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-134">`checked(x)`: Evaluate expression in checked context</span></span>
    - <span data-ttu-id="c7d0b-135">`unchecked(x)`: evaluar expresión en contexto no comprobado.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-135">`unchecked(x)`: Evaluate expression in unchecked context</span></span>
    - <span data-ttu-id="c7d0b-136">`default(T)`: obtener valor predeterminado de tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-136">`default(T)`: Obtain default value of type `T`</span></span>
    - <span data-ttu-id="c7d0b-137">`delegate {...}`: función anónima (método anónimo).</span><span class="sxs-lookup"><span data-stu-id="c7d0b-137">`delegate {...}`: Anonymous function (anonymous method)</span></span>
* <span data-ttu-id="c7d0b-138">Unario</span><span class="sxs-lookup"><span data-stu-id="c7d0b-138">Unary</span></span>
    - <span data-ttu-id="c7d0b-139">`+x`: identidad.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-139">`+x`: Identity</span></span>
    - <span data-ttu-id="c7d0b-140">`-x`: negación.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-140">`-x`: Negation</span></span>
    - <span data-ttu-id="c7d0b-141">`!x`: negación lógica.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-141">`!x`: Logical negation</span></span>
    - <span data-ttu-id="c7d0b-142">`~x`: negación bit a bit.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-142">`~x`: Bitwise negation</span></span>
    - <span data-ttu-id="c7d0b-143">`++x`: preincremento.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-143">`++x`: Pre-increment</span></span>
    - <span data-ttu-id="c7d0b-144">`--x`: predecremento.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-144">`--x`: Pre-decrement</span></span>
    - <span data-ttu-id="c7d0b-145">`(T)x`: convertir explícitamente `x` en el tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-145">`(T)x`: Explicitly convert `x` to type `T`</span></span>
    - <span data-ttu-id="c7d0b-146">`await x`: esperar asincrónicamente a que finalice `x`.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-146">`await x`: Asynchronously wait for `x` to complete</span></span>
* <span data-ttu-id="c7d0b-147">Multiplicativo</span><span class="sxs-lookup"><span data-stu-id="c7d0b-147">Multiplicative</span></span>
    - <span data-ttu-id="c7d0b-148">`x * y`: multiplicación.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-148">`x * y`: Multiplication</span></span>
    - <span data-ttu-id="c7d0b-149">`x / y`: división.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-149">`x / y`: Division</span></span>
    - <span data-ttu-id="c7d0b-150">`x % y`: aviso.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-150">`x % y`: Remainder</span></span>
* <span data-ttu-id="c7d0b-151">Aditivo</span><span class="sxs-lookup"><span data-stu-id="c7d0b-151">Additive</span></span>
    - <span data-ttu-id="c7d0b-152">`x + y`: suma, concatenación de cadenas, combinación de delegados.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-152">`x + y`: Addition, string concatenation, delegate combination</span></span>
    - <span data-ttu-id="c7d0b-153">`x – y`: resta, eliminación de delegados.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-153">`x – y`: Subtraction, delegate removal</span></span>
* <span data-ttu-id="c7d0b-154">Shift</span><span class="sxs-lookup"><span data-stu-id="c7d0b-154">Shift</span></span>
    - <span data-ttu-id="c7d0b-155">`x << y`: desplazamiento a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-155">`x << y`: Shift left</span></span>
    - <span data-ttu-id="c7d0b-156">`x >> y`: desplazamiento a la derecha.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-156">`x >> y`: Shift right</span></span>
* <span data-ttu-id="c7d0b-157">Comprobación de tipos y relacional</span><span class="sxs-lookup"><span data-stu-id="c7d0b-157">Relational and type testing</span></span>
    - <span data-ttu-id="c7d0b-158">`x < y`: menor que.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-158">`x < y`: Less than</span></span>
    - <span data-ttu-id="c7d0b-159">`x > y`: mayor que.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-159">`x > y`: Greater than</span></span>
    - <span data-ttu-id="c7d0b-160">`x <= y`: menor o igual que.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-160">`x <= y`: Less than or equal</span></span>
    - <span data-ttu-id="c7d0b-161">`x >= y`: mayor o igual que.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-161">`x >= y`: Greater than or equal</span></span>
    - <span data-ttu-id="c7d0b-162">`x is T`: volver a ejecutar `true` si `x` es una `T`, de lo contrario `false`.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-162">`x is T`: Return `true` if `x` is a `T`, `false` otherwise</span></span>
    - <span data-ttu-id="c7d0b-163">`x as T`: volver a ejecutar `x` con tipo `T`, o `null` si `x` no es una `T`.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-163">`x as T`: Return `x` typed as `T`, or `null` if `x` is not a `T`</span></span>
* <span data-ttu-id="c7d0b-164">Igualdad</span><span class="sxs-lookup"><span data-stu-id="c7d0b-164">Equality</span></span>
    - <span data-ttu-id="c7d0b-165">`x == y`: igual que.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-165">`x == y`: Equal</span></span>
    - <span data-ttu-id="c7d0b-166">`x != y`: no igual que.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-166">`x != y`: Not equal</span></span>
* <span data-ttu-id="c7d0b-167">AND lógico</span><span class="sxs-lookup"><span data-stu-id="c7d0b-167">Logical AND</span></span>
    - <span data-ttu-id="c7d0b-168">`x & y`: AND bit a bit entero, AND lógico booleano.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-168">`x & y`: Integer bitwise AND, boolean logical AND</span></span>
* <span data-ttu-id="c7d0b-169">XOR lógico</span><span class="sxs-lookup"><span data-stu-id="c7d0b-169">Logical XOR</span></span>
    - <span data-ttu-id="c7d0b-170">`x ^ y`: XOR bit a bit entero, XOR lógico booleano.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-170">`x ^ y`: Integer bitwise XOR, boolean logical XOR</span></span>
* <span data-ttu-id="c7d0b-171">OR lógico</span><span class="sxs-lookup"><span data-stu-id="c7d0b-171">Logical OR</span></span>
    - <span data-ttu-id="c7d0b-172">`x | y`: OR bit a bit entero, OR lógico booleano.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-172">`x | y`: Integer bitwise OR, boolean logical OR</span></span>
* <span data-ttu-id="c7d0b-173">AND condicional</span><span class="sxs-lookup"><span data-stu-id="c7d0b-173">Conditional AND</span></span>
    - <span data-ttu-id="c7d0b-174">`x && y`: evalúa `y` solo si `x` no es `false`.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-174">`x && y`: Evaluates `y` only if `x` is not `false`</span></span>
* <span data-ttu-id="c7d0b-175">OR condicional</span><span class="sxs-lookup"><span data-stu-id="c7d0b-175">Conditional OR</span></span>
    - <span data-ttu-id="c7d0b-176">`x || y`: evalúa `y` solo si `x` no es `true`.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-176">`x || y`: Evaluates `y` only if `x` is not `true`</span></span>
* <span data-ttu-id="c7d0b-177">Uso combinado de NULL</span><span class="sxs-lookup"><span data-stu-id="c7d0b-177">Null coalescing</span></span>
    - <span data-ttu-id="c7d0b-178">`x ?? y`: se evalúa como `y` si `x` es null, de lo contrario, como `x`.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-178">`x ?? y`: Evaluates to `y` if `x` is null, to `x` otherwise</span></span>
* <span data-ttu-id="c7d0b-179">Condicional</span><span class="sxs-lookup"><span data-stu-id="c7d0b-179">Conditional</span></span>
    - <span data-ttu-id="c7d0b-180">`x ? y : z`: se evalúa como `y` si `x` es `true` o `z` si `x` es `false`.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-180">`x ? y : z`: Evaluates `y` if `x` is `true`, `z` if `x` is `false`</span></span>
* <span data-ttu-id="c7d0b-181">Asignación o función anónima</span><span class="sxs-lookup"><span data-stu-id="c7d0b-181">Assignment or anonymous function</span></span>
    - <span data-ttu-id="c7d0b-182">`x = y`: asignación.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-182">`x = y`: Assignment</span></span>
    - <span data-ttu-id="c7d0b-183">`x op= y`: asignación compuesta; operadores admitidos son:</span><span class="sxs-lookup"><span data-stu-id="c7d0b-183">`x op= y`: Compound assignment; supported operators are</span></span>
        - <span data-ttu-id="c7d0b-184">`*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`</span><span class="sxs-lookup"><span data-stu-id="c7d0b-184">`*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`</span></span>
    - <span data-ttu-id="c7d0b-185">`(T x) => y`: función anónima (expresión lambda).</span><span class="sxs-lookup"><span data-stu-id="c7d0b-185">`(T x) => y`: Anonymous function (lambda expression)</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="c7d0b-186">[Anterior](types-and-variables.md)
[Siguiente](statements.md)</span><span class="sxs-lookup"><span data-stu-id="c7d0b-186">[Previous](types-and-variables.md)
[Next](statements.md)</span></span>

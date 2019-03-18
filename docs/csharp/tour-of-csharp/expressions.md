---
title: 'Expresiones de C#: un paseo por el lenguaje C#'
description: Las expresiones, los operandos y los operadores son bloques de construcción del lenguaje C#.
ms.date: 11/06/2016
ms.assetid: 20d5eb10-7381-47b9-ad90-f1cc895aa27e
ms.openlocfilehash: 7a7f65eb7ba3da3f9630bbcb92d8578d60d2095d
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2019
ms.locfileid: "57846602"
---
# <a name="expressions"></a><span data-ttu-id="5804f-103">Expresiones</span><span class="sxs-lookup"><span data-stu-id="5804f-103">Expressions</span></span>

<span data-ttu-id="5804f-104">Las *expresiones* se construyen con *operandos* y *operadores*.</span><span class="sxs-lookup"><span data-stu-id="5804f-104">*Expressions* are constructed from *operands* and *operators*.</span></span> <span data-ttu-id="5804f-105">Los operadores de una expresión indican qué operaciones se aplican a los operandos.</span><span class="sxs-lookup"><span data-stu-id="5804f-105">The operators of an expression indicate which operations to apply to the operands.</span></span> <span data-ttu-id="5804f-106">Ejemplos de operadores incluyen `+`, `-`, `*`, `/` y `new`.</span><span class="sxs-lookup"><span data-stu-id="5804f-106">Examples of operators include `+`, `-`, `*`, `/`, and `new`.</span></span> <span data-ttu-id="5804f-107">Algunos ejemplos de operandos son literales, campos, variables locales y expresiones.</span><span class="sxs-lookup"><span data-stu-id="5804f-107">Examples of operands include literals, fields, local variables, and expressions.</span></span>

<span data-ttu-id="5804f-108">Cuando una expresión contiene varios operadores, la *precedencia* de los operadores controla el orden en que se evalúan los operadores individuales.</span><span class="sxs-lookup"><span data-stu-id="5804f-108">When an expression contains multiple operators, the *precedence* of the operators controls the order in which the individual operators are evaluated.</span></span> <span data-ttu-id="5804f-109">Por ejemplo, la expresión `x + y * z` se evalúa como `x + (y * z)` porque el operador `*` tiene mayor precedencia que el operador `+`.</span><span class="sxs-lookup"><span data-stu-id="5804f-109">For example, the expression `x + y * z` is evaluated as `x + (y * z)` because the `*` operator has higher precedence than the `+` operator.</span></span>

<span data-ttu-id="5804f-110">Cuando un operando se encuentra entre dos operadores con la misma precedencia, la *asociatividad* de los operadores controla el orden en que se realizan las operaciones:</span><span class="sxs-lookup"><span data-stu-id="5804f-110">When an operand occurs between two operators with the same precedence, the *associativity* of the operators controls the order in which the operations are performed:</span></span>

* <span data-ttu-id="5804f-111">Excepto los operadores de asignación, todos los operadores binarios son *asociativos a la izquierda*, lo que significa que las operaciones se realizan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="5804f-111">Except for the assignment operators, all binary operators are *left-associative*, meaning that operations are performed from left to right.</span></span> <span data-ttu-id="5804f-112">Por ejemplo, `x + y + z` se evalúa como `(x + y) + z`.</span><span class="sxs-lookup"><span data-stu-id="5804f-112">For example, `x + y + z` is evaluated as `(x + y) + z`.</span></span>
* <span data-ttu-id="5804f-113">Los operadores de asignación y el operador condicional (`?:`) son *asociativos a la derecha*, lo que significa que las operaciones se realizan de derecha a izquierda.</span><span class="sxs-lookup"><span data-stu-id="5804f-113">The assignment operators and the conditional operator (`?:`) are *right-associative*, meaning that operations are performed from right to left.</span></span> <span data-ttu-id="5804f-114">Por ejemplo, `x = y = z` se evalúa como `x = (y = z)`.</span><span class="sxs-lookup"><span data-stu-id="5804f-114">For example, `x = y = z` is evaluated as `x = (y = z)`.</span></span>

<span data-ttu-id="5804f-115">La precedencia y la asociatividad pueden controlarse mediante paréntesis.</span><span class="sxs-lookup"><span data-stu-id="5804f-115">Precedence and associativity can be controlled using parentheses.</span></span> <span data-ttu-id="5804f-116">Por ejemplo, `x + y * z` primero multiplica `y` por `z` y luego suma el resultado a `x`, pero `(x + y) * z` primero suma `x` y `y` y luego multiplica el resultado por `z`.</span><span class="sxs-lookup"><span data-stu-id="5804f-116">For example, `x + y * z` first multiplies `y` by `z` and then adds the result to `x`, but `(x + y) * z` first adds `x` and `y` and then multiplies the result by `z`.</span></span>

<span data-ttu-id="5804f-117">La mayoría de los operadores se pueden *sobrecargar*.</span><span class="sxs-lookup"><span data-stu-id="5804f-117">Most operators can be *overloaded*.</span></span> <span data-ttu-id="5804f-118">La sobrecarga de operador permite la especificación de implementaciones de operadores definidas por el usuario para operaciones donde uno o ambos operandos son de un tipo de struct o una clase definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="5804f-118">Operator overloading permits user-defined operator implementations to be specified for operations where one or both of the operands are of a user-defined class or struct type.</span></span>

<span data-ttu-id="5804f-119">A continuación se resumen los operadores de C#, con las categorías de operador en orden de precedencia de mayor a menor.</span><span class="sxs-lookup"><span data-stu-id="5804f-119">The following summarizes C#’s operators, listing the operator categories in order of precedence from highest to lowest.</span></span> <span data-ttu-id="5804f-120">Los operadores de la misma categoría tienen la misma precedencia.</span><span class="sxs-lookup"><span data-stu-id="5804f-120">Operators in the same category have equal precedence.</span></span> <span data-ttu-id="5804f-121">En cada categoría, hay una lista de expresiones de esa categoría junto con la descripción de ese tipo de expresión.</span><span class="sxs-lookup"><span data-stu-id="5804f-121">Under each category is a list of expressions in that category along with the description of that expression type.</span></span>

* <span data-ttu-id="5804f-122">Principal</span><span class="sxs-lookup"><span data-stu-id="5804f-122">Primary</span></span>
    - <span data-ttu-id="5804f-123">`x.m`: Acceso a miembros</span><span class="sxs-lookup"><span data-stu-id="5804f-123">`x.m`: Member access</span></span>
    - <span data-ttu-id="5804f-124">`x(...)`: Invocación de método y delegado</span><span class="sxs-lookup"><span data-stu-id="5804f-124">`x(...)`: Method and delegate invocation</span></span>
    - <span data-ttu-id="5804f-125">`x[...]`: Acceso a matriz e indizador</span><span class="sxs-lookup"><span data-stu-id="5804f-125">`x[...]`: Array and indexer access</span></span>
    - <span data-ttu-id="5804f-126">`x++`: Postincremento</span><span class="sxs-lookup"><span data-stu-id="5804f-126">`x++`: Post-increment</span></span>
    - <span data-ttu-id="5804f-127">`x--`: Postdecremento</span><span class="sxs-lookup"><span data-stu-id="5804f-127">`x--`: Post-decrement</span></span>
    - <span data-ttu-id="5804f-128">`new T(...)`: Creación de objetos y delegados</span><span class="sxs-lookup"><span data-stu-id="5804f-128">`new T(...)`: Object and delegate creation</span></span>
    - <span data-ttu-id="5804f-129">`new T(...){...}`: creación de objetos con inicializador</span><span class="sxs-lookup"><span data-stu-id="5804f-129">`new T(...){...}`: Object creation with initializer</span></span>
    - <span data-ttu-id="5804f-130">`new {...}`:  inicializador de objetos anónimos</span><span class="sxs-lookup"><span data-stu-id="5804f-130">`new {...}`:  Anonymous object initializer</span></span>
    - <span data-ttu-id="5804f-131">`new T[...]`: creación de matriz</span><span class="sxs-lookup"><span data-stu-id="5804f-131">`new T[...]`: Array creation</span></span>
    - <span data-ttu-id="5804f-132">`typeof(T)`: obtener el objeto <xref:System.Type> para `T`</span><span class="sxs-lookup"><span data-stu-id="5804f-132">`typeof(T)`: Obtain <xref:System.Type> object for `T`</span></span>
    - <span data-ttu-id="5804f-133">`checked(x)`: Evaluar expresión en contexto comprobado</span><span class="sxs-lookup"><span data-stu-id="5804f-133">`checked(x)`: Evaluate expression in checked context</span></span>
    - <span data-ttu-id="5804f-134">`unchecked(x)`: Evaluar expresión en contexto no comprobado</span><span class="sxs-lookup"><span data-stu-id="5804f-134">`unchecked(x)`: Evaluate expression in unchecked context</span></span>
    - <span data-ttu-id="5804f-135">`default(T)`: obtener valor predeterminado de tipo `T`</span><span class="sxs-lookup"><span data-stu-id="5804f-135">`default(T)`: Obtain default value of type `T`</span></span>
    - <span data-ttu-id="5804f-136">`delegate {...}`: Función anónima (método anónimo)</span><span class="sxs-lookup"><span data-stu-id="5804f-136">`delegate {...}`: Anonymous function (anonymous method)</span></span>
* <span data-ttu-id="5804f-137">Unario</span><span class="sxs-lookup"><span data-stu-id="5804f-137">Unary</span></span>
    - <span data-ttu-id="5804f-138">`+x`: identidad</span><span class="sxs-lookup"><span data-stu-id="5804f-138">`+x`: Identity</span></span>
    - <span data-ttu-id="5804f-139">`-x`: Negación</span><span class="sxs-lookup"><span data-stu-id="5804f-139">`-x`: Negation</span></span>
    - <span data-ttu-id="5804f-140">`!x`: Negación lógica</span><span class="sxs-lookup"><span data-stu-id="5804f-140">`!x`: Logical negation</span></span>
    - <span data-ttu-id="5804f-141">`~x`: Negación bit a bit</span><span class="sxs-lookup"><span data-stu-id="5804f-141">`~x`: Bitwise negation</span></span>
    - <span data-ttu-id="5804f-142">`++x`: Preincremento</span><span class="sxs-lookup"><span data-stu-id="5804f-142">`++x`: Pre-increment</span></span>
    - <span data-ttu-id="5804f-143">`--x`: Predecremento</span><span class="sxs-lookup"><span data-stu-id="5804f-143">`--x`: Pre-decrement</span></span>
    - <span data-ttu-id="5804f-144">`(T)x`: convertir explícitamente `x` en el tipo `T`</span><span class="sxs-lookup"><span data-stu-id="5804f-144">`(T)x`: Explicitly convert `x` to type `T`</span></span>
    - <span data-ttu-id="5804f-145">`await x`: esperar asincrónicamente a que finalice `x`</span><span class="sxs-lookup"><span data-stu-id="5804f-145">`await x`: Asynchronously wait for `x` to complete</span></span>
* <span data-ttu-id="5804f-146">Multiplicativo</span><span class="sxs-lookup"><span data-stu-id="5804f-146">Multiplicative</span></span>
    - <span data-ttu-id="5804f-147">`x * y`: Multiplicación</span><span class="sxs-lookup"><span data-stu-id="5804f-147">`x * y`: Multiplication</span></span>
    - <span data-ttu-id="5804f-148">`x / y`: División</span><span class="sxs-lookup"><span data-stu-id="5804f-148">`x / y`: Division</span></span>
    - <span data-ttu-id="5804f-149">`x % y`: Resto</span><span class="sxs-lookup"><span data-stu-id="5804f-149">`x % y`: Remainder</span></span>
* <span data-ttu-id="5804f-150">Aditivo</span><span class="sxs-lookup"><span data-stu-id="5804f-150">Additive</span></span>
    - <span data-ttu-id="5804f-151">`x + y`: Suma, concatenación de cadenas, combinación de delegados</span><span class="sxs-lookup"><span data-stu-id="5804f-151">`x + y`: Addition, string concatenation, delegate combination</span></span>
    - <span data-ttu-id="5804f-152">`x – y`: Resta, eliminación de delegados</span><span class="sxs-lookup"><span data-stu-id="5804f-152">`x – y`: Subtraction, delegate removal</span></span>
* <span data-ttu-id="5804f-153">Shift</span><span class="sxs-lookup"><span data-stu-id="5804f-153">Shift</span></span>
    - <span data-ttu-id="5804f-154">`x << y`: Desplazamiento a la izquierda</span><span class="sxs-lookup"><span data-stu-id="5804f-154">`x << y`: Shift left</span></span>
    - <span data-ttu-id="5804f-155">`x >> y`: Desplazamiento a la derecha</span><span class="sxs-lookup"><span data-stu-id="5804f-155">`x >> y`: Shift right</span></span>
* <span data-ttu-id="5804f-156">Comprobación de tipos y relacional</span><span class="sxs-lookup"><span data-stu-id="5804f-156">Relational and type testing</span></span>
    - <span data-ttu-id="5804f-157">`x < y`: Menor que</span><span class="sxs-lookup"><span data-stu-id="5804f-157">`x < y`: Less than</span></span>
    - <span data-ttu-id="5804f-158">`x > y`: Mayor que</span><span class="sxs-lookup"><span data-stu-id="5804f-158">`x > y`: Greater than</span></span>
    - <span data-ttu-id="5804f-159">`x <= y`: Menor o igual que</span><span class="sxs-lookup"><span data-stu-id="5804f-159">`x <= y`: Less than or equal</span></span>
    - <span data-ttu-id="5804f-160">`x >= y`: Mayor o igual que</span><span class="sxs-lookup"><span data-stu-id="5804f-160">`x >= y`: Greater than or equal</span></span>
    - <span data-ttu-id="5804f-161">`x is T`: volver a ejecutar `true` si `x` es una `T`, de lo contrario `false`</span><span class="sxs-lookup"><span data-stu-id="5804f-161">`x is T`: Return `true` if `x` is a `T`, `false` otherwise</span></span>
    - <span data-ttu-id="5804f-162">`x as T`: volver a ejecutar `x` con tipo `T`, o `null` si `x` no es una `T`</span><span class="sxs-lookup"><span data-stu-id="5804f-162">`x as T`: Return `x` typed as `T`, or `null` if `x` is not a `T`</span></span>
* <span data-ttu-id="5804f-163">Igualdad</span><span class="sxs-lookup"><span data-stu-id="5804f-163">Equality</span></span>
    - <span data-ttu-id="5804f-164">`x == y`: Igual</span><span class="sxs-lookup"><span data-stu-id="5804f-164">`x == y`: Equal</span></span>
    - <span data-ttu-id="5804f-165">`x != y`: No igual</span><span class="sxs-lookup"><span data-stu-id="5804f-165">`x != y`: Not equal</span></span>
* <span data-ttu-id="5804f-166">AND lógico</span><span class="sxs-lookup"><span data-stu-id="5804f-166">Logical AND</span></span>
    - <span data-ttu-id="5804f-167">`x & y`: AND bit a bit entero, AND lógico booleano</span><span class="sxs-lookup"><span data-stu-id="5804f-167">`x & y`: Integer bitwise AND, boolean logical AND</span></span>
* <span data-ttu-id="5804f-168">XOR lógico</span><span class="sxs-lookup"><span data-stu-id="5804f-168">Logical XOR</span></span>
    - <span data-ttu-id="5804f-169">`x ^ y`: XOR bit a bit entero, XOR lógico booleano</span><span class="sxs-lookup"><span data-stu-id="5804f-169">`x ^ y`: Integer bitwise XOR, boolean logical XOR</span></span>
* <span data-ttu-id="5804f-170">OR lógico</span><span class="sxs-lookup"><span data-stu-id="5804f-170">Logical OR</span></span>
    - <span data-ttu-id="5804f-171">`x | y`: OR bit a bit entero, OR lógico booleano</span><span class="sxs-lookup"><span data-stu-id="5804f-171">`x | y`: Integer bitwise OR, boolean logical OR</span></span>
* <span data-ttu-id="5804f-172">AND condicional</span><span class="sxs-lookup"><span data-stu-id="5804f-172">Conditional AND</span></span>
    - <span data-ttu-id="5804f-173">`x && y`: evalúa `y` solo si `x` no es `false`</span><span class="sxs-lookup"><span data-stu-id="5804f-173">`x && y`: Evaluates `y` only if `x` is not `false`</span></span>
* <span data-ttu-id="5804f-174">OR condicional</span><span class="sxs-lookup"><span data-stu-id="5804f-174">Conditional OR</span></span>
    - <span data-ttu-id="5804f-175">`x || y`: evalúa `y` solo si `x` no es `true`</span><span class="sxs-lookup"><span data-stu-id="5804f-175">`x || y`: Evaluates `y` only if `x` is not `true`</span></span>
* <span data-ttu-id="5804f-176">Uso combinado de NULL</span><span class="sxs-lookup"><span data-stu-id="5804f-176">Null coalescing</span></span>
    - <span data-ttu-id="5804f-177">`x ?? y`: se evalúa como `y` si `x` es NULL, de lo contrario, como `x`</span><span class="sxs-lookup"><span data-stu-id="5804f-177">`x ?? y`: Evaluates to `y` if `x` is null, to `x` otherwise</span></span>
* <span data-ttu-id="5804f-178">Condicional</span><span class="sxs-lookup"><span data-stu-id="5804f-178">Conditional</span></span>
    - <span data-ttu-id="5804f-179">`x ? y : z`: se evalúa como `y` si `x` es `true` o `z` si `x` es `false`</span><span class="sxs-lookup"><span data-stu-id="5804f-179">`x ? y : z`: Evaluates `y` if `x` is `true`, `z` if `x` is `false`</span></span>
* <span data-ttu-id="5804f-180">Asignación o función anónima</span><span class="sxs-lookup"><span data-stu-id="5804f-180">Assignment or anonymous function</span></span>
    - <span data-ttu-id="5804f-181">`x = y`: Asignación</span><span class="sxs-lookup"><span data-stu-id="5804f-181">`x = y`: Assignment</span></span>
    - <span data-ttu-id="5804f-182">`x op= y`: asignación compuesta; los operadores admitidos son</span><span class="sxs-lookup"><span data-stu-id="5804f-182">`x op= y`: Compound assignment; supported operators are</span></span>
        - <span data-ttu-id="5804f-183">`*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`</span><span class="sxs-lookup"><span data-stu-id="5804f-183">`*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`</span></span>
    - <span data-ttu-id="5804f-184">`(T x) => y`: Función anónima (expresión lambda)</span><span class="sxs-lookup"><span data-stu-id="5804f-184">`(T x) => y`: Anonymous function (lambda expression)</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="5804f-185">[Anterior](types-and-variables.md)
> [Siguiente](statements.md)</span><span class="sxs-lookup"><span data-stu-id="5804f-185">[Previous](types-and-variables.md)
[Next](statements.md)</span></span>

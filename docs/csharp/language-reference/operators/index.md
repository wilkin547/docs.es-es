---
title: 'Operadores de C#: referencia de C#'
ms.date: 04/30/2019
f1_keywords:
- cs.operators
helpviewer_keywords:
- boolean operators [C#]
- expressions [C#], operators
- logical operators [C#]
- operators [C#]
- Visual C#, operators
- indirection operators [C#]
- assignment operators [C#]
- shift operators [C#]
- relational operators [C#]
- bitwise operators [C#]
- address operators [C#]
- keywords [C#], operators
- arithmetic operators [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
ms.openlocfilehash: 13ad16ab768cdaee96cab29811e2ed058dee977a
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512237"
---
# <a name="c-operators-c-reference"></a><span data-ttu-id="2690a-102">Operadores de C# (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="2690a-102">C# operators (C# reference)</span></span>

<span data-ttu-id="2690a-103">C# proporciona una serie de operadores predefinidos compatibles con los tipos integrados.</span><span class="sxs-lookup"><span data-stu-id="2690a-103">C# provides a number of predefined operators supported by the built-in types.</span></span> <span data-ttu-id="2690a-104">Por ejemplo, los [operadores aritméticos](arithmetic-operators.md) realizan operaciones aritméticas con operandos de tipos numéricos integrados, y los [operadores lógicos booleanos](boolean-logical-operators.md) realizan operaciones lógicas con los operandos [bool](../keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="2690a-104">For example, [arithmetic operators](arithmetic-operators.md) perform arithmetic operations with operands of built-in numeric types and [Boolean logical operators](boolean-logical-operators.md) perform logical operations with the [bool](../keywords/bool.md) operands.</span></span>

<span data-ttu-id="2690a-105">Un tipo definido por el usuario puede sobrecargar determinados operadores para definir el comportamiento correspondiente para los operandos de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="2690a-105">A user-defined type can overload certain operators to define the corresponding behavior for the operands of that type.</span></span> <span data-ttu-id="2690a-106">Para obtener más información, vea [Sobrecarga de operadores](operator-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="2690a-106">For more information, see [Operator overloading](operator-overloading.md).</span></span>

<span data-ttu-id="2690a-107">En las secciones siguientes se enumeran los operadores de C# desde la precedencia más alta a la más baja.</span><span class="sxs-lookup"><span data-stu-id="2690a-107">The following sections list the C# operators starting with the highest precedence to the lowest.</span></span> <span data-ttu-id="2690a-108">Los operadores de cada sección comparten el mismo nivel de precedencia.</span><span class="sxs-lookup"><span data-stu-id="2690a-108">The operators within each section share the same precedence level.</span></span>

## <a name="primary-operators"></a><span data-ttu-id="2690a-109">Operadores principales</span><span class="sxs-lookup"><span data-stu-id="2690a-109">Primary operators</span></span>

<span data-ttu-id="2690a-110">Estos son los operadores de precedencia más alta.</span><span class="sxs-lookup"><span data-stu-id="2690a-110">These are the highest precedence operators.</span></span>

<span data-ttu-id="2690a-111">[x.y](member-access-operators.md#member-access-operator-): acceso a miembros.</span><span class="sxs-lookup"><span data-stu-id="2690a-111">[x.y](member-access-operators.md#member-access-operator-) – member access.</span></span>

<span data-ttu-id="2690a-112">[x?.y](member-access-operators.md#null-conditional-operators--and-): acceso a miembros condicionales nulos.</span><span class="sxs-lookup"><span data-stu-id="2690a-112">[x?.y](member-access-operators.md#null-conditional-operators--and-) – null conditional member access.</span></span> <span data-ttu-id="2690a-113">Devuelve `null` si el operando izquierdo se evalúa como `null`.</span><span class="sxs-lookup"><span data-stu-id="2690a-113">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="2690a-114">[x?[y]](member-access-operators.md#null-conditional-operators--and-): elemento de matriz condicional NULL o acceso al indizador de tipos.</span><span class="sxs-lookup"><span data-stu-id="2690a-114">[x?[y]](member-access-operators.md#null-conditional-operators--and-) - null conditional array element or type indexer access.</span></span> <span data-ttu-id="2690a-115">Devuelve `null` si el operando izquierdo se evalúa como `null`.</span><span class="sxs-lookup"><span data-stu-id="2690a-115">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="2690a-116">[f(x)](member-access-operators.md#invocation-operator-): llamada de método o invocación de delegado.</span><span class="sxs-lookup"><span data-stu-id="2690a-116">[f(x)](member-access-operators.md#invocation-operator-) – method call or delegate invocation.</span></span>

<span data-ttu-id="2690a-117">[a&#91;x&#93;](member-access-operators.md#indexer-operator-): elemento de matriz o acceso al indizador de tipos.</span><span class="sxs-lookup"><span data-stu-id="2690a-117">[a&#91;x&#93;](member-access-operators.md#indexer-operator-) – array element or type indexer access.</span></span>

<span data-ttu-id="2690a-118">[x++](arithmetic-operators.md#increment-operator-): incremento de postfijo.</span><span class="sxs-lookup"><span data-stu-id="2690a-118">[x++](arithmetic-operators.md#increment-operator-) – postfix increment.</span></span> <span data-ttu-id="2690a-119">Devuelve el valor de x y, a continuación, actualiza la ubicación de almacenamiento con el valor de x que es uno mayor (normalmente agrega el entero 1).</span><span class="sxs-lookup"><span data-stu-id="2690a-119">Returns the value of x and then updates the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="2690a-120">[x--](arithmetic-operators.md#decrement-operator---): decremento de postfijo.</span><span class="sxs-lookup"><span data-stu-id="2690a-120">[x--](arithmetic-operators.md#decrement-operator---) –  postfix decrement.</span></span> <span data-ttu-id="2690a-121">Devuelve el valor de x; a continuación, actualiza la ubicación de almacenamiento con el valor de x que es uno menos (normalmente resta el entero 1).</span><span class="sxs-lookup"><span data-stu-id="2690a-121">Returns the value of x and then updates the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="2690a-122">[new](new-operator.md): creación de instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="2690a-122">[new](new-operator.md) – type instantiation.</span></span>

<span data-ttu-id="2690a-123">[typeof](type-testing-and-conversion-operators.md#typeof-operator): devuelve el objeto <xref:System.Type> que representa el operando.</span><span class="sxs-lookup"><span data-stu-id="2690a-123">[typeof](type-testing-and-conversion-operators.md#typeof-operator) – returns the <xref:System.Type> object representing the operand.</span></span>

<span data-ttu-id="2690a-124">[checked](../keywords/checked.md): habilita la comprobación de desbordamiento para operaciones con enteros.</span><span class="sxs-lookup"><span data-stu-id="2690a-124">[checked](../keywords/checked.md) – enables overflow checking for integer operations.</span></span>

<span data-ttu-id="2690a-125">[unchecked](../keywords/unchecked.md): deshabilita la comprobación de desbordamiento para operaciones con enteros.</span><span class="sxs-lookup"><span data-stu-id="2690a-125">[unchecked](../keywords/unchecked.md) – disables overflow checking for integer operations.</span></span> <span data-ttu-id="2690a-126">Este es el comportamiento predeterminado del compilador.</span><span class="sxs-lookup"><span data-stu-id="2690a-126">This is the default compiler behavior.</span></span>

<span data-ttu-id="2690a-127">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) genera el valor predeterminado del tipo T.</span><span class="sxs-lookup"><span data-stu-id="2690a-127">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) – produces the default value of type T.</span></span>

<span data-ttu-id="2690a-128">[nameof](nameof.md): obtiene el nombre simple (incompleto) de una variable, tipo o miembro como una cadena constante.</span><span class="sxs-lookup"><span data-stu-id="2690a-128">[nameof](nameof.md) - obtains the simple (unqualified) name of a variable, type, or member as a constant string.</span></span>

<span data-ttu-id="2690a-129">[delegate](delegate-operator.md): declara y devuelve una instancia de delegado.</span><span class="sxs-lookup"><span data-stu-id="2690a-129">[delegate](delegate-operator.md) – declares and returns a delegate instance.</span></span>

<span data-ttu-id="2690a-130">[sizeof](sizeof.md): devuelve el tamaño en bytes del operando de tipo.</span><span class="sxs-lookup"><span data-stu-id="2690a-130">[sizeof](sizeof.md) – returns the size in bytes of the type operand.</span></span>

<span data-ttu-id="2690a-131">[stackalloc](stackalloc.md): asigna un bloque de memoria en la pila.</span><span class="sxs-lookup"><span data-stu-id="2690a-131">[stackalloc](stackalloc.md) - allocates a block of memory on the stack.</span></span>

<span data-ttu-id="2690a-132">[->](pointer-related-operators.md#pointer-member-access-operator--): direccionamiento indirecto del puntero combinado con acceso a miembros.</span><span class="sxs-lookup"><span data-stu-id="2690a-132">[->](pointer-related-operators.md#pointer-member-access-operator--) – pointer indirection combined with member access.</span></span>

## <a name="unary-operators"></a><span data-ttu-id="2690a-133">Operadores unarios</span><span class="sxs-lookup"><span data-stu-id="2690a-133">Unary operators</span></span>

<span data-ttu-id="2690a-134">Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="2690a-134">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="2690a-135">[+x](addition-operator.md): devuelve el valor de x.</span><span class="sxs-lookup"><span data-stu-id="2690a-135">[+x](addition-operator.md) – returns the value of x.</span></span>

<span data-ttu-id="2690a-136">[-x](subtraction-operator.md): negación numérica.</span><span class="sxs-lookup"><span data-stu-id="2690a-136">[-x](subtraction-operator.md) – numeric negation.</span></span>

<span data-ttu-id="2690a-137">[\!x](boolean-logical-operators.md#logical-negation-operator-): negación lógica.</span><span class="sxs-lookup"><span data-stu-id="2690a-137">[\!x](boolean-logical-operators.md#logical-negation-operator-) – logical negation.</span></span>

<span data-ttu-id="2690a-138">[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-): complemento bit a bit.</span><span class="sxs-lookup"><span data-stu-id="2690a-138">[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-) – bitwise complement.</span></span>

<span data-ttu-id="2690a-139">[++x](arithmetic-operators.md#increment-operator-): incremento de prefijo.</span><span class="sxs-lookup"><span data-stu-id="2690a-139">[++x](arithmetic-operators.md#increment-operator-) – prefix increment.</span></span> <span data-ttu-id="2690a-140">Devuelve el valor de x después de actualizar la ubicación de almacenamiento con el valor de x que es uno mayor (normalmente agrega el entero 1).</span><span class="sxs-lookup"><span data-stu-id="2690a-140">Returns the value of x after updating the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="2690a-141">[--x](arithmetic-operators.md#decrement-operator---): decremento de prefijo.</span><span class="sxs-lookup"><span data-stu-id="2690a-141">[--x](arithmetic-operators.md#decrement-operator---) – prefix decrement.</span></span> <span data-ttu-id="2690a-142">Devuelve el valor de x después de actualizar la ubicación de almacenamiento con el valor de x que es uno menos (normalmente resta el entero 1).</span><span class="sxs-lookup"><span data-stu-id="2690a-142">Returns the value of x after updating the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="2690a-143">[(T)x](type-testing-and-conversion-operators.md#cast-operator-): conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="2690a-143">[(T)x](type-testing-and-conversion-operators.md#cast-operator-) – type casting.</span></span>

<span data-ttu-id="2690a-144">[await](../keywords/await.md): espera una `Task`.</span><span class="sxs-lookup"><span data-stu-id="2690a-144">[await](../keywords/await.md) – awaits a `Task`.</span></span>

<span data-ttu-id="2690a-145">[&x](pointer-related-operators.md#address-of-operator-): dirección de una variable.</span><span class="sxs-lookup"><span data-stu-id="2690a-145">[&x](pointer-related-operators.md#address-of-operator-) – address of a variable.</span></span>

<span data-ttu-id="2690a-146">[\*x](pointer-related-operators.md#pointer-indirection-operator-): direccionamiento indirecto del puntero o desreferenciación.</span><span class="sxs-lookup"><span data-stu-id="2690a-146">[\*x](pointer-related-operators.md#pointer-indirection-operator-) – pointer indirection, or dereference.</span></span>

<span data-ttu-id="2690a-147">El [operador true](true-false-operators.md) devuelve el valor [bool](../keywords/bool.md) `true` para indicar que un operando es definitivamente true.</span><span class="sxs-lookup"><span data-stu-id="2690a-147">[true operator](true-false-operators.md) - returns the [bool](../keywords/bool.md) value `true` to indicate that an operand is definitely true.</span></span>

<span data-ttu-id="2690a-148">El [operador false](true-false-operators.md) devuelve el valor [bool](../keywords/bool.md) `true` para indicar que un operado es definitivamente "false".</span><span class="sxs-lookup"><span data-stu-id="2690a-148">[false operator](true-false-operators.md) - returns the [bool](../keywords/bool.md) value `true` to indicate that an operand is definitely false.</span></span>

## <a name="multiplicative-operators"></a><span data-ttu-id="2690a-149">Operadores de multiplicación</span><span class="sxs-lookup"><span data-stu-id="2690a-149">Multiplicative operators</span></span>

<span data-ttu-id="2690a-150">Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="2690a-150">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="2690a-151">[x \* y](arithmetic-operators.md#multiplication-operator-): multiplicación.</span><span class="sxs-lookup"><span data-stu-id="2690a-151">[x \* y](arithmetic-operators.md#multiplication-operator-) – multiplication.</span></span>

<span data-ttu-id="2690a-152">[x / y](arithmetic-operators.md#division-operator-): división.</span><span class="sxs-lookup"><span data-stu-id="2690a-152">[x / y](arithmetic-operators.md#division-operator-) – division.</span></span> <span data-ttu-id="2690a-153">Si los operandos son enteros, el resultado es un entero que se trunca hacia cero (por ejemplo, `-7 / 2 is -3`).</span><span class="sxs-lookup"><span data-stu-id="2690a-153">If the operands are integers, the result is an integer truncated toward zero (for example, `-7 / 2 is -3`).</span></span>

<span data-ttu-id="2690a-154">[x % y](arithmetic-operators.md#remainder-operator-): resto.</span><span class="sxs-lookup"><span data-stu-id="2690a-154">[x % y](arithmetic-operators.md#remainder-operator-) – remainder.</span></span> <span data-ttu-id="2690a-155">Si los operandos son enteros, devuelve el resto de dividir x entre y.</span><span class="sxs-lookup"><span data-stu-id="2690a-155">If the operands are integers, this returns the remainder of dividing x by y.</span></span>  <span data-ttu-id="2690a-156">Si `q = x / y` y `r = x % y`, entonces `x = q * y + r`.</span><span class="sxs-lookup"><span data-stu-id="2690a-156">If `q = x / y` and `r = x % y`, then `x = q * y + r`.</span></span>

## <a name="additive-operators"></a><span data-ttu-id="2690a-157">Operadores aditivos</span><span class="sxs-lookup"><span data-stu-id="2690a-157">Additive operators</span></span>

<span data-ttu-id="2690a-158">Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="2690a-158">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="2690a-159">[x + y](arithmetic-operators.md#addition-operator-): suma.</span><span class="sxs-lookup"><span data-stu-id="2690a-159">[x + y](arithmetic-operators.md#addition-operator-) – addition.</span></span>

<span data-ttu-id="2690a-160">[x – y](arithmetic-operators.md#subtraction-operator--): resta.</span><span class="sxs-lookup"><span data-stu-id="2690a-160">[x – y](arithmetic-operators.md#subtraction-operator--) – subtraction.</span></span>

## <a name="shift-operators"></a><span data-ttu-id="2690a-161">Operadores de desplazamiento</span><span class="sxs-lookup"><span data-stu-id="2690a-161">Shift operators</span></span>

<span data-ttu-id="2690a-162">Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="2690a-162">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="2690a-163">[x <\<  y](bitwise-and-shift-operators.md#left-shift-operator-): desplaza los bits a la izquierda y rellena con cero a la derecha.</span><span class="sxs-lookup"><span data-stu-id="2690a-163">[x <\<  y](bitwise-and-shift-operators.md#left-shift-operator-) – shift bits left and fill with zero on the right.</span></span>

<span data-ttu-id="2690a-164">[x >> y](bitwise-and-shift-operators.md#right-shift-operator-): desplaza los bits a la derecha.</span><span class="sxs-lookup"><span data-stu-id="2690a-164">[x >> y](bitwise-and-shift-operators.md#right-shift-operator-) – shift bits right.</span></span> <span data-ttu-id="2690a-165">Si el operando izquierdo es `int` o `long`, los bits de la izquierda se rellenan con el bit de signo.</span><span class="sxs-lookup"><span data-stu-id="2690a-165">If the left operand is `int` or `long`, then left bits are filled with the sign bit.</span></span> <span data-ttu-id="2690a-166">Si el operando izquierdo es `uint` o `ulong`, los bits de la izquierda se rellenan con cero.</span><span class="sxs-lookup"><span data-stu-id="2690a-166">If the left operand is `uint` or `ulong`, then left bits are filled with zero.</span></span>

## <a name="relational-and-type-testing-operators"></a><span data-ttu-id="2690a-167">Operadores de comprobación de tipos y relacionales</span><span class="sxs-lookup"><span data-stu-id="2690a-167">Relational and type-testing operators</span></span>

<span data-ttu-id="2690a-168">Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="2690a-168">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="2690a-169">[x \< y](comparison-operators.md#less-than-operator-): menor que (true si x es menor que y).</span><span class="sxs-lookup"><span data-stu-id="2690a-169">[x \< y](comparison-operators.md#less-than-operator-) – less than (true if x is less than y).</span></span>

<span data-ttu-id="2690a-170">[x > y](comparison-operators.md#greater-than-operator-): mayor que (true si x es mayor que y).</span><span class="sxs-lookup"><span data-stu-id="2690a-170">[x > y](comparison-operators.md#greater-than-operator-) – greater than (true if x is greater than y).</span></span>

<span data-ttu-id="2690a-171">[x \<= y](comparison-operators.md#less-than-or-equal-operator-): menor o igual que.</span><span class="sxs-lookup"><span data-stu-id="2690a-171">[x \<= y](comparison-operators.md#less-than-or-equal-operator-) – less than or equal to.</span></span>

<span data-ttu-id="2690a-172">[x >= y](comparison-operators.md#greater-than-or-equal-operator-): mayor o igual que.</span><span class="sxs-lookup"><span data-stu-id="2690a-172">[x >= y](comparison-operators.md#greater-than-or-equal-operator-) – greater than or equal to.</span></span>

<span data-ttu-id="2690a-173">[is](type-testing-and-conversion-operators.md#is-operator): compatibilidad de tipos.</span><span class="sxs-lookup"><span data-stu-id="2690a-173">[is](type-testing-and-conversion-operators.md#is-operator) – type compatibility.</span></span> <span data-ttu-id="2690a-174">Devuelve `true` si el operando izquierdo evaluado se puede convertir al tipo especificado en el operando derecho.</span><span class="sxs-lookup"><span data-stu-id="2690a-174">Returns `true` if the evaluated left operand can be cast to the type specified by the right operand.</span></span>

<span data-ttu-id="2690a-175">[as](type-testing-and-conversion-operators.md#as-operator): conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="2690a-175">[as](type-testing-and-conversion-operators.md#as-operator) – type conversion.</span></span> <span data-ttu-id="2690a-176">Devuelve el operando izquierdo convertido al tipo especificado por el operando derecho, pero `as` devuelve `null` donde `(T)x` iniciaría una excepción.</span><span class="sxs-lookup"><span data-stu-id="2690a-176">Returns the left operand cast to the type specified by the right operand, but `as` returns `null` where `(T)x` would throw an exception.</span></span>

## <a name="equality-operators"></a><span data-ttu-id="2690a-177">Operadores de igualdad</span><span class="sxs-lookup"><span data-stu-id="2690a-177">Equality operators</span></span>

<span data-ttu-id="2690a-178">Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="2690a-178">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="2690a-179">[x == y](equality-operators.md#equality-operator-): igualdad.</span><span class="sxs-lookup"><span data-stu-id="2690a-179">[x == y](equality-operators.md#equality-operator-) – equality.</span></span> <span data-ttu-id="2690a-180">De forma predeterminada, para los tipos de referencia distintos de `string`, devuelve igualdad de referencia (prueba de identidad).</span><span class="sxs-lookup"><span data-stu-id="2690a-180">By default, for reference types other than `string`, this returns reference equality (identity test).</span></span> <span data-ttu-id="2690a-181">Sin embargo, los tipos pueden sobrecargar `==`, por lo que si su intención es probar la identidad, es mejor usar el método `ReferenceEquals` en `object`.</span><span class="sxs-lookup"><span data-stu-id="2690a-181">However, types can overload `==`, so if your intent is to test identity, it is best to use the `ReferenceEquals` method on `object`.</span></span>

<span data-ttu-id="2690a-182">[x != y](equality-operators.md#inequality-operator-): distinto de.</span><span class="sxs-lookup"><span data-stu-id="2690a-182">[x != y](equality-operators.md#inequality-operator-) – not equal.</span></span> <span data-ttu-id="2690a-183">Vea el comentario de `==`.</span><span class="sxs-lookup"><span data-stu-id="2690a-183">See comment for `==`.</span></span> <span data-ttu-id="2690a-184">Si un tipo sobrecarga `==`, debe sobrecargar `!=`.</span><span class="sxs-lookup"><span data-stu-id="2690a-184">If a type overloads `==`, then it must overload `!=`.</span></span>

## <a name="logical-and-operator"></a><span data-ttu-id="2690a-185">AND lógico (operador)</span><span class="sxs-lookup"><span data-stu-id="2690a-185">Logical AND operator</span></span>

<span data-ttu-id="2690a-186">Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="2690a-186">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="2690a-187">`x & y` – [AND lógico](boolean-logical-operators.md#logical-and-operator-) para los operandos `bool` o [AND lógico bit a bit](bitwise-and-shift-operators.md#logical-and-operator-) para los operandos de los tipos integrales.</span><span class="sxs-lookup"><span data-stu-id="2690a-187">`x & y` – [logical AND](boolean-logical-operators.md#logical-and-operator-) for the `bool` operands or [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) for the operands of the integral types.</span></span>

## <a name="logical-xor-operator"></a><span data-ttu-id="2690a-188">Operador lógico XOR</span><span class="sxs-lookup"><span data-stu-id="2690a-188">Logical XOR operator</span></span>

<span data-ttu-id="2690a-189">Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="2690a-189">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="2690a-190">`x ^ y` – [XOR lógico](boolean-logical-operators.md#logical-exclusive-or-operator-) para los operandos `bool` o [XOR lógico bit a bit](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) para los operandos de los tipos integrales.</span><span class="sxs-lookup"><span data-stu-id="2690a-190">`x ^ y` – [logical XOR](boolean-logical-operators.md#logical-exclusive-or-operator-) for the `bool` operands or [bitwise logical XOR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) for the operands of the integral types.</span></span>

## <a name="logical-or-operator"></a><span data-ttu-id="2690a-191">Operador lógico OR (||)</span><span class="sxs-lookup"><span data-stu-id="2690a-191">Logical OR operator</span></span>

<span data-ttu-id="2690a-192">Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="2690a-192">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="2690a-193">`x | y` – [OR lógico](boolean-logical-operators.md#logical-or-operator-) para los operandos `bool` o [OR lógico bit a bit](bitwise-and-shift-operators.md#logical-or-operator-) para los operandos de los tipos integrales.</span><span class="sxs-lookup"><span data-stu-id="2690a-193">`x | y` – [logical OR](boolean-logical-operators.md#logical-or-operator-) for the `bool` operands or [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) for the operands of the integral types.</span></span>

## <a name="conditional-and-operator"></a><span data-ttu-id="2690a-194">Operador condicional AND</span><span class="sxs-lookup"><span data-stu-id="2690a-194">Conditional AND operator</span></span>

<span data-ttu-id="2690a-195">Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="2690a-195">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="2690a-196">[x && y](boolean-logical-operators.md#conditional-logical-and-operator-): AND lógico.</span><span class="sxs-lookup"><span data-stu-id="2690a-196">[x && y](boolean-logical-operators.md#conditional-logical-and-operator-) – logical AND.</span></span> <span data-ttu-id="2690a-197">Si `x` se evalúa como `false`, `y` no se evalúa.</span><span class="sxs-lookup"><span data-stu-id="2690a-197">If `x` evaluates to `false`, then `y` is not evaluated.</span></span>

## <a name="conditional-or-operator"></a><span data-ttu-id="2690a-198">Operador condicional OR</span><span class="sxs-lookup"><span data-stu-id="2690a-198">Conditional OR operator</span></span>

<span data-ttu-id="2690a-199">Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="2690a-199">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="2690a-200">[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-): OR lógico.</span><span class="sxs-lookup"><span data-stu-id="2690a-200">[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) – logical OR.</span></span> <span data-ttu-id="2690a-201">Si `x` se evalúa como `true`, `y` no se evalúa.</span><span class="sxs-lookup"><span data-stu-id="2690a-201">If `x` evaluates to `true`, then `y` is not evaluated.</span></span>

## <a name="null-coalescing-operator"></a><span data-ttu-id="2690a-202">Operador de uso combinado de null</span><span class="sxs-lookup"><span data-stu-id="2690a-202">Null-coalescing operator</span></span>

<span data-ttu-id="2690a-203">Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="2690a-203">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="2690a-204">[x ?? y](null-coalescing-operator.md): devuelve `x` si no es `null`; de lo contrario, devuelve `y`.</span><span class="sxs-lookup"><span data-stu-id="2690a-204">[x ?? y](null-coalescing-operator.md) – returns `x` if it is non-`null`; otherwise, returns `y`.</span></span>

## <a name="conditional-operator"></a><span data-ttu-id="2690a-205">Operador condicional</span><span class="sxs-lookup"><span data-stu-id="2690a-205">Conditional operator</span></span>

<span data-ttu-id="2690a-206">Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="2690a-206">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="2690a-207">[t ? x : y](conditional-operator.md): si la prueba `t` se evalúa como true, evalúa y devuelve `x`; en caso contrario, evalúa y devuelve `y`.</span><span class="sxs-lookup"><span data-stu-id="2690a-207">[t ? x : y](conditional-operator.md) – if test `t` evaluates to true, then evaluate and return `x`; otherwise, evaluate and return `y`.</span></span>

## <a name="assignment-and-lambda-operators"></a><span data-ttu-id="2690a-208">Operadores de asignación y lambda</span><span class="sxs-lookup"><span data-stu-id="2690a-208">Assignment and lambda operators</span></span>

<span data-ttu-id="2690a-209">Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="2690a-209">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="2690a-210">[x = y](assignment-operator.md): asignación.</span><span class="sxs-lookup"><span data-stu-id="2690a-210">[x = y](assignment-operator.md) – assignment.</span></span>

<span data-ttu-id="2690a-211">[x += y](arithmetic-operators.md#compound-assignment): incremento.</span><span class="sxs-lookup"><span data-stu-id="2690a-211">[x += y](arithmetic-operators.md#compound-assignment) – increment.</span></span> <span data-ttu-id="2690a-212">Agregue el valor de `y` al valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="2690a-212">Add the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="2690a-213">Si `x` designa un [evento](../keywords/event.md), `y` debe ser un método adecuado que C# agregue como un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="2690a-213">If `x` designates an [event](../keywords/event.md), then `y` must be an appropriate method that C# adds as an event handler.</span></span>

<span data-ttu-id="2690a-214">[x -= y](arithmetic-operators.md#compound-assignment): decremento.</span><span class="sxs-lookup"><span data-stu-id="2690a-214">[x -= y](arithmetic-operators.md#compound-assignment) – decrement.</span></span> <span data-ttu-id="2690a-215">Reste el valor de `y` del valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="2690a-215">Subtract the value of `y` from the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="2690a-216">Si `x` designa un [evento](../keywords/event.md), `y` debe ser un método adecuado que C# quite como un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="2690a-216">If `x` designates an [event](../keywords/event.md), then `y` must be an appropriate method that C# removes as an event handler.</span></span>

<span data-ttu-id="2690a-217">[x \*= y](arithmetic-operators.md#compound-assignment): asignación de multiplicación.</span><span class="sxs-lookup"><span data-stu-id="2690a-217">[x \*= y](arithmetic-operators.md#compound-assignment) – multiplication assignment.</span></span> <span data-ttu-id="2690a-218">Multiplique el valor de `y` por el valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="2690a-218">Multiply the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="2690a-219">[x /= y](arithmetic-operators.md#compound-assignment): asignación de división.</span><span class="sxs-lookup"><span data-stu-id="2690a-219">[x /= y](arithmetic-operators.md#compound-assignment) – division assignment.</span></span> <span data-ttu-id="2690a-220">Divida el valor de `x` por el valor de `y`, almacene el resultado en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="2690a-220">Divide the value of `x` by the value of `y`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="2690a-221">[x %= y](arithmetic-operators.md#compound-assignment): asignación del resto.</span><span class="sxs-lookup"><span data-stu-id="2690a-221">[x %= y](arithmetic-operators.md#compound-assignment) – remainder assignment.</span></span> <span data-ttu-id="2690a-222">Divida el valor de `x` por el valor de `y`, almacene el resto en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="2690a-222">Divide the value of `x` by the value of `y`, store the remainder in `x`, and return the new value.</span></span>

<span data-ttu-id="2690a-223">[x &= y](boolean-logical-operators.md#compound-assignment): asignación de AND.</span><span class="sxs-lookup"><span data-stu-id="2690a-223">[x &= y](boolean-logical-operators.md#compound-assignment) – AND assignment.</span></span> <span data-ttu-id="2690a-224">AND el valor de `y` con el valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="2690a-224">AND the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="2690a-225">[x &#124;= y](boolean-logical-operators.md#compound-assignment): asignación de OR.</span><span class="sxs-lookup"><span data-stu-id="2690a-225">[x &#124;= y](boolean-logical-operators.md#compound-assignment) – OR assignment.</span></span> <span data-ttu-id="2690a-226">OR el valor de `y` con el valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="2690a-226">OR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="2690a-227">[x ^= y](boolean-logical-operators.md#compound-assignment): asignación de XOR.</span><span class="sxs-lookup"><span data-stu-id="2690a-227">[x ^= y](boolean-logical-operators.md#compound-assignment) – XOR assignment.</span></span> <span data-ttu-id="2690a-228">XOR el valor de `y` con el valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="2690a-228">XOR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="2690a-229">[x <<= y](bitwise-and-shift-operators.md#compound-assignment): asignación de desplazamiento a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="2690a-229">[x <<= y](bitwise-and-shift-operators.md#compound-assignment) – left-shift assignment.</span></span> <span data-ttu-id="2690a-230">Desplace el valor de `x` a la izquierda `y` lugares, almacene el resultado en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="2690a-230">Shift the value of `x` left by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="2690a-231">[x >>= y](bitwise-and-shift-operators.md#compound-assignment): asignación de desplazamiento a la derecha.</span><span class="sxs-lookup"><span data-stu-id="2690a-231">[x >>= y](bitwise-and-shift-operators.md#compound-assignment) – right-shift assignment.</span></span> <span data-ttu-id="2690a-232">Desplace el valor de `x` a la derecha `y` posiciones, almacene el resultado en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="2690a-232">Shift the value of `x` right by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="2690a-233">[=>](lambda-operator.md): declaración lambda.</span><span class="sxs-lookup"><span data-stu-id="2690a-233">[=>](lambda-operator.md) – lambda declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="2690a-234">Vea también</span><span class="sxs-lookup"><span data-stu-id="2690a-234">See also</span></span>

- [<span data-ttu-id="2690a-235">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="2690a-235">C# reference</span></span>](../index.md)
- [<span data-ttu-id="2690a-236">Operadores</span><span class="sxs-lookup"><span data-stu-id="2690a-236">Operators</span></span>](../../programming-guide/statements-expressions-operators/operators.md)

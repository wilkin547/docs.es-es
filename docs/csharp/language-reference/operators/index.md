---
title: Operadores de C#
ms.date: 04/04/2018
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
ms.openlocfilehash: f4267caeb6301950b9f6a8b9545a47b9f48e7920
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61689819"
---
# <a name="c-operators"></a><span data-ttu-id="8ea1b-102">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="8ea1b-102">C# operators</span></span>

<span data-ttu-id="8ea1b-103">C# proporciona muchos operadores, que son símbolos que especifican las operaciones (matemáticas, indización, llamada de función, etc.) que se realizan en una expresión.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-103">C# provides many operators, which are symbols that specify which operations (math, indexing, function call, etc.) to perform in an expression.</span></span> <span data-ttu-id="8ea1b-104">Puede [sobrecargar](../../programming-guide/statements-expressions-operators/overloadable-operators.md) muchos operadores para cambiar su significado al aplicarlos a un tipo definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-104">You can [overload](../../programming-guide/statements-expressions-operators/overloadable-operators.md) many operators to change their meaning when applied to a user-defined type.</span></span>

<span data-ttu-id="8ea1b-105">Las operaciones de tipos enteros (como `==`, `!=`, `<`, `>`, `&` y `|`) suelen estar permitidas en los tipos de enumeración (`enum`).</span><span class="sxs-lookup"><span data-stu-id="8ea1b-105">Operations on integral types (such as `==`, `!=`, `<`, `>`, `&`, `|`) are generally allowed on enumeration (`enum`) types.</span></span>

<span data-ttu-id="8ea1b-106">En las secciones siguientes se enumeran los operadores de C# desde la precedencia más alta a la más baja.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-106">The sections below list the C# operators starting with the highest precedence to the lowest.</span></span> <span data-ttu-id="8ea1b-107">Los operadores de cada sección comparten el mismo nivel de precedencia.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-107">The operators within each section share the same precedence level.</span></span>

## <a name="primary-operators"></a><span data-ttu-id="8ea1b-108">Operadores principales</span><span class="sxs-lookup"><span data-stu-id="8ea1b-108">Primary operators</span></span>

<span data-ttu-id="8ea1b-109">Estos son los operadores de precedencia más alta.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-109">These are the highest precedence operators.</span></span>

<span data-ttu-id="8ea1b-110">[x.y](member-access-operator.md): acceso a miembros.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-110">[x.y](member-access-operator.md) – member access.</span></span>

<span data-ttu-id="8ea1b-111">[x?.y](null-conditional-operators.md): acceso a miembros condicionales nulos.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-111">[x?.y](null-conditional-operators.md) – null conditional member access.</span></span> <span data-ttu-id="8ea1b-112">Devuelve `null` si el operando izquierdo se evalúa como `null`.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-112">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="8ea1b-113">[x?[y]](null-conditional-operators.md): acceso a índices condicionales nulos.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-113">[x?[y]](null-conditional-operators.md) - null conditional index access.</span></span> <span data-ttu-id="8ea1b-114">Devuelve `null` si el operando izquierdo se evalúa como `null`.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-114">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="8ea1b-115">[f(x)](invocation-operator.md): invocación de función.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-115">[f(x)](invocation-operator.md) – function invocation.</span></span>

<span data-ttu-id="8ea1b-116">[a&#91;x&#93;](index-operator.md): indización de objeto agregado.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-116">[a&#91;x&#93;](index-operator.md) – aggregate object indexing.</span></span>

<span data-ttu-id="8ea1b-117">[x++](arithmetic-operators.md#increment-operator-): incremento de postfijo.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-117">[x++](arithmetic-operators.md#increment-operator-) – postfix increment.</span></span> <span data-ttu-id="8ea1b-118">Devuelve el valor de x y, a continuación, actualiza la ubicación de almacenamiento con el valor de x que es uno mayor (normalmente agrega el entero 1).</span><span class="sxs-lookup"><span data-stu-id="8ea1b-118">Returns the value of x and then updates the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="8ea1b-119">[x--](arithmetic-operators.md#decrement-operator---): decremento de postfijo.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-119">[x--](arithmetic-operators.md#decrement-operator---) –  postfix decrement.</span></span> <span data-ttu-id="8ea1b-120">Devuelve el valor de x; a continuación, actualiza la ubicación de almacenamiento con el valor de x que es uno menos (normalmente resta el entero 1).</span><span class="sxs-lookup"><span data-stu-id="8ea1b-120">Returns the value of x and then updates the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="8ea1b-121">[new](../keywords/new-operator.md): creación de instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-121">[new](../keywords/new-operator.md) – type instantiation.</span></span>

<span data-ttu-id="8ea1b-122">[typeof](../keywords/typeof.md): devuelve el objeto <xref:System.Type> que representa el operando.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-122">[typeof](../keywords/typeof.md) – returns the <xref:System.Type> object representing the operand.</span></span>

<span data-ttu-id="8ea1b-123">[checked](../keywords/checked.md): habilita la comprobación de desbordamiento para operaciones con enteros.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-123">[checked](../keywords/checked.md) – enables overflow checking for integer operations.</span></span>

<span data-ttu-id="8ea1b-124">[unchecked](../keywords/unchecked.md): deshabilita la comprobación de desbordamiento para operaciones con enteros.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-124">[unchecked](../keywords/unchecked.md) – disables overflow checking for integer operations.</span></span> <span data-ttu-id="8ea1b-125">Este es el comportamiento predeterminado del compilador.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-125">This is the default compiler behavior.</span></span>

<span data-ttu-id="8ea1b-126">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) genera el valor predeterminado del tipo T.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-126">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) – produces the default value of type T.</span></span>

<span data-ttu-id="8ea1b-127">[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md): declara y devuelve una instancia de delegado.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-127">[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md) – declares and returns a delegate instance.</span></span>

<span data-ttu-id="8ea1b-128">[sizeof](../keywords/sizeof.md): devuelve el tamaño en bytes del operando de tipo.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-128">[sizeof](../keywords/sizeof.md) – returns the size in bytes of the type operand.</span></span>

<span data-ttu-id="8ea1b-129">[->](dereference-operator.md): desreferenciación del puntero combinada con acceso a miembros.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-129">[->](dereference-operator.md) – pointer dereferencing combined with member access.</span></span>

## <a name="unary-operators"></a><span data-ttu-id="8ea1b-130">Operadores unarios</span><span class="sxs-lookup"><span data-stu-id="8ea1b-130">Unary operators</span></span>

<span data-ttu-id="8ea1b-131">Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-131">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="8ea1b-132">[+x](addition-operator.md): devuelve el valor de x.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-132">[+x](addition-operator.md) – returns the value of x.</span></span>

<span data-ttu-id="8ea1b-133">[-x](subtraction-operator.md): negación numérica.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-133">[-x](subtraction-operator.md) – numeric negation.</span></span>

<span data-ttu-id="8ea1b-134">[\!x](boolean-logical-operators.md#logical-negation-operator-): negación lógica.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-134">[\!x](boolean-logical-operators.md#logical-negation-operator-) – logical negation.</span></span>

<span data-ttu-id="8ea1b-135">[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-): complemento bit a bit.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-135">[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-) – bitwise complement.</span></span>

<span data-ttu-id="8ea1b-136">[++x](arithmetic-operators.md#increment-operator-): incremento de prefijo.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-136">[++x](arithmetic-operators.md#increment-operator-) – prefix increment.</span></span> <span data-ttu-id="8ea1b-137">Devuelve el valor de x después de actualizar la ubicación de almacenamiento con el valor de x que es uno mayor (normalmente agrega el entero 1).</span><span class="sxs-lookup"><span data-stu-id="8ea1b-137">Returns the value of x after updating the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="8ea1b-138">[--x](arithmetic-operators.md#decrement-operator---): decremento de prefijo.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-138">[--x](arithmetic-operators.md#decrement-operator---) – prefix decrement.</span></span> <span data-ttu-id="8ea1b-139">Devuelve el valor de x después de actualizar la ubicación de almacenamiento con el valor de x que es uno menos (normalmente resta el entero 1).</span><span class="sxs-lookup"><span data-stu-id="8ea1b-139">Returns the value of x after updating the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="8ea1b-140">[(T)x](invocation-operator.md): conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-140">[(T)x](invocation-operator.md) – type casting.</span></span>

<span data-ttu-id="8ea1b-141">[await](../keywords/await.md): espera una `Task`.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-141">[await](../keywords/await.md) – awaits a `Task`.</span></span>

<span data-ttu-id="8ea1b-142">[&x](and-operator.md): dirección de.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-142">[&x](and-operator.md) – address of.</span></span>

<span data-ttu-id="8ea1b-143">[\*x](multiplication-operator.md): desreferenciación.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-143">[\*x](multiplication-operator.md) – dereferencing.</span></span>

<span data-ttu-id="8ea1b-144">El [operador true](../keywords/true-false-operators.md) devuelve el valor [bool](../keywords/bool.md) `true` para indicar que un operando es definitivamente true.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-144">[true operator](../keywords/true-false-operators.md) - returns the [bool](../keywords/bool.md) value `true` to indicate that an operand is definitely true.</span></span>

<span data-ttu-id="8ea1b-145">El [operador false](../keywords/true-false-operators.md) devuelve el valor [bool](../keywords/bool.md) `true` para indicar que un operado es definitivamente "false".</span><span class="sxs-lookup"><span data-stu-id="8ea1b-145">[false operator](../keywords/true-false-operators.md) - returns the [bool](../keywords/bool.md) value `true` to indicate that an operand is definitely false.</span></span>

## <a name="multiplicative-operators"></a><span data-ttu-id="8ea1b-146">Operadores de multiplicación</span><span class="sxs-lookup"><span data-stu-id="8ea1b-146">Multiplicative operators</span></span>

<span data-ttu-id="8ea1b-147">Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-147">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="8ea1b-148">[x \* y](arithmetic-operators.md#multiplication-operator-): multiplicación.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-148">[x \* y](arithmetic-operators.md#multiplication-operator-) – multiplication.</span></span>

<span data-ttu-id="8ea1b-149">[x / y](arithmetic-operators.md#division-operator-): división.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-149">[x / y](arithmetic-operators.md#division-operator-) – division.</span></span> <span data-ttu-id="8ea1b-150">Si los operandos son enteros, el resultado es un entero que se trunca hacia cero (por ejemplo, `-7 / 2 is -3`).</span><span class="sxs-lookup"><span data-stu-id="8ea1b-150">If the operands are integers, the result is an integer truncated toward zero (for example, `-7 / 2 is -3`).</span></span>

<span data-ttu-id="8ea1b-151">[x % y](arithmetic-operators.md#remainder-operator-): resto.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-151">[x % y](arithmetic-operators.md#remainder-operator-) – remainder.</span></span> <span data-ttu-id="8ea1b-152">Si los operandos son enteros, devuelve el resto de dividir x entre y.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-152">If the operands are integers, this returns the remainder of dividing x by y.</span></span>  <span data-ttu-id="8ea1b-153">Si `q = x / y` y `r = x % y`, entonces `x = q * y + r`.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-153">If `q = x / y` and `r = x % y`, then `x = q * y + r`.</span></span>

## <a name="additive-operators"></a><span data-ttu-id="8ea1b-154">Operadores aditivos</span><span class="sxs-lookup"><span data-stu-id="8ea1b-154">Additive operators</span></span>

<span data-ttu-id="8ea1b-155">Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-155">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="8ea1b-156">[x + y](arithmetic-operators.md#addition-operator-): suma.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-156">[x + y](arithmetic-operators.md#addition-operator-) – addition.</span></span>

<span data-ttu-id="8ea1b-157">[x – y](arithmetic-operators.md#subtraction-operator--): resta.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-157">[x – y](arithmetic-operators.md#subtraction-operator--) – subtraction.</span></span>

## <a name="shift-operators"></a><span data-ttu-id="8ea1b-158">Operadores de desplazamiento</span><span class="sxs-lookup"><span data-stu-id="8ea1b-158">Shift operators</span></span>

<span data-ttu-id="8ea1b-159">Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-159">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="8ea1b-160">[x <\<  y](bitwise-and-shift-operators.md#left-shift-operator-): desplaza los bits a la izquierda y rellena con cero a la derecha.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-160">[x <\<  y](bitwise-and-shift-operators.md#left-shift-operator-) – shift bits left and fill with zero on the right.</span></span>

<span data-ttu-id="8ea1b-161">[x >> y](bitwise-and-shift-operators.md#right-shift-operator-): desplaza los bits a la derecha.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-161">[x >> y](bitwise-and-shift-operators.md#right-shift-operator-) – shift bits right.</span></span> <span data-ttu-id="8ea1b-162">Si el operando izquierdo es `int` o `long`, los bits de la izquierda se rellenan con el bit de signo.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-162">If the left operand is `int` or `long`, then left bits are filled with the sign bit.</span></span> <span data-ttu-id="8ea1b-163">Si el operando izquierdo es `uint` o `ulong`, los bits de la izquierda se rellenan con cero.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-163">If the left operand is `uint` or `ulong`, then left bits are filled with zero.</span></span>

## <a name="relational-and-type-testing-operators"></a><span data-ttu-id="8ea1b-164">Operadores de comprobación de tipos y relacionales</span><span class="sxs-lookup"><span data-stu-id="8ea1b-164">Relational and type-testing operators</span></span>

<span data-ttu-id="8ea1b-165">Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-165">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="8ea1b-166">[x \< y](less-than-operator.md): menor que (true si x es menor que y).</span><span class="sxs-lookup"><span data-stu-id="8ea1b-166">[x \< y](less-than-operator.md) – less than (true if x is less than y).</span></span>

<span data-ttu-id="8ea1b-167">[x > y](greater-than-operator.md): mayor que (true si x es mayor que y).</span><span class="sxs-lookup"><span data-stu-id="8ea1b-167">[x > y](greater-than-operator.md) – greater than (true if x is greater than y).</span></span>

<span data-ttu-id="8ea1b-168">[x \<= y](less-than-equal-operator.md): menor o igual que.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-168">[x \<= y](less-than-equal-operator.md) – less than or equal to.</span></span>

<span data-ttu-id="8ea1b-169">[x >= y](greater-than-equal-operator.md): mayor o igual que.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-169">[x >= y](greater-than-equal-operator.md) – greater than or equal to.</span></span>

<span data-ttu-id="8ea1b-170">[is](../keywords/is.md): compatibilidad de tipos.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-170">[is](../keywords/is.md) – type compatibility.</span></span> <span data-ttu-id="8ea1b-171">Devuelve true si el operando izquierdo evaluado se puede convertir al tipo especificado en el operando derecho (un tipo estático).</span><span class="sxs-lookup"><span data-stu-id="8ea1b-171">Returns true if the evaluated left operand can be cast to the type specified in the right operand (a static type).</span></span>

<span data-ttu-id="8ea1b-172">[as](../keywords/as.md): conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-172">[as](../keywords/as.md) – type conversion.</span></span> <span data-ttu-id="8ea1b-173">Devuelve el operando izquierdo convertido al tipo especificado por el operando derecho (un tipo estático), pero `as` devuelve `null` donde `(T)x` produciría una excepción.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-173">Returns the left operand cast to the type specified by the right operand (a static type), but `as` returns `null` where `(T)x` would throw an exception.</span></span>

## <a name="equality-operators"></a><span data-ttu-id="8ea1b-174">Operadores de igualdad</span><span class="sxs-lookup"><span data-stu-id="8ea1b-174">Equality operators</span></span>

<span data-ttu-id="8ea1b-175">Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-175">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="8ea1b-176">[x == y](equality-operators.md#equality-operator-): igualdad.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-176">[x == y](equality-operators.md#equality-operator-) – equality.</span></span> <span data-ttu-id="8ea1b-177">De forma predeterminada, para los tipos de referencia distintos de `string`, devuelve igualdad de referencia (prueba de identidad).</span><span class="sxs-lookup"><span data-stu-id="8ea1b-177">By default, for reference types other than `string`, this returns reference equality (identity test).</span></span> <span data-ttu-id="8ea1b-178">Sin embargo, los tipos pueden sobrecargar `==`, por lo que si su intención es probar la identidad, es mejor usar el método `ReferenceEquals` en `object`.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-178">However, types can overload `==`, so if your intent is to test identity, it is best to use the `ReferenceEquals` method on `object`.</span></span>

<span data-ttu-id="8ea1b-179">[x != y](equality-operators.md#inequality-operator-): distinto de.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-179">[x != y](equality-operators.md#inequality-operator-) – not equal.</span></span> <span data-ttu-id="8ea1b-180">Vea el comentario de `==`.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-180">See comment for `==`.</span></span> <span data-ttu-id="8ea1b-181">Si un tipo sobrecarga `==`, debe sobrecargar `!=`.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-181">If a type overloads `==`, then it must overload `!=`.</span></span>

## <a name="logical-and-operator"></a><span data-ttu-id="8ea1b-182">AND lógico (operador)</span><span class="sxs-lookup"><span data-stu-id="8ea1b-182">Logical AND operator</span></span>

<span data-ttu-id="8ea1b-183">Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-183">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="8ea1b-184">`x & y` – [AND lógico](boolean-logical-operators.md#logical-and-operator-) para los operandos `bool` o [AND lógico bit a bit](bitwise-and-shift-operators.md#logical-and-operator-) para los operandos de los tipos integrales.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-184">`x & y` – [logical AND](boolean-logical-operators.md#logical-and-operator-) for the `bool` operands or [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) for the operands of the integral types.</span></span>

## <a name="logical-xor-operator"></a><span data-ttu-id="8ea1b-185">Operador lógico XOR</span><span class="sxs-lookup"><span data-stu-id="8ea1b-185">Logical XOR operator</span></span>

<span data-ttu-id="8ea1b-186">Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-186">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="8ea1b-187">`x ^ y` – [XOR lógico](boolean-logical-operators.md#logical-exclusive-or-operator-) para los operandos `bool` o [XOR lógico bit a bit](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) para los operandos de los tipos integrales.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-187">`x ^ y` – [logical XOR](boolean-logical-operators.md#logical-exclusive-or-operator-) for the `bool` operands or [bitwise logical XOR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) for the operands of the integral types.</span></span>

## <a name="logical-or-operator"></a><span data-ttu-id="8ea1b-188">Operador lógico OR (||)</span><span class="sxs-lookup"><span data-stu-id="8ea1b-188">Logical OR operator</span></span>

<span data-ttu-id="8ea1b-189">Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-189">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="8ea1b-190">`x | y` – [OR lógico](boolean-logical-operators.md#logical-or-operator-) para los operandos `bool` o [OR lógico bit a bit](bitwise-and-shift-operators.md#logical-or-operator-) para los operandos de los tipos integrales.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-190">`x | y` – [logical OR](boolean-logical-operators.md#logical-or-operator-) for the `bool` operands or [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) for the operands of the integral types.</span></span>

## <a name="conditional-and-operator"></a><span data-ttu-id="8ea1b-191">Operador condicional AND</span><span class="sxs-lookup"><span data-stu-id="8ea1b-191">Conditional AND operator</span></span>

<span data-ttu-id="8ea1b-192">Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-192">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="8ea1b-193">[x && y](boolean-logical-operators.md#conditional-logical-and-operator-): AND lógico.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-193">[x && y](boolean-logical-operators.md#conditional-logical-and-operator-) – logical AND.</span></span> <span data-ttu-id="8ea1b-194">Si el primer operando se evalúa como false, C# no evalúa el segundo operando.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-194">If the first operand evaluates to false, then C# does not evaluate the second operand.</span></span>

## <a name="conditional-or-operator"></a><span data-ttu-id="8ea1b-195">Operador condicional OR</span><span class="sxs-lookup"><span data-stu-id="8ea1b-195">Conditional OR operator</span></span>

<span data-ttu-id="8ea1b-196">Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-196">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="8ea1b-197">[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-): OR lógico.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-197">[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) – logical OR.</span></span> <span data-ttu-id="8ea1b-198">Si el primer operando se evalúa como true, C# no evalúa el segundo operando.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-198">If the first operand evaluates to true, then C# does not evaluate the second operand.</span></span>

## <a name="null-coalescing-operator"></a><span data-ttu-id="8ea1b-199">Operador de uso combinado de null</span><span class="sxs-lookup"><span data-stu-id="8ea1b-199">Null-coalescing operator</span></span>

<span data-ttu-id="8ea1b-200">Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-200">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="8ea1b-201">[x ?? y](null-coalescing-operator.md): devuelve `x` si no es `null`; de lo contrario, devuelve `y`.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-201">[x ?? y](null-coalescing-operator.md) – returns `x` if it is non-`null`; otherwise, returns `y`.</span></span>

## <a name="conditional-operator"></a><span data-ttu-id="8ea1b-202">Operador condicional</span><span class="sxs-lookup"><span data-stu-id="8ea1b-202">Conditional operator</span></span>

<span data-ttu-id="8ea1b-203">Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-203">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="8ea1b-204">[t ? x : y](conditional-operator.md): si la prueba `t` se evalúa como true, evalúa y devuelve `x`; en caso contrario, evalúa y devuelve `y`.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-204">[t ? x : y](conditional-operator.md) – if test `t` evaluates to true, then evaluate and return `x`; otherwise, evaluate and return `y`.</span></span>

## <a name="assignment-and-lambda-operators"></a><span data-ttu-id="8ea1b-205">Operadores de asignación y Lambda</span><span class="sxs-lookup"><span data-stu-id="8ea1b-205">Assignment and Lambda operators</span></span>

<span data-ttu-id="8ea1b-206">Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-206">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="8ea1b-207">[x = y](assignment-operator.md): asignación.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-207">[x = y](assignment-operator.md) – assignment.</span></span>

<span data-ttu-id="8ea1b-208">[x += y](addition-assignment-operator.md): incremento.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-208">[x += y](addition-assignment-operator.md) – increment.</span></span> <span data-ttu-id="8ea1b-209">Agregue el valor de `y` al valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-209">Add the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="8ea1b-210">Si `x` designa un `event`, `y` debe ser una función adecuada que C# agregue como un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-210">If `x` designates an `event`, then `y` must be an appropriate function that C# adds as an event handler.</span></span>

<span data-ttu-id="8ea1b-211">[x -= y](subtraction-assignment-operator.md): decremento.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-211">[x -= y](subtraction-assignment-operator.md) – decrement.</span></span> <span data-ttu-id="8ea1b-212">Reste el valor de `y` del valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-212">Subtract the value of `y` from the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="8ea1b-213">Si `x` designa un `event`, `y` debe ser una función adecuada que C# quite como un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-213">If `x` designates an `event`, then `y` must be an appropriate function that C# removes as an event handler.</span></span>

<span data-ttu-id="8ea1b-214">[x \*= y](arithmetic-operators.md#compound-assignment): asignación de multiplicación.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-214">[x \*= y](arithmetic-operators.md#compound-assignment) – multiplication assignment.</span></span> <span data-ttu-id="8ea1b-215">Multiplique el valor de `y` por el valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-215">Multiply the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="8ea1b-216">[x /= y](arithmetic-operators.md#compound-assignment): asignación de división.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-216">[x /= y](arithmetic-operators.md#compound-assignment) – division assignment.</span></span> <span data-ttu-id="8ea1b-217">Divida el valor de `x` por el valor de `y`, almacene el resultado en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-217">Divide the value of `x` by the value of `y`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="8ea1b-218">[x %= y](arithmetic-operators.md#compound-assignment): asignación del resto.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-218">[x %= y](arithmetic-operators.md#compound-assignment) – remainder assignment.</span></span> <span data-ttu-id="8ea1b-219">Divida el valor de `x` por el valor de `y`, almacene el resto en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-219">Divide the value of `x` by the value of `y`, store the remainder in `x`, and return the new value.</span></span>

<span data-ttu-id="8ea1b-220">[x &= y](boolean-logical-operators.md#compound-assignment): asignación de AND.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-220">[x &= y](boolean-logical-operators.md#compound-assignment) – AND assignment.</span></span> <span data-ttu-id="8ea1b-221">AND el valor de `y` con el valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-221">AND the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="8ea1b-222">[x &#124;= y](boolean-logical-operators.md#compound-assignment): asignación de OR.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-222">[x &#124;= y](boolean-logical-operators.md#compound-assignment) – OR assignment.</span></span> <span data-ttu-id="8ea1b-223">OR el valor de `y` con el valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-223">OR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="8ea1b-224">[x ^= y](boolean-logical-operators.md#compound-assignment): asignación de XOR.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-224">[x ^= y](boolean-logical-operators.md#compound-assignment) – XOR assignment.</span></span> <span data-ttu-id="8ea1b-225">XOR el valor de `y` con el valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-225">XOR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="8ea1b-226">[x <<= y](bitwise-and-shift-operators.md#compound-assignment): asignación de desplazamiento a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-226">[x <<= y](bitwise-and-shift-operators.md#compound-assignment) – left-shift assignment.</span></span> <span data-ttu-id="8ea1b-227">Desplace el valor de `x` a la izquierda `y` lugares, almacene el resultado en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-227">Shift the value of `x` left by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="8ea1b-228">[x >>= y](bitwise-and-shift-operators.md#compound-assignment): asignación de desplazamiento a la derecha.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-228">[x >>= y](bitwise-and-shift-operators.md#compound-assignment) – right-shift assignment.</span></span> <span data-ttu-id="8ea1b-229">Desplace el valor de `x` a la derecha `y` posiciones, almacene el resultado en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-229">Shift the value of `x` right by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="8ea1b-230">[=>](lambda-operator.md): declaración lambda.</span><span class="sxs-lookup"><span data-stu-id="8ea1b-230">[=>](lambda-operator.md) – lambda declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ea1b-231">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ea1b-231">See also</span></span>

- [<span data-ttu-id="8ea1b-232">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="8ea1b-232">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="8ea1b-233">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="8ea1b-233">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8ea1b-234">C#</span><span class="sxs-lookup"><span data-stu-id="8ea1b-234">C#</span></span>](../../index.md)
- [<span data-ttu-id="8ea1b-235">Operadores sobrecargables</span><span class="sxs-lookup"><span data-stu-id="8ea1b-235">Overloadable operators</span></span>](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [<span data-ttu-id="8ea1b-236">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="8ea1b-236">C# Keywords</span></span>](../keywords/index.md)

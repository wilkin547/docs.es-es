---
title: 'Operadores de C#'
ms.date: 04/04/2018
f1_keywords:
  - cs.operators
helpviewer_keywords:
  - 'boolean operators [C#]'
  - 'expressions [C#], operators'
  - 'logical operators [C#]'
  - 'operators [C#]'
  - 'Visual C#, operators'
  - 'indirection operators [C#]'
  - 'assignment operators [C#]'
  - 'shift operators [C#]'
  - 'relational operators [C#]'
  - 'bitwise operators [C#]'
  - 'address operators [C#]'
  - 'keywords [C#], operators'
  - 'arithmetic operators [C#]'
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
---
# <a name="c-operators"></a><span data-ttu-id="cff73-102">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="cff73-102">C# operators</span></span>

<span data-ttu-id="cff73-103">C# proporciona muchos operadores, que son símbolos que especifican las operaciones (matemáticas, indización, llamada de función, etc.) que se realizan en una expresión.</span><span class="sxs-lookup"><span data-stu-id="cff73-103">C# provides many operators, which are symbols that specify which operations (math, indexing, function call, etc.) to perform in an expression.</span></span> <span data-ttu-id="cff73-104">Puede [sobrecargar](../../programming-guide/statements-expressions-operators/overloadable-operators.md) muchos operadores para cambiar su significado al aplicarlos a un tipo definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="cff73-104">You can [overload](../../programming-guide/statements-expressions-operators/overloadable-operators.md) many operators to change their meaning when applied to a user-defined type.</span></span>

<span data-ttu-id="cff73-105">Las operaciones de tipos enteros (como `==`, `!=`, `<`, `>`, `&` y `|`) suelen estar permitidas en los tipos de enumeración (`enum`).</span><span class="sxs-lookup"><span data-stu-id="cff73-105">Operations on integral types (such as `==`, `!=`, `<`, `>`, `&`, `|`) are generally allowed on enumeration (`enum`) types.</span></span>

<span data-ttu-id="cff73-106">En las secciones siguientes se enumeran los operadores de C# desde la precedencia más alta a la más baja.</span><span class="sxs-lookup"><span data-stu-id="cff73-106">The sections below list the C# operators starting with the highest precedence to the lowest.</span></span> <span data-ttu-id="cff73-107">Los operadores de cada sección comparten el mismo nivel de precedencia.</span><span class="sxs-lookup"><span data-stu-id="cff73-107">The operators within each section share the same precedence level.</span></span>

## <a name="primary-operators"></a><span data-ttu-id="cff73-108">Operadores principales</span><span class="sxs-lookup"><span data-stu-id="cff73-108">Primary operators</span></span>

<span data-ttu-id="cff73-109">Estos son los operadores de precedencia más alta.</span><span class="sxs-lookup"><span data-stu-id="cff73-109">These are the highest precedence operators.</span></span>

<span data-ttu-id="cff73-110">[x.y](member-access-operator.md): acceso a miembros.</span><span class="sxs-lookup"><span data-stu-id="cff73-110">[x.y](member-access-operator.md) – member access.</span></span>

<span data-ttu-id="cff73-111">[x?.y](null-conditional-operators.md): acceso a miembros condicionales nulos.</span><span class="sxs-lookup"><span data-stu-id="cff73-111">[x?.y](null-conditional-operators.md) – null conditional member access.</span></span> <span data-ttu-id="cff73-112">Devuelve `null` si el operando izquierdo se evalúa como `null`.</span><span class="sxs-lookup"><span data-stu-id="cff73-112">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="cff73-113">[x?[y]](null-conditional-operators.md): acceso a índices condicionales nulos.</span><span class="sxs-lookup"><span data-stu-id="cff73-113">[x?[y]](null-conditional-operators.md) - null conditional index access.</span></span> <span data-ttu-id="cff73-114">Devuelve `null` si el operando izquierdo se evalúa como `null`.</span><span class="sxs-lookup"><span data-stu-id="cff73-114">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="cff73-115">[f(x)](invocation-operator.md): invocación de función.</span><span class="sxs-lookup"><span data-stu-id="cff73-115">[f(x)](invocation-operator.md) – function invocation.</span></span>

<span data-ttu-id="cff73-116">[a&#91;x&#93;](index-operator.md): indización de objeto agregado.</span><span class="sxs-lookup"><span data-stu-id="cff73-116">[a&#91;x&#93;](index-operator.md) – aggregate object indexing.</span></span>

<span data-ttu-id="cff73-117">[x++](arithmetic-operators.md#increment-operator-): incremento de postfijo.</span><span class="sxs-lookup"><span data-stu-id="cff73-117">[x++](arithmetic-operators.md#increment-operator-) – postfix increment.</span></span> <span data-ttu-id="cff73-118">Devuelve el valor de x y, a continuación, actualiza la ubicación de almacenamiento con el valor de x que es uno mayor (normalmente agrega el entero 1).</span><span class="sxs-lookup"><span data-stu-id="cff73-118">Returns the value of x and then updates the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="cff73-119">[x--](arithmetic-operators.md#decrement-operator---): decremento de postfijo.</span><span class="sxs-lookup"><span data-stu-id="cff73-119">[x--](arithmetic-operators.md#decrement-operator---) –  postfix decrement.</span></span> <span data-ttu-id="cff73-120">Devuelve el valor de x; a continuación, actualiza la ubicación de almacenamiento con el valor de x que es uno menos (normalmente resta el entero 1).</span><span class="sxs-lookup"><span data-stu-id="cff73-120">Returns the value of x and then updates the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="cff73-121">[new](../keywords/new-operator.md): creación de instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="cff73-121">[new](../keywords/new-operator.md) – type instantiation.</span></span>

<span data-ttu-id="cff73-122">[typeof](../keywords/typeof.md): devuelve el objeto <xref:System.Type> que representa el operando.</span><span class="sxs-lookup"><span data-stu-id="cff73-122">[typeof](../keywords/typeof.md) – returns the <xref:System.Type> object representing the operand.</span></span>

<span data-ttu-id="cff73-123">[checked](../keywords/checked.md): habilita la comprobación de desbordamiento para operaciones con enteros.</span><span class="sxs-lookup"><span data-stu-id="cff73-123">[checked](../keywords/checked.md) – enables overflow checking for integer operations.</span></span>

<span data-ttu-id="cff73-124">[unchecked](../keywords/unchecked.md): deshabilita la comprobación de desbordamiento para operaciones con enteros.</span><span class="sxs-lookup"><span data-stu-id="cff73-124">[unchecked](../keywords/unchecked.md) – disables overflow checking for integer operations.</span></span> <span data-ttu-id="cff73-125">Este es el comportamiento predeterminado del compilador.</span><span class="sxs-lookup"><span data-stu-id="cff73-125">This is the default compiler behavior.</span></span>

<span data-ttu-id="cff73-126">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) genera el valor predeterminado del tipo T.</span><span class="sxs-lookup"><span data-stu-id="cff73-126">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) – produces the default value of type T.</span></span>

<span data-ttu-id="cff73-127">[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md): declara y devuelve una instancia de delegado.</span><span class="sxs-lookup"><span data-stu-id="cff73-127">[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md) – declares and returns a delegate instance.</span></span>

<span data-ttu-id="cff73-128">[sizeof](../keywords/sizeof.md): devuelve el tamaño en bytes del operando de tipo.</span><span class="sxs-lookup"><span data-stu-id="cff73-128">[sizeof](../keywords/sizeof.md) – returns the size in bytes of the type operand.</span></span>

<span data-ttu-id="cff73-129">[->](dereference-operator.md): desreferenciación del puntero combinada con acceso a miembros.</span><span class="sxs-lookup"><span data-stu-id="cff73-129">[->](dereference-operator.md) – pointer dereferencing combined with member access.</span></span>

## <a name="unary-operators"></a><span data-ttu-id="cff73-130">Operadores unarios</span><span class="sxs-lookup"><span data-stu-id="cff73-130">Unary operators</span></span>

<span data-ttu-id="cff73-131">Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="cff73-131">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="cff73-132">[+x](addition-operator.md): devuelve el valor de x.</span><span class="sxs-lookup"><span data-stu-id="cff73-132">[+x](addition-operator.md) – returns the value of x.</span></span>

<span data-ttu-id="cff73-133">[-x](subtraction-operator.md): negación numérica.</span><span class="sxs-lookup"><span data-stu-id="cff73-133">[-x](subtraction-operator.md) – numeric negation.</span></span>

<span data-ttu-id="cff73-134">[\!x](logical-negation-operator.md): negación lógica.</span><span class="sxs-lookup"><span data-stu-id="cff73-134">[\!x](logical-negation-operator.md) – logical negation.</span></span>

<span data-ttu-id="cff73-135">[~x](bitwise-complement-operator.md): complemento bit a bit.</span><span class="sxs-lookup"><span data-stu-id="cff73-135">[~x](bitwise-complement-operator.md) – bitwise complement.</span></span>

<span data-ttu-id="cff73-136">[++x](arithmetic-operators.md#increment-operator-): incremento de prefijo.</span><span class="sxs-lookup"><span data-stu-id="cff73-136">[++x](arithmetic-operators.md#increment-operator-) – prefix increment.</span></span> <span data-ttu-id="cff73-137">Devuelve el valor de x después de actualizar la ubicación de almacenamiento con el valor de x que es uno mayor (normalmente agrega el entero 1).</span><span class="sxs-lookup"><span data-stu-id="cff73-137">Returns the value of x after updating the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="cff73-138">[--x](arithmetic-operators.md#decrement-operator---): decremento de prefijo.</span><span class="sxs-lookup"><span data-stu-id="cff73-138">[--x](arithmetic-operators.md#decrement-operator---) – prefix decrement.</span></span> <span data-ttu-id="cff73-139">Devuelve el valor de x después de actualizar la ubicación de almacenamiento con el valor de x que es uno menos (normalmente resta el entero 1).</span><span class="sxs-lookup"><span data-stu-id="cff73-139">Returns the value of x after updating the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="cff73-140">[(T)x](invocation-operator.md): conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="cff73-140">[(T)x](invocation-operator.md) – type casting.</span></span>

<span data-ttu-id="cff73-141">[await](../keywords/await.md): espera una `Task`.</span><span class="sxs-lookup"><span data-stu-id="cff73-141">[await](../keywords/await.md) – awaits a `Task`.</span></span>

<span data-ttu-id="cff73-142">[&x](and-operator.md): dirección de.</span><span class="sxs-lookup"><span data-stu-id="cff73-142">[&x](and-operator.md) – address of.</span></span>

<span data-ttu-id="cff73-143">[\*x](multiplication-operator.md): desreferenciación.</span><span class="sxs-lookup"><span data-stu-id="cff73-143">[\*x](multiplication-operator.md) – dereferencing.</span></span>

## <a name="multiplicative-operators"></a><span data-ttu-id="cff73-144">Operadores de multiplicación</span><span class="sxs-lookup"><span data-stu-id="cff73-144">Multiplicative operators</span></span>

<span data-ttu-id="cff73-145">Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="cff73-145">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="cff73-146">[x \* y](arithmetic-operators.md#multiplication-operator-): multiplicación.</span><span class="sxs-lookup"><span data-stu-id="cff73-146">[x \* y](arithmetic-operators.md#multiplication-operator-) – multiplication.</span></span>

<span data-ttu-id="cff73-147">[x / y](arithmetic-operators.md#division-operator-): división.</span><span class="sxs-lookup"><span data-stu-id="cff73-147">[x / y](arithmetic-operators.md#division-operator-) – division.</span></span> <span data-ttu-id="cff73-148">Si los operandos son enteros, el resultado es un entero que se trunca hacia cero (por ejemplo, `-7 / 2 is -3`).</span><span class="sxs-lookup"><span data-stu-id="cff73-148">If the operands are integers, the result is an integer truncated toward zero (for example, `-7 / 2 is -3`).</span></span>

<span data-ttu-id="cff73-149">[x % y](arithmetic-operators.md#remainder-operator-): resto.</span><span class="sxs-lookup"><span data-stu-id="cff73-149">[x % y](arithmetic-operators.md#remainder-operator-) – remainder.</span></span> <span data-ttu-id="cff73-150">Si los operandos son enteros, devuelve el resto de dividir x entre y.</span><span class="sxs-lookup"><span data-stu-id="cff73-150">If the operands are integers, this returns the remainder of dividing x by y.</span></span>  <span data-ttu-id="cff73-151">Si `q = x / y` y `r = x % y`, entonces `x = q * y + r`.</span><span class="sxs-lookup"><span data-stu-id="cff73-151">If `q = x / y` and `r = x % y`, then `x = q * y + r`.</span></span>

## <a name="additive-operators"></a><span data-ttu-id="cff73-152">Operadores aditivos</span><span class="sxs-lookup"><span data-stu-id="cff73-152">Additive operators</span></span>

<span data-ttu-id="cff73-153">Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="cff73-153">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="cff73-154">[x + y](arithmetic-operators.md#addition-operator-): suma.</span><span class="sxs-lookup"><span data-stu-id="cff73-154">[x + y](arithmetic-operators.md#addition-operator-) – addition.</span></span>

<span data-ttu-id="cff73-155">[x – y](arithmetic-operators.md#subtraction-operator--): resta.</span><span class="sxs-lookup"><span data-stu-id="cff73-155">[x – y](arithmetic-operators.md#subtraction-operator--) – subtraction.</span></span>

## <a name="shift-operators"></a><span data-ttu-id="cff73-156">Operadores de desplazamiento</span><span class="sxs-lookup"><span data-stu-id="cff73-156">Shift operators</span></span>

<span data-ttu-id="cff73-157">Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="cff73-157">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="cff73-158">[x <\<  y](left-shift-operator.md): desplaza los bits a la izquierda y rellena con cero a la derecha.</span><span class="sxs-lookup"><span data-stu-id="cff73-158">[x <\<  y](left-shift-operator.md) – shift bits left and fill with zero on the right.</span></span>

<span data-ttu-id="cff73-159">[x >> y](right-shift-operator.md): desplaza los bits a la derecha.</span><span class="sxs-lookup"><span data-stu-id="cff73-159">[x >> y](right-shift-operator.md) – shift bits right.</span></span> <span data-ttu-id="cff73-160">Si el operando izquierdo es `int` o `long`, los bits de la izquierda se rellenan con el bit de signo.</span><span class="sxs-lookup"><span data-stu-id="cff73-160">If the left operand is `int` or `long`, then left bits are filled with the sign bit.</span></span> <span data-ttu-id="cff73-161">Si el operando izquierdo es `uint` o `ulong`, los bits de la izquierda se rellenan con cero.</span><span class="sxs-lookup"><span data-stu-id="cff73-161">If the left operand is `uint` or `ulong`, then left bits are filled with zero.</span></span>

## <a name="relational-and-type-testing-operators"></a><span data-ttu-id="cff73-162">Operadores de comprobación de tipos y relacionales</span><span class="sxs-lookup"><span data-stu-id="cff73-162">Relational and type-testing operators</span></span>

<span data-ttu-id="cff73-163">Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="cff73-163">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="cff73-164">[x \< y](less-than-operator.md): menor que (true si x es menor que y).</span><span class="sxs-lookup"><span data-stu-id="cff73-164">[x \< y](less-than-operator.md) – less than (true if x is less than y).</span></span>

<span data-ttu-id="cff73-165">[x > y](greater-than-operator.md): mayor que (true si x es mayor que y).</span><span class="sxs-lookup"><span data-stu-id="cff73-165">[x > y](greater-than-operator.md) – greater than (true if x is greater than y).</span></span>

<span data-ttu-id="cff73-166">[x \<= y](less-than-equal-operator.md): menor o igual que.</span><span class="sxs-lookup"><span data-stu-id="cff73-166">[x \<= y](less-than-equal-operator.md) – less than or equal to.</span></span>

<span data-ttu-id="cff73-167">[x >= y](greater-than-equal-operator.md): mayor o igual que.</span><span class="sxs-lookup"><span data-stu-id="cff73-167">[x >= y](greater-than-equal-operator.md) – greater than or equal to.</span></span>

<span data-ttu-id="cff73-168">[is](../keywords/is.md): compatibilidad de tipos.</span><span class="sxs-lookup"><span data-stu-id="cff73-168">[is](../keywords/is.md) – type compatibility.</span></span> <span data-ttu-id="cff73-169">Devuelve true si el operando izquierdo evaluado se puede convertir al tipo especificado en el operando derecho (un tipo estático).</span><span class="sxs-lookup"><span data-stu-id="cff73-169">Returns true if the evaluated left operand can be cast to the type specified in the right operand (a static type).</span></span>

<span data-ttu-id="cff73-170">[as](../keywords/as.md): conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="cff73-170">[as](../keywords/as.md) – type conversion.</span></span> <span data-ttu-id="cff73-171">Devuelve el operando izquierdo convertido al tipo especificado por el operando derecho (un tipo estático), pero `as` devuelve `null` donde `(T)x` produciría una excepción.</span><span class="sxs-lookup"><span data-stu-id="cff73-171">Returns the left operand cast to the type specified by the right operand (a static type), but `as` returns `null` where `(T)x` would throw an exception.</span></span>

## <a name="equality-operators"></a><span data-ttu-id="cff73-172">Operadores de igualdad</span><span class="sxs-lookup"><span data-stu-id="cff73-172">Equality operators</span></span>

<span data-ttu-id="cff73-173">Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="cff73-173">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="cff73-174">[x == y](equality-comparison-operator.md): igualdad.</span><span class="sxs-lookup"><span data-stu-id="cff73-174">[x == y](equality-comparison-operator.md) – equality.</span></span> <span data-ttu-id="cff73-175">De forma predeterminada, para los tipos de referencia distintos de `string`, devuelve igualdad de referencia (prueba de identidad).</span><span class="sxs-lookup"><span data-stu-id="cff73-175">By default, for reference types other than `string`, this returns reference equality (identity test).</span></span> <span data-ttu-id="cff73-176">Sin embargo, los tipos pueden sobrecargar `==`, por lo que si su intención es probar la identidad, es mejor usar el método `ReferenceEquals` en `object`.</span><span class="sxs-lookup"><span data-stu-id="cff73-176">However, types can overload `==`, so if your intent is to test identity, it is best to use the `ReferenceEquals` method on `object`.</span></span>

<span data-ttu-id="cff73-177">[x != y](not-equal-operator.md): distinto de.</span><span class="sxs-lookup"><span data-stu-id="cff73-177">[x != y](not-equal-operator.md) – not equal.</span></span> <span data-ttu-id="cff73-178">Vea el comentario de `==`.</span><span class="sxs-lookup"><span data-stu-id="cff73-178">See comment for `==`.</span></span> <span data-ttu-id="cff73-179">Si un tipo sobrecarga `==`, debe sobrecargar `!=`.</span><span class="sxs-lookup"><span data-stu-id="cff73-179">If a type overloads `==`, then it must overload `!=`.</span></span>

## <a name="logical-and-operator"></a><span data-ttu-id="cff73-180">AND lógico (operador)</span><span class="sxs-lookup"><span data-stu-id="cff73-180">Logical AND operator</span></span>

<span data-ttu-id="cff73-181">Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="cff73-181">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="cff73-182">[x & y](and-operator.md): AND lógico o bit a bit.</span><span class="sxs-lookup"><span data-stu-id="cff73-182">[x & y](and-operator.md) – logical or bitwise AND.</span></span> <span data-ttu-id="cff73-183">Por lo general puede usarlo con tipos enteros y tipos `enum`.</span><span class="sxs-lookup"><span data-stu-id="cff73-183">You can generally use this with integer types and `enum` types.</span></span>

## <a name="logical-xor-operator"></a><span data-ttu-id="cff73-184">Operador lógico XOR</span><span class="sxs-lookup"><span data-stu-id="cff73-184">Logical XOR operator</span></span>

<span data-ttu-id="cff73-185">Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="cff73-185">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="cff73-186">[x ^ y](xor-operator.md): XOR lógico o bit a bit.</span><span class="sxs-lookup"><span data-stu-id="cff73-186">[x ^ y](xor-operator.md) – logical or bitwise XOR.</span></span> <span data-ttu-id="cff73-187">Por lo general puede usarlo con tipos enteros y tipos `enum`.</span><span class="sxs-lookup"><span data-stu-id="cff73-187">You can generally use this with integer types and `enum` types.</span></span>

## <a name="logical-or-operator"></a><span data-ttu-id="cff73-188">Operador lógico OR (||)</span><span class="sxs-lookup"><span data-stu-id="cff73-188">Logical OR operator</span></span>

<span data-ttu-id="cff73-189">Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="cff73-189">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="cff73-190">[x &#124; y](or-operator.md): OR lógico o bit a bit.</span><span class="sxs-lookup"><span data-stu-id="cff73-190">[x &#124; y](or-operator.md) – logical or bitwise OR.</span></span> <span data-ttu-id="cff73-191">Por lo general puede usarlo con tipos enteros y tipos `enum`.</span><span class="sxs-lookup"><span data-stu-id="cff73-191">You can generally use this with integer types and `enum` types.</span></span>

## <a name="conditional-and-operator"></a><span data-ttu-id="cff73-192">Operador condicional AND</span><span class="sxs-lookup"><span data-stu-id="cff73-192">Conditional AND operator</span></span>

<span data-ttu-id="cff73-193">Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="cff73-193">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="cff73-194">[x && y](conditional-and-operator.md): AND lógico.</span><span class="sxs-lookup"><span data-stu-id="cff73-194">[x && y](conditional-and-operator.md) – logical AND.</span></span> <span data-ttu-id="cff73-195">Si el primer operando se evalúa como false, C# no evalúa el segundo operando.</span><span class="sxs-lookup"><span data-stu-id="cff73-195">If the first operand evaluates to false, then C# does not evaluate the second operand.</span></span>

## <a name="conditional-or-operator"></a><span data-ttu-id="cff73-196">Operador condicional OR</span><span class="sxs-lookup"><span data-stu-id="cff73-196">Conditional OR operator</span></span>

<span data-ttu-id="cff73-197">Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="cff73-197">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="cff73-198">[x &#124;&#124; y](conditional-or-operator.md): OR lógico.</span><span class="sxs-lookup"><span data-stu-id="cff73-198">[x &#124;&#124; y](conditional-or-operator.md) – logical OR.</span></span> <span data-ttu-id="cff73-199">Si el primer operando se evalúa como true, C# no evalúa el segundo operando.</span><span class="sxs-lookup"><span data-stu-id="cff73-199">If the first operand evaluates to true, then C# does not evaluate the second operand.</span></span>

## <a name="null-coalescing-operator"></a><span data-ttu-id="cff73-200">Operador de uso combinado de null</span><span class="sxs-lookup"><span data-stu-id="cff73-200">Null-coalescing operator</span></span>

<span data-ttu-id="cff73-201">Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="cff73-201">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="cff73-202">[x ?? y](null-coalescing-operator.md): devuelve `x` si no es `null`; de lo contrario, devuelve `y`.</span><span class="sxs-lookup"><span data-stu-id="cff73-202">[x ?? y](null-coalescing-operator.md) – returns `x` if it is non-`null`; otherwise, returns `y`.</span></span>

## <a name="conditional-operator"></a><span data-ttu-id="cff73-203">Operador condicional</span><span class="sxs-lookup"><span data-stu-id="cff73-203">Conditional operator</span></span>

<span data-ttu-id="cff73-204">Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="cff73-204">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="cff73-205">[t ? x : y](conditional-operator.md): si la prueba `t` se evalúa como true, evalúa y devuelve `x`; en caso contrario, evalúa y devuelve `y`.</span><span class="sxs-lookup"><span data-stu-id="cff73-205">[t ? x : y](conditional-operator.md) – if test `t` evaluates to true, then evaluate and return `x`; otherwise, evaluate and return `y`.</span></span>

## <a name="assignment-and-lambda-operators"></a><span data-ttu-id="cff73-206">Operadores de asignación y Lambda</span><span class="sxs-lookup"><span data-stu-id="cff73-206">Assignment and Lambda operators</span></span>

<span data-ttu-id="cff73-207">Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.</span><span class="sxs-lookup"><span data-stu-id="cff73-207">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="cff73-208">[x = y](assignment-operator.md): asignación.</span><span class="sxs-lookup"><span data-stu-id="cff73-208">[x = y](assignment-operator.md) – assignment.</span></span>

<span data-ttu-id="cff73-209">[x += y](addition-assignment-operator.md): incremento.</span><span class="sxs-lookup"><span data-stu-id="cff73-209">[x += y](addition-assignment-operator.md) – increment.</span></span> <span data-ttu-id="cff73-210">Agregue el valor de `y` al valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="cff73-210">Add the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="cff73-211">Si `x` designa un `event`, `y` debe ser una función adecuada que C# agregue como un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="cff73-211">If `x` designates an `event`, then `y` must be an appropriate function that C# adds as an event handler.</span></span>

<span data-ttu-id="cff73-212">[x -= y](subtraction-assignment-operator.md): decremento.</span><span class="sxs-lookup"><span data-stu-id="cff73-212">[x -= y](subtraction-assignment-operator.md) – decrement.</span></span> <span data-ttu-id="cff73-213">Reste el valor de `y` del valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="cff73-213">Subtract the value of `y` from the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="cff73-214">Si `x` designa un `event`, `y` debe ser una función adecuada que C# quite como un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="cff73-214">If `x` designates an `event`, then `y` must be an appropriate function that C# removes as an event handler</span></span>

<span data-ttu-id="cff73-215">[x \*= y](multiplication-assignment-operator.md): asignación de multiplicación.</span><span class="sxs-lookup"><span data-stu-id="cff73-215">[x \*= y](multiplication-assignment-operator.md) – multiplication assignment.</span></span> <span data-ttu-id="cff73-216">Multiplique el valor de `y` por el valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="cff73-216">Multiply the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="cff73-217">[x /= y](arithmetic-operators.md#compound-assignment): asignación de división.</span><span class="sxs-lookup"><span data-stu-id="cff73-217">[x /= y](arithmetic-operators.md#compound-assignment) – division assignment.</span></span> <span data-ttu-id="cff73-218">Divida el valor de `x` por el valor de `y`, almacene el resultado en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="cff73-218">Divide the value of `x` by the value of `y`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="cff73-219">[x %= y](arithmetic-operators.md#compound-assignment): asignación del resto.</span><span class="sxs-lookup"><span data-stu-id="cff73-219">[x %= y](arithmetic-operators.md#compound-assignment) – remainder assignment.</span></span> <span data-ttu-id="cff73-220">Divida el valor de `x` por el valor de `y`, almacene el resto en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="cff73-220">Divide the value of `x` by the value of `y`, store the remainder in `x`, and return the new value.</span></span>

<span data-ttu-id="cff73-221">[x &= y](and-assignment-operator.md): asignación de AND.</span><span class="sxs-lookup"><span data-stu-id="cff73-221">[x &= y](and-assignment-operator.md) – AND assignment.</span></span> <span data-ttu-id="cff73-222">AND el valor de `y` con el valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="cff73-222">AND the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="cff73-223">[x &#124;= y](or-assignment-operator.md): asignación de OR.</span><span class="sxs-lookup"><span data-stu-id="cff73-223">[x &#124;= y](or-assignment-operator.md) – OR assignment.</span></span> <span data-ttu-id="cff73-224">OR el valor de `y` con el valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="cff73-224">OR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="cff73-225">[x ^= y](xor-assignment-operator.md): asignación de XOR.</span><span class="sxs-lookup"><span data-stu-id="cff73-225">[x ^= y](xor-assignment-operator.md) – XOR assignment.</span></span> <span data-ttu-id="cff73-226">XOR el valor de `y` con el valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="cff73-226">XOR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="cff73-227">[x <<= y](left-shift-assignment-operator.md): asignación de desplazamiento a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="cff73-227">[x <<= y](left-shift-assignment-operator.md) – left-shift assignment.</span></span> <span data-ttu-id="cff73-228">Desplace el valor de `x` a la izquierda `y` lugares, almacene el resultado en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="cff73-228">Shift the value of `x` left by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="cff73-229">[x >>= y](right-shift-assignment-operator.md): asignación de desplazamiento a la derecha.</span><span class="sxs-lookup"><span data-stu-id="cff73-229">[x >>= y](right-shift-assignment-operator.md) – right-shift assignment.</span></span> <span data-ttu-id="cff73-230">Desplace el valor de `x` a la derecha `y` posiciones, almacene el resultado en `x` y devuelva el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="cff73-230">Shift the value of `x` right by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="cff73-231">[=>](lambda-operator.md): declaración lambda.</span><span class="sxs-lookup"><span data-stu-id="cff73-231">[=>](lambda-operator.md) – lambda declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="cff73-232">Vea también</span><span class="sxs-lookup"><span data-stu-id="cff73-232">See also</span></span>

- [<span data-ttu-id="cff73-233">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="cff73-233">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="cff73-234">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="cff73-234">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="cff73-235">C#</span><span class="sxs-lookup"><span data-stu-id="cff73-235">C#</span></span>](../../index.md)
- [<span data-ttu-id="cff73-236">Operadores sobrecargables</span><span class="sxs-lookup"><span data-stu-id="cff73-236">Overloadable Operators</span></span>](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [<span data-ttu-id="cff73-237">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="cff73-237">C# Keywords</span></span>](../keywords/index.md)
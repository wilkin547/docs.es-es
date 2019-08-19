---
title: Conversiones
description: Obtenga información sobre F# cómo el lenguaje de programación proporciona operadores de conversión para las conversiones aritméticas entre varios tipos primitivos.
ms.date: 05/16/2016
ms.openlocfilehash: ee4df588caabf58c7b9e18961e217ef8f15fcf93
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630435"
---
# <a name="casting-and-conversions-f"></a><span data-ttu-id="13ce4-103">Conversiones (F#)</span><span class="sxs-lookup"><span data-stu-id="13ce4-103">Casting and Conversions (F#)</span></span>

<span data-ttu-id="13ce4-104">En este tema se describe la compatibilidad con las conversiones de tipos en F#.</span><span class="sxs-lookup"><span data-stu-id="13ce4-104">This topic describes support for type conversions in F#.</span></span>

## <a name="arithmetic-types"></a><span data-ttu-id="13ce4-105">Tipos aritméticos</span><span class="sxs-lookup"><span data-stu-id="13ce4-105">Arithmetic Types</span></span>

<span data-ttu-id="13ce4-106">F#proporciona operadores de conversión para las conversiones aritméticas entre varios tipos primitivos, como entre tipos de punto flotante y enteros.</span><span class="sxs-lookup"><span data-stu-id="13ce4-106">F# provides conversion operators for arithmetic conversions between various primitive types, such as between integer and floating point types.</span></span> <span data-ttu-id="13ce4-107">Los operadores de conversión integral y char tienen formularios comprobados y no comprobados; los operadores de punto flotante y `enum` el operador de conversión no lo hacen.</span><span class="sxs-lookup"><span data-stu-id="13ce4-107">The integral and char conversion operators have checked and unchecked forms; the floating point operators and the `enum` conversion operator do not.</span></span> <span data-ttu-id="13ce4-108">Los formularios no comprobados se definen `Microsoft.FSharp.Core.Operators` en y los formularios marcados se `Microsoft.FSharp.Core.Operators.Checked`definen en.</span><span class="sxs-lookup"><span data-stu-id="13ce4-108">The unchecked forms are defined in `Microsoft.FSharp.Core.Operators` and the checked forms are defined in `Microsoft.FSharp.Core.Operators.Checked`.</span></span> <span data-ttu-id="13ce4-109">Los formularios comprobados comprueban si hay desbordamiento y generan una excepción en tiempo de ejecución si el valor resultante supera los límites del tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="13ce4-109">The checked forms check for overflow and generate a runtime exception if the resulting value exceeds the limits of the target type.</span></span>

<span data-ttu-id="13ce4-110">Cada uno de estos operadores tiene el mismo nombre que el nombre del tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="13ce4-110">Each of these operators has the same name as the name of the destination type.</span></span> <span data-ttu-id="13ce4-111">Por ejemplo, en el código siguiente, en el que los tipos se anotan explícitamente, `byte` aparece con dos significados diferentes.</span><span class="sxs-lookup"><span data-stu-id="13ce4-111">For example, in the following code, in which the types are explicitly annotated, `byte` appears with two different meanings.</span></span> <span data-ttu-id="13ce4-112">La primera aparición es el tipo y el segundo es el operador de conversión.</span><span class="sxs-lookup"><span data-stu-id="13ce4-112">The first occurrence is the type and the second is the conversion operator.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

<span data-ttu-id="13ce4-113">En la tabla siguiente se muestran los operadores F#de conversión definidos en.</span><span class="sxs-lookup"><span data-stu-id="13ce4-113">The following table shows conversion operators defined in F#.</span></span>

|<span data-ttu-id="13ce4-114">Operador</span><span class="sxs-lookup"><span data-stu-id="13ce4-114">Operator</span></span>|<span data-ttu-id="13ce4-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="13ce4-115">Description</span></span>|
|--------|-----------|
|`byte`|<span data-ttu-id="13ce4-116">Convertir en byte, un tipo sin signo de 8 bits.</span><span class="sxs-lookup"><span data-stu-id="13ce4-116">Convert to byte, an 8-bit unsigned type.</span></span>|
|`sbyte`|<span data-ttu-id="13ce4-117">Convertir en bytes con signo.</span><span class="sxs-lookup"><span data-stu-id="13ce4-117">Convert to signed byte.</span></span>|
|`int16`|<span data-ttu-id="13ce4-118">Convertir en un entero de 16 bits con signo.</span><span class="sxs-lookup"><span data-stu-id="13ce4-118">Convert to a 16-bit signed integer.</span></span>|
|`uint16`|<span data-ttu-id="13ce4-119">Convertir en un entero de 16 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="13ce4-119">Convert to a 16-bit unsigned integer.</span></span>|
|`int32, int`|<span data-ttu-id="13ce4-120">Convertir en un entero de 32 bits con signo.</span><span class="sxs-lookup"><span data-stu-id="13ce4-120">Convert to a 32-bit signed integer.</span></span>|
|`uint32`|<span data-ttu-id="13ce4-121">Convertir en un entero de 32 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="13ce4-121">Convert to a 32-bit unsigned integer.</span></span>|
|`int64`|<span data-ttu-id="13ce4-122">Convertir en un entero de 64 bits con signo.</span><span class="sxs-lookup"><span data-stu-id="13ce4-122">Convert to a 64-bit signed integer.</span></span>|
|`uint64`|<span data-ttu-id="13ce4-123">Convertir en un entero de 64 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="13ce4-123">Convert to a 64-bit unsigned integer.</span></span>|
|`nativeint`|<span data-ttu-id="13ce4-124">Convertir en un entero nativo.</span><span class="sxs-lookup"><span data-stu-id="13ce4-124">Convert to a native integer.</span></span>|
|`unativeint`|<span data-ttu-id="13ce4-125">Convertir en un entero nativo sin signo.</span><span class="sxs-lookup"><span data-stu-id="13ce4-125">Convert to an unsigned native integer.</span></span>|
|`float, double`|<span data-ttu-id="13ce4-126">Convertir en un número de punto flotante de IEEE de doble precisión de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="13ce4-126">Convert to a 64-bit double-precision IEEE floating point number.</span></span>|
|`float32, single`|<span data-ttu-id="13ce4-127">Convertir en un número de punto flotante de IEEE de precisión sencilla de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="13ce4-127">Convert to a 32-bit single-precision IEEE floating point number.</span></span>|
|`decimal`|<span data-ttu-id="13ce4-128">Convertir en `System.Decimal`.</span><span class="sxs-lookup"><span data-stu-id="13ce4-128">Convert to `System.Decimal`.</span></span>|
|`char`|<span data-ttu-id="13ce4-129">Convertir en `System.Char`, un carácter Unicode.</span><span class="sxs-lookup"><span data-stu-id="13ce4-129">Convert to `System.Char`, a Unicode character.</span></span>|
|`enum`|<span data-ttu-id="13ce4-130">Convertir en un tipo enumerado.</span><span class="sxs-lookup"><span data-stu-id="13ce4-130">Convert to an enumerated type.</span></span>|

<span data-ttu-id="13ce4-131">Además de los tipos primitivos integrados, puede usar estos operadores con tipos que implementan `op_Explicit` los métodos o `op_Implicit` con las firmas adecuadas.</span><span class="sxs-lookup"><span data-stu-id="13ce4-131">In addition to built-in primitive types, you can use these operators with types that implement `op_Explicit` or `op_Implicit` methods with appropriate signatures.</span></span> <span data-ttu-id="13ce4-132">Por ejemplo, el `int` operador de conversión funciona con cualquier tipo que proporcione un método `op_Explicit` estático que toma el tipo como parámetro y devuelve `int`.</span><span class="sxs-lookup"><span data-stu-id="13ce4-132">For example, the `int` conversion operator works with any type that provides a static method `op_Explicit` that takes the type as a parameter and returns `int`.</span></span> <span data-ttu-id="13ce4-133">Como excepción especial a la regla general de que los métodos no se pueden sobrecargar por tipo de valor devuelto, `op_Explicit` puede `op_Implicit`hacerlo para y.</span><span class="sxs-lookup"><span data-stu-id="13ce4-133">As a special exception to the general rule that methods cannot be overloaded by return type, you can do this for `op_Explicit` and `op_Implicit`.</span></span>

## <a name="enumerated-types"></a><span data-ttu-id="13ce4-134">Tipos enumerados</span><span class="sxs-lookup"><span data-stu-id="13ce4-134">Enumerated Types</span></span>

<span data-ttu-id="13ce4-135">El `enum` operador es un operador genérico que toma un parámetro `enum` de tipo que representa el tipo de al que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="13ce4-135">The `enum` operator is a generic operator that takes one type parameter that represents the type of the `enum` to convert to.</span></span> <span data-ttu-id="13ce4-136">Cuando se convierte a un tipo enumerado, la inferencia de tipos intenta determinar el tipo de `enum` al que se desea convertir.</span><span class="sxs-lookup"><span data-stu-id="13ce4-136">When it converts to an enumerated type, type inference attempts to determine the type of the `enum` that you want to convert to.</span></span> <span data-ttu-id="13ce4-137">En el ejemplo siguiente, la variable `col1` no se anota explícitamente, pero su tipo se deduce de la prueba de igualdad posterior.</span><span class="sxs-lookup"><span data-stu-id="13ce4-137">In the following example, the variable `col1` is not explicitly annotated, but its type is inferred from the later equality test.</span></span> <span data-ttu-id="13ce4-138">Por consiguiente, el compilador puede deducir que se `Color` está convirtiendo en una enumeración.</span><span class="sxs-lookup"><span data-stu-id="13ce4-138">Therefore, the compiler can deduce that you are converting to a `Color` enumeration.</span></span> <span data-ttu-id="13ce4-139">Como alternativa, puede proporcionar una anotación `col2` de tipo, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="13ce4-139">Alternatively, you can supply a type annotation, as with `col2` in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]

<span data-ttu-id="13ce4-140">También puede especificar explícitamente el tipo de enumeración de destino como un parámetro de tipo, como en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="13ce4-140">You can also specify the target enumeration type explicitly as a type parameter, as in the following code:</span></span>

```fsharp
let col3 = enum<Color> 3
```

<span data-ttu-id="13ce4-141">Tenga en cuenta que las conversiones de enumeración funcionan solo si el tipo subyacente de la enumeración es compatible con el tipo que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="13ce4-141">Note that the enumeration casts work only if the underlying type of the enumeration is compatible with the type being converted.</span></span> <span data-ttu-id="13ce4-142">En el código siguiente, la conversión no se compila debido a la falta de `int32` coincidencia `uint32`entre y.</span><span class="sxs-lookup"><span data-stu-id="13ce4-142">In the following code, the conversion fails to compile because of the mismatch between `int32` and `uint32`.</span></span>

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

<span data-ttu-id="13ce4-143">Para obtener más información, vea [Enumeraciones](enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="13ce4-143">For more information, see [Enumerations](enumerations.md).</span></span>

## <a name="casting-object-types"></a><span data-ttu-id="13ce4-144">Convertir tipos de objeto</span><span class="sxs-lookup"><span data-stu-id="13ce4-144">Casting Object Types</span></span>

<span data-ttu-id="13ce4-145">La conversión entre tipos en una jerarquía de objetos es fundamental para la programación orientada a objetos.</span><span class="sxs-lookup"><span data-stu-id="13ce4-145">Conversion between types in an object hierarchy is fundamental to object-oriented programming.</span></span> <span data-ttu-id="13ce4-146">Hay dos tipos básicos de conversiones: conversión hacia arriba (conversión) y conversión hacia abajo (downcasting).</span><span class="sxs-lookup"><span data-stu-id="13ce4-146">There are two basic types of conversions: casting up (upcasting) and casting down (downcasting).</span></span> <span data-ttu-id="13ce4-147">La conversión de una jerarquía significa la conversión de una referencia de objeto derivada a una referencia de objeto base.</span><span class="sxs-lookup"><span data-stu-id="13ce4-147">Casting up a hierarchy means casting from a derived object reference to a base object reference.</span></span> <span data-ttu-id="13ce4-148">Se garantiza que este tipo de conversión funciona siempre y cuando la clase base se encuentra en la jerarquía de herencia de la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="13ce4-148">Such a cast is guaranteed to work as long as the base class is in the inheritance hierarchy of the derived class.</span></span> <span data-ttu-id="13ce4-149">La conversión de una jerarquía de una referencia de objeto base a una referencia de objeto derivada solo se realiza correctamente si el objeto es realmente una instancia del tipo de destino (derivado) correcto o un tipo derivado del tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="13ce4-149">Casting down a hierarchy, from a base object reference to a derived object reference, succeeds only if the object actually is an instance of the correct destination (derived) type or a type derived from the destination type.</span></span>

<span data-ttu-id="13ce4-150">F#proporciona operadores para estos tipos de conversiones.</span><span class="sxs-lookup"><span data-stu-id="13ce4-150">F# provides operators for these types of conversions.</span></span> <span data-ttu-id="13ce4-151">El `:>` operador convierte hacia arriba la jerarquía y el `:?>` operador convierte en la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="13ce4-151">The `:>` operator casts up the hierarchy, and the `:?>` operator casts down the hierarchy.</span></span>

### <a name="upcasting"></a><span data-ttu-id="13ce4-152">Convertir</span><span class="sxs-lookup"><span data-stu-id="13ce4-152">Upcasting</span></span>

<span data-ttu-id="13ce4-153">En muchos lenguajes orientados a objetos, la conversión cruzada es implícita; en F#, las reglas son ligeramente diferentes.</span><span class="sxs-lookup"><span data-stu-id="13ce4-153">In many object-oriented languages, upcasting is implicit; in F#, the rules are slightly different.</span></span> <span data-ttu-id="13ce4-154">La conversión se aplica automáticamente cuando se pasan argumentos a métodos en un tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="13ce4-154">Upcasting is applied automatically when you pass arguments to methods on an object type.</span></span> <span data-ttu-id="13ce4-155">Sin embargo, en el caso de las funciones enlazadas a un módulo, la conversión cruzada no es automática, a menos que el tipo de parámetro se declare como un tipo flexible.</span><span class="sxs-lookup"><span data-stu-id="13ce4-155">However, for let-bound functions in a module, upcasting is not automatic, unless the parameter type is declared as a flexible type.</span></span> <span data-ttu-id="13ce4-156">Para obtener más información, vea [tipos flexibles](flexible-Types.md).</span><span class="sxs-lookup"><span data-stu-id="13ce4-156">For more information, see [Flexible Types](flexible-Types.md).</span></span>

<span data-ttu-id="13ce4-157">El `:>` operador realiza una conversión estática, lo que significa que el éxito de la conversión se determina en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="13ce4-157">The `:>` operator performs a static cast, which means that the success of the cast is determined at compile time.</span></span> <span data-ttu-id="13ce4-158">Si una conversión que usa `:>` se compila correctamente, es una conversión válida y no tiene posibilidad de errores en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="13ce4-158">If a cast that uses `:>` compiles successfully, it is a valid cast and has no chance of failure at run time.</span></span>

<span data-ttu-id="13ce4-159">También puede usar el `upcast` operador para realizar esta conversión.</span><span class="sxs-lookup"><span data-stu-id="13ce4-159">You can also use the `upcast` operator to perform such a conversion.</span></span> <span data-ttu-id="13ce4-160">La expresión siguiente especifica una conversión hacia arriba en la jerarquía:</span><span class="sxs-lookup"><span data-stu-id="13ce4-160">The following expression specifies a conversion up the hierarchy:</span></span>

```fsharp
upcast expression
```

<span data-ttu-id="13ce4-161">Cuando se usa el operador de conversión, el compilador intenta deducir el tipo al que se va a convertir desde el contexto.</span><span class="sxs-lookup"><span data-stu-id="13ce4-161">When you use the upcast operator, the compiler attempts to infer the type you are converting to from the context.</span></span> <span data-ttu-id="13ce4-162">Si el compilador no puede determinar el tipo de destino, el compilador informa de un error.</span><span class="sxs-lookup"><span data-stu-id="13ce4-162">If the compiler is unable to determine the target type, the compiler reports an error.</span></span>

### <a name="downcasting"></a><span data-ttu-id="13ce4-163">Downcasting</span><span class="sxs-lookup"><span data-stu-id="13ce4-163">Downcasting</span></span>

<span data-ttu-id="13ce4-164">El `:?>` operador realiza una conversión dinámica, lo que significa que el éxito de la conversión se determina en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="13ce4-164">The `:?>` operator performs a dynamic cast, which means that the success of the cast is determined at run time.</span></span> <span data-ttu-id="13ce4-165">Una conversión que usa el `:?>` operador no se comprueba en tiempo de compilación; pero en tiempo de ejecución, se realiza un intento de conversión al tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="13ce4-165">A cast that uses the `:?>` operator is not checked at compile time; but at run time, an attempt is made to cast to the specified type.</span></span> <span data-ttu-id="13ce4-166">Si el objeto es compatible con el tipo de destino, la conversión se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="13ce4-166">If the object is compatible with the target type, the cast succeeds.</span></span> <span data-ttu-id="13ce4-167">Si el objeto no es compatible con el tipo de destino, el Runtime genera `InvalidCastException`una.</span><span class="sxs-lookup"><span data-stu-id="13ce4-167">If the object is not compatible with the target type, the runtime raises an `InvalidCastException`.</span></span>

<span data-ttu-id="13ce4-168">También puede utilizar el `downcast` operador para realizar una conversión de tipos dinámica.</span><span class="sxs-lookup"><span data-stu-id="13ce4-168">You can also use the `downcast` operator to perform a dynamic type conversion.</span></span> <span data-ttu-id="13ce4-169">La expresión siguiente especifica una conversión hacia abajo en la jerarquía hasta un tipo que se deduce del contexto del programa:</span><span class="sxs-lookup"><span data-stu-id="13ce4-169">The following expression specifies a conversion down the hierarchy to a type that is inferred from program context:</span></span>

```fsharp
downcast expression
```

<span data-ttu-id="13ce4-170">Como en el `upcast` caso del operador, si el compilador no puede inferir un tipo de destino específico desde el contexto, notifica un error.</span><span class="sxs-lookup"><span data-stu-id="13ce4-170">As for the `upcast` operator, if the compiler cannot infer a specific target type from the context, it reports an error.</span></span>

<span data-ttu-id="13ce4-171">En el código siguiente se muestra el uso de `:>` los `:?>` operadores y.</span><span class="sxs-lookup"><span data-stu-id="13ce4-171">The following code illustrates the use of the `:>` and `:?>` operators.</span></span> <span data-ttu-id="13ce4-172">El código muestra que el `:?>` operador se utiliza mejor cuando sabe que la conversión se realizará correctamente, porque se `InvalidCastException` produce si se produce un error en la conversión.</span><span class="sxs-lookup"><span data-stu-id="13ce4-172">The code illustrates that the `:?>` operator is best used when you know that conversion will succeed, because it throws `InvalidCastException` if the conversion fails.</span></span> <span data-ttu-id="13ce4-173">Si no sabe que una conversión se realizará correctamente, una prueba de tipo que utiliza `match` una expresión es mejor porque evita la sobrecarga de generar una excepción.</span><span class="sxs-lookup"><span data-stu-id="13ce4-173">If you do not know that a conversion will succeed, a type test that uses a `match` expression is better because it avoids the overhead of generating an exception.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

<span data-ttu-id="13ce4-174">Dado que los `downcast` operadores `upcast` genéricos y dependen de la inferencia de tipos para determinar el argumento y el tipo de valor devuelto, en el código anterior, puede reemplazar</span><span class="sxs-lookup"><span data-stu-id="13ce4-174">Because generic operators `downcast` and `upcast` rely on type inference to determine the argument and return type, in the above code, you can replace</span></span>

```fsharp
let base1 = d1 :> Base1
```

<span data-ttu-id="13ce4-175">with</span><span class="sxs-lookup"><span data-stu-id="13ce4-175">with</span></span>

```fsharp
let base1 = upcast d1
```

<span data-ttu-id="13ce4-176">En el código anterior, el tipo de argumento y los tipos `Derived1` de `Base1`valor devuelto son y, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="13ce4-176">In the previous code, the argument type and return types are `Derived1` and `Base1`, respectively.</span></span>

<span data-ttu-id="13ce4-177">Para obtener más información sobre las pruebas de tipos, vea [expresiones de coincidencia](match-Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="13ce4-177">For more information about type tests, see [Match Expressions](match-Expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="13ce4-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="13ce4-178">See also</span></span>

- [<span data-ttu-id="13ce4-179">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="13ce4-179">F# Language Reference</span></span>](index.md)

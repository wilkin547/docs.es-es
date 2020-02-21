---
title: Conversiones
description: Obtenga información sobre F# cómo el lenguaje de programación proporciona operadores de conversión para las conversiones aritméticas entre varios tipos primitivos.
ms.date: 02/20/2020
ms.openlocfilehash: 5f9727d14a7ae070e0f0f71fa0a0abe04f662071
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543591"
---
# <a name="casting-and-conversions-f"></a><span data-ttu-id="2011e-103">Conversiones (F#)</span><span class="sxs-lookup"><span data-stu-id="2011e-103">Casting and Conversions (F#)</span></span>

<span data-ttu-id="2011e-104">En este tema se describe la compatibilidad con las conversiones de tipos en F#.</span><span class="sxs-lookup"><span data-stu-id="2011e-104">This topic describes support for type conversions in F#.</span></span>

## <a name="arithmetic-types"></a><span data-ttu-id="2011e-105">Tipos aritméticos</span><span class="sxs-lookup"><span data-stu-id="2011e-105">Arithmetic Types</span></span>

<span data-ttu-id="2011e-106">F#proporciona operadores de conversión para las conversiones aritméticas entre varios tipos primitivos, como entre tipos de punto flotante y enteros.</span><span class="sxs-lookup"><span data-stu-id="2011e-106">F# provides conversion operators for arithmetic conversions between various primitive types, such as between integer and floating point types.</span></span> <span data-ttu-id="2011e-107">Los operadores de conversión integral y char tienen formularios comprobados y no comprobados; los operadores de punto flotante y el operador de conversión `enum` no.</span><span class="sxs-lookup"><span data-stu-id="2011e-107">The integral and char conversion operators have checked and unchecked forms; the floating point operators and the `enum` conversion operator do not.</span></span> <span data-ttu-id="2011e-108">Los formularios no comprobados se definen en `Microsoft.FSharp.Core.Operators` y los formularios marcados se definen en `Microsoft.FSharp.Core.Operators.Checked`.</span><span class="sxs-lookup"><span data-stu-id="2011e-108">The unchecked forms are defined in `Microsoft.FSharp.Core.Operators` and the checked forms are defined in `Microsoft.FSharp.Core.Operators.Checked`.</span></span> <span data-ttu-id="2011e-109">Los formularios comprobados comprueban si hay desbordamiento y generan una excepción en tiempo de ejecución si el valor resultante supera los límites del tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="2011e-109">The checked forms check for overflow and generate a runtime exception if the resulting value exceeds the limits of the target type.</span></span>

<span data-ttu-id="2011e-110">Cada uno de estos operadores tiene el mismo nombre que el nombre del tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="2011e-110">Each of these operators has the same name as the name of the destination type.</span></span> <span data-ttu-id="2011e-111">Por ejemplo, en el código siguiente, en el que los tipos se anotan explícitamente, `byte` aparece con dos significados diferentes.</span><span class="sxs-lookup"><span data-stu-id="2011e-111">For example, in the following code, in which the types are explicitly annotated, `byte` appears with two different meanings.</span></span> <span data-ttu-id="2011e-112">La primera aparición es el tipo y el segundo es el operador de conversión.</span><span class="sxs-lookup"><span data-stu-id="2011e-112">The first occurrence is the type and the second is the conversion operator.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

<span data-ttu-id="2011e-113">En la tabla siguiente se muestran los operadores F#de conversión definidos en.</span><span class="sxs-lookup"><span data-stu-id="2011e-113">The following table shows conversion operators defined in F#.</span></span>

|<span data-ttu-id="2011e-114">Operator</span><span class="sxs-lookup"><span data-stu-id="2011e-114">Operator</span></span>|<span data-ttu-id="2011e-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="2011e-115">Description</span></span>|
|--------|-----------|
|`byte`|<span data-ttu-id="2011e-116">Convertir en byte, un tipo sin signo de 8 bits.</span><span class="sxs-lookup"><span data-stu-id="2011e-116">Convert to byte, an 8-bit unsigned type.</span></span>|
|`sbyte`|<span data-ttu-id="2011e-117">Convertir en bytes con signo.</span><span class="sxs-lookup"><span data-stu-id="2011e-117">Convert to signed byte.</span></span>|
|`int16`|<span data-ttu-id="2011e-118">Convertir en un entero de 16 bits con signo.</span><span class="sxs-lookup"><span data-stu-id="2011e-118">Convert to a 16-bit signed integer.</span></span>|
|`uint16`|<span data-ttu-id="2011e-119">Convertir en un entero de 16 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="2011e-119">Convert to a 16-bit unsigned integer.</span></span>|
|`int32, int`|<span data-ttu-id="2011e-120">Convertir en un entero de 32 bits con signo.</span><span class="sxs-lookup"><span data-stu-id="2011e-120">Convert to a 32-bit signed integer.</span></span>|
|`uint32`|<span data-ttu-id="2011e-121">Convertir en un entero de 32 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="2011e-121">Convert to a 32-bit unsigned integer.</span></span>|
|`int64`|<span data-ttu-id="2011e-122">Convertir en un entero de 64 bits con signo.</span><span class="sxs-lookup"><span data-stu-id="2011e-122">Convert to a 64-bit signed integer.</span></span>|
|`uint64`|<span data-ttu-id="2011e-123">Convertir en un entero de 64 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="2011e-123">Convert to a 64-bit unsigned integer.</span></span>|
|`nativeint`|<span data-ttu-id="2011e-124">Convertir en un entero nativo.</span><span class="sxs-lookup"><span data-stu-id="2011e-124">Convert to a native integer.</span></span>|
|`unativeint`|<span data-ttu-id="2011e-125">Convertir en un entero nativo sin signo.</span><span class="sxs-lookup"><span data-stu-id="2011e-125">Convert to an unsigned native integer.</span></span>|
|`float, double`|<span data-ttu-id="2011e-126">Convertir en un número de punto flotante de IEEE de doble precisión de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="2011e-126">Convert to a 64-bit double-precision IEEE floating point number.</span></span>|
|`float32, single`|<span data-ttu-id="2011e-127">Convertir en un número de punto flotante de IEEE de precisión sencilla de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="2011e-127">Convert to a 32-bit single-precision IEEE floating point number.</span></span>|
|`decimal`|<span data-ttu-id="2011e-128">Convertir en `System.Decimal`.</span><span class="sxs-lookup"><span data-stu-id="2011e-128">Convert to `System.Decimal`.</span></span>|
|`char`|<span data-ttu-id="2011e-129">Convertir en `System.Char`, un carácter Unicode.</span><span class="sxs-lookup"><span data-stu-id="2011e-129">Convert to `System.Char`, a Unicode character.</span></span>|
|`enum`|<span data-ttu-id="2011e-130">Convertir en un tipo enumerado.</span><span class="sxs-lookup"><span data-stu-id="2011e-130">Convert to an enumerated type.</span></span>|

<span data-ttu-id="2011e-131">Además de los tipos primitivos integrados, puede usar estos operadores con tipos que implementan `op_Explicit` o `op_Implicit` métodos con las firmas adecuadas.</span><span class="sxs-lookup"><span data-stu-id="2011e-131">In addition to built-in primitive types, you can use these operators with types that implement `op_Explicit` or `op_Implicit` methods with appropriate signatures.</span></span> <span data-ttu-id="2011e-132">Por ejemplo, el operador de conversión `int` funciona con cualquier tipo que proporcione un método estático `op_Explicit` que toma el tipo como parámetro y devuelve `int`.</span><span class="sxs-lookup"><span data-stu-id="2011e-132">For example, the `int` conversion operator works with any type that provides a static method `op_Explicit` that takes the type as a parameter and returns `int`.</span></span> <span data-ttu-id="2011e-133">Como excepción especial a la regla general de que los métodos no se pueden sobrecargar por tipo de valor devuelto, puede hacerlo para `op_Explicit` y `op_Implicit`.</span><span class="sxs-lookup"><span data-stu-id="2011e-133">As a special exception to the general rule that methods cannot be overloaded by return type, you can do this for `op_Explicit` and `op_Implicit`.</span></span>

## <a name="enumerated-types"></a><span data-ttu-id="2011e-134">Tipos enumerados</span><span class="sxs-lookup"><span data-stu-id="2011e-134">Enumerated Types</span></span>

<span data-ttu-id="2011e-135">El operador `enum` es un operador genérico que toma un parámetro de tipo que representa el tipo del `enum` al que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="2011e-135">The `enum` operator is a generic operator that takes one type parameter that represents the type of the `enum` to convert to.</span></span> <span data-ttu-id="2011e-136">Cuando se convierte a un tipo enumerado, la inferencia de tipos intenta determinar el tipo de `enum` al que se desea convertir.</span><span class="sxs-lookup"><span data-stu-id="2011e-136">When it converts to an enumerated type, type inference attempts to determine the type of the `enum` that you want to convert to.</span></span> <span data-ttu-id="2011e-137">En el ejemplo siguiente, la variable `col1` no se anota explícitamente, pero su tipo se deduce de la prueba de igualdad posterior.</span><span class="sxs-lookup"><span data-stu-id="2011e-137">In the following example, the variable `col1` is not explicitly annotated, but its type is inferred from the later equality test.</span></span> <span data-ttu-id="2011e-138">Por consiguiente, el compilador puede deducir que se está convirtiendo en una enumeración `Color`.</span><span class="sxs-lookup"><span data-stu-id="2011e-138">Therefore, the compiler can deduce that you are converting to a `Color` enumeration.</span></span> <span data-ttu-id="2011e-139">Como alternativa, puede proporcionar una anotación de tipo, como con `col2` en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="2011e-139">Alternatively, you can supply a type annotation, as with `col2` in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]

<span data-ttu-id="2011e-140">También puede especificar explícitamente el tipo de enumeración de destino como un parámetro de tipo, como en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="2011e-140">You can also specify the target enumeration type explicitly as a type parameter, as in the following code:</span></span>

```fsharp
let col3 = enum<Color> 3
```

<span data-ttu-id="2011e-141">Tenga en cuenta que las conversiones de enumeración funcionan solo si el tipo subyacente de la enumeración es compatible con el tipo que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="2011e-141">Note that the enumeration casts work only if the underlying type of the enumeration is compatible with the type being converted.</span></span> <span data-ttu-id="2011e-142">En el código siguiente, la conversión no se compila debido a la falta de coincidencia entre `int32` y `uint32`.</span><span class="sxs-lookup"><span data-stu-id="2011e-142">In the following code, the conversion fails to compile because of the mismatch between `int32` and `uint32`.</span></span>

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

<span data-ttu-id="2011e-143">Para obtener más información, vea [enumeraciones](enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="2011e-143">For more information, see [Enumerations](enumerations.md).</span></span>

## <a name="casting-object-types"></a><span data-ttu-id="2011e-144">Convertir tipos de objeto</span><span class="sxs-lookup"><span data-stu-id="2011e-144">Casting Object Types</span></span>

<span data-ttu-id="2011e-145">La conversión entre tipos en una jerarquía de objetos es fundamental para la programación orientada a objetos.</span><span class="sxs-lookup"><span data-stu-id="2011e-145">Conversion between types in an object hierarchy is fundamental to object-oriented programming.</span></span> <span data-ttu-id="2011e-146">Hay dos tipos básicos de conversiones: conversión hacia arriba (conversión) y conversión hacia abajo (downcasting).</span><span class="sxs-lookup"><span data-stu-id="2011e-146">There are two basic types of conversions: casting up (upcasting) and casting down (downcasting).</span></span> <span data-ttu-id="2011e-147">La conversión de una jerarquía significa la conversión de una referencia de objeto derivada a una referencia de objeto base.</span><span class="sxs-lookup"><span data-stu-id="2011e-147">Casting up a hierarchy means casting from a derived object reference to a base object reference.</span></span> <span data-ttu-id="2011e-148">Se garantiza que este tipo de conversión funciona siempre y cuando la clase base se encuentra en la jerarquía de herencia de la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="2011e-148">Such a cast is guaranteed to work as long as the base class is in the inheritance hierarchy of the derived class.</span></span> <span data-ttu-id="2011e-149">La conversión de una jerarquía de una referencia de objeto base a una referencia de objeto derivada solo se realiza correctamente si el objeto es realmente una instancia del tipo de destino (derivado) correcto o un tipo derivado del tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="2011e-149">Casting down a hierarchy, from a base object reference to a derived object reference, succeeds only if the object actually is an instance of the correct destination (derived) type or a type derived from the destination type.</span></span>

<span data-ttu-id="2011e-150">F#proporciona operadores para estos tipos de conversiones.</span><span class="sxs-lookup"><span data-stu-id="2011e-150">F# provides operators for these types of conversions.</span></span> <span data-ttu-id="2011e-151">El operador `:>` convierte hacia arriba la jerarquía y el operador `:?>` convierte en la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="2011e-151">The `:>` operator casts up the hierarchy, and the `:?>` operator casts down the hierarchy.</span></span>

### <a name="upcasting"></a><span data-ttu-id="2011e-152">Convertir</span><span class="sxs-lookup"><span data-stu-id="2011e-152">Upcasting</span></span>

<span data-ttu-id="2011e-153">En muchos lenguajes orientados a objetos, la conversión cruzada es implícita; en F#, las reglas son ligeramente diferentes.</span><span class="sxs-lookup"><span data-stu-id="2011e-153">In many object-oriented languages, upcasting is implicit; in F#, the rules are slightly different.</span></span> <span data-ttu-id="2011e-154">La conversión se aplica automáticamente cuando se pasan argumentos a métodos en un tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="2011e-154">Upcasting is applied automatically when you pass arguments to methods on an object type.</span></span> <span data-ttu-id="2011e-155">Sin embargo, en el caso de las funciones enlazadas a un módulo, la conversión cruzada no es automática, a menos que el tipo de parámetro se declare como un tipo flexible.</span><span class="sxs-lookup"><span data-stu-id="2011e-155">However, for let-bound functions in a module, upcasting is not automatic, unless the parameter type is declared as a flexible type.</span></span> <span data-ttu-id="2011e-156">Para obtener más información, vea [tipos flexibles](flexible-Types.md).</span><span class="sxs-lookup"><span data-stu-id="2011e-156">For more information, see [Flexible Types](flexible-Types.md).</span></span>

<span data-ttu-id="2011e-157">El operador `:>` realiza una conversión estática, lo que significa que el éxito de la conversión se determina en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="2011e-157">The `:>` operator performs a static cast, which means that the success of the cast is determined at compile time.</span></span> <span data-ttu-id="2011e-158">Si una conversión que usa `:>` se compila correctamente, es una conversión válida y no tiene posibilidad de errores en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2011e-158">If a cast that uses `:>` compiles successfully, it is a valid cast and has no chance of failure at run time.</span></span>

<span data-ttu-id="2011e-159">También puede usar el operador `upcast` para realizar esta conversión.</span><span class="sxs-lookup"><span data-stu-id="2011e-159">You can also use the `upcast` operator to perform such a conversion.</span></span> <span data-ttu-id="2011e-160">La expresión siguiente especifica una conversión hacia arriba en la jerarquía:</span><span class="sxs-lookup"><span data-stu-id="2011e-160">The following expression specifies a conversion up the hierarchy:</span></span>

```fsharp
upcast expression
```

<span data-ttu-id="2011e-161">Cuando se usa el operador de conversión, el compilador intenta deducir el tipo al que se va a convertir desde el contexto.</span><span class="sxs-lookup"><span data-stu-id="2011e-161">When you use the upcast operator, the compiler attempts to infer the type you are converting to from the context.</span></span> <span data-ttu-id="2011e-162">Si el compilador no puede determinar el tipo de destino, el compilador informa de un error.</span><span class="sxs-lookup"><span data-stu-id="2011e-162">If the compiler is unable to determine the target type, the compiler reports an error.</span></span> <span data-ttu-id="2011e-163">Es posible que se requiera una anotación de tipo.</span><span class="sxs-lookup"><span data-stu-id="2011e-163">A type annotation may be required.</span></span>

### <a name="downcasting"></a><span data-ttu-id="2011e-164">Downcasting</span><span class="sxs-lookup"><span data-stu-id="2011e-164">Downcasting</span></span>

<span data-ttu-id="2011e-165">El operador `:?>` realiza una conversión dinámica, lo que significa que el éxito de la conversión se determina en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2011e-165">The `:?>` operator performs a dynamic cast, which means that the success of the cast is determined at run time.</span></span> <span data-ttu-id="2011e-166">Una conversión que usa el operador `:?>` no se comprueba en tiempo de compilación; pero en tiempo de ejecución, se realiza un intento de conversión al tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="2011e-166">A cast that uses the `:?>` operator is not checked at compile time; but at run time, an attempt is made to cast to the specified type.</span></span> <span data-ttu-id="2011e-167">Si el objeto es compatible con el tipo de destino, la conversión se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="2011e-167">If the object is compatible with the target type, the cast succeeds.</span></span> <span data-ttu-id="2011e-168">Si el objeto no es compatible con el tipo de destino, el motor en tiempo de ejecución genera un `InvalidCastException`.</span><span class="sxs-lookup"><span data-stu-id="2011e-168">If the object is not compatible with the target type, the runtime raises an `InvalidCastException`.</span></span>

<span data-ttu-id="2011e-169">También puede usar el operador `downcast` para realizar una conversión de tipos dinámica.</span><span class="sxs-lookup"><span data-stu-id="2011e-169">You can also use the `downcast` operator to perform a dynamic type conversion.</span></span> <span data-ttu-id="2011e-170">La expresión siguiente especifica una conversión hacia abajo en la jerarquía hasta un tipo que se deduce del contexto del programa:</span><span class="sxs-lookup"><span data-stu-id="2011e-170">The following expression specifies a conversion down the hierarchy to a type that is inferred from program context:</span></span>

```fsharp
downcast expression
```

<span data-ttu-id="2011e-171">Como en el caso del operador `upcast`, si el compilador no puede inferir un tipo de destino específico del contexto, notifica un error.</span><span class="sxs-lookup"><span data-stu-id="2011e-171">As for the `upcast` operator, if the compiler cannot infer a specific target type from the context, it reports an error.</span></span> <span data-ttu-id="2011e-172">Es posible que se requiera una anotación de tipo.</span><span class="sxs-lookup"><span data-stu-id="2011e-172">A type annotation may be required.</span></span>

<span data-ttu-id="2011e-173">En el código siguiente se muestra el uso de los operadores `:>` y `:?>`.</span><span class="sxs-lookup"><span data-stu-id="2011e-173">The following code illustrates the use of the `:>` and `:?>` operators.</span></span> <span data-ttu-id="2011e-174">El código muestra que el operador de `:?>` se utiliza mejor cuando sabe que la conversión se realizará correctamente, ya que produce `InvalidCastException` si se produce un error en la conversión.</span><span class="sxs-lookup"><span data-stu-id="2011e-174">The code illustrates that the `:?>` operator is best used when you know that conversion will succeed, because it throws `InvalidCastException` if the conversion fails.</span></span> <span data-ttu-id="2011e-175">Si no sabe que una conversión se realizará correctamente, una prueba de tipo que use una expresión `match` es mejor porque evita la sobrecarga de generar una excepción.</span><span class="sxs-lookup"><span data-stu-id="2011e-175">If you do not know that a conversion will succeed, a type test that uses a `match` expression is better because it avoids the overhead of generating an exception.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

<span data-ttu-id="2011e-176">Dado que los operadores genéricos `downcast` y `upcast` dependen de la inferencia de tipos para determinar el argumento y el tipo de valor devuelto, en el código anterior, puede reemplazar</span><span class="sxs-lookup"><span data-stu-id="2011e-176">Because generic operators `downcast` and `upcast` rely on type inference to determine the argument and return type, in the above code, you can replace</span></span>

```fsharp
let base1 = d1 :> Base1
```

<span data-ttu-id="2011e-177">con</span><span class="sxs-lookup"><span data-stu-id="2011e-177">with</span></span>

```fsharp
let base1: Base1 = upcast d1
```

<span data-ttu-id="2011e-178">Tenga en cuenta que se requiere una anotación de tipo, ya que `upcast` por sí misma no pudo determinar la clase base.</span><span class="sxs-lookup"><span data-stu-id="2011e-178">Note that a type annotation is required, since `upcast` by itself could not determine the base class.</span></span>

## <a name="see-also"></a><span data-ttu-id="2011e-179">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2011e-179">See also</span></span>

- [<span data-ttu-id="2011e-180">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="2011e-180">F# Language Reference</span></span>](index.md)

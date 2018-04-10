---
title: Conversiones (F#)
description: 'Obtenga información acerca de cómo el lenguaje de programación de F # proporciona operadores de conversión para las conversiones aritméticas entre distintos tipos primitivos.'
keywords: visual f#, f#, programación funcional
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: db30db67-da21-4206-bf0c-9211bd3cb22f
ms.openlocfilehash: df8352b0dd8651f1480515311454a218ea79b971
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2018
---
# <a name="casting-and-conversions-f"></a><span data-ttu-id="52f00-104">Conversiones (F#)</span><span class="sxs-lookup"><span data-stu-id="52f00-104">Casting and Conversions (F#)</span></span>

<span data-ttu-id="52f00-105">Este tema describe la compatibilidad con las conversiones de tipos en F #.</span><span class="sxs-lookup"><span data-stu-id="52f00-105">This topic describes support for type conversions in F#.</span></span>

## <a name="arithmetic-types"></a><span data-ttu-id="52f00-106">Tipos aritméticos</span><span class="sxs-lookup"><span data-stu-id="52f00-106">Arithmetic Types</span></span>
<span data-ttu-id="52f00-107">F # proporciona operadores de conversión para las conversiones aritméticas entre distintos tipos primitivos, como entre enteros y tipos de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="52f00-107">F# provides conversion operators for arithmetic conversions between various primitive types, such as between integer and floating point types.</span></span> <span data-ttu-id="52f00-108">Los operadores de conversión de enteros y char se comprobaron y formularios no está activadas; el punto flotante operadores y `enum` operador de conversión no tienen que serlo.</span><span class="sxs-lookup"><span data-stu-id="52f00-108">The integral and char conversion operators have checked and unchecked forms; the floating point operators and the `enum` conversion operator do not.</span></span> <span data-ttu-id="52f00-109">Los formularios no está activados se definen en `Microsoft.FSharp.Core.Operators` y la activada, los formularios se definen en `Microsoft.FSharp.Core.Operators.Checked`.</span><span class="sxs-lookup"><span data-stu-id="52f00-109">The unchecked forms are defined in `Microsoft.FSharp.Core.Operators` and the checked forms are defined in `Microsoft.FSharp.Core.Operators.Checked`.</span></span> <span data-ttu-id="52f00-110">Las formas comprobadas comprobación el desbordamiento y generan una excepción en tiempo de ejecución si el valor resultante supera los límites del tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="52f00-110">The checked forms check for overflow and generate a runtime exception if the resulting value exceeds the limits of the target type.</span></span>

<span data-ttu-id="52f00-111">Cada uno de estos operadores tiene el mismo nombre que el nombre del tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="52f00-111">Each of these operators has the same name as the name of the destination type.</span></span> <span data-ttu-id="52f00-112">Por ejemplo, en el código siguiente, en el que los tipos se anotan explícitamente, `byte` aparece con dos significados diferentes.</span><span class="sxs-lookup"><span data-stu-id="52f00-112">For example, in the following code, in which the types are explicitly annotated, `byte` appears with two different meanings.</span></span> <span data-ttu-id="52f00-113">La primera aparición es el tipo y el segundo es el operador de conversión.</span><span class="sxs-lookup"><span data-stu-id="52f00-113">The first occurrence is the type and the second is the conversion operator.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

<span data-ttu-id="52f00-114">La siguiente tabla muestra los operadores de conversión definidos en F #.</span><span class="sxs-lookup"><span data-stu-id="52f00-114">The following table shows conversion operators defined in F#.</span></span>

|<span data-ttu-id="52f00-115">Operador</span><span class="sxs-lookup"><span data-stu-id="52f00-115">Operator</span></span>|<span data-ttu-id="52f00-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="52f00-116">Description</span></span>|
|--------|-----------|
|`byte`|<span data-ttu-id="52f00-117">Convertir en un byte, un tipo sin signo de 8 bits.</span><span class="sxs-lookup"><span data-stu-id="52f00-117">Convert to byte, an 8-bit unsigned type.</span></span>|
|`sbyte`|<span data-ttu-id="52f00-118">Convertir en un byte con signo.</span><span class="sxs-lookup"><span data-stu-id="52f00-118">Convert to signed byte.</span></span>|
|`int16`|<span data-ttu-id="52f00-119">Convertir en un entero de 16 bits con signo.</span><span class="sxs-lookup"><span data-stu-id="52f00-119">Convert to a 16-bit signed integer.</span></span>|
|`uint16`|<span data-ttu-id="52f00-120">Convertir en un entero de 16 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="52f00-120">Convert to a 16-bit unsigned integer.</span></span>|
|`int32, int`|<span data-ttu-id="52f00-121">Convertir en un entero de 32 bits con signo.</span><span class="sxs-lookup"><span data-stu-id="52f00-121">Convert to a 32-bit signed integer.</span></span>|
|`uint32`|<span data-ttu-id="52f00-122">Convertir en un entero de 32 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="52f00-122">Convert to a 32-bit unsigned integer.</span></span>|
|`int64`|<span data-ttu-id="52f00-123">Convertir en un entero de 64 bits con signo.</span><span class="sxs-lookup"><span data-stu-id="52f00-123">Convert to a 64-bit signed integer.</span></span>|
|`uint64`|<span data-ttu-id="52f00-124">Convertir en un entero de 64 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="52f00-124">Convert to a 64-bit unsigned integer.</span></span>|
|`nativeint`|<span data-ttu-id="52f00-125">Convertir en un entero nativo.</span><span class="sxs-lookup"><span data-stu-id="52f00-125">Convert to a native integer.</span></span>|
|`unativeint`|<span data-ttu-id="52f00-126">Convertir en un entero nativo sin signo.</span><span class="sxs-lookup"><span data-stu-id="52f00-126">Convert to an unsigned native integer.</span></span>|
|`float, double`|<span data-ttu-id="52f00-127">Convertir en un IEEE de doble precisión de 64 bits números de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="52f00-127">Convert to a 64-bit double-precision IEEE floating point number.</span></span>|
|`float32, single`|<span data-ttu-id="52f00-128">Convertir en un IEEE de precisión sencilla de 32 bits números de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="52f00-128">Convert to a 32-bit single-precision IEEE floating point number.</span></span>|
|`decimal`|<span data-ttu-id="52f00-129">Convertir en `System.Decimal`.</span><span class="sxs-lookup"><span data-stu-id="52f00-129">Convert to `System.Decimal`.</span></span>|
|`char`|<span data-ttu-id="52f00-130">Convertir en `System.Char`, un carácter Unicode.</span><span class="sxs-lookup"><span data-stu-id="52f00-130">Convert to `System.Char`, a Unicode character.</span></span>|
|`enum`|<span data-ttu-id="52f00-131">Convertir a un tipo enumerado.</span><span class="sxs-lookup"><span data-stu-id="52f00-131">Convert to an enumerated type.</span></span>|
<span data-ttu-id="52f00-132">Además de los tipos primitivos integrados, puede utilizar estos operadores con tipos que implementan `op_Explicit` o `op_Implicit` métodos con firmas adecuadas.</span><span class="sxs-lookup"><span data-stu-id="52f00-132">In addition to built-in primitive types, you can use these operators with types that implement `op_Explicit` or `op_Implicit` methods with appropriate signatures.</span></span> <span data-ttu-id="52f00-133">Por ejemplo, el `int` operador de conversión funciona con cualquier tipo que proporciona un método estático `op_Explicit` que toma el tipo como un parámetro y devuelve `int`.</span><span class="sxs-lookup"><span data-stu-id="52f00-133">For example, the `int` conversion operator works with any type that provides a static method `op_Explicit` that takes the type as a parameter and returns `int`.</span></span> <span data-ttu-id="52f00-134">Como una excepción especial para el que no se pueden sobrecargar métodos por tipo de valor devuelto por regla general, también puede hacer esto para `op_Explicit` y `op_Implicit`.</span><span class="sxs-lookup"><span data-stu-id="52f00-134">As a special exception to the general rule that methods cannot be overloaded by return type, you can do this for `op_Explicit` and `op_Implicit`.</span></span>

## <a name="enumerated-types"></a><span data-ttu-id="52f00-135">Tipos enumerados</span><span class="sxs-lookup"><span data-stu-id="52f00-135">Enumerated Types</span></span>
<span data-ttu-id="52f00-136">El `enum` es un operador genérico que toma un parámetro de tipo que representa el tipo de la `enum` para convertir en.</span><span class="sxs-lookup"><span data-stu-id="52f00-136">The `enum` operator is a generic operator that takes one type parameter that represents the type of the `enum` to convert to.</span></span> <span data-ttu-id="52f00-137">Cuando convierte en un tipo enumerado, escriba inferencia intenta determinar el tipo de la `enum` que desea convertir.</span><span class="sxs-lookup"><span data-stu-id="52f00-137">When it converts to an enumerated type, type inference attempts to determine the type of the `enum` that you want to convert to.</span></span> <span data-ttu-id="52f00-138">En el ejemplo siguiente, la variable `col1` no está anotada explícitamente, pero su tipo se deduce de la prueba de igualdad posterior.</span><span class="sxs-lookup"><span data-stu-id="52f00-138">In the following example, the variable `col1` is not explicitly annotated, but its type is inferred from the later equality test.</span></span> <span data-ttu-id="52f00-139">Por lo tanto, el compilador puede deducir que va a convertir en un `Color` enumeración.</span><span class="sxs-lookup"><span data-stu-id="52f00-139">Therefore, the compiler can deduce that you are converting to a `Color` enumeration.</span></span> <span data-ttu-id="52f00-140">Como alternativa, puede proporcionar una anotación de tipo, al igual que con `col2` en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="52f00-140">Alternatively, you can supply a type annotation, as with `col2` in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]
    
<span data-ttu-id="52f00-141">También puede especificar explícitamente el tipo de enumeración de destino como un parámetro de tipo, como en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="52f00-141">You can also specify the target enumeration type explicitly as a type parameter, as in the following code:</span></span>

```fsharp
let col3 = enum<Color> 3
```

<span data-ttu-id="52f00-142">Tenga en cuenta que la enumeración convierte trabajo solo si el tipo subyacente de la enumeración es compatible con el tipo que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="52f00-142">Note that the enumeration casts work only if the underlying type of the enumeration is compatible with the type being converted.</span></span> <span data-ttu-id="52f00-143">En el código siguiente, la conversión no se puede compilar debido a la falta de correspondencia entre `int32` y `uint32`.</span><span class="sxs-lookup"><span data-stu-id="52f00-143">In the following code, the conversion fails to compile because of the mismatch between `int32` and `uint32`.</span></span>

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

<span data-ttu-id="52f00-144">Para obtener más información, consulte [enumeraciones](enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="52f00-144">For more information, see [Enumerations](enumerations.md).</span></span>

## <a name="casting-object-types"></a><span data-ttu-id="52f00-145">Conversión de tipos de objeto</span><span class="sxs-lookup"><span data-stu-id="52f00-145">Casting Object Types</span></span>
<span data-ttu-id="52f00-146">Conversión entre tipos en una jerarquía de objetos, es fundamental para la programación orientada a objetos.</span><span class="sxs-lookup"><span data-stu-id="52f00-146">Conversion between types in an object hierarchy is fundamental to object-oriented programming.</span></span> <span data-ttu-id="52f00-147">Hay dos tipos básicos de conversiones: (conversión hacia arriba) de conversión y conversión en tipos inferiores (conversión).</span><span class="sxs-lookup"><span data-stu-id="52f00-147">There are two basic types of conversions: casting up (upcasting) and casting down (downcasting).</span></span> <span data-ttu-id="52f00-148">Conversión de una jerarquía significa que la conversión de una referencia a objeto derivada a una referencia de objeto base.</span><span class="sxs-lookup"><span data-stu-id="52f00-148">Casting up a hierarchy means casting from a derived object reference to a base object reference.</span></span> <span data-ttu-id="52f00-149">Se garantiza que una conversión de tipos para que funcione como la clase base está en la jerarquía de herencia de la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="52f00-149">Such a cast is guaranteed to work as long as the base class is in the inheritance hierarchy of the derived class.</span></span> <span data-ttu-id="52f00-150">Conversión de una jerarquía, de una referencia de objeto base para una referencia de objeto derivado, se realiza correctamente sólo si el objeto es realmente una instancia del tipo de destino correcto (derivado) o un tipo derivado del tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="52f00-150">Casting down a hierarchy, from a base object reference to a derived object reference, succeeds only if the object actually is an instance of the correct destination (derived) type or a type derived from the destination type.</span></span>

<span data-ttu-id="52f00-151">F # proporciona operadores para estos tipos de conversiones.</span><span class="sxs-lookup"><span data-stu-id="52f00-151">F# provides operators for these types of conversions.</span></span> <span data-ttu-id="52f00-152">El `:>` operador convierte hacia arriba en la jerarquía y el `:?>` operador convierte hacia abajo en la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="52f00-152">The `:>` operator casts up the hierarchy, and the `:?>` operator casts down the hierarchy.</span></span>

### <a name="upcasting"></a><span data-ttu-id="52f00-153">Conversión hacia arriba</span><span class="sxs-lookup"><span data-stu-id="52f00-153">Upcasting</span></span>
<span data-ttu-id="52f00-154">En muchos lenguajes orientados a objetos, una conversión es implícita; en F #, las reglas son ligeramente diferentes.</span><span class="sxs-lookup"><span data-stu-id="52f00-154">In many object-oriented languages, upcasting is implicit; in F#, the rules are slightly different.</span></span> <span data-ttu-id="52f00-155">Conversión hacia arriba se aplica automáticamente cuando se pasan argumentos a los métodos en un tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="52f00-155">Upcasting is applied automatically when you pass arguments to methods on an object type.</span></span> <span data-ttu-id="52f00-156">Sin embargo, para las funciones enlazadas a permiten en un módulo, una conversión no es automática, a menos que el tipo de parámetro se declara como un tipo flexible.</span><span class="sxs-lookup"><span data-stu-id="52f00-156">However, for let-bound functions in a module, upcasting is not automatic, unless the parameter type is declared as a flexible type.</span></span> <span data-ttu-id="52f00-157">Para obtener más información, consulte [tipos flexibles](flexible-Types.md).</span><span class="sxs-lookup"><span data-stu-id="52f00-157">For more information, see [Flexible Types](flexible-Types.md).</span></span>

<span data-ttu-id="52f00-158">El `:>` operador realiza una conversión de tipos, lo que significa que el éxito de la conversión se determina en tiempo de compilación estática.</span><span class="sxs-lookup"><span data-stu-id="52f00-158">The `:>` operator performs a static cast, which means that the success of the cast is determined at compile time.</span></span> <span data-ttu-id="52f00-159">Si una conversión que utiliza `:>` se compila correctamente, es una conversión válida y no tiene ninguna posibilidad de error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="52f00-159">If a cast that uses `:>` compiles successfully, it is a valid cast and has no chance of failure at run time.</span></span>

<span data-ttu-id="52f00-160">También puede usar el `upcast` operador para realizar este tipo de conversión.</span><span class="sxs-lookup"><span data-stu-id="52f00-160">You can also use the `upcast` operator to perform such a conversion.</span></span> <span data-ttu-id="52f00-161">La expresión siguiente especifica una conversión hacia arriba en la jerarquía:</span><span class="sxs-lookup"><span data-stu-id="52f00-161">The following expression specifies a conversion up the hierarchy:</span></span>

```fsharp
upcast expression
```

<span data-ttu-id="52f00-162">Cuando se usa el upcast (operador), el compilador intenta inferir el tipo que se va a convertir a partir del contexto.</span><span class="sxs-lookup"><span data-stu-id="52f00-162">When you use the upcast operator, the compiler attempts to infer the type you are converting to from the context.</span></span> <span data-ttu-id="52f00-163">Si el compilador no puede determinar el tipo de destino, el compilador informa de un error.</span><span class="sxs-lookup"><span data-stu-id="52f00-163">If the compiler is unable to determine the target type, the compiler reports an error.</span></span>

### <a name="downcasting"></a><span data-ttu-id="52f00-164">Convertir a tipo heredado</span><span class="sxs-lookup"><span data-stu-id="52f00-164">Downcasting</span></span>
<span data-ttu-id="52f00-165">El `:?>` operador realiza una conversión de tipos, lo que significa que el éxito de la conversión se determina en tiempo de ejecución dinámica.</span><span class="sxs-lookup"><span data-stu-id="52f00-165">The `:?>` operator performs a dynamic cast, which means that the success of the cast is determined at run time.</span></span> <span data-ttu-id="52f00-166">Una conversión que utiliza el `:?>` operador no se comprueba en tiempo de compilación; pero en tiempo de ejecución, se realiza un intento para convertir al tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="52f00-166">A cast that uses the `:?>` operator is not checked at compile time; but at run time, an attempt is made to cast to the specified type.</span></span> <span data-ttu-id="52f00-167">Si el objeto es compatible con el tipo de destino, la conversión se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="52f00-167">If the object is compatible with the target type, the cast succeeds.</span></span> <span data-ttu-id="52f00-168">Si el objeto no es compatible con el tipo de destino, el tiempo de ejecución genera un `InvalidCastException`.</span><span class="sxs-lookup"><span data-stu-id="52f00-168">If the object is not compatible with the target type, the runtime raises an `InvalidCastException`.</span></span>

<span data-ttu-id="52f00-169">También puede usar el `downcast` operador que se va a realizar una conversión de tipo dinámico.</span><span class="sxs-lookup"><span data-stu-id="52f00-169">You can also use the `downcast` operator to perform a dynamic type conversion.</span></span> <span data-ttu-id="52f00-170">La expresión siguiente especifica una conversión hacia abajo en la jerarquía a un tipo que se deduce del contexto de programa:</span><span class="sxs-lookup"><span data-stu-id="52f00-170">The following expression specifies a conversion down the hierarchy to a type that is inferred from program context:</span></span>

```fsharp
downcast expression
```

<span data-ttu-id="52f00-171">Igual que en el `upcast` (operador), si el compilador no puede inferir un tipo de destino específico en el contexto, notifica un error.</span><span class="sxs-lookup"><span data-stu-id="52f00-171">As for the `upcast` operator, if the compiler cannot infer a specific target type from the context, it reports an error.</span></span>

<span data-ttu-id="52f00-172">El código siguiente muestra el uso de la `:>` y `:?>` operadores.</span><span class="sxs-lookup"><span data-stu-id="52f00-172">The following code illustrates the use of the `:>` and `:?>` operators.</span></span> <span data-ttu-id="52f00-173">El código que muestra la `:?>` operador se usa mejor cuando se sabe que conversión se realizará correctamente, porque produce `InvalidCastException` si se produce un error en la conversión.</span><span class="sxs-lookup"><span data-stu-id="52f00-173">The code illustrates that the `:?>` operator is best used when you know that conversion will succeed, because it throws `InvalidCastException` if the conversion fails.</span></span> <span data-ttu-id="52f00-174">Si no sabe que una conversión se realizará correctamente, una prueba de tipo que utiliza un `match` expresión es mejor porque evita la sobrecarga de generar una excepción.</span><span class="sxs-lookup"><span data-stu-id="52f00-174">If you do not know that a conversion will succeed, a type test that uses a `match` expression is better because it avoids the overhead of generating an exception.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

<span data-ttu-id="52f00-175">Dado que operadores genéricos `downcast` y `upcast` se basan en la inferencia de tipos para determinar el tipo de argumentos y valores devueltos, en el código anterior, puede reemplazar</span><span class="sxs-lookup"><span data-stu-id="52f00-175">Because generic operators `downcast` and `upcast` rely on type inference to determine the argument and return type, in the above code, you can replace</span></span>

```fsharp
let base1 = d1 :> Base1
```

<span data-ttu-id="52f00-176">with</span><span class="sxs-lookup"><span data-stu-id="52f00-176">with</span></span>

```fsharp
let base1 = upcast d1
```

<span data-ttu-id="52f00-177">En el código anterior, el tipo de argumento y los tipos de valor devuelto son `Derived1` y `Base1`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="52f00-177">In the previous code, the argument type and return types are `Derived1` and `Base1`, respectively.</span></span>

<span data-ttu-id="52f00-178">Para obtener más información acerca de las pruebas de tipo, consulte [expresiones de coincidencia](match-Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="52f00-178">For more information about type tests, see [Match Expressions](match-Expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="52f00-179">Vea también</span><span class="sxs-lookup"><span data-stu-id="52f00-179">See Also</span></span>
[<span data-ttu-id="52f00-180">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="52f00-180">F# Language Reference</span></span>](index.md)

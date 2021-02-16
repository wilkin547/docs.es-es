---
description: 'Más información sobre: conversiones implícitas y explícitas (Visual Basic)'
title: Conversiones implícitas y explícitas
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [Visual Basic], type
- variables [Visual Basic], changing data type
- casting
- conversions [Visual Basic], data type
- type conversion [Visual Basic], implicit conversions
- CType function [Visual Basic], conversions
- casting, data types
- data type conversion [Visual Basic], explicit
- type conversion [Visual Basic], explicit conversions
- data types [Visual Basic], casting
- conversions [Visual Basic], implicit
- explicit data type conversions [Visual Basic]
- conversions [Visual Basic]
- changing data types [Visual Basic]
- conversions [Visual Basic], explicit
- data type conversion [Visual Basic], implicit
- implicit data type conversions [Visual Basic]
ms.assetid: 77de1659-af8a-492c-967e-e7ef60ccce66
ms.openlocfilehash: 6a53c0998025cc8c19274c67d9dfe1c50a4f1373
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100483955"
---
# <a name="implicit-and-explicit-conversions-visual-basic"></a><span data-ttu-id="62020-103">Conversiones implícita y explícita (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62020-103">Implicit and Explicit Conversions (Visual Basic)</span></span>

<span data-ttu-id="62020-104">Una *conversión implícita* no requiere ninguna sintaxis especial en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="62020-104">An *implicit conversion* does not require any special syntax in the source code.</span></span> <span data-ttu-id="62020-105">En el ejemplo siguiente, Visual Basic convierte implícitamente el valor de `k` en un valor de punto flotante de precisión sencilla antes de asignarlo a `q` .</span><span class="sxs-lookup"><span data-stu-id="62020-105">In the following example, Visual Basic implicitly converts the value of `k` to a single-precision floating-point value before assigning it to `q`.</span></span>

```vb
Dim k As Integer
Dim q As Double
' Integer widens to Double, so you can do this with Option Strict On.
k = 432
q = k
```

<span data-ttu-id="62020-106">Una *conversión explícita* utiliza una palabra clave de conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="62020-106">An *explicit conversion* uses a type conversion keyword.</span></span> <span data-ttu-id="62020-107">Visual Basic proporciona varias palabras clave, que convierten una expresión entre paréntesis en el tipo de datos deseado.</span><span class="sxs-lookup"><span data-stu-id="62020-107">Visual Basic provides several such keywords, which coerce an expression in parentheses to the desired data type.</span></span> <span data-ttu-id="62020-108">Estas palabras clave actúan como funciones, pero el compilador genera el código insertado, por lo que la ejecución es ligeramente más rápida que con una llamada de función.</span><span class="sxs-lookup"><span data-stu-id="62020-108">These keywords act like functions, but the compiler generates the code inline, so execution is slightly faster than with a function call.</span></span>

<span data-ttu-id="62020-109">En la siguiente extensión del ejemplo anterior, la `CInt` palabra clave convierte el valor de de `q` nuevo en un entero antes de asignarlo a `k` .</span><span class="sxs-lookup"><span data-stu-id="62020-109">In the following extension of the preceding example, the `CInt` keyword converts the value of `q` back to an integer before assigning it to `k`.</span></span>

```vb
' q had been assigned the value 432 from k.
q = Math.Sqrt(q)
k = CInt(q)
' k now has the value 21 (rounded square root of 432).
```

## <a name="conversion-keywords"></a><span data-ttu-id="62020-110">Palabras clave para conversiones</span><span class="sxs-lookup"><span data-stu-id="62020-110">Conversion Keywords</span></span>

<span data-ttu-id="62020-111">En la tabla siguiente se muestran las palabras clave de conversión disponibles.</span><span class="sxs-lookup"><span data-stu-id="62020-111">The following table shows the available conversion keywords.</span></span>

|<span data-ttu-id="62020-112">Palabra clave de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="62020-112">Type conversion keyword</span></span>|<span data-ttu-id="62020-113">Convierte una expresión al tipo de datos</span><span class="sxs-lookup"><span data-stu-id="62020-113">Converts an expression to data type</span></span>|<span data-ttu-id="62020-114">Tipos de datos permitidos de la expresión que se va a convertir</span><span class="sxs-lookup"><span data-stu-id="62020-114">Allowable data types of expression to be converted</span></span>|
|---|---|---|
|`CBool`|[<span data-ttu-id="62020-115">Tipo de datos Boolean</span><span class="sxs-lookup"><span data-stu-id="62020-115">Boolean Data Type</span></span>](../../../language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="62020-116">Cualquier tipo numérico (incluidos `Byte` los `SByte` tipos enumerados, y), `String` , `Object`</span><span class="sxs-lookup"><span data-stu-id="62020-116">Any numeric type (including `Byte`, `SByte`, and enumerated types), `String`, `Object`</span></span>|
|`CByte`|[<span data-ttu-id="62020-117">Tipo de datos Byte</span><span class="sxs-lookup"><span data-stu-id="62020-117">Byte Data Type</span></span>](../../../language-reference/data-types/byte-data-type.md)|<span data-ttu-id="62020-118">Cualquier tipo numérico (incluidos `SByte` y tipos enumerados), `Boolean` , `String` , `Object`</span><span class="sxs-lookup"><span data-stu-id="62020-118">Any numeric type (including `SByte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CChar`|[<span data-ttu-id="62020-119">Tipo de datos Char</span><span class="sxs-lookup"><span data-stu-id="62020-119">Char Data Type</span></span>](../../../language-reference/data-types/char-data-type.md)|<span data-ttu-id="62020-120">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="62020-120">`String`, `Object`</span></span>|
|`CDate`|[<span data-ttu-id="62020-121">Tipo de datos Date</span><span class="sxs-lookup"><span data-stu-id="62020-121">Date Data Type</span></span>](../../../language-reference/data-types/date-data-type.md)|<span data-ttu-id="62020-122">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="62020-122">`String`, `Object`</span></span>|
|`CDbl`|[<span data-ttu-id="62020-123">Tipo de datos Double</span><span class="sxs-lookup"><span data-stu-id="62020-123">Double Data Type</span></span>](../../../language-reference/data-types/double-data-type.md)|<span data-ttu-id="62020-124">Cualquier tipo numérico (incluidos `Byte` los `SByte` tipos enumerados, y), `Boolean` , `String` , `Object`</span><span class="sxs-lookup"><span data-stu-id="62020-124">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CDec`|[<span data-ttu-id="62020-125">Tipo de datos Decimal</span><span class="sxs-lookup"><span data-stu-id="62020-125">Decimal Data Type</span></span>](../../../language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="62020-126">Cualquier tipo numérico (incluidos `Byte` los `SByte` tipos enumerados, y), `Boolean` , `String` , `Object`</span><span class="sxs-lookup"><span data-stu-id="62020-126">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CInt`|[<span data-ttu-id="62020-127">Tipo de datos Integer</span><span class="sxs-lookup"><span data-stu-id="62020-127">Integer Data Type</span></span>](../../../language-reference/data-types/integer-data-type.md)|<span data-ttu-id="62020-128">Cualquier tipo numérico (incluidos `Byte` los `SByte` tipos enumerados, y), `Boolean` , `String` , `Object`</span><span class="sxs-lookup"><span data-stu-id="62020-128">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CLng`|[<span data-ttu-id="62020-129">Tipo de datos Long</span><span class="sxs-lookup"><span data-stu-id="62020-129">Long Data Type</span></span>](../../../language-reference/data-types/long-data-type.md)|<span data-ttu-id="62020-130">Cualquier tipo numérico (incluidos `Byte` los `SByte` tipos enumerados, y), `Boolean` , `String` , `Object`</span><span class="sxs-lookup"><span data-stu-id="62020-130">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CObj`|[<span data-ttu-id="62020-131">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="62020-131">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)|<span data-ttu-id="62020-132">Cualquier tipo</span><span class="sxs-lookup"><span data-stu-id="62020-132">Any type</span></span>|
|`CSByte`|[<span data-ttu-id="62020-133">Tipo de datos SByte</span><span class="sxs-lookup"><span data-stu-id="62020-133">SByte Data Type</span></span>](../../../language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="62020-134">Cualquier tipo numérico (incluidos `Byte` y tipos enumerados), `Boolean` , `String` , `Object`</span><span class="sxs-lookup"><span data-stu-id="62020-134">Any numeric type (including `Byte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CShort`|[<span data-ttu-id="62020-135">Tipo de datos Short</span><span class="sxs-lookup"><span data-stu-id="62020-135">Short Data Type</span></span>](../../../language-reference/data-types/short-data-type.md)|<span data-ttu-id="62020-136">Cualquier tipo numérico (incluidos `Byte` los `SByte` tipos enumerados, y), `Boolean` , `String` , `Object`</span><span class="sxs-lookup"><span data-stu-id="62020-136">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CSng`|[<span data-ttu-id="62020-137">Tipo de datos Single</span><span class="sxs-lookup"><span data-stu-id="62020-137">Single Data Type</span></span>](../../../language-reference/data-types/single-data-type.md)|<span data-ttu-id="62020-138">Cualquier tipo numérico (incluidos `Byte` los `SByte` tipos enumerados, y), `Boolean` , `String` , `Object`</span><span class="sxs-lookup"><span data-stu-id="62020-138">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CStr`|[<span data-ttu-id="62020-139">String (Tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="62020-139">String Data Type</span></span>](../../../language-reference/data-types/string-data-type.md)|<span data-ttu-id="62020-140">Cualquier tipo numérico (incluidos `Byte` los `SByte` tipos enumerados, y), `Boolean` , `Char` , `Char` array, `Date` , `Object`</span><span class="sxs-lookup"><span data-stu-id="62020-140">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `Char`, `Char` array, `Date`, `Object`</span></span>|
|`CType`|<span data-ttu-id="62020-141">Tipo especificado después de la coma ( `,` )</span><span class="sxs-lookup"><span data-stu-id="62020-141">Type specified following the comma (`,`)</span></span>|<span data-ttu-id="62020-142">Al convertir a un *tipo de datos elemental* (incluida una matriz de un tipo elemental), los mismos tipos que se permiten para la palabra clave de conversión correspondiente</span><span class="sxs-lookup"><span data-stu-id="62020-142">When converting to an *elementary data type* (including an array of an elementary type), the same types as allowed for the corresponding conversion keyword</span></span><br /><br /> <span data-ttu-id="62020-143">Al convertir a un *tipo de datos compuesto*, las interfaces que implementa y las clases de las que hereda</span><span class="sxs-lookup"><span data-stu-id="62020-143">When converting to a *composite data type*, the interfaces it implements and the classes from which it inherits</span></span><br /><br /> <span data-ttu-id="62020-144">Al convertir a una clase o estructura en la que se ha sobrecargado `CType` , esa clase o estructura</span><span class="sxs-lookup"><span data-stu-id="62020-144">When converting to a class or structure on which you have overloaded `CType`, that class or structure</span></span>|
|`CUInt`|[<span data-ttu-id="62020-145">Tipo de datos UInteger</span><span class="sxs-lookup"><span data-stu-id="62020-145">UInteger Data Type</span></span>](../../../language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="62020-146">Cualquier tipo numérico (incluidos `Byte` los `SByte` tipos enumerados, y), `Boolean` , `String` , `Object`</span><span class="sxs-lookup"><span data-stu-id="62020-146">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CULng`|[<span data-ttu-id="62020-147">Tipo de datos ULong</span><span class="sxs-lookup"><span data-stu-id="62020-147">ULong Data Type</span></span>](../../../language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="62020-148">Cualquier tipo numérico (incluidos `Byte` los `SByte` tipos enumerados, y), `Boolean` , `String` , `Object`</span><span class="sxs-lookup"><span data-stu-id="62020-148">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CUShort`|[<span data-ttu-id="62020-149">Tipo de datos UShort</span><span class="sxs-lookup"><span data-stu-id="62020-149">UShort Data Type</span></span>](../../../language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="62020-150">Cualquier tipo numérico (incluidos `Byte` los `SByte` tipos enumerados, y), `Boolean` , `String` , `Object`</span><span class="sxs-lookup"><span data-stu-id="62020-150">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|

## <a name="the-ctype-function"></a><span data-ttu-id="62020-151">La función CType</span><span class="sxs-lookup"><span data-stu-id="62020-151">The CType Function</span></span>

<span data-ttu-id="62020-152">La [función ctype](../../../language-reference/functions/ctype-function.md) funciona con dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="62020-152">The [CType Function](../../../language-reference/functions/ctype-function.md) operates on two arguments.</span></span> <span data-ttu-id="62020-153">El primero es la expresión que se va a convertir y el segundo es el tipo de datos de destino o la clase de objeto.</span><span class="sxs-lookup"><span data-stu-id="62020-153">The first is the expression to be converted, and the second is the destination data type or object class.</span></span> <span data-ttu-id="62020-154">Tenga en cuenta que el primer argumento debe ser una expresión, no un tipo.</span><span class="sxs-lookup"><span data-stu-id="62020-154">Note that the first argument must be an expression, not a type.</span></span>

<span data-ttu-id="62020-155">`CType` es una *función insertada*, lo que significa que el código compilado realiza la conversión, a menudo sin generar una llamada de función.</span><span class="sxs-lookup"><span data-stu-id="62020-155">`CType` is an *inline function*, meaning the compiled code makes the conversion, often without generating a function call.</span></span> <span data-ttu-id="62020-156">De este modo se aumenta el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="62020-156">This improves performance.</span></span>

<span data-ttu-id="62020-157">Para obtener una comparación de `CType` con las otras palabras clave de conversión de tipos, vea operador [DirectCast](../../../language-reference/operators/directcast-operator.md) y [operador TryCast](../../../language-reference/operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="62020-157">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../language-reference/operators/trycast-operator.md).</span></span>

### <a name="elementary-types"></a><span data-ttu-id="62020-158">Tipos elementales</span><span class="sxs-lookup"><span data-stu-id="62020-158">Elementary Types</span></span>

<span data-ttu-id="62020-159">El siguiente ejemplo muestra el uso de `CType`.</span><span class="sxs-lookup"><span data-stu-id="62020-159">The following example demonstrates the use of `CType`.</span></span>

```vb
k = CType(q, Integer)
' The following statement coerces w to the specific object class Label.
f = CType(w, Label)
```

### <a name="composite-types"></a><span data-ttu-id="62020-160">Tipos compuestos</span><span class="sxs-lookup"><span data-stu-id="62020-160">Composite Types</span></span>

<span data-ttu-id="62020-161">Puede usar `CType` para convertir valores en tipos de datos compuestos y en tipos elementales.</span><span class="sxs-lookup"><span data-stu-id="62020-161">You can use `CType` to convert values to composite data types as well as to elementary types.</span></span> <span data-ttu-id="62020-162">También se puede utilizar para forzar una clase de objeto al tipo de una de sus interfaces, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="62020-162">You can also use it to coerce an object class to the type of one of its interfaces, as in the following example.</span></span>

```vb
' Assume class cZone implements interface iZone.
Dim h As Object
' The first argument to CType must be an expression, not a type.
Dim cZ As cZone
' The following statement coerces a cZone object to its interface iZone.
h = CType(cZ, iZone)
```

### <a name="array-types"></a><span data-ttu-id="62020-163">Tipos de matriz</span><span class="sxs-lookup"><span data-stu-id="62020-163">Array Types</span></span>

<span data-ttu-id="62020-164">`CType` también puede convertir los tipos de datos de matriz, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="62020-164">`CType` can also convert array data types, as in the following example.</span></span>

```vb
Dim v() As classV
Dim obArray() As Object
' Assume some object array has been assigned to obArray.
' Check for run-time type compatibility.
If TypeOf obArray Is classV()
    ' obArray can be converted to classV.
    v = CType(obArray, classV())
End If
```

<span data-ttu-id="62020-165">Para obtener más información y un ejemplo, vea [conversiones de matrices](array-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="62020-165">For more information and an example, see [Array Conversions](array-conversions.md).</span></span>

### <a name="types-defining-ctype"></a><span data-ttu-id="62020-166">Tipos que definen CType</span><span class="sxs-lookup"><span data-stu-id="62020-166">Types Defining CType</span></span>

<span data-ttu-id="62020-167">Puede definir `CType` en una clase o estructura que haya definido.</span><span class="sxs-lookup"><span data-stu-id="62020-167">You can define `CType` on a class or structure you have defined.</span></span> <span data-ttu-id="62020-168">Esto le permite convertir valores a y desde el tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="62020-168">This allows you to convert values to and from the type of your class or structure.</span></span> <span data-ttu-id="62020-169">Para obtener más información y un ejemplo, vea [Cómo: definir un operador de conversión](../procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="62020-169">For more information and an example, see [How to: Define a Conversion Operator](../procedures/how-to-define-a-conversion-operator.md).</span></span>

> [!NOTE]
> <span data-ttu-id="62020-170">Los valores utilizados con una palabra clave de conversión deben ser válidos para el tipo de datos de destino o se produce un error.</span><span class="sxs-lookup"><span data-stu-id="62020-170">Values used with a conversion keyword must be valid for the destination data type, or an error occurs.</span></span> <span data-ttu-id="62020-171">Por ejemplo, si intenta convertir `Long` en `Integer` , el valor de `Long` debe estar dentro del intervalo válido para el `Integer` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="62020-171">For example, if you attempt to convert a `Long` to an `Integer`, the value of the `Long` must be within the valid range for the `Integer` data type.</span></span>

> [!CAUTION]
> <span data-ttu-id="62020-172">`CType`Si se especifica que se realice la conversión de un tipo de clase a otro, se producirá un error en tiempo de ejecución si el tipo de origen no se deriva del tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="62020-172">Specifying `CType` to convert from one class type to another fails at run time if the source type does not derive from the destination type.</span></span> <span data-ttu-id="62020-173">Este tipo de error produce una <xref:System.InvalidCastException> excepción.</span><span class="sxs-lookup"><span data-stu-id="62020-173">Such a failure throws an <xref:System.InvalidCastException> exception.</span></span>

<span data-ttu-id="62020-174">Sin embargo, si uno de los tipos es una estructura o clase definida, y si ha definido `CType` en esa estructura o clase, una conversión puede realizarse correctamente si satisface los requisitos de `CType` .</span><span class="sxs-lookup"><span data-stu-id="62020-174">However, if one of the types is a structure or class you have defined, and if you have defined `CType` on that structure or class, a conversion can succeed if it satisfies the requirements of your `CType`.</span></span> <span data-ttu-id="62020-175">Vea [Cómo: definir un operador de conversión](../procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="62020-175">See [How to: Define a Conversion Operator](../procedures/how-to-define-a-conversion-operator.md).</span></span>

<span data-ttu-id="62020-176">La realización de una conversión explícita también se conoce como *convertir* una expresión en un tipo de datos o clase de objeto determinado.</span><span class="sxs-lookup"><span data-stu-id="62020-176">Performing an explicit conversion is also known as *casting* an expression to a given data type or object class.</span></span>

## <a name="see-also"></a><span data-ttu-id="62020-177">Consulte también</span><span class="sxs-lookup"><span data-stu-id="62020-177">See also</span></span>

- [<span data-ttu-id="62020-178">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="62020-178">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="62020-179">Conversiones entre cadenas y otros tipos</span><span class="sxs-lookup"><span data-stu-id="62020-179">Conversions Between Strings and Other Types</span></span>](conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="62020-180">Cómo: Convertir un objeto en otro tipo en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="62020-180">How to: Convert an Object to Another Type in Visual Basic</span></span>](how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="62020-181">Estructuras</span><span class="sxs-lookup"><span data-stu-id="62020-181">Structures</span></span>](structures.md)
- [<span data-ttu-id="62020-182">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="62020-182">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="62020-183">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="62020-183">Type Conversion Functions</span></span>](../../../language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="62020-184">Solución de problemas de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="62020-184">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)

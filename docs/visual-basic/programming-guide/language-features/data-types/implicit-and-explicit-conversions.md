---
title: Conversiones implícita y explícita (Visual Basic)
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
ms.openlocfilehash: 09d96b304ba3bcf2a9de2812ce37ae69dba73a41
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "44037245"
---
# <a name="implicit-and-explicit-conversions-visual-basic"></a><span data-ttu-id="ab040-102">Conversiones implícita y explícita (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab040-102">Implicit and Explicit Conversions (Visual Basic)</span></span>
<span data-ttu-id="ab040-103">Un *conversión implícita* no requiere ninguna sintaxis especial en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="ab040-103">An *implicit conversion* does not require any special syntax in the source code.</span></span> <span data-ttu-id="ab040-104">En el ejemplo siguiente, Visual Basic convierte implícitamente el valor de `k` a un valor de punto flotante de precisión sencilla antes de asignarlo a `q`.</span><span class="sxs-lookup"><span data-stu-id="ab040-104">In the following example, Visual Basic implicitly converts the value of `k` to a single-precision floating-point value before assigning it to `q`.</span></span>  
  
```  
Dim k As Integer  
Dim q As Double  
' Integer widens to Double, so you can do this with Option Strict On.  
k = 432  
q = k  
```  
  
 <span data-ttu-id="ab040-105">Un *conversión explícita* utiliza una palabra clave de conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="ab040-105">An *explicit conversion* uses a type conversion keyword.</span></span> <span data-ttu-id="ab040-106">Visual Basic ofrece varias palabras clave que convierten una expresión entre paréntesis al tipo de datos deseado.</span><span class="sxs-lookup"><span data-stu-id="ab040-106">Visual Basic provides several such keywords, which coerce an expression in parentheses to the desired data type.</span></span> <span data-ttu-id="ab040-107">Estas palabras clave actúan como funciones, pero el compilador genera el código en línea, por lo que la ejecución es ligeramente más rápida que con una llamada de función.</span><span class="sxs-lookup"><span data-stu-id="ab040-107">These keywords act like functions, but the compiler generates the code inline, so execution is slightly faster than with a function call.</span></span>  
  
 <span data-ttu-id="ab040-108">En la siguiente extensión del ejemplo anterior, el `CInt` palabra clave convierte el valor de `q` a un entero antes de asignarlo a `k`.</span><span class="sxs-lookup"><span data-stu-id="ab040-108">In the following extension of the preceding example, the `CInt` keyword converts the value of `q` back to an integer before assigning it to `k`.</span></span>  
  
```  
' q had been assigned the value 432 from k.  
q = Math.Sqrt(q)  
k = CInt(q)  
' k now has the value 21 (rounded square root of 432).  
```  
  
## <a name="conversion-keywords"></a><span data-ttu-id="ab040-109">Palabras clave para conversiones</span><span class="sxs-lookup"><span data-stu-id="ab040-109">Conversion Keywords</span></span>  
 <span data-ttu-id="ab040-110">La siguiente tabla muestra las palabras clave de conversión disponibles.</span><span class="sxs-lookup"><span data-stu-id="ab040-110">The following table shows the available conversion keywords.</span></span>  
  
|<span data-ttu-id="ab040-111">Palabra clave de conversión de tipo</span><span class="sxs-lookup"><span data-stu-id="ab040-111">Type conversion keyword</span></span>|<span data-ttu-id="ab040-112">Convierte una expresión al tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ab040-112">Converts an expression to data type</span></span>|<span data-ttu-id="ab040-113">Tipos de datos permitida de expresión que se va a convertir</span><span class="sxs-lookup"><span data-stu-id="ab040-113">Allowable data types of expression to be converted</span></span>|  
|---|---|---|  
|`CBool`|[<span data-ttu-id="ab040-114">Boolean (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="ab040-114">Boolean Data Type</span></span>](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="ab040-115">Cualquier tipo numérico (incluidos `Byte`, `SByte`y los tipos enumerados), `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="ab040-115">Any numeric type (including `Byte`, `SByte`, and enumerated types), `String`, `Object`</span></span>|  
|`CByte`|[<span data-ttu-id="ab040-116">Byte (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="ab040-116">Byte Data Type</span></span>](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="ab040-117">Cualquier tipo numérico (incluidos `SByte` y los tipos enumerados), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="ab040-117">Any numeric type (including `SByte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CChar`|[<span data-ttu-id="ab040-118">Char (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="ab040-118">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="ab040-119">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="ab040-119">`String`, `Object`</span></span>|  
|`CDate`|[<span data-ttu-id="ab040-120">Date (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="ab040-120">Date Data Type</span></span>](../../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="ab040-121">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="ab040-121">`String`, `Object`</span></span>|  
|`CDbl`|[<span data-ttu-id="ab040-122">Double (tipos de datos)</span><span class="sxs-lookup"><span data-stu-id="ab040-122">Double Data Type</span></span>](../../../../visual-basic/language-reference/data-types/double-data-type.md)|<span data-ttu-id="ab040-123">Cualquier tipo numérico (incluidos `Byte`, `SByte`y los tipos enumerados), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="ab040-123">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CDec`|[<span data-ttu-id="ab040-124">Decimal (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="ab040-124">Decimal Data Type</span></span>](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="ab040-125">Cualquier tipo numérico (incluidos `Byte`, `SByte`y los tipos enumerados), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="ab040-125">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CInt`|[<span data-ttu-id="ab040-126">Integer (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="ab040-126">Integer Data Type</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="ab040-127">Cualquier tipo numérico (incluidos `Byte`, `SByte`y los tipos enumerados), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="ab040-127">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CLng`|[<span data-ttu-id="ab040-128">Long (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="ab040-128">Long Data Type</span></span>](../../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="ab040-129">Cualquier tipo numérico (incluidos `Byte`, `SByte`y los tipos enumerados), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="ab040-129">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CObj`|[<span data-ttu-id="ab040-130">Tipo de objeto de datos</span><span class="sxs-lookup"><span data-stu-id="ab040-130">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)|<span data-ttu-id="ab040-131">Cualquier tipo</span><span class="sxs-lookup"><span data-stu-id="ab040-131">Any type</span></span>|  
|`CSByte`|[<span data-ttu-id="ab040-132">SByte (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="ab040-132">SByte Data Type</span></span>](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="ab040-133">Cualquier tipo numérico (incluidos `Byte` y los tipos enumerados), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="ab040-133">Any numeric type (including `Byte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CShort`|[<span data-ttu-id="ab040-134">Short (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="ab040-134">Short Data Type</span></span>](../../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="ab040-135">Cualquier tipo numérico (incluidos `Byte`, `SByte`y los tipos enumerados), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="ab040-135">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CSng`|[<span data-ttu-id="ab040-136">Single (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="ab040-136">Single Data Type</span></span>](../../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="ab040-137">Cualquier tipo numérico (incluidos `Byte`, `SByte`y los tipos enumerados), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="ab040-137">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CStr`|[<span data-ttu-id="ab040-138">String (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="ab040-138">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)|<span data-ttu-id="ab040-139">Cualquier tipo numérico (incluidos `Byte`, `SByte`y los tipos enumerados), `Boolean`, `Char`, `Char` matriz, `Date`, `Object`</span><span class="sxs-lookup"><span data-stu-id="ab040-139">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `Char`, `Char` array, `Date`, `Object`</span></span>|  
|`CType`|<span data-ttu-id="ab040-140">Tipo especificado después de la coma (`,`)</span><span class="sxs-lookup"><span data-stu-id="ab040-140">Type specified following the comma (`,`)</span></span>|<span data-ttu-id="ab040-141">Al convertir a un *tipo de datos básico* (incluida una matriz de un tipo básico), el mismo tipos como el de la palabra clave de conversión correspondiente</span><span class="sxs-lookup"><span data-stu-id="ab040-141">When converting to an *elementary data type* (including an array of an elementary type), the same types as allowed for the corresponding conversion keyword</span></span><br /><br /> <span data-ttu-id="ab040-142">Al convertir a un *tipo de datos compuesto*, las interfaces que implementa y las clases de las que hereda</span><span class="sxs-lookup"><span data-stu-id="ab040-142">When converting to a *composite data type*, the interfaces it implements and the classes from which it inherits</span></span><br /><br /> <span data-ttu-id="ab040-143">Cuando se convierte en una clase o estructura en el que ha sobrecargado `CType`, esa clase o estructura</span><span class="sxs-lookup"><span data-stu-id="ab040-143">When converting to a class or structure on which you have overloaded `CType`, that class or structure</span></span>|  
|`CUInt`|[<span data-ttu-id="ab040-144">UInteger (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="ab040-144">UInteger Data Type</span></span>](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="ab040-145">Cualquier tipo numérico (incluidos `Byte`, `SByte`y los tipos enumerados), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="ab040-145">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CULng`|[<span data-ttu-id="ab040-146">ULong (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="ab040-146">ULong Data Type</span></span>](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="ab040-147">Cualquier tipo numérico (incluidos `Byte`, `SByte`y los tipos enumerados), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="ab040-147">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CUShort`|[<span data-ttu-id="ab040-148">UShort (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="ab040-148">UShort Data Type</span></span>](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="ab040-149">Cualquier tipo numérico (incluidos `Byte`, `SByte`y los tipos enumerados), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="ab040-149">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
  
## <a name="the-ctype-function"></a><span data-ttu-id="ab040-150">CType (función)</span><span class="sxs-lookup"><span data-stu-id="ab040-150">The CType Function</span></span>  
 <span data-ttu-id="ab040-151">El [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) actúa sobre dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="ab040-151">The [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) operates on two arguments.</span></span> <span data-ttu-id="ab040-152">La primera es la expresión que se va a convertir y el segundo es la clase de tipo u objeto de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="ab040-152">The first is the expression to be converted, and the second is the destination data type or object class.</span></span> <span data-ttu-id="ab040-153">Tenga en cuenta que el primer argumento debe ser una expresión, no es un tipo.</span><span class="sxs-lookup"><span data-stu-id="ab040-153">Note that the first argument must be an expression, not a type.</span></span>  
  
 <span data-ttu-id="ab040-154">`CType` es un *función inline*, lo que significa que el código compilado realiza la conversión, a menudo llaman a sin generar una función.</span><span class="sxs-lookup"><span data-stu-id="ab040-154">`CType` is an *inline function*, meaning the compiled code makes the conversion, often without generating a function call.</span></span> <span data-ttu-id="ab040-155">Esto mejora el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ab040-155">This improves performance.</span></span>  
  
 <span data-ttu-id="ab040-156">Para obtener una comparación de `CType` con otro tipo palabras clave de conversión, consulte [DirectCast (operador)](../../../../visual-basic/language-reference/operators/directcast-operator.md) y [TryCast (operador)](../../../../visual-basic/language-reference/operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="ab040-156">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../../visual-basic/language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span>  
  
### <a name="elementary-types"></a><span data-ttu-id="ab040-157">Tipos elementales</span><span class="sxs-lookup"><span data-stu-id="ab040-157">Elementary Types</span></span>  
 <span data-ttu-id="ab040-158">El siguiente ejemplo muestra el uso de `CType`.</span><span class="sxs-lookup"><span data-stu-id="ab040-158">The following example demonstrates the use of `CType`.</span></span>  
  
```  
k = CType(q, Integer)  
' The following statement coerces w to the specific object class Label.  
f = CType(w, Label)  
```  
  
### <a name="composite-types"></a><span data-ttu-id="ab040-159">Tipos compuestos</span><span class="sxs-lookup"><span data-stu-id="ab040-159">Composite Types</span></span>  
 <span data-ttu-id="ab040-160">Puede usar `CType` para convertir valores a tipos de datos compuestos, así como en tipos elementales.</span><span class="sxs-lookup"><span data-stu-id="ab040-160">You can use `CType` to convert values to composite data types as well as to elementary types.</span></span> <span data-ttu-id="ab040-161">También puede usar para convertir una clase de objeto para el tipo de uno de sus interfaces, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ab040-161">You can also use it to coerce an object class to the type of one of its interfaces, as in the following example.</span></span>  
  
```  
' Assume class cZone implements interface iZone.  
Dim h As Object  
' The first argument to CType must be an expression, not a type.  
Dim cZ As cZone  
' The following statement coerces a cZone object to its interface iZone.  
h = CType(cZ, iZone)  
```  
  
### <a name="array-types"></a><span data-ttu-id="ab040-162">Tipos de matriz</span><span class="sxs-lookup"><span data-stu-id="ab040-162">Array Types</span></span>  
 <span data-ttu-id="ab040-163">`CType` También se puede convertir a tipos de datos de matriz, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ab040-163">`CType` can also convert array data types, as in the following example.</span></span>  
  
```  
Dim v() As classV  
Dim obArray() As Object  
' Assume some object array has been assigned to obArray.  
' Check for run-time type compatibility.  
If TypeOf obArray Is classV()  
    ' obArray can be converted to classV.  
    v = CType(obArray, classV())  
End If  
```  
  
 <span data-ttu-id="ab040-164">Para obtener más información y un ejemplo, vea [conversiones de matrices](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="ab040-164">For more information and an example, see [Array Conversions](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md).</span></span>  
  
### <a name="types-defining-ctype"></a><span data-ttu-id="ab040-165">Tipos que define CType</span><span class="sxs-lookup"><span data-stu-id="ab040-165">Types Defining CType</span></span>  
 <span data-ttu-id="ab040-166">Puede definir `CType` en una clase o estructura que ha definido.</span><span class="sxs-lookup"><span data-stu-id="ab040-166">You can define `CType` on a class or structure you have defined.</span></span> <span data-ttu-id="ab040-167">Esto le permite convertir los valores a y desde el tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="ab040-167">This allows you to convert values to and from the type of your class or structure.</span></span> <span data-ttu-id="ab040-168">Para obtener más información y un ejemplo, vea [Cómo: definir un operador de conversión](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="ab040-168">For more information and an example, see [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ab040-169">Los valores utilizados con una palabra clave de conversión deben ser válidos para el tipo de datos de destino, o se produce un error.</span><span class="sxs-lookup"><span data-stu-id="ab040-169">Values used with a conversion keyword must be valid for the destination data type, or an error occurs.</span></span> <span data-ttu-id="ab040-170">Por ejemplo, si se intenta convertir un `Long` a un `Integer`, el valor de la `Long` debe estar dentro del intervalo válido para el `Integer` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="ab040-170">For example, if you attempt to convert a `Long` to an `Integer`, the value of the `Long` must be within the valid range for the `Integer` data type.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="ab040-171">Especificar `CType` para convertir de un tipo de clase a otro se produce un error en tiempo de ejecución si el tipo de origen no se deriva el tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="ab040-171">Specifying `CType` to convert from one class type to another fails at run time if the source type does not derive from the destination type.</span></span> <span data-ttu-id="ab040-172">Este error se produce un <xref:System.InvalidCastException> excepción.</span><span class="sxs-lookup"><span data-stu-id="ab040-172">Such a failure throws an <xref:System.InvalidCastException> exception.</span></span>  
  
 <span data-ttu-id="ab040-173">Sin embargo, si uno de los tipos es una estructura o clase que se ha definido, y si ha definido `CType` en esa clase o estructura, una conversión puede tener éxito si satisface los requisitos de su `CType`.</span><span class="sxs-lookup"><span data-stu-id="ab040-173">However, if one of the types is a structure or class you have defined, and if you have defined `CType` on that structure or class, a conversion can succeed if it satisfies the requirements of your `CType`.</span></span> <span data-ttu-id="ab040-174">Consulte [Cómo: definir un operador de conversión](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="ab040-174">See [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
 <span data-ttu-id="ab040-175">Realizar una conversión explícita es también conocida como *conversión* una expresión a una clase de tipo u objeto de datos determinado.</span><span class="sxs-lookup"><span data-stu-id="ab040-175">Performing an explicit conversion is also known as *casting* an expression to a given data type or object class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab040-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab040-176">See Also</span></span>  
 [<span data-ttu-id="ab040-177">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ab040-177">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="ab040-178">Conversiones entre cadenas y otros tipos</span><span class="sxs-lookup"><span data-stu-id="ab040-178">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [<span data-ttu-id="ab040-179">Cómo: convertir un objeto a otro tipo en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ab040-179">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [<span data-ttu-id="ab040-180">Estructuras</span><span class="sxs-lookup"><span data-stu-id="ab040-180">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="ab040-181">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="ab040-181">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="ab040-182">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="ab040-182">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="ab040-183">Solución de problemas de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="ab040-183">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)

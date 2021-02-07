---
description: 'Más información sobre: funciones de conversión de tipos (Visual Basic)'
title: Type Conversion Functions
ms.date: 10/24/2018
f1_keywords:
- vb.CUShort
- vb.csng
- vb.CDate
- CByte
- CSng
- vb.CDec
- CBool
- CStr
- vb.CULng
- CDec
- CVErr
- CDbl
- CShort
- vb.CObj
- vb.CVErr
- CULng
- vb.cdbl
- vb.cbool
- CObj
- CDate
- CLng
- vb.cstr
- vb.cbyte
- vb.clng
- vb.CChar
- CUShort
- vb.CUInt
- vb.cint
- vb.CShort
- CInt
- CUInt
- CChar
helpviewer_keywords:
- CDate function
- CByte function
- Integer data type [Visual Basic], converting
- string conversion [Visual Basic], conversion functions
- fractions
- data types [Visual Basic], converting
- text, converting
- CDec function
- Char data type [Visual Basic], converting
- type conversion [Visual Basic], functions for
- Single data type [Visual Basic], converting
- numbers [Visual Basic], rounding
- rounding numbers [Visual Basic], type conversion
- CUShort function
- Long data type [Visual Basic], converting
- return values [Visual Basic], data types
- single-precision numbers [Visual Basic], converting
- data type conversion [Visual Basic], functions for
- CStr function
- times [Visual Basic], converting
- CSng function
- conversions [Visual Basic], type conversion functions
- CBool function
- CDbl function
- CUInt function
- Currency data type [Visual Basic], conversion functions
- numbers [Visual Basic], converting
- Double data type [Visual Basic], converting
- CLng function
- CSByte function
- double-precision numbers
- Decimal data type [Visual Basic], converting
- Boolean data type [Visual Basic], converting
- integers [Visual Basic], type conversion functions
- dates [Visual Basic], converting
- CULng function
- CInt function
- Date data type [Visual Basic], converting
- Byte data type [Visual Basic], converting
- String data type [Visual Basic], converting
- CChar function
- banker's rounding
- Short data type [Visual Basic], converting
- rounding numbers [Visual Basic], banker's rounding
- type conversion [Visual Basic], Visual Basic vs. .NET Framework
ms.assetid: d9d8d165-f967-44ff-a6cd-598e4740a99e
ms.openlocfilehash: c2e701b522bbeb32f4f6f448acd78e09b0616f46
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731089"
---
# <a name="type-conversion-functions-visual-basic"></a><span data-ttu-id="585d7-103">Funciones de conversión de tipos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="585d7-103">Type Conversion Functions (Visual Basic)</span></span>

<span data-ttu-id="585d7-104">Estas funciones se compilan en línea, lo que significa que el código de conversión forma parte del código que evalúa la expresión.</span><span class="sxs-lookup"><span data-stu-id="585d7-104">These functions are compiled inline, meaning the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="585d7-105">A veces no hay ninguna llamada a un procedimiento para realizar la conversión, lo que mejora el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="585d7-105">Sometimes there is no call to a procedure to accomplish the conversion, which improves performance.</span></span> <span data-ttu-id="585d7-106">Cada función convierte una expresión en un tipo de datos específico.</span><span class="sxs-lookup"><span data-stu-id="585d7-106">Each function coerces an expression to a specific data type.</span></span>

## <a name="syntax"></a><span data-ttu-id="585d7-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="585d7-107">Syntax</span></span>

```vb
CBool(expression)
CByte(expression)
CChar(expression)
CDate(expression)
CDbl(expression)
CDec(expression)
CInt(expression)
CLng(expression)
CObj(expression)
CSByte(expression)
CShort(expression)
CSng(expression)
CStr(expression)
CUInt(expression)
CULng(expression)
CUShort(expression)
```

## <a name="part"></a><span data-ttu-id="585d7-108">Parte</span><span class="sxs-lookup"><span data-stu-id="585d7-108">Part</span></span>

`expression`  
<span data-ttu-id="585d7-109">Necesario.</span><span class="sxs-lookup"><span data-stu-id="585d7-109">Required.</span></span> <span data-ttu-id="585d7-110">Cualquier expresión del tipo de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="585d7-110">Any expression of the source data type.</span></span>

## <a name="return-value-data-type"></a><span data-ttu-id="585d7-111">Tipo de datos de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="585d7-111">Return Value Data Type</span></span>

<span data-ttu-id="585d7-112">El nombre de la función determina el tipo de datos del valor que devuelve, tal y como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="585d7-112">The function name determines the data type of the value it returns, as shown in the following table.</span></span>

|<span data-ttu-id="585d7-113">Nombre de la función</span><span class="sxs-lookup"><span data-stu-id="585d7-113">Function name</span></span>|<span data-ttu-id="585d7-114">Tipo de datos devuelto</span><span class="sxs-lookup"><span data-stu-id="585d7-114">Return data type</span></span>|<span data-ttu-id="585d7-115">Intervalo para el `expression` argumento</span><span class="sxs-lookup"><span data-stu-id="585d7-115">Range for `expression` argument</span></span>|
|-------------------|----------------------|-------------------------------------|
|`CBool`|[<span data-ttu-id="585d7-116">Tipo de datos Boolean</span><span class="sxs-lookup"><span data-stu-id="585d7-116">Boolean Data Type</span></span>](../data-types/boolean-data-type.md)|<span data-ttu-id="585d7-117">Cualquier `Char` expresión válida o `String` numérica.</span><span class="sxs-lookup"><span data-stu-id="585d7-117">Any valid `Char` or `String` or numeric expression.</span></span>|
|`CByte`|[<span data-ttu-id="585d7-118">Tipo de datos Byte</span><span class="sxs-lookup"><span data-stu-id="585d7-118">Byte Data Type</span></span>](../data-types/byte-data-type.md)|<span data-ttu-id="585d7-119"><xref:System.Byte.MinValue?displayProperty=nameWithType> (0) a <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (sin signo); las partes fraccionarias se redondean<sup> . 1</sup></span><span class="sxs-lookup"><span data-stu-id="585d7-119"><xref:System.Byte.MinValue?displayProperty=nameWithType> (0) through <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="585d7-120">A partir de Visual Basic 15,8, Visual Basic optimiza el rendimiento de la conversión de punto flotante a byte con la `CByte` función; vea la sección [comentarios](#remarks) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="585d7-120">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to byte conversion with the `CByte` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="585d7-121">Vea la sección [ejemplo de cint](#cint-example) para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="585d7-121">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CChar`|[<span data-ttu-id="585d7-122">Tipo de datos Char</span><span class="sxs-lookup"><span data-stu-id="585d7-122">Char Data Type</span></span>](../data-types/char-data-type.md)|<span data-ttu-id="585d7-123">Cualquier `Char` expresión o válida `String` ; solo se convierte el primer carácter de un `String` ; el valor puede ser de 0 a 65535 (sin signo).</span><span class="sxs-lookup"><span data-stu-id="585d7-123">Any valid `Char` or `String` expression; only first character of a `String` is converted; value can be 0 through 65535 (unsigned).</span></span>|
|`CDate`|[<span data-ttu-id="585d7-124">Tipo de datos Date</span><span class="sxs-lookup"><span data-stu-id="585d7-124">Date Data Type</span></span>](../data-types/date-data-type.md)|<span data-ttu-id="585d7-125">Cualquier representación válida de una fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="585d7-125">Any valid representation of a date and time.</span></span>|
|`CDbl`|[<span data-ttu-id="585d7-126">Tipo de datos Double</span><span class="sxs-lookup"><span data-stu-id="585d7-126">Double Data Type</span></span>](../data-types/double-data-type.md)|<span data-ttu-id="585d7-127">-1.79769313486231570 e + 308 a-4.94065645841246544 E-324 para los valores negativos; 4.94065645841246544 e-324 a 1.79769313486231570 E + 308 para los valores positivos.</span><span class="sxs-lookup"><span data-stu-id="585d7-127">-1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values; 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span>|
|`CDec`|[<span data-ttu-id="585d7-128">Tipo de datos Decimal</span><span class="sxs-lookup"><span data-stu-id="585d7-128">Decimal Data Type</span></span>](../data-types/decimal-data-type.md)|<span data-ttu-id="585d7-129">+/-79.228.162.514.264.337.593.543.950.335 para números con escala cero, es decir, números sin decimales.</span><span class="sxs-lookup"><span data-stu-id="585d7-129">+/-79,228,162,514,264,337,593,543,950,335 for zero-scaled numbers, that is, numbers with no decimal places.</span></span> <span data-ttu-id="585d7-130">En el caso de números con 28 posiciones decimales, el intervalo es +/-7,9228162514264337593543950335.</span><span class="sxs-lookup"><span data-stu-id="585d7-130">For numbers with 28 decimal places, the range is +/-7.9228162514264337593543950335.</span></span> <span data-ttu-id="585d7-131">El número más pequeño posible distinto de cero es 0,0000000000000000000000000001 (+/-1E-28).</span><span class="sxs-lookup"><span data-stu-id="585d7-131">The smallest possible non-zero number is 0.0000000000000000000000000001 (+/-1E-28).</span></span>|
|`CInt`|[<span data-ttu-id="585d7-132">Tipo de datos Integer</span><span class="sxs-lookup"><span data-stu-id="585d7-132">Integer Data Type</span></span>](../data-types/integer-data-type.md)|<span data-ttu-id="585d7-133"><xref:System.Int32.MinValue?displayProperty=nameWithType> (-2.147.483.648) a <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2.147.483.647); las partes fraccionarias se redondean.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="585d7-133"><xref:System.Int32.MinValue?displayProperty=nameWithType> (-2,147,483,648) through <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2,147,483,647); fractional parts are rounded.<sup>1</sup></span></span> <br/><br/><span data-ttu-id="585d7-134">A partir de Visual Basic 15,8, Visual Basic optimiza el rendimiento de la conversión de punto flotante a entero con la `CInt` función; vea la sección [comentarios](#remarks) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="585d7-134">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to integer conversion with the `CInt` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="585d7-135">Vea la sección [ejemplo de cint](#cint-example) para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="585d7-135">See the [CInt Example](#cint-example) section for an example.</span></span> |
|`CLng`|[<span data-ttu-id="585d7-136">Tipo de datos Long</span><span class="sxs-lookup"><span data-stu-id="585d7-136">Long Data Type</span></span>](../data-types/long-data-type.md)|<span data-ttu-id="585d7-137"><xref:System.Int64.MinValue?displayProperty=nameWithType> (-9.223.372.036.854.775.808) a <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9.223.372.036.854.775.807); las partes fraccionarias se redondean.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="585d7-137"><xref:System.Int64.MinValue?displayProperty=nameWithType> (-9,223,372,036,854,775,808) through <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9,223,372,036,854,775,807); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="585d7-138">A partir de Visual Basic 15,8, Visual Basic optimiza el rendimiento de la conversión de enteros de punto flotante a 64 bits con la `CLng` función; vea la sección [comentarios](#remarks) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="585d7-138">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to 64-bit integer conversion with the `CLng` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="585d7-139">Vea la sección [ejemplo de cint](#cint-example) para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="585d7-139">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CObj`|[<span data-ttu-id="585d7-140">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="585d7-140">Object Data Type</span></span>](../data-types/object-data-type.md)|<span data-ttu-id="585d7-141">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="585d7-141">Any valid expression.</span></span>|
|`CSByte`|[<span data-ttu-id="585d7-142">Tipo de datos SByte</span><span class="sxs-lookup"><span data-stu-id="585d7-142">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)|<span data-ttu-id="585d7-143"><xref:System.SByte.MinValue?displayProperty=nameWithType> (-128) a <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); las partes fraccionarias se redondean.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="585d7-143"><xref:System.SByte.MinValue?displayProperty=nameWithType> (-128) through <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="585d7-144">A partir de Visual Basic 15,8, Visual Basic optimiza el rendimiento de la conversión de bytes de punto flotante a firma con la `CSByte` función; vea la sección [comentarios](#remarks) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="585d7-144">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to signed byte conversion with the `CSByte` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="585d7-145">Vea la sección [ejemplo de cint](#cint-example) para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="585d7-145">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CShort`|[<span data-ttu-id="585d7-146">Tipo de datos Short</span><span class="sxs-lookup"><span data-stu-id="585d7-146">Short Data Type</span></span>](../data-types/short-data-type.md)|<span data-ttu-id="585d7-147"><xref:System.Int16.MinValue?displayProperty=nameWithType> (-32.768) a <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32.767); las partes fraccionarias se redondean.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="585d7-147"><xref:System.Int16.MinValue?displayProperty=nameWithType> (-32,768) through <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32,767); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="585d7-148">A partir de Visual Basic 15,8, Visual Basic optimiza el rendimiento de la conversión de enteros de punto flotante a 16 bits con la `CShort` función; vea la sección [comentarios](#remarks) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="585d7-148">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to 16-bit integer conversion with the `CShort` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="585d7-149">Vea la sección [ejemplo de cint](#cint-example) para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="585d7-149">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CSng`|[<span data-ttu-id="585d7-150">Tipo de datos Single</span><span class="sxs-lookup"><span data-stu-id="585d7-150">Single Data Type</span></span>](../data-types/single-data-type.md)|<span data-ttu-id="585d7-151">-3.402823 e + 38 a-401298e E-45 para los valores negativos; 401298e e-45 a 3.402823 E + 38 para los valores positivos.</span><span class="sxs-lookup"><span data-stu-id="585d7-151">-3.402823E+38 through -1.401298E-45 for negative values; 1.401298E-45 through 3.402823E+38 for positive values.</span></span>|
|`CStr`|[<span data-ttu-id="585d7-152">String (Tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="585d7-152">String Data Type</span></span>](../data-types/string-data-type.md)|<span data-ttu-id="585d7-153">Returns para `CStr` dependen del `expression` argumento.</span><span class="sxs-lookup"><span data-stu-id="585d7-153">Returns for `CStr` depend on the `expression` argument.</span></span> <span data-ttu-id="585d7-154">Vea [valores devueltos para la función CSTR](return-values-for-the-cstr-function.md).</span><span class="sxs-lookup"><span data-stu-id="585d7-154">See [Return Values for the CStr Function](return-values-for-the-cstr-function.md).</span></span>|
|`CUInt`|[<span data-ttu-id="585d7-155">Tipo de datos UInteger</span><span class="sxs-lookup"><span data-stu-id="585d7-155">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)|<span data-ttu-id="585d7-156"><xref:System.UInt32.MinValue?displayProperty=nameWithType> (0) a <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4.294.967.295) (sin signo); las partes fraccionarias se redondean<sup> . 1</sup></span><span class="sxs-lookup"><span data-stu-id="585d7-156"><xref:System.UInt32.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4,294,967,295) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="585d7-157">A partir de Visual Basic 15,8, Visual Basic optimiza el rendimiento de la conversión de enteros de punto flotante a sin signo con la `CUInt` función; vea la sección [comentarios](#remarks) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="585d7-157">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned integer conversion with the `CUInt` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="585d7-158">Vea la sección [ejemplo de cint](#cint-example) para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="585d7-158">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CULng`|[<span data-ttu-id="585d7-159">Tipo de datos ULong</span><span class="sxs-lookup"><span data-stu-id="585d7-159">ULong Data Type</span></span>](../data-types/ulong-data-type.md)|<span data-ttu-id="585d7-160"><xref:System.UInt64.MinValue?displayProperty=nameWithType> (0) a <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18446744073709551615) (sin signo); las partes fraccionarias se redondean<sup> . 1</sup></span><span class="sxs-lookup"><span data-stu-id="585d7-160"><xref:System.UInt64.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18,446,744,073,709,551,615) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="585d7-161">A partir de Visual Basic 15,8, Visual Basic optimiza el rendimiento de la conversión de punto flotante a entero largo sin signo con la `CULng` función; vea la sección [comentarios](#remarks) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="585d7-161">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned long integer conversion with the `CULng` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="585d7-162">Vea la sección [ejemplo de cint](#cint-example) para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="585d7-162">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CUShort`|[<span data-ttu-id="585d7-163">Tipo de datos UShort</span><span class="sxs-lookup"><span data-stu-id="585d7-163">UShort Data Type</span></span>](../data-types/ushort-data-type.md)|<span data-ttu-id="585d7-164"><xref:System.UInt16.MinValue?displayProperty=nameWithType> (0) a <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65.535) (sin signo); las partes fraccionarias se redondean<sup> . 1</sup></span><span class="sxs-lookup"><span data-stu-id="585d7-164"><xref:System.UInt16.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65,535) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="585d7-165">A partir de Visual Basic 15,8, Visual Basic optimiza el rendimiento de la conversión de enteros de punto flotante a sin signo de 16 bits con la `CUShort` función; vea la sección [comentarios](#remarks) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="585d7-165">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned 16-bit integer conversion with the `CUShort` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="585d7-166">Vea la sección [ejemplo de cint](#cint-example) para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="585d7-166">See the [CInt Example](#cint-example) section for an example.</span></span>|

<span data-ttu-id="585d7-167"><sup>1</sup> las partes fraccionarias pueden estar sujetas a un tipo especial de redondeo denominado *redondeo bancario*.</span><span class="sxs-lookup"><span data-stu-id="585d7-167"><sup>1</sup> Fractional parts can be subject to a special type of rounding called *banker's rounding*.</span></span> <span data-ttu-id="585d7-168">Vea "Comentarios" para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="585d7-168">See "Remarks" for more information.</span></span>

## <a name="remarks"></a><span data-ttu-id="585d7-169">Observaciones</span><span class="sxs-lookup"><span data-stu-id="585d7-169">Remarks</span></span>

<span data-ttu-id="585d7-170">Como norma general, debe usar las funciones de conversión de tipo Visual Basic en preferencia a los métodos de .NET Framework como `ToString()` , ya sea en la <xref:System.Convert> clase o en una estructura o clase de tipo individual.</span><span class="sxs-lookup"><span data-stu-id="585d7-170">As a rule, you should use the Visual Basic type conversion functions in preference to the .NET Framework methods such as `ToString()`, either on the <xref:System.Convert> class or on an individual type structure or class.</span></span> <span data-ttu-id="585d7-171">Las funciones de Visual Basic están diseñadas para una interacción óptima con el código Visual Basic y también hacen que el código fuente sea más corto y más fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="585d7-171">The Visual Basic functions are designed for optimal interaction with Visual Basic code, and they also make your source code shorter and easier to read.</span></span> <span data-ttu-id="585d7-172">Además, los métodos de conversión de .NET Framework no siempre producen los mismos resultados que las funciones de Visual Basic, por ejemplo, al convertir `Boolean` a `Integer` .</span><span class="sxs-lookup"><span data-stu-id="585d7-172">In addition, the .NET Framework conversion methods do not always produce the same results as the Visual Basic functions, for example when converting `Boolean` to `Integer`.</span></span> <span data-ttu-id="585d7-173">Para obtener más información, vea [solución de problemas de tipos de datos](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="585d7-173">For more information, see [Troubleshooting Data Types](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

<span data-ttu-id="585d7-174">A partir de Visual Basic 15,8, el rendimiento de la conversión de punto flotante a entero se optimiza al pasar el <xref:System.Single> <xref:System.Double> valor o devuelto por los métodos siguientes a una de las funciones de conversión de enteros ( `CByte` , `CShort` , `CInt` , `CLng` , `CSByte` , `CUShort` , `CUInt` , `CULng` ):</span><span class="sxs-lookup"><span data-stu-id="585d7-174">Starting with Visual Basic 15.8, the performance of floating-point-to-integer conversion is optimized when you pass the <xref:System.Single> or <xref:System.Double> value returned by the following methods to one of the integer conversion functions (`CByte`, `CShort`, `CInt`, `CLng`, `CSByte`, `CUShort`, `CUInt`, `CULng`):</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Single)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Single)?displayProperty=nameWithType>
- <xref:System.Math.Ceiling(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Floor(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Round(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Truncate(System.Double)?displayProperty=nameWithType>

<span data-ttu-id="585d7-175">Esta optimización permite que el código que realiza un gran número de conversiones de enteros se ejecute hasta dos veces más rápido.</span><span class="sxs-lookup"><span data-stu-id="585d7-175">This optimization allows code that does a large number of integer conversions to run up to twice as fast.</span></span> <span data-ttu-id="585d7-176">En el ejemplo siguiente se muestran estas conversiones optimizadas de punto flotante a entero:</span><span class="sxs-lookup"><span data-stu-id="585d7-176">The following example illustrates these optimized floating-point-to-integer conversions:</span></span>

```vb
Dim s As Single = 173.7619
Dim d As Double = s

Dim i1 As Integer = CInt(Fix(s))               ' Result: 173
Dim b1 As Byte = CByte(Int(d))                 ' Result: 173
Dim s1 AS Short = CShort(Math.Truncate(s))     ' Result: 173
Dim i2 As Integer = CInt(Math.Ceiling(d))      ' Result: 174
Dim i3 As Integer = CInt(Math.Round(s))        ' Result: 174
```

## <a name="behavior"></a><span data-ttu-id="585d7-177">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="585d7-177">Behavior</span></span>

- <span data-ttu-id="585d7-178">**Conversión.**</span><span class="sxs-lookup"><span data-stu-id="585d7-178">**Coercion.**</span></span> <span data-ttu-id="585d7-179">En general, puede utilizar las funciones de conversión de tipos de datos para convertir el resultado de una operación en un tipo de datos determinado en lugar del tipo de datos predeterminado.</span><span class="sxs-lookup"><span data-stu-id="585d7-179">In general, you can use the data type conversion functions to coerce the result of an operation to a particular data type rather than the default data type.</span></span> <span data-ttu-id="585d7-180">Por ejemplo, use `CDec` para forzar la aritmética decimal en los casos en los que normalmente tendría lugar la aritmética de precisión sencilla, doble precisión o entero.</span><span class="sxs-lookup"><span data-stu-id="585d7-180">For example, use `CDec` to force decimal arithmetic in cases where single-precision, double-precision, or integer arithmetic would normally take place.</span></span>

- <span data-ttu-id="585d7-181">**Conversiones con errores.**</span><span class="sxs-lookup"><span data-stu-id="585d7-181">**Failed Conversions.**</span></span> <span data-ttu-id="585d7-182">Si el que se `expression` pasa a la función está fuera del intervalo del tipo de datos al que se va a convertir, <xref:System.OverflowException> se produce una.</span><span class="sxs-lookup"><span data-stu-id="585d7-182">If the `expression` passed to the function is outside the range of the data type to which it is to be converted, an <xref:System.OverflowException> occurs.</span></span>

- <span data-ttu-id="585d7-183">**Partes fraccionarias.**</span><span class="sxs-lookup"><span data-stu-id="585d7-183">**Fractional Parts.**</span></span> <span data-ttu-id="585d7-184">Cuando se convierte un valor no entero en un tipo entero, las funciones de conversión de enteros ( `CByte` , `CInt` , `CLng` , `CSByte` , `CShort` , `CUInt` , `CULng` y `CUShort` ) quitan la parte fraccionaria y redondean el valor al entero más cercano.</span><span class="sxs-lookup"><span data-stu-id="585d7-184">When you convert a nonintegral value to an integral type, the integer conversion functions (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, and `CUShort`) remove the fractional part and round the value to the closest integer.</span></span>

     <span data-ttu-id="585d7-185">Si la parte fraccionaria es exactamente 0,5, las funciones de conversión de enteros lo redondean al entero par más cercano.</span><span class="sxs-lookup"><span data-stu-id="585d7-185">If the fractional part is exactly 0.5, the integer conversion functions round it to the nearest even integer.</span></span> <span data-ttu-id="585d7-186">Por ejemplo, 0,5 se redondea a 0 y 1,5 y 2,5 se redondean a 2.</span><span class="sxs-lookup"><span data-stu-id="585d7-186">For example, 0.5 rounds to 0, and 1.5 and 2.5 both round to 2.</span></span> <span data-ttu-id="585d7-187">A veces, esto se denomina *redondeo bancario* y su finalidad es compensar una diferencia que podría acumularse al agregar muchos de estos números juntos.</span><span class="sxs-lookup"><span data-stu-id="585d7-187">This is sometimes called *banker's rounding*, and its purpose is to compensate for a bias that could accumulate when adding many such numbers together.</span></span>

     <span data-ttu-id="585d7-188">`CInt` y `CLng` difieren de las <xref:Microsoft.VisualBasic.Conversion.Int%2A> <xref:Microsoft.VisualBasic.Conversion.Fix%2A> funciones y, que truncan, en lugar de redondear, la parte fraccionaria de un número.</span><span class="sxs-lookup"><span data-stu-id="585d7-188">`CInt` and `CLng` differ from the <xref:Microsoft.VisualBasic.Conversion.Int%2A> and <xref:Microsoft.VisualBasic.Conversion.Fix%2A> functions, which truncate, rather than round, the fractional part of a number.</span></span> <span data-ttu-id="585d7-189">Además, `Fix` y `Int` siempre devuelven un valor del mismo tipo de datos que se pasa.</span><span class="sxs-lookup"><span data-stu-id="585d7-189">Also, `Fix` and `Int` always return a value of the same data type as you pass in.</span></span>

- <span data-ttu-id="585d7-190">**Conversiones de fecha y hora.**</span><span class="sxs-lookup"><span data-stu-id="585d7-190">**Date/Time Conversions.**</span></span> <span data-ttu-id="585d7-191">Use la <xref:Microsoft.VisualBasic.Information.IsDate%2A> función para determinar si un valor se puede convertir en una fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="585d7-191">Use the <xref:Microsoft.VisualBasic.Information.IsDate%2A> function to determine if a value can be converted to a date and time.</span></span> <span data-ttu-id="585d7-192">`CDate` reconoce los literales de fecha y los literales de hora, pero no los valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="585d7-192">`CDate` recognizes date literals and time literals but not numeric values.</span></span> <span data-ttu-id="585d7-193">Para convertir un valor Visual Basic 6,0 en `Date` un `Date` valor de Visual Basic 2005 o versiones posteriores, puede utilizar el <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="585d7-193">To convert a Visual Basic 6.0 `Date` value to a `Date` value in Visual Basic 2005 or later versions, you can use the <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> method.</span></span>

- <span data-ttu-id="585d7-194">**Valores de fecha y hora neutros.**</span><span class="sxs-lookup"><span data-stu-id="585d7-194">**Neutral Date/Time Values.**</span></span> <span data-ttu-id="585d7-195">El [tipo de datos Date](../data-types/date-data-type.md) siempre contiene información de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="585d7-195">The [Date Data Type](../data-types/date-data-type.md) always contains both date and time information.</span></span> <span data-ttu-id="585d7-196">A efectos de la conversión de tipos, Visual Basic considera 1/1/0001 (1 de enero del año 1) para que sea un *valor neutro* para la fecha y 00:00:00 (medianoche) como valor neutro para el tiempo.</span><span class="sxs-lookup"><span data-stu-id="585d7-196">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="585d7-197">Si convierte un `Date` valor en una cadena, no `CStr` incluye valores neutros en la cadena resultante.</span><span class="sxs-lookup"><span data-stu-id="585d7-197">If you convert a `Date` value to a string, `CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="585d7-198">Por ejemplo, si convierte `#January 1, 0001 9:30:00#` en una cadena, el resultado es "9:30:00 AM"; se suprime la información de fecha.</span><span class="sxs-lookup"><span data-stu-id="585d7-198">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="585d7-199">Sin embargo, la información de fecha todavía está presente en el `Date` valor original y se puede recuperar con funciones como <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> function.</span><span class="sxs-lookup"><span data-stu-id="585d7-199">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> function.</span></span>

- <span data-ttu-id="585d7-200">**Confidencialidad de la referencia cultural.**</span><span class="sxs-lookup"><span data-stu-id="585d7-200">**Culture Sensitivity.**</span></span> <span data-ttu-id="585d7-201">Las funciones de conversión de tipos que implican cadenas realizan conversiones basadas en la configuración de la referencia cultural actual de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="585d7-201">The type conversion functions involving strings perform conversions based on the current culture settings for the application.</span></span> <span data-ttu-id="585d7-202">Por ejemplo, `CDate` reconoce los formatos de fecha según la configuración regional del sistema.</span><span class="sxs-lookup"><span data-stu-id="585d7-202">For example, `CDate` recognizes date formats according to the locale setting of your system.</span></span> <span data-ttu-id="585d7-203">Debe proporcionar el día, el mes y el año en el orden correcto de la configuración regional, o la fecha podría no interpretarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="585d7-203">You must provide the day, month, and year in the correct order for your locale, or the date might not be interpreted correctly.</span></span> <span data-ttu-id="585d7-204">No se reconoce el formato de fecha larga si contiene una cadena de día de la semana, como "miércoles".</span><span class="sxs-lookup"><span data-stu-id="585d7-204">A long date format is not recognized if it contains a day-of-the-week string, such as "Wednesday".</span></span>

     <span data-ttu-id="585d7-205">Si necesita convertir a o desde una representación de cadena de un valor en un formato distinto del especificado por la configuración regional, no puede usar las funciones de conversión de tipo Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="585d7-205">If you need to convert to or from a string representation of a value in a format other than the one specified by your locale, you cannot use the Visual Basic type conversion functions.</span></span> <span data-ttu-id="585d7-206">Para ello, use los `ToString(IFormatProvider)` métodos y `Parse(String, IFormatProvider)` del tipo de ese valor.</span><span class="sxs-lookup"><span data-stu-id="585d7-206">To do this, use the `ToString(IFormatProvider)` and `Parse(String, IFormatProvider)` methods of that value's type.</span></span> <span data-ttu-id="585d7-207">Por ejemplo, <xref:System.Double.Parse%2A?displayProperty=nameWithType> se usa al convertir una cadena en un `Double` y se usa <xref:System.Double.ToString%2A?displayProperty=nameWithType> al convertir un valor de tipo `Double` en una cadena.</span><span class="sxs-lookup"><span data-stu-id="585d7-207">For example, use <xref:System.Double.Parse%2A?displayProperty=nameWithType> when converting a string to a `Double`, and use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a string.</span></span>

## <a name="ctype-function"></a><span data-ttu-id="585d7-208">CType Function</span><span class="sxs-lookup"><span data-stu-id="585d7-208">CType Function</span></span>

<span data-ttu-id="585d7-209">La [función ctype](ctype-function.md) toma un segundo argumento, `typename` , y se convierte `expression` en `typename` , donde `typename` puede ser cualquier tipo de datos, estructura, clase o interfaz a la que exista una conversión válida.</span><span class="sxs-lookup"><span data-stu-id="585d7-209">The [CType Function](ctype-function.md) takes a second argument, `typename`, and coerces `expression` to `typename`, where `typename` can be any data type, structure, class, or interface to which there exists a valid conversion.</span></span>

<span data-ttu-id="585d7-210">Para obtener una comparación de `CType` con las otras palabras clave de conversión de tipos, vea operador [DirectCast](../operators/directcast-operator.md) y [operador TryCast](../operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="585d7-210">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../operators/directcast-operator.md) and [TryCast Operator](../operators/trycast-operator.md).</span></span>

## <a name="cbool-example"></a><span data-ttu-id="585d7-211">Ejemplo de CBool</span><span class="sxs-lookup"><span data-stu-id="585d7-211">CBool Example</span></span>

<span data-ttu-id="585d7-212">En el ejemplo siguiente se utiliza la `CBool` función para convertir expresiones en `Boolean` valores.</span><span class="sxs-lookup"><span data-stu-id="585d7-212">The following example uses the `CBool` function to convert expressions to `Boolean` values.</span></span> <span data-ttu-id="585d7-213">Si una expresión se evalúa como un valor distinto de cero, `CBool` devuelve `True` ; de lo contrario, devuelve `False` .</span><span class="sxs-lookup"><span data-stu-id="585d7-213">If an expression evaluates to a nonzero value, `CBool` returns `True`; otherwise, it returns `False`.</span></span>

[!code-vb[VbVbalrFunctions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#1)]

## <a name="cbyte-example"></a><span data-ttu-id="585d7-214">Ejemplo de CByte</span><span class="sxs-lookup"><span data-stu-id="585d7-214">CByte Example</span></span>

<span data-ttu-id="585d7-215">En el ejemplo siguiente se utiliza la `CByte` función para convertir una expresión en `Byte` .</span><span class="sxs-lookup"><span data-stu-id="585d7-215">The following example uses the `CByte` function to convert an expression to a `Byte`.</span></span>

[!code-vb[VbVbalrFunctions#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#2)]

## <a name="cchar-example"></a><span data-ttu-id="585d7-216">Ejemplo de CChar</span><span class="sxs-lookup"><span data-stu-id="585d7-216">CChar Example</span></span>

<span data-ttu-id="585d7-217">En el ejemplo siguiente se utiliza la `CChar` función para convertir el primer carácter de una `String` expresión a un `Char` tipo.</span><span class="sxs-lookup"><span data-stu-id="585d7-217">The following example uses the `CChar` function to convert the first character of a `String` expression to a `Char` type.</span></span>

[!code-vb[VbVbalrFunctions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#3)]

<span data-ttu-id="585d7-218">El argumento de entrada de `CChar` debe ser de tipo de datos `Char` o `String` .</span><span class="sxs-lookup"><span data-stu-id="585d7-218">The input argument to `CChar` must be of data type `Char` or `String`.</span></span> <span data-ttu-id="585d7-219">No se puede usar `CChar` para convertir un número en un carácter, porque `CChar` no puede aceptar un tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="585d7-219">You cannot use `CChar` to convert a number to a character, because `CChar` cannot accept a numeric data type.</span></span> <span data-ttu-id="585d7-220">En el ejemplo siguiente se obtiene un número que representa un punto de código (código de carácter) y lo convierte en el carácter correspondiente.</span><span class="sxs-lookup"><span data-stu-id="585d7-220">The following example obtains a number representing a code point (character code) and converts it to the corresponding character.</span></span> <span data-ttu-id="585d7-221">Usa la <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> función para obtener la cadena de dígitos, `CInt` convertir la cadena al tipo `Integer` y `ChrW` convertir el número al tipo `Char` .</span><span class="sxs-lookup"><span data-stu-id="585d7-221">It uses the <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> function to obtain the string of digits, `CInt` to convert the string to type `Integer`, and `ChrW` to convert the number to type `Char`.</span></span>

[!code-vb[VbVbalrFunctions#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#4)]

## <a name="cdate-example"></a><span data-ttu-id="585d7-222">Ejemplo de CDate</span><span class="sxs-lookup"><span data-stu-id="585d7-222">CDate Example</span></span>

<span data-ttu-id="585d7-223">En el ejemplo siguiente se utiliza la `CDate` función para convertir cadenas en `Date` valores.</span><span class="sxs-lookup"><span data-stu-id="585d7-223">The following example uses the `CDate` function to convert strings to `Date` values.</span></span> <span data-ttu-id="585d7-224">En general, no se recomienda codificar las fechas y horas de forma rígida como cadenas (como se muestra en este ejemplo).</span><span class="sxs-lookup"><span data-stu-id="585d7-224">In general, hard-coding dates and times as strings (as shown in this example) is not recommended.</span></span> <span data-ttu-id="585d7-225">Utilice literales de fecha y literales de hora, como #Feb 12, 1969 # y #4:45:23 PM #, en su lugar.</span><span class="sxs-lookup"><span data-stu-id="585d7-225">Use date literals and time literals, such as #Feb 12, 1969# and #4:45:23 PM#, instead.</span></span>

[!code-vb[VbVbalrFunctions#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#5)]

## <a name="cdbl-example"></a><span data-ttu-id="585d7-226">Ejemplo de CDbl</span><span class="sxs-lookup"><span data-stu-id="585d7-226">CDbl Example</span></span>

[!code-vb[VbVbalrFunctions#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#6)]

## <a name="cdec-example"></a><span data-ttu-id="585d7-227">Ejemplo de CDec</span><span class="sxs-lookup"><span data-stu-id="585d7-227">CDec Example</span></span>

<span data-ttu-id="585d7-228">En el ejemplo siguiente se utiliza la `CDec` función para convertir un valor numérico en `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="585d7-228">The following example uses the `CDec` function to convert a numeric value to `Decimal`.</span></span>

[!code-vb[VbVbalrFunctions#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#7)]

## <a name="cint-example"></a><span data-ttu-id="585d7-229">Ejemplo de CInt</span><span class="sxs-lookup"><span data-stu-id="585d7-229">CInt Example</span></span>

<span data-ttu-id="585d7-230">En el ejemplo siguiente se utiliza la `CInt` función para convertir un valor en `Integer` .</span><span class="sxs-lookup"><span data-stu-id="585d7-230">The following example uses the `CInt` function to convert a value to `Integer`.</span></span>

[!code-vb[VbVbalrFunctions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#8)]

## <a name="clng-example"></a><span data-ttu-id="585d7-231">Ejemplo de CLng</span><span class="sxs-lookup"><span data-stu-id="585d7-231">CLng Example</span></span>

<span data-ttu-id="585d7-232">En el ejemplo siguiente se utiliza la `CLng` función para convertir valores en `Long` .</span><span class="sxs-lookup"><span data-stu-id="585d7-232">The following example uses the `CLng` function to convert values to `Long`.</span></span>

[!code-vb[VbVbalrFunctions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#9)]

## <a name="cobj-example"></a><span data-ttu-id="585d7-233">Ejemplo de CObj</span><span class="sxs-lookup"><span data-stu-id="585d7-233">CObj Example</span></span>

<span data-ttu-id="585d7-234">En el ejemplo siguiente se utiliza la `CObj` función para convertir un valor numérico en `Object` .</span><span class="sxs-lookup"><span data-stu-id="585d7-234">The following example uses the `CObj` function to convert a numeric value to `Object`.</span></span> <span data-ttu-id="585d7-235">La `Object` propia variable solo contiene un puntero de cuatro bytes, que señala al `Double` valor que se le ha asignado.</span><span class="sxs-lookup"><span data-stu-id="585d7-235">The `Object` variable itself contains only a four-byte pointer, which points to the `Double` value assigned to it.</span></span>

[!code-vb[VbVbalrFunctions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#10)]

## <a name="csbyte-example"></a><span data-ttu-id="585d7-236">Ejemplo de CSByte</span><span class="sxs-lookup"><span data-stu-id="585d7-236">CSByte Example</span></span>

<span data-ttu-id="585d7-237">En el ejemplo siguiente se utiliza la `CSByte` función para convertir un valor numérico en `SByte` .</span><span class="sxs-lookup"><span data-stu-id="585d7-237">The following example uses the `CSByte` function to convert a numeric value to `SByte`.</span></span>

[!code-vb[VbVbalrFunctions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#11)]

## <a name="cshort-example"></a><span data-ttu-id="585d7-238">Ejemplo de CShort</span><span class="sxs-lookup"><span data-stu-id="585d7-238">CShort Example</span></span>

<span data-ttu-id="585d7-239">En el ejemplo siguiente se utiliza la `CShort` función para convertir un valor numérico en `Short` .</span><span class="sxs-lookup"><span data-stu-id="585d7-239">The following example uses the `CShort` function to convert a numeric value to `Short`.</span></span>

[!code-vb[VbVbalrFunctions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#12)]

## <a name="csng-example"></a><span data-ttu-id="585d7-240">Ejemplo de CSng</span><span class="sxs-lookup"><span data-stu-id="585d7-240">CSng Example</span></span>

<span data-ttu-id="585d7-241">En el ejemplo siguiente se utiliza la `CSng` función para convertir valores en `Single` .</span><span class="sxs-lookup"><span data-stu-id="585d7-241">The following example uses the `CSng` function to convert values to `Single`.</span></span>

[!code-vb[VbVbalrFunctions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#13)]

## <a name="cstr-example"></a><span data-ttu-id="585d7-242">Ejemplo de CStr</span><span class="sxs-lookup"><span data-stu-id="585d7-242">CStr Example</span></span>

<span data-ttu-id="585d7-243">En el ejemplo siguiente se utiliza la `CStr` función para convertir un valor numérico en `String` .</span><span class="sxs-lookup"><span data-stu-id="585d7-243">The following example uses the `CStr` function to convert a numeric value to `String`.</span></span>

[!code-vb[VbVbalrFunctions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#14)]

<span data-ttu-id="585d7-244">En el ejemplo siguiente se utiliza la `CStr` función para convertir `Date` valores en `String` valores.</span><span class="sxs-lookup"><span data-stu-id="585d7-244">The following example uses the `CStr` function to convert `Date` values to `String` values.</span></span>

[!code-vb[VbVbalrFunctions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#15)]

<span data-ttu-id="585d7-245">`CStr` siempre representa un `Date` valor en el formato corto estándar para la configuración regional actual, por ejemplo, "6/15/2003 4:35:47 PM".</span><span class="sxs-lookup"><span data-stu-id="585d7-245">`CStr` always renders a `Date` value in the standard short format for the current locale, for example, "6/15/2003 4:35:47 PM".</span></span> <span data-ttu-id="585d7-246">Sin embargo, `CStr` suprime los *valores neutros* de 1/1/0001 para la fecha y 00:00:00 para la hora.</span><span class="sxs-lookup"><span data-stu-id="585d7-246">However, `CStr` suppresses the *neutral values* of 1/1/0001 for the date and 00:00:00 for the time.</span></span>

<span data-ttu-id="585d7-247">Para obtener más información sobre los valores devueltos por `CStr` , vea [valores devueltos para la función CSTR](return-values-for-the-cstr-function.md).</span><span class="sxs-lookup"><span data-stu-id="585d7-247">For more detail on the values returned by `CStr`, see [Return Values for the CStr Function](return-values-for-the-cstr-function.md).</span></span>

## <a name="cuint-example"></a><span data-ttu-id="585d7-248">Ejemplo de CUInt</span><span class="sxs-lookup"><span data-stu-id="585d7-248">CUInt Example</span></span>

<span data-ttu-id="585d7-249">En el ejemplo siguiente se utiliza la `CUInt` función para convertir un valor numérico en `UInteger` .</span><span class="sxs-lookup"><span data-stu-id="585d7-249">The following example uses the `CUInt` function to convert a numeric value to `UInteger`.</span></span>

[!code-vb[VbVbalrFunctions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#16)]

## <a name="culng-example"></a><span data-ttu-id="585d7-250">Ejemplo de CULng</span><span class="sxs-lookup"><span data-stu-id="585d7-250">CULng Example</span></span>

<span data-ttu-id="585d7-251">En el ejemplo siguiente se utiliza la `CULng` función para convertir un valor numérico en `ULong` .</span><span class="sxs-lookup"><span data-stu-id="585d7-251">The following example uses the `CULng` function to convert a numeric value to `ULong`.</span></span>

[!code-vb[VbVbalrFunctions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#17)]

## <a name="cushort-example"></a><span data-ttu-id="585d7-252">Ejemplo de CUShort</span><span class="sxs-lookup"><span data-stu-id="585d7-252">CUShort Example</span></span>

<span data-ttu-id="585d7-253">En el ejemplo siguiente se utiliza la `CUShort` función para convertir un valor numérico en `UShort` .</span><span class="sxs-lookup"><span data-stu-id="585d7-253">The following example uses the `CUShort` function to convert a numeric value to `UShort`.</span></span>

[!code-vb[VbVbalrFunctions#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#18)]

## <a name="see-also"></a><span data-ttu-id="585d7-254">Vea también</span><span class="sxs-lookup"><span data-stu-id="585d7-254">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- <xref:Microsoft.VisualBasic.Strings.Format%2A>
- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:Microsoft.VisualBasic.Conversion.Oct%2A>
- <xref:Microsoft.VisualBasic.Conversion.Str%2A>
- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [<span data-ttu-id="585d7-255">Funciones de conversión</span><span class="sxs-lookup"><span data-stu-id="585d7-255">Conversion Functions</span></span>](conversion-functions.md)
- [<span data-ttu-id="585d7-256">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="585d7-256">Type Conversions in Visual Basic</span></span>](../../programming-guide/language-features/data-types/type-conversions.md)

---
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
ms.openlocfilehash: 5c0cfae01da02222d0827e81ec1ed35ce353ead1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415380"
---
# <a name="type-conversion-functions-visual-basic"></a><span data-ttu-id="5345c-102">Funciones de conversión de tipos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5345c-102">Type Conversion Functions (Visual Basic)</span></span>

<span data-ttu-id="5345c-103">Estas funciones se compilan en línea, lo que significa que el código de conversión forma parte del código que evalúa la expresión.</span><span class="sxs-lookup"><span data-stu-id="5345c-103">These functions are compiled inline, meaning the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="5345c-104">A veces no hay ninguna llamada a un procedimiento para realizar la conversión, lo que mejora el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="5345c-104">Sometimes there is no call to a procedure to accomplish the conversion, which improves performance.</span></span> <span data-ttu-id="5345c-105">Cada función convierte una expresión en un tipo de datos específico.</span><span class="sxs-lookup"><span data-stu-id="5345c-105">Each function coerces an expression to a specific data type.</span></span>

## <a name="syntax"></a><span data-ttu-id="5345c-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5345c-106">Syntax</span></span>

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

## <a name="part"></a><span data-ttu-id="5345c-107">Parte</span><span class="sxs-lookup"><span data-stu-id="5345c-107">Part</span></span>

`expression`  
<span data-ttu-id="5345c-108">Necesario.</span><span class="sxs-lookup"><span data-stu-id="5345c-108">Required.</span></span> <span data-ttu-id="5345c-109">Cualquier expresión del tipo de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="5345c-109">Any expression of the source data type.</span></span>

## <a name="return-value-data-type"></a><span data-ttu-id="5345c-110">Tipo de datos de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5345c-110">Return Value Data Type</span></span>

<span data-ttu-id="5345c-111">El nombre de la función determina el tipo de datos del valor que devuelve, tal y como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="5345c-111">The function name determines the data type of the value it returns, as shown in the following table.</span></span>

|<span data-ttu-id="5345c-112">Nombre de función</span><span class="sxs-lookup"><span data-stu-id="5345c-112">Function name</span></span>|<span data-ttu-id="5345c-113">Tipo de datos devuelto</span><span class="sxs-lookup"><span data-stu-id="5345c-113">Return data type</span></span>|<span data-ttu-id="5345c-114">Intervalo para el `expression` argumento</span><span class="sxs-lookup"><span data-stu-id="5345c-114">Range for `expression` argument</span></span>|
|-------------------|----------------------|-------------------------------------|
|`CBool`|[<span data-ttu-id="5345c-115">Tipo de datos Boolean</span><span class="sxs-lookup"><span data-stu-id="5345c-115">Boolean Data Type</span></span>](../data-types/boolean-data-type.md)|<span data-ttu-id="5345c-116">Cualquier `Char` expresión válida o `String` numérica.</span><span class="sxs-lookup"><span data-stu-id="5345c-116">Any valid `Char` or `String` or numeric expression.</span></span>|
|`CByte`|[<span data-ttu-id="5345c-117">Tipo de datos Byte</span><span class="sxs-lookup"><span data-stu-id="5345c-117">Byte Data Type</span></span>](../data-types/byte-data-type.md)|<span data-ttu-id="5345c-118"><xref:System.Byte.MinValue?displayProperty=nameWithType>(0) a <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (sin signo); las partes fraccionarias se redondean<sup> . 1</sup></span><span class="sxs-lookup"><span data-stu-id="5345c-118"><xref:System.Byte.MinValue?displayProperty=nameWithType> (0) through <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="5345c-119">A partir de Visual Basic 15,8, Visual Basic optimiza el rendimiento de la conversión de punto flotante a byte con la `CByte` función; vea la sección [comentarios](#remarks) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="5345c-119">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to byte conversion with the `CByte` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="5345c-120">Vea la sección [ejemplo de cint](#cint-example) para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5345c-120">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CChar`|[<span data-ttu-id="5345c-121">Tipo de datos Char</span><span class="sxs-lookup"><span data-stu-id="5345c-121">Char Data Type</span></span>](../data-types/char-data-type.md)|<span data-ttu-id="5345c-122">Cualquier `Char` expresión o válida `String` ; solo se convierte el primer carácter de un `String` ; el valor puede ser de 0 a 65535 (sin signo).</span><span class="sxs-lookup"><span data-stu-id="5345c-122">Any valid `Char` or `String` expression; only first character of a `String` is converted; value can be 0 through 65535 (unsigned).</span></span>|
|`CDate`|[<span data-ttu-id="5345c-123">Tipo de datos Date</span><span class="sxs-lookup"><span data-stu-id="5345c-123">Date Data Type</span></span>](../data-types/date-data-type.md)|<span data-ttu-id="5345c-124">Cualquier representación válida de una fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="5345c-124">Any valid representation of a date and time.</span></span>|
|`CDbl`|[<span data-ttu-id="5345c-125">Tipo de datos Double</span><span class="sxs-lookup"><span data-stu-id="5345c-125">Double Data Type</span></span>](../data-types/double-data-type.md)|<span data-ttu-id="5345c-126">-1.79769313486231570 e + 308 a-4.94065645841246544 E-324 para los valores negativos; 4.94065645841246544 e-324 a 1.79769313486231570 E + 308 para los valores positivos.</span><span class="sxs-lookup"><span data-stu-id="5345c-126">-1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values; 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span>|
|`CDec`|[<span data-ttu-id="5345c-127">Tipo de datos Decimal</span><span class="sxs-lookup"><span data-stu-id="5345c-127">Decimal Data Type</span></span>](../data-types/decimal-data-type.md)|<span data-ttu-id="5345c-128">+/-79.228.162.514.264.337.593.543.950.335 para números con escala cero, es decir, números sin decimales.</span><span class="sxs-lookup"><span data-stu-id="5345c-128">+/-79,228,162,514,264,337,593,543,950,335 for zero-scaled numbers, that is, numbers with no decimal places.</span></span> <span data-ttu-id="5345c-129">En el caso de números con 28 posiciones decimales, el intervalo es +/-7,9228162514264337593543950335.</span><span class="sxs-lookup"><span data-stu-id="5345c-129">For numbers with 28 decimal places, the range is +/-7.9228162514264337593543950335.</span></span> <span data-ttu-id="5345c-130">El número más pequeño posible distinto de cero es 0,0000000000000000000000000001 (+/-1E-28).</span><span class="sxs-lookup"><span data-stu-id="5345c-130">The smallest possible non-zero number is 0.0000000000000000000000000001 (+/-1E-28).</span></span>|
|`CInt`|[<span data-ttu-id="5345c-131">Tipo de datos Integer</span><span class="sxs-lookup"><span data-stu-id="5345c-131">Integer Data Type</span></span>](../data-types/integer-data-type.md)|<span data-ttu-id="5345c-132"><xref:System.Int32.MinValue?displayProperty=nameWithType>(-2.147.483.648) a <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2.147.483.647); las partes fraccionarias se redondean.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="5345c-132"><xref:System.Int32.MinValue?displayProperty=nameWithType> (-2,147,483,648) through <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2,147,483,647); fractional parts are rounded.<sup>1</sup></span></span> <br/><br/><span data-ttu-id="5345c-133">A partir de Visual Basic 15,8, Visual Basic optimiza el rendimiento de la conversión de punto flotante a entero con la `CInt` función; vea la sección [comentarios](#remarks) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="5345c-133">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to integer conversion with the `CInt` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="5345c-134">Vea la sección [ejemplo de cint](#cint-example) para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5345c-134">See the [CInt Example](#cint-example) section for an example.</span></span> |
|`CLng`|[<span data-ttu-id="5345c-135">Tipo de datos Long</span><span class="sxs-lookup"><span data-stu-id="5345c-135">Long Data Type</span></span>](../data-types/long-data-type.md)|<span data-ttu-id="5345c-136"><xref:System.Int64.MinValue?displayProperty=nameWithType>(-9.223.372.036.854.775.808) a <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9.223.372.036.854.775.807); las partes fraccionarias se redondean.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="5345c-136"><xref:System.Int64.MinValue?displayProperty=nameWithType> (-9,223,372,036,854,775,808) through <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9,223,372,036,854,775,807); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="5345c-137">A partir de Visual Basic 15,8, Visual Basic optimiza el rendimiento de la conversión de enteros de punto flotante a 64 bits con la `CLng` función; vea la sección [comentarios](#remarks) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="5345c-137">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to 64-bit integer conversion with the `CLng` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="5345c-138">Vea la sección [ejemplo de cint](#cint-example) para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5345c-138">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CObj`|[<span data-ttu-id="5345c-139">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="5345c-139">Object Data Type</span></span>](../data-types/object-data-type.md)|<span data-ttu-id="5345c-140">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="5345c-140">Any valid expression.</span></span>|
|`CSByte`|[<span data-ttu-id="5345c-141">Tipo de datos SByte</span><span class="sxs-lookup"><span data-stu-id="5345c-141">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)|<span data-ttu-id="5345c-142"><xref:System.SByte.MinValue?displayProperty=nameWithType>(-128) a <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); las partes fraccionarias se redondean.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="5345c-142"><xref:System.SByte.MinValue?displayProperty=nameWithType> (-128) through <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="5345c-143">A partir de Visual Basic 15,8, Visual Basic optimiza el rendimiento de la conversión de bytes de punto flotante a firma con la `CSByte` función; vea la sección [comentarios](#remarks) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="5345c-143">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to signed byte conversion with the `CSByte` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="5345c-144">Vea la sección [ejemplo de cint](#cint-example) para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5345c-144">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CShort`|[<span data-ttu-id="5345c-145">Tipo de datos Short</span><span class="sxs-lookup"><span data-stu-id="5345c-145">Short Data Type</span></span>](../data-types/short-data-type.md)|<span data-ttu-id="5345c-146"><xref:System.Int16.MinValue?displayProperty=nameWithType>(-32.768) a <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32.767); las partes fraccionarias se redondean.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="5345c-146"><xref:System.Int16.MinValue?displayProperty=nameWithType> (-32,768) through <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32,767); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="5345c-147">A partir de Visual Basic 15,8, Visual Basic optimiza el rendimiento de la conversión de enteros de punto flotante a 16 bits con la `CShort` función; vea la sección [comentarios](#remarks) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="5345c-147">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to 16-bit integer conversion with the `CShort` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="5345c-148">Vea la sección [ejemplo de cint](#cint-example) para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5345c-148">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CSng`|[<span data-ttu-id="5345c-149">Tipo de datos Single</span><span class="sxs-lookup"><span data-stu-id="5345c-149">Single Data Type</span></span>](../data-types/single-data-type.md)|<span data-ttu-id="5345c-150">-3.402823 e + 38 a-401298e E-45 para los valores negativos; 401298e e-45 a 3.402823 E + 38 para los valores positivos.</span><span class="sxs-lookup"><span data-stu-id="5345c-150">-3.402823E+38 through -1.401298E-45 for negative values; 1.401298E-45 through 3.402823E+38 for positive values.</span></span>|
|`CStr`|[<span data-ttu-id="5345c-151">String (Tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="5345c-151">String Data Type</span></span>](../data-types/string-data-type.md)|<span data-ttu-id="5345c-152">Returns para `CStr` dependen del `expression` argumento.</span><span class="sxs-lookup"><span data-stu-id="5345c-152">Returns for `CStr` depend on the `expression` argument.</span></span> <span data-ttu-id="5345c-153">Vea [valores devueltos para la función CSTR](return-values-for-the-cstr-function.md).</span><span class="sxs-lookup"><span data-stu-id="5345c-153">See [Return Values for the CStr Function](return-values-for-the-cstr-function.md).</span></span>|
|`CUInt`|[<span data-ttu-id="5345c-154">Tipo de datos UInteger</span><span class="sxs-lookup"><span data-stu-id="5345c-154">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)|<span data-ttu-id="5345c-155"><xref:System.UInt32.MinValue?displayProperty=nameWithType>(0) a <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4.294.967.295) (sin signo); las partes fraccionarias se redondean<sup> . 1</sup></span><span class="sxs-lookup"><span data-stu-id="5345c-155"><xref:System.UInt32.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4,294,967,295) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="5345c-156">A partir de Visual Basic 15,8, Visual Basic optimiza el rendimiento de la conversión de enteros de punto flotante a sin signo con la `CUInt` función; vea la sección [comentarios](#remarks) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="5345c-156">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned integer conversion with the `CUInt` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="5345c-157">Vea la sección [ejemplo de cint](#cint-example) para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5345c-157">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CULng`|[<span data-ttu-id="5345c-158">Tipo de datos ULong</span><span class="sxs-lookup"><span data-stu-id="5345c-158">ULong Data Type</span></span>](../data-types/ulong-data-type.md)|<span data-ttu-id="5345c-159"><xref:System.UInt64.MinValue?displayProperty=nameWithType>(0) a <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18446744073709551615) (sin signo); las partes fraccionarias se redondean<sup> . 1</sup></span><span class="sxs-lookup"><span data-stu-id="5345c-159"><xref:System.UInt64.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18,446,744,073,709,551,615) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="5345c-160">A partir de Visual Basic 15,8, Visual Basic optimiza el rendimiento de la conversión de punto flotante a entero largo sin signo con la `CULng` función; vea la sección [comentarios](#remarks) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="5345c-160">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned long integer conversion with the `CULng` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="5345c-161">Vea la sección [ejemplo de cint](#cint-example) para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5345c-161">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CUShort`|[<span data-ttu-id="5345c-162">Tipo de datos UShort</span><span class="sxs-lookup"><span data-stu-id="5345c-162">UShort Data Type</span></span>](../data-types/ushort-data-type.md)|<span data-ttu-id="5345c-163"><xref:System.UInt16.MinValue?displayProperty=nameWithType>(0) a <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65.535) (sin signo); las partes fraccionarias se redondean<sup> . 1</sup></span><span class="sxs-lookup"><span data-stu-id="5345c-163"><xref:System.UInt16.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65,535) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="5345c-164">A partir de Visual Basic 15,8, Visual Basic optimiza el rendimiento de la conversión de enteros de punto flotante a sin signo de 16 bits con la `CUShort` función; vea la sección [comentarios](#remarks) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="5345c-164">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned 16-bit integer conversion with the `CUShort` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="5345c-165">Vea la sección [ejemplo de cint](#cint-example) para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5345c-165">See the [CInt Example](#cint-example) section for an example.</span></span>|

<span data-ttu-id="5345c-166"><sup>1</sup> las partes fraccionarias pueden estar sujetas a un tipo especial de redondeo denominado *redondeo bancario*.</span><span class="sxs-lookup"><span data-stu-id="5345c-166"><sup>1</sup> Fractional parts can be subject to a special type of rounding called *banker's rounding*.</span></span> <span data-ttu-id="5345c-167">Vea "Comentarios" para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="5345c-167">See "Remarks" for more information.</span></span>

## <a name="remarks"></a><span data-ttu-id="5345c-168">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5345c-168">Remarks</span></span>

<span data-ttu-id="5345c-169">Como norma general, debe usar las funciones de conversión de tipo Visual Basic en preferencia a los métodos de .NET Framework como `ToString()` , ya sea en la <xref:System.Convert> clase o en una estructura o clase de tipo individual.</span><span class="sxs-lookup"><span data-stu-id="5345c-169">As a rule, you should use the Visual Basic type conversion functions in preference to the .NET Framework methods such as `ToString()`, either on the <xref:System.Convert> class or on an individual type structure or class.</span></span> <span data-ttu-id="5345c-170">Las funciones de Visual Basic están diseñadas para una interacción óptima con el código Visual Basic y también hacen que el código fuente sea más corto y más fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="5345c-170">The Visual Basic functions are designed for optimal interaction with Visual Basic code, and they also make your source code shorter and easier to read.</span></span> <span data-ttu-id="5345c-171">Además, los métodos de conversión de .NET Framework no siempre producen los mismos resultados que las funciones de Visual Basic, por ejemplo, al convertir `Boolean` a `Integer` .</span><span class="sxs-lookup"><span data-stu-id="5345c-171">In addition, the .NET Framework conversion methods do not always produce the same results as the Visual Basic functions, for example when converting `Boolean` to `Integer`.</span></span> <span data-ttu-id="5345c-172">Para obtener más información, vea [solución de problemas de tipos de datos](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="5345c-172">For more information, see [Troubleshooting Data Types](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

<span data-ttu-id="5345c-173">A partir de Visual Basic 15,8, el rendimiento de la conversión de punto flotante a entero se optimiza al pasar el <xref:System.Single> <xref:System.Double> valor o devuelto por los métodos siguientes a una de las funciones de conversión de enteros ( `CByte` , `CShort` , `CInt` , `CLng` , `CSByte` , `CUShort` , `CUInt` , `CULng` ):</span><span class="sxs-lookup"><span data-stu-id="5345c-173">Starting with Visual Basic 15.8, the performance of floating-point-to-integer conversion is optimized when you pass the <xref:System.Single> or <xref:System.Double> value returned by the following methods to one of the integer conversion functions (`CByte`, `CShort`, `CInt`, `CLng`, `CSByte`, `CUShort`, `CUInt`, `CULng`):</span></span>

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

<span data-ttu-id="5345c-174">Esta optimización permite que el código que realiza un gran número de conversiones de enteros se ejecute hasta dos veces más rápido.</span><span class="sxs-lookup"><span data-stu-id="5345c-174">This optimization allows code that does a large number of integer conversions to run up to twice as fast.</span></span> <span data-ttu-id="5345c-175">En el ejemplo siguiente se muestran estas conversiones optimizadas de punto flotante a entero:</span><span class="sxs-lookup"><span data-stu-id="5345c-175">The following example illustrates these optimized floating-point-to-integer conversions:</span></span>

```vb
Dim s As Single = 173.7619
Dim d As Double = s

Dim i1 As Integer = CInt(Fix(s))               ' Result: 173
Dim b1 As Byte = CByte(Int(d))                 ' Result: 173
Dim s1 AS Short = CShort(Math.Truncate(s))     ' Result: 173
Dim i2 As Integer = CInt(Math.Ceiling(d))      ' Result: 174
Dim i3 As Integer = CInt(Math.Round(s))        ' Result: 174
```

## <a name="behavior"></a><span data-ttu-id="5345c-176">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="5345c-176">Behavior</span></span>

- <span data-ttu-id="5345c-177">**Conversión.**</span><span class="sxs-lookup"><span data-stu-id="5345c-177">**Coercion.**</span></span> <span data-ttu-id="5345c-178">En general, puede utilizar las funciones de conversión de tipos de datos para convertir el resultado de una operación en un tipo de datos determinado en lugar del tipo de datos predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5345c-178">In general, you can use the data type conversion functions to coerce the result of an operation to a particular data type rather than the default data type.</span></span> <span data-ttu-id="5345c-179">Por ejemplo, use `CDec` para forzar la aritmética decimal en los casos en los que normalmente tendría lugar la aritmética de precisión sencilla, doble precisión o entero.</span><span class="sxs-lookup"><span data-stu-id="5345c-179">For example, use `CDec` to force decimal arithmetic in cases where single-precision, double-precision, or integer arithmetic would normally take place.</span></span>

- <span data-ttu-id="5345c-180">**Conversiones con errores.**</span><span class="sxs-lookup"><span data-stu-id="5345c-180">**Failed Conversions.**</span></span> <span data-ttu-id="5345c-181">Si el que se `expression` pasa a la función está fuera del intervalo del tipo de datos al que se va a convertir, <xref:System.OverflowException> se produce una.</span><span class="sxs-lookup"><span data-stu-id="5345c-181">If the `expression` passed to the function is outside the range of the data type to which it is to be converted, an <xref:System.OverflowException> occurs.</span></span>

- <span data-ttu-id="5345c-182">**Partes fraccionarias.**</span><span class="sxs-lookup"><span data-stu-id="5345c-182">**Fractional Parts.**</span></span> <span data-ttu-id="5345c-183">Cuando se convierte un valor no entero en un tipo entero, las funciones de conversión de enteros ( `CByte` , `CInt` , `CLng` , `CSByte` , `CShort` , `CUInt` , `CULng` y `CUShort` ) quitan la parte fraccionaria y redondean el valor al entero más cercano.</span><span class="sxs-lookup"><span data-stu-id="5345c-183">When you convert a nonintegral value to an integral type, the integer conversion functions (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, and `CUShort`) remove the fractional part and round the value to the closest integer.</span></span>

     <span data-ttu-id="5345c-184">Si la parte fraccionaria es exactamente 0,5, las funciones de conversión de enteros lo redondean al entero par más cercano.</span><span class="sxs-lookup"><span data-stu-id="5345c-184">If the fractional part is exactly 0.5, the integer conversion functions round it to the nearest even integer.</span></span> <span data-ttu-id="5345c-185">Por ejemplo, 0,5 se redondea a 0 y 1,5 y 2,5 se redondean a 2.</span><span class="sxs-lookup"><span data-stu-id="5345c-185">For example, 0.5 rounds to 0, and 1.5 and 2.5 both round to 2.</span></span> <span data-ttu-id="5345c-186">A veces, esto se denomina *redondeo bancario*y su finalidad es compensar una diferencia que podría acumularse al agregar muchos de estos números juntos.</span><span class="sxs-lookup"><span data-stu-id="5345c-186">This is sometimes called *banker's rounding*, and its purpose is to compensate for a bias that could accumulate when adding many such numbers together.</span></span>

     <span data-ttu-id="5345c-187">`CInt`y `CLng` difieren de las <xref:Microsoft.VisualBasic.Conversion.Int%2A> <xref:Microsoft.VisualBasic.Conversion.Fix%2A> funciones y, que truncan, en lugar de redondear, la parte fraccionaria de un número.</span><span class="sxs-lookup"><span data-stu-id="5345c-187">`CInt` and `CLng` differ from the <xref:Microsoft.VisualBasic.Conversion.Int%2A> and <xref:Microsoft.VisualBasic.Conversion.Fix%2A> functions, which truncate, rather than round, the fractional part of a number.</span></span> <span data-ttu-id="5345c-188">Además, `Fix` y `Int` siempre devuelven un valor del mismo tipo de datos que se pasa.</span><span class="sxs-lookup"><span data-stu-id="5345c-188">Also, `Fix` and `Int` always return a value of the same data type as you pass in.</span></span>

- <span data-ttu-id="5345c-189">**Conversiones de fecha y hora.**</span><span class="sxs-lookup"><span data-stu-id="5345c-189">**Date/Time Conversions.**</span></span> <span data-ttu-id="5345c-190">Use la <xref:Microsoft.VisualBasic.Information.IsDate%2A> función para determinar si un valor se puede convertir en una fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="5345c-190">Use the <xref:Microsoft.VisualBasic.Information.IsDate%2A> function to determine if a value can be converted to a date and time.</span></span> <span data-ttu-id="5345c-191">`CDate`reconoce los literales de fecha y los literales de hora, pero no los valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="5345c-191">`CDate` recognizes date literals and time literals but not numeric values.</span></span> <span data-ttu-id="5345c-192">Para convertir un valor Visual Basic 6,0 en `Date` un `Date` valor de Visual Basic 2005 o versiones posteriores, puede utilizar el <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="5345c-192">To convert a Visual Basic 6.0 `Date` value to a `Date` value in Visual Basic 2005 or later versions, you can use the <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> method.</span></span>

- <span data-ttu-id="5345c-193">**Valores de fecha y hora neutros.**</span><span class="sxs-lookup"><span data-stu-id="5345c-193">**Neutral Date/Time Values.**</span></span> <span data-ttu-id="5345c-194">El [tipo de datos Date](../data-types/date-data-type.md) siempre contiene información de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="5345c-194">The [Date Data Type](../data-types/date-data-type.md) always contains both date and time information.</span></span> <span data-ttu-id="5345c-195">A efectos de la conversión de tipos, Visual Basic considera 1/1/0001 (1 de enero del año 1) para que sea un *valor neutro* para la fecha y 00:00:00 (medianoche) como valor neutro para el tiempo.</span><span class="sxs-lookup"><span data-stu-id="5345c-195">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="5345c-196">Si convierte un `Date` valor en una cadena, no `CStr` incluye valores neutros en la cadena resultante.</span><span class="sxs-lookup"><span data-stu-id="5345c-196">If you convert a `Date` value to a string, `CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="5345c-197">Por ejemplo, si convierte `#January 1, 0001 9:30:00#` en una cadena, el resultado es "9:30:00 AM"; se suprime la información de fecha.</span><span class="sxs-lookup"><span data-stu-id="5345c-197">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="5345c-198">Sin embargo, la información de fecha todavía está presente en el `Date` valor original y se puede recuperar con funciones como <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> function.</span><span class="sxs-lookup"><span data-stu-id="5345c-198">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> function.</span></span>

- <span data-ttu-id="5345c-199">**Confidencialidad de la referencia cultural.**</span><span class="sxs-lookup"><span data-stu-id="5345c-199">**Culture Sensitivity.**</span></span> <span data-ttu-id="5345c-200">Las funciones de conversión de tipos que implican cadenas realizan conversiones basadas en la configuración de la referencia cultural actual de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5345c-200">The type conversion functions involving strings perform conversions based on the current culture settings for the application.</span></span> <span data-ttu-id="5345c-201">Por ejemplo, `CDate` reconoce los formatos de fecha según la configuración regional del sistema.</span><span class="sxs-lookup"><span data-stu-id="5345c-201">For example, `CDate` recognizes date formats according to the locale setting of your system.</span></span> <span data-ttu-id="5345c-202">Debe proporcionar el día, el mes y el año en el orden correcto de la configuración regional, o la fecha podría no interpretarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="5345c-202">You must provide the day, month, and year in the correct order for your locale, or the date might not be interpreted correctly.</span></span> <span data-ttu-id="5345c-203">No se reconoce el formato de fecha larga si contiene una cadena de día de la semana, como "miércoles".</span><span class="sxs-lookup"><span data-stu-id="5345c-203">A long date format is not recognized if it contains a day-of-the-week string, such as "Wednesday".</span></span>

     <span data-ttu-id="5345c-204">Si necesita convertir a o desde una representación de cadena de un valor en un formato distinto del especificado por la configuración regional, no puede usar las funciones de conversión de tipo Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5345c-204">If you need to convert to or from a string representation of a value in a format other than the one specified by your locale, you cannot use the Visual Basic type conversion functions.</span></span> <span data-ttu-id="5345c-205">Para ello, use los `ToString(IFormatProvider)` métodos y `Parse(String, IFormatProvider)` del tipo de ese valor.</span><span class="sxs-lookup"><span data-stu-id="5345c-205">To do this, use the `ToString(IFormatProvider)` and `Parse(String, IFormatProvider)` methods of that value's type.</span></span> <span data-ttu-id="5345c-206">Por ejemplo, <xref:System.Double.Parse%2A?displayProperty=nameWithType> se usa al convertir una cadena en un `Double` y se usa <xref:System.Double.ToString%2A?displayProperty=nameWithType> al convertir un valor de tipo `Double` en una cadena.</span><span class="sxs-lookup"><span data-stu-id="5345c-206">For example, use <xref:System.Double.Parse%2A?displayProperty=nameWithType> when converting a string to a `Double`, and use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a string.</span></span>

## <a name="ctype-function"></a><span data-ttu-id="5345c-207">CType Function</span><span class="sxs-lookup"><span data-stu-id="5345c-207">CType Function</span></span>

<span data-ttu-id="5345c-208">La [función ctype](ctype-function.md) toma un segundo argumento, `typename` , y se convierte `expression` en `typename` , donde `typename` puede ser cualquier tipo de datos, estructura, clase o interfaz a la que exista una conversión válida.</span><span class="sxs-lookup"><span data-stu-id="5345c-208">The [CType Function](ctype-function.md) takes a second argument, `typename`, and coerces `expression` to `typename`, where `typename` can be any data type, structure, class, or interface to which there exists a valid conversion.</span></span>

<span data-ttu-id="5345c-209">Para obtener una comparación de `CType` con las otras palabras clave de conversión de tipos, vea operador [DirectCast](../operators/directcast-operator.md) y [operador TryCast](../operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="5345c-209">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../operators/directcast-operator.md) and [TryCast Operator](../operators/trycast-operator.md).</span></span>

## <a name="cbool-example"></a><span data-ttu-id="5345c-210">Ejemplo de CBool</span><span class="sxs-lookup"><span data-stu-id="5345c-210">CBool Example</span></span>

<span data-ttu-id="5345c-211">En el ejemplo siguiente se utiliza la `CBool` función para convertir expresiones en `Boolean` valores.</span><span class="sxs-lookup"><span data-stu-id="5345c-211">The following example uses the `CBool` function to convert expressions to `Boolean` values.</span></span> <span data-ttu-id="5345c-212">Si una expresión se evalúa como un valor distinto de cero, `CBool` devuelve `True` ; de lo contrario, devuelve `False` .</span><span class="sxs-lookup"><span data-stu-id="5345c-212">If an expression evaluates to a nonzero value, `CBool` returns `True`; otherwise, it returns `False`.</span></span>

[!code-vb[VbVbalrFunctions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#1)]

## <a name="cbyte-example"></a><span data-ttu-id="5345c-213">Ejemplo de CByte</span><span class="sxs-lookup"><span data-stu-id="5345c-213">CByte Example</span></span>

<span data-ttu-id="5345c-214">En el ejemplo siguiente se utiliza la `CByte` función para convertir una expresión en `Byte` .</span><span class="sxs-lookup"><span data-stu-id="5345c-214">The following example uses the `CByte` function to convert an expression to a `Byte`.</span></span>

[!code-vb[VbVbalrFunctions#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#2)]

## <a name="cchar-example"></a><span data-ttu-id="5345c-215">Ejemplo de CChar</span><span class="sxs-lookup"><span data-stu-id="5345c-215">CChar Example</span></span>

<span data-ttu-id="5345c-216">En el ejemplo siguiente se utiliza la `CChar` función para convertir el primer carácter de una `String` expresión a un `Char` tipo.</span><span class="sxs-lookup"><span data-stu-id="5345c-216">The following example uses the `CChar` function to convert the first character of a `String` expression to a `Char` type.</span></span>

[!code-vb[VbVbalrFunctions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#3)]

<span data-ttu-id="5345c-217">El argumento de entrada de `CChar` debe ser de tipo de datos `Char` o `String` .</span><span class="sxs-lookup"><span data-stu-id="5345c-217">The input argument to `CChar` must be of data type `Char` or `String`.</span></span> <span data-ttu-id="5345c-218">No se puede usar `CChar` para convertir un número en un carácter, porque `CChar` no puede aceptar un tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="5345c-218">You cannot use `CChar` to convert a number to a character, because `CChar` cannot accept a numeric data type.</span></span> <span data-ttu-id="5345c-219">En el ejemplo siguiente se obtiene un número que representa un punto de código (código de carácter) y lo convierte en el carácter correspondiente.</span><span class="sxs-lookup"><span data-stu-id="5345c-219">The following example obtains a number representing a code point (character code) and converts it to the corresponding character.</span></span> <span data-ttu-id="5345c-220">Usa la <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> función para obtener la cadena de dígitos, `CInt` convertir la cadena al tipo `Integer` y `ChrW` convertir el número al tipo `Char` .</span><span class="sxs-lookup"><span data-stu-id="5345c-220">It uses the <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> function to obtain the string of digits, `CInt` to convert the string to type `Integer`, and `ChrW` to convert the number to type `Char`.</span></span>

[!code-vb[VbVbalrFunctions#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#4)]

## <a name="cdate-example"></a><span data-ttu-id="5345c-221">Ejemplo de CDate</span><span class="sxs-lookup"><span data-stu-id="5345c-221">CDate Example</span></span>

<span data-ttu-id="5345c-222">En el ejemplo siguiente se utiliza la `CDate` función para convertir cadenas en `Date` valores.</span><span class="sxs-lookup"><span data-stu-id="5345c-222">The following example uses the `CDate` function to convert strings to `Date` values.</span></span> <span data-ttu-id="5345c-223">En general, no se recomienda codificar las fechas y horas de forma rígida como cadenas (como se muestra en este ejemplo).</span><span class="sxs-lookup"><span data-stu-id="5345c-223">In general, hard-coding dates and times as strings (as shown in this example) is not recommended.</span></span> <span data-ttu-id="5345c-224">Utilice literales de fecha y literales de hora, como #Feb 12, 1969 # y #4:45:23 PM #, en su lugar.</span><span class="sxs-lookup"><span data-stu-id="5345c-224">Use date literals and time literals, such as #Feb 12, 1969# and #4:45:23 PM#, instead.</span></span>

[!code-vb[VbVbalrFunctions#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#5)]

## <a name="cdbl-example"></a><span data-ttu-id="5345c-225">Ejemplo de CDbl</span><span class="sxs-lookup"><span data-stu-id="5345c-225">CDbl Example</span></span>

[!code-vb[VbVbalrFunctions#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#6)]

## <a name="cdec-example"></a><span data-ttu-id="5345c-226">Ejemplo de CDec</span><span class="sxs-lookup"><span data-stu-id="5345c-226">CDec Example</span></span>

<span data-ttu-id="5345c-227">En el ejemplo siguiente se utiliza la `CDec` función para convertir un valor numérico en `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="5345c-227">The following example uses the `CDec` function to convert a numeric value to `Decimal`.</span></span>

[!code-vb[VbVbalrFunctions#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#7)]

## <a name="cint-example"></a><span data-ttu-id="5345c-228">Ejemplo de CInt</span><span class="sxs-lookup"><span data-stu-id="5345c-228">CInt Example</span></span>

<span data-ttu-id="5345c-229">En el ejemplo siguiente se utiliza la `CInt` función para convertir un valor en `Integer` .</span><span class="sxs-lookup"><span data-stu-id="5345c-229">The following example uses the `CInt` function to convert a value to `Integer`.</span></span>

[!code-vb[VbVbalrFunctions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#8)]

## <a name="clng-example"></a><span data-ttu-id="5345c-230">Ejemplo de CLng</span><span class="sxs-lookup"><span data-stu-id="5345c-230">CLng Example</span></span>

<span data-ttu-id="5345c-231">En el ejemplo siguiente se utiliza la `CLng` función para convertir valores en `Long` .</span><span class="sxs-lookup"><span data-stu-id="5345c-231">The following example uses the `CLng` function to convert values to `Long`.</span></span>

[!code-vb[VbVbalrFunctions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#9)]

## <a name="cobj-example"></a><span data-ttu-id="5345c-232">Ejemplo de CObj</span><span class="sxs-lookup"><span data-stu-id="5345c-232">CObj Example</span></span>

<span data-ttu-id="5345c-233">En el ejemplo siguiente se utiliza la `CObj` función para convertir un valor numérico en `Object` .</span><span class="sxs-lookup"><span data-stu-id="5345c-233">The following example uses the `CObj` function to convert a numeric value to `Object`.</span></span> <span data-ttu-id="5345c-234">La `Object` propia variable solo contiene un puntero de cuatro bytes, que señala al `Double` valor que se le ha asignado.</span><span class="sxs-lookup"><span data-stu-id="5345c-234">The `Object` variable itself contains only a four-byte pointer, which points to the `Double` value assigned to it.</span></span>

[!code-vb[VbVbalrFunctions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#10)]

## <a name="csbyte-example"></a><span data-ttu-id="5345c-235">Ejemplo de CSByte</span><span class="sxs-lookup"><span data-stu-id="5345c-235">CSByte Example</span></span>

<span data-ttu-id="5345c-236">En el ejemplo siguiente se utiliza la `CSByte` función para convertir un valor numérico en `SByte` .</span><span class="sxs-lookup"><span data-stu-id="5345c-236">The following example uses the `CSByte` function to convert a numeric value to `SByte`.</span></span>

[!code-vb[VbVbalrFunctions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#11)]

## <a name="cshort-example"></a><span data-ttu-id="5345c-237">Ejemplo de CShort</span><span class="sxs-lookup"><span data-stu-id="5345c-237">CShort Example</span></span>

<span data-ttu-id="5345c-238">En el ejemplo siguiente se utiliza la `CShort` función para convertir un valor numérico en `Short` .</span><span class="sxs-lookup"><span data-stu-id="5345c-238">The following example uses the `CShort` function to convert a numeric value to `Short`.</span></span>

[!code-vb[VbVbalrFunctions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#12)]

## <a name="csng-example"></a><span data-ttu-id="5345c-239">Ejemplo de CSng</span><span class="sxs-lookup"><span data-stu-id="5345c-239">CSng Example</span></span>

<span data-ttu-id="5345c-240">En el ejemplo siguiente se utiliza la `CSng` función para convertir valores en `Single` .</span><span class="sxs-lookup"><span data-stu-id="5345c-240">The following example uses the `CSng` function to convert values to `Single`.</span></span>

[!code-vb[VbVbalrFunctions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#13)]

## <a name="cstr-example"></a><span data-ttu-id="5345c-241">Ejemplo de CStr</span><span class="sxs-lookup"><span data-stu-id="5345c-241">CStr Example</span></span>

<span data-ttu-id="5345c-242">En el ejemplo siguiente se utiliza la `CStr` función para convertir un valor numérico en `String` .</span><span class="sxs-lookup"><span data-stu-id="5345c-242">The following example uses the `CStr` function to convert a numeric value to `String`.</span></span>

[!code-vb[VbVbalrFunctions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#14)]

<span data-ttu-id="5345c-243">En el ejemplo siguiente se utiliza la `CStr` función para convertir `Date` valores en `String` valores.</span><span class="sxs-lookup"><span data-stu-id="5345c-243">The following example uses the `CStr` function to convert `Date` values to `String` values.</span></span>

[!code-vb[VbVbalrFunctions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#15)]

<span data-ttu-id="5345c-244">`CStr`siempre representa un `Date` valor en el formato corto estándar para la configuración regional actual, por ejemplo, "6/15/2003 4:35:47 PM".</span><span class="sxs-lookup"><span data-stu-id="5345c-244">`CStr` always renders a `Date` value in the standard short format for the current locale, for example, "6/15/2003 4:35:47 PM".</span></span> <span data-ttu-id="5345c-245">Sin embargo, `CStr` suprime los *valores neutros* de 1/1/0001 para la fecha y 00:00:00 para la hora.</span><span class="sxs-lookup"><span data-stu-id="5345c-245">However, `CStr` suppresses the *neutral values* of 1/1/0001 for the date and 00:00:00 for the time.</span></span>

<span data-ttu-id="5345c-246">Para obtener más información sobre los valores devueltos por `CStr` , vea [valores devueltos para la función CSTR](return-values-for-the-cstr-function.md).</span><span class="sxs-lookup"><span data-stu-id="5345c-246">For more detail on the values returned by `CStr`, see [Return Values for the CStr Function](return-values-for-the-cstr-function.md).</span></span>

## <a name="cuint-example"></a><span data-ttu-id="5345c-247">Ejemplo de CUInt</span><span class="sxs-lookup"><span data-stu-id="5345c-247">CUInt Example</span></span>

<span data-ttu-id="5345c-248">En el ejemplo siguiente se utiliza la `CUInt` función para convertir un valor numérico en `UInteger` .</span><span class="sxs-lookup"><span data-stu-id="5345c-248">The following example uses the `CUInt` function to convert a numeric value to `UInteger`.</span></span>

[!code-vb[VbVbalrFunctions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#16)]

## <a name="culng-example"></a><span data-ttu-id="5345c-249">Ejemplo de CULng</span><span class="sxs-lookup"><span data-stu-id="5345c-249">CULng Example</span></span>

<span data-ttu-id="5345c-250">En el ejemplo siguiente se utiliza la `CULng` función para convertir un valor numérico en `ULong` .</span><span class="sxs-lookup"><span data-stu-id="5345c-250">The following example uses the `CULng` function to convert a numeric value to `ULong`.</span></span>

[!code-vb[VbVbalrFunctions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#17)]

## <a name="cushort-example"></a><span data-ttu-id="5345c-251">Ejemplo de CUShort</span><span class="sxs-lookup"><span data-stu-id="5345c-251">CUShort Example</span></span>

<span data-ttu-id="5345c-252">En el ejemplo siguiente se utiliza la `CUShort` función para convertir un valor numérico en `UShort` .</span><span class="sxs-lookup"><span data-stu-id="5345c-252">The following example uses the `CUShort` function to convert a numeric value to `UShort`.</span></span>

[!code-vb[VbVbalrFunctions#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#18)]

## <a name="see-also"></a><span data-ttu-id="5345c-253">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5345c-253">See also</span></span>

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
- [<span data-ttu-id="5345c-254">Funciones de conversión</span><span class="sxs-lookup"><span data-stu-id="5345c-254">Conversion Functions</span></span>](conversion-functions.md)
- [<span data-ttu-id="5345c-255">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5345c-255">Type Conversions in Visual Basic</span></span>](../../programming-guide/language-features/data-types/type-conversions.md)

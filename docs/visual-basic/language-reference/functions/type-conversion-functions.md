---
title: Funciones de conversión de tipos (Visual Basic)
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
ms.openlocfilehash: 2b750f41343a4a68e29af6055815efd1e6470252
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816270"
---
# <a name="type-conversion-functions-visual-basic"></a><span data-ttu-id="9ef69-102">Funciones de conversión de tipos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9ef69-102">Type Conversion Functions (Visual Basic)</span></span>
<span data-ttu-id="9ef69-103">Estas funciones están compilados en línea, lo que significa que el código de conversión forma parte del código que evalúa la expresión.</span><span class="sxs-lookup"><span data-stu-id="9ef69-103">These functions are compiled inline, meaning the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="9ef69-104">En ocasiones, no hay ninguna llamada a un procedimiento para realizar la conversión, lo que mejora el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="9ef69-104">Sometimes there is no call to a procedure to accomplish the conversion, which improves performance.</span></span> <span data-ttu-id="9ef69-105">Cada función convierte una expresión a un tipo de datos específico.</span><span class="sxs-lookup"><span data-stu-id="9ef69-105">Each function coerces an expression to a specific data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ef69-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9ef69-106">Syntax</span></span>  
  
```  
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
  
## <a name="part"></a><span data-ttu-id="9ef69-107">Parte</span><span class="sxs-lookup"><span data-stu-id="9ef69-107">Part</span></span>  
 `expression`  
 <span data-ttu-id="9ef69-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="9ef69-108">Required.</span></span> <span data-ttu-id="9ef69-109">Cualquier expresión del tipo de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="9ef69-109">Any expression of the source data type.</span></span>  
  
## <a name="return-value-data-type"></a><span data-ttu-id="9ef69-110">Tipo de datos de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9ef69-110">Return Value Data Type</span></span>  
 <span data-ttu-id="9ef69-111">El nombre de la función determina el tipo de datos del valor que devuelve, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="9ef69-111">The function name determines the data type of the value it returns, as shown in the following table.</span></span>  
  
|<span data-ttu-id="9ef69-112">Nombre de la función</span><span class="sxs-lookup"><span data-stu-id="9ef69-112">Function name</span></span>|<span data-ttu-id="9ef69-113">Tipo de datos devuelto</span><span class="sxs-lookup"><span data-stu-id="9ef69-113">Return data type</span></span>|<span data-ttu-id="9ef69-114">Intervalo para `expression` argumento</span><span class="sxs-lookup"><span data-stu-id="9ef69-114">Range for `expression` argument</span></span>|  
|-------------------|----------------------|-------------------------------------|  
|`CBool`|[<span data-ttu-id="9ef69-115">Boolean (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="9ef69-115">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="9ef69-116">Cualquier `Char` o `String` o expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="9ef69-116">Any valid `Char` or `String` or numeric expression.</span></span>|  
|`CByte`|[<span data-ttu-id="9ef69-117">Byte (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="9ef69-117">Byte Data Type</span></span>](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="9ef69-118"><xref:System.Byte.MinValue?displayProperty=nameWithType> (0) a través de <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (sin signo); se redondean partes fraccionarias.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="9ef69-118"><xref:System.Byte.MinValue?displayProperty=nameWithType> (0) through <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="9ef69-119">A partir de 15,8 Visual Basic, Visual Basic optimiza el rendimiento de punto flotante para la conversión de bytes con el `CByte` función; vea la [comentarios](#remarks) sección para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9ef69-119">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to byte conversion with the `CByte` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="9ef69-120">Consulte la [ejemplo CInt](#cint-example) sección para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9ef69-120">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CChar`|[<span data-ttu-id="9ef69-121">Char (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="9ef69-121">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="9ef69-122">Cualquier `Char` o `String` expresión; sólo primer carácter de un `String` se convierten; puede oscilar entre 0 y 65535 (sin signo).</span><span class="sxs-lookup"><span data-stu-id="9ef69-122">Any valid `Char` or `String` expression; only first character of a `String` is converted; value can be 0 through 65535 (unsigned).</span></span>|  
|`CDate`|[<span data-ttu-id="9ef69-123">Date (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="9ef69-123">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="9ef69-124">Cualquier representación válida de una fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="9ef69-124">Any valid representation of a date and time.</span></span>|  
|`CDbl`|[<span data-ttu-id="9ef69-125">Double (tipos de datos)</span><span class="sxs-lookup"><span data-stu-id="9ef69-125">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)|<span data-ttu-id="9ef69-126">-1, 79769313486231570E + 308 a - 4, 94065645841246544E-324 para valores negativos; 4, 94065645841246544E-324 a 1, 79769313486231570E + 308 para los valores positivos.</span><span class="sxs-lookup"><span data-stu-id="9ef69-126">-1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values; 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span>|  
|`CDec`|[<span data-ttu-id="9ef69-127">Decimal (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="9ef69-127">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="9ef69-128">+/-79.228.162.514.264.337.593.543.950.335 para números a partir de cero, es decir, los números sin posiciones decimales.</span><span class="sxs-lookup"><span data-stu-id="9ef69-128">+/-79,228,162,514,264,337,593,543,950,335 for zero-scaled numbers, that is, numbers with no decimal places.</span></span> <span data-ttu-id="9ef69-129">Para números con 28 posiciones decimales, el intervalo es +/-7,9228162514264337593543950335.</span><span class="sxs-lookup"><span data-stu-id="9ef69-129">For numbers with 28 decimal places, the range is +/-7.9228162514264337593543950335.</span></span> <span data-ttu-id="9ef69-130">El menor número posible distinto de cero es 0,0000000000000000000000000001 (+/-1E-28).</span><span class="sxs-lookup"><span data-stu-id="9ef69-130">The smallest possible non-zero number is 0.0000000000000000000000000001 (+/-1E-28).</span></span>|  
|`CInt`|[<span data-ttu-id="9ef69-131">Integer (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="9ef69-131">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="9ef69-132"><xref:System.Int32.MinValue?displayProperty=nameWithType> (-2.147.483.648) a través de <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2.147.483.647); se redondean partes fraccionarias.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="9ef69-132"><xref:System.Int32.MinValue?displayProperty=nameWithType> (-2,147,483,648) through <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2,147,483,647); fractional parts are rounded.<sup>1</sup></span></span> <br/><br/><span data-ttu-id="9ef69-133">A partir de 15,8 Visual Basic, Visual Basic optimiza el rendimiento de punto flotante para la conversión de entero con el `CInt` función; vea la [comentarios](#remarks) sección para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9ef69-133">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to integer conversion with the `CInt` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="9ef69-134">Consulte la [ejemplo CInt](#cint-example) sección para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9ef69-134">See the [CInt Example](#cint-example) section for an example.</span></span> |  
|`CLng`|[<span data-ttu-id="9ef69-135">Long (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="9ef69-135">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="9ef69-136"><xref:System.Int64.MinValue?displayProperty=nameWithType> (-9.223.372.036.854.775.808) a través de <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9.223.372.036.854.775.807); se redondean partes fraccionarias.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="9ef69-136"><xref:System.Int64.MinValue?displayProperty=nameWithType> (-9,223,372,036,854,775,808) through <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9,223,372,036,854,775,807); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="9ef69-137">A partir de 15,8 Visual Basic, Visual Basic optimiza el rendimiento de punto flotante para la conversión de entero de 64 bits con el `CLng` función; vea la [comentarios](#remarks) sección para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9ef69-137">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to 64-bit integer conversion with the `CLng` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="9ef69-138">Consulte la [ejemplo CInt](#cint-example) sección para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9ef69-138">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CObj`|[<span data-ttu-id="9ef69-139">Tipo de objeto de datos</span><span class="sxs-lookup"><span data-stu-id="9ef69-139">Object Data Type</span></span>](../../../visual-basic/language-reference/data-types/object-data-type.md)|<span data-ttu-id="9ef69-140">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="9ef69-140">Any valid expression.</span></span>|  
|`CSByte`|[<span data-ttu-id="9ef69-141">SByte (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="9ef69-141">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="9ef69-142"><xref:System.SByte.MinValue?displayProperty=nameWithType> -(128) a través de <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); se redondean partes fraccionarias.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="9ef69-142"><xref:System.SByte.MinValue?displayProperty=nameWithType> (-128) through <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="9ef69-143">A partir de 15,8 Visual Basic, Visual Basic optimiza el rendimiento de punto flotante para la conversión de bytes con signo con el `CSByte` función; vea la [comentarios](#remarks) sección para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9ef69-143">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to signed byte conversion with the `CSByte` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="9ef69-144">Consulte la [ejemplo CInt](#cint-example) sección para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9ef69-144">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CShort`|[<span data-ttu-id="9ef69-145">Short (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="9ef69-145">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="9ef69-146"><xref:System.Int16.MinValue?displayProperty=nameWithType> (-32.768) a través de <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32.767); se redondean partes fraccionarias.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="9ef69-146"><xref:System.Int16.MinValue?displayProperty=nameWithType> (-32,768) through <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32,767); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="9ef69-147">A partir de 15,8 Visual Basic, Visual Basic optimiza el rendimiento de punto flotante para la conversión de entero de 16 bits con el `CShort` función; vea la [comentarios](#remarks) sección para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9ef69-147">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to 16-bit integer conversion with the `CShort` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="9ef69-148">Consulte la [ejemplo CInt](#cint-example) sección para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9ef69-148">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CSng`|[<span data-ttu-id="9ef69-149">Single (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="9ef69-149">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="9ef69-150">-3, 402823E + 38 a - 1, 401298E-45 para los valores negativos; 1, 401298E-45 a 3, 402823E + 38 para los valores positivos.</span><span class="sxs-lookup"><span data-stu-id="9ef69-150">-3.402823E+38 through -1.401298E-45 for negative values; 1.401298E-45 through 3.402823E+38 for positive values.</span></span>|  
|`CStr`|[<span data-ttu-id="9ef69-151">String (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="9ef69-151">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)|<span data-ttu-id="9ef69-152">Devuelve para `CStr` dependen de la `expression` argumento.</span><span class="sxs-lookup"><span data-stu-id="9ef69-152">Returns for `CStr` depend on the `expression` argument.</span></span> <span data-ttu-id="9ef69-153">Consulte [valores devueltos para la función CStr](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span><span class="sxs-lookup"><span data-stu-id="9ef69-153">See [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>|  
|`CUInt`|[<span data-ttu-id="9ef69-154">UInteger (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="9ef69-154">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="9ef69-155"><xref:System.UInt32.MinValue?displayProperty=nameWithType> (0) a través de <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4,294,967,295) (sin signo); se redondean partes fraccionarias.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="9ef69-155"><xref:System.UInt32.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4,294,967,295) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="9ef69-156">A partir de 15,8 Visual Basic, Visual Basic optimiza el rendimiento de punto flotante para la conversión de entero sin signo con el `CUInt` función; vea la [comentarios](#remarks) sección para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9ef69-156">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned integer conversion with the `CUInt` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="9ef69-157">Consulte la [ejemplo CInt](#cint-example) sección para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9ef69-157">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CULng`|[<span data-ttu-id="9ef69-158">ULong (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="9ef69-158">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="9ef69-159"><xref:System.UInt64.MinValue?displayProperty=nameWithType> (0) a través de <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18.446.744.073.709.551.615) (sin signo); se redondean partes fraccionarias.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="9ef69-159"><xref:System.UInt64.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18,446,744,073,709,551,615) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="9ef69-160">A partir de 15,8 Visual Basic, Visual Basic optimiza el rendimiento de punto flotante para la conversión de entero largo sin signo con el `CULng` función; vea la [comentarios](#remarks) sección para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9ef69-160">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned long integer conversion with the `CULng` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="9ef69-161">Consulte la [ejemplo CInt](#cint-example) sección para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9ef69-161">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CUShort`|[<span data-ttu-id="9ef69-162">UShort (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="9ef69-162">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="9ef69-163"><xref:System.UInt16.MinValue?displayProperty=nameWithType> (0) a través de <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65.535) (sin signo); se redondean partes fraccionarias.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="9ef69-163"><xref:System.UInt16.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65,535) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="9ef69-164">A partir de 15,8 Visual Basic, Visual Basic optimiza el rendimiento de punto flotante para la conversión de entero de 16 bits sin signo con el `CUShort` función; vea la [comentarios](#remarks) sección para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9ef69-164">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned 16-bit integer conversion with the `CUShort` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="9ef69-165">Consulte la [ejemplo CInt](#cint-example) sección para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9ef69-165">See the [CInt Example](#cint-example) section for an example.</span></span>|  
  
 <span data-ttu-id="9ef69-166"><sup>1</sup> partes fraccionarias pueden estar sujetas a un tipo especial de redondeo llamado *redondeo bancario*.</span><span class="sxs-lookup"><span data-stu-id="9ef69-166"><sup>1</sup> Fractional parts can be subject to a special type of rounding called *banker's rounding*.</span></span> <span data-ttu-id="9ef69-167">Para obtener más información, vea "Comentarios".</span><span class="sxs-lookup"><span data-stu-id="9ef69-167">See "Remarks" for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ef69-168">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9ef69-168">Remarks</span></span>  
 <span data-ttu-id="9ef69-169">Como norma, debe utilizar las funciones de conversión de tipo Visual Basic con preferencia a los métodos de .NET Framework como `ToString()`, ya sea en la <xref:System.Convert> clase o en una estructura de tipo individual o una clase.</span><span class="sxs-lookup"><span data-stu-id="9ef69-169">As a rule, you should use the Visual Basic type conversion functions in preference to the .NET Framework methods such as `ToString()`, either on the <xref:System.Convert> class or on an individual type structure or class.</span></span> <span data-ttu-id="9ef69-170">Las funciones de Visual Basic están diseñadas para la interacción óptima con código de Visual Basic, y también realizan el código fuente más corto y fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="9ef69-170">The Visual Basic functions are designed for optimal interaction with Visual Basic code, and they also make your source code shorter and easier to read.</span></span> <span data-ttu-id="9ef69-171">Además, los métodos de conversión de .NET Framework no siempre producen los mismos resultados que las funciones de Visual Basic, por ejemplo, al convertir `Boolean` a `Integer`.</span><span class="sxs-lookup"><span data-stu-id="9ef69-171">In addition, the .NET Framework conversion methods do not always produce the same results as the Visual Basic functions, for example when converting `Boolean` to `Integer`.</span></span> <span data-ttu-id="9ef69-172">Para obtener más información, consulte [solución de problemas de los tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="9ef69-172">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  


<span data-ttu-id="9ef69-173">A partir de Visual Basic 15,8, se optimiza el rendimiento de la conversión de flotante a punto a entero al pasar el <xref:System.Single> o <xref:System.Double> valor devuelto por los métodos siguientes para una de las funciones de conversión de enteros (`CByte`, `CShort`, `CInt`, `CLng`, `CSByte`, `CUShort`, `CUInt`, `CULng`):</span><span class="sxs-lookup"><span data-stu-id="9ef69-173">Starting with Visual Basic 15.8, the performance of floating-point-to-integer conversion is optimized when you pass the <xref:System.Single> or <xref:System.Double> value returned by the following methods to one of the integer conversion functions (`CByte`, `CShort`, `CInt`, `CLng`, `CSByte`, `CUShort`, `CUInt`, `CULng`):</span></span>

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

<span data-ttu-id="9ef69-174">Esta optimización permite que el código que realiza un gran número de conversiones de enteros al ejecutarse el doble de rápido.</span><span class="sxs-lookup"><span data-stu-id="9ef69-174">This optimization allows code that does a large number of integer conversions to run up to twice as fast.</span></span> <span data-ttu-id="9ef69-175">El ejemplo siguiente muestra estas conversiones de flotante a punto para entero optimizadas:</span><span class="sxs-lookup"><span data-stu-id="9ef69-175">The following example illustrates these optimized floating-point-to-integer conversions:</span></span>

```vb
Dim s As Single = 173.7619
Dim d As Double = s 

Dim i1 As Integer = CInt(Fix(s))               ' Result: 173
Dim b1 As Byte = CByte(Int(d))                 ' Result: 173
Dim s1 AS Short = CShort(Math.Truncate(s))     ' Result: 173
Dim i2 As Integer = CInt(Math.Ceiling(d))      ' Result: 174
Dim i3 As Integer = CInt(Math.Round(s))        ' Result: 174
```

## <a name="behavior"></a><span data-ttu-id="9ef69-176">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="9ef69-176">Behavior</span></span>  
  
-   <span data-ttu-id="9ef69-177">**Coercion.**</span><span class="sxs-lookup"><span data-stu-id="9ef69-177">**Coercion.**</span></span> <span data-ttu-id="9ef69-178">En general, puede usar las funciones de conversión de tipo de datos para convertir el resultado de una operación a un tipo de datos concreto en lugar de con el tipo de datos de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9ef69-178">In general, you can use the data type conversion functions to coerce the result of an operation to a particular data type rather than the default data type.</span></span> <span data-ttu-id="9ef69-179">Por ejemplo, use `CDec` para forzar la aritmética decimal en los casos donde se haría precisión sencilla, doble precisión o aritmética de enteros.</span><span class="sxs-lookup"><span data-stu-id="9ef69-179">For example, use `CDec` to force decimal arithmetic in cases where single-precision, double-precision, or integer arithmetic would normally take place.</span></span>  
  
-   <span data-ttu-id="9ef69-180">**Error en conversiones.**</span><span class="sxs-lookup"><span data-stu-id="9ef69-180">**Failed Conversions.**</span></span> <span data-ttu-id="9ef69-181">Si el `expression` pasa a la función es fuera del intervalo del tipo de datos donde va a convertir, un <xref:System.OverflowException> se produce.</span><span class="sxs-lookup"><span data-stu-id="9ef69-181">If the `expression` passed to the function is outside the range of the data type to which it is to be converted, an <xref:System.OverflowException> occurs.</span></span>  
  
-   <span data-ttu-id="9ef69-182">**Partes fraccionarias.**</span><span class="sxs-lookup"><span data-stu-id="9ef69-182">**Fractional Parts.**</span></span> <span data-ttu-id="9ef69-183">Escriba al convertir un valor no integral a un entero, las funciones de conversión de enteros (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, y `CUShort`) quitar el fraccionarios parte y redondeo del valor al entero más próximo.</span><span class="sxs-lookup"><span data-stu-id="9ef69-183">When you convert a nonintegral value to an integral type, the integer conversion functions (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, and `CUShort`) remove the fractional part and round the value to the closest integer.</span></span>  
  
     <span data-ttu-id="9ef69-184">Si la parte fraccionaria es exactamente 0,5, las funciones de conversión de enteros que redondean el entero par más próximo.</span><span class="sxs-lookup"><span data-stu-id="9ef69-184">If the fractional part is exactly 0.5, the integer conversion functions round it to the nearest even integer.</span></span> <span data-ttu-id="9ef69-185">Por ejemplo, 0,5 se redondea a 0 y 1,5 y 2,5 se redondean a 2.</span><span class="sxs-lookup"><span data-stu-id="9ef69-185">For example, 0.5 rounds to 0, and 1.5 and 2.5 both round to 2.</span></span> <span data-ttu-id="9ef69-186">Esto se denomina a veces *redondeo bancario*, y su finalidad es compensar una tendencia que se podría acumular al sumar muchos de estos números.</span><span class="sxs-lookup"><span data-stu-id="9ef69-186">This is sometimes called *banker's rounding*, and its purpose is to compensate for a bias that could accumulate when adding many such numbers together.</span></span>  
  
     <span data-ttu-id="9ef69-187">`CInt` y `CLng` diferir la <xref:Microsoft.VisualBasic.Conversion.Int%2A> y <xref:Microsoft.VisualBasic.Conversion.Fix%2A> funciones, que se truncan en lugar de ida y vuelta, la parte fraccionaria de un número.</span><span class="sxs-lookup"><span data-stu-id="9ef69-187">`CInt` and `CLng` differ from the <xref:Microsoft.VisualBasic.Conversion.Int%2A> and <xref:Microsoft.VisualBasic.Conversion.Fix%2A> functions, which truncate, rather than round, the fractional part of a number.</span></span> <span data-ttu-id="9ef69-188">Además, `Fix` y `Int` siempre devuelven un valor del mismo tipo de datos que se pasa.</span><span class="sxs-lookup"><span data-stu-id="9ef69-188">Also, `Fix` and `Int` always return a value of the same data type as you pass in.</span></span>  
  
-   <span data-ttu-id="9ef69-189">**Las conversiones de fecha y hora.**</span><span class="sxs-lookup"><span data-stu-id="9ef69-189">**Date/Time Conversions.**</span></span> <span data-ttu-id="9ef69-190">Use el <xref:Microsoft.VisualBasic.Information.IsDate%2A> función para determinar si se puede convertir un valor a una fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="9ef69-190">Use the <xref:Microsoft.VisualBasic.Information.IsDate%2A> function to determine if a value can be converted to a date and time.</span></span> <span data-ttu-id="9ef69-191">`CDate` reconoce los literales de fecha y hora, pero no valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="9ef69-191">`CDate` recognizes date literals and time literals but not numeric values.</span></span> <span data-ttu-id="9ef69-192">Para convertir un objeto Visual Basic 6.0 `Date` valor a un `Date` valor en Visual Basic 2005 o versiones posteriores, puede usar el <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="9ef69-192">To convert a Visual Basic 6.0 `Date` value to a `Date` value in Visual Basic 2005 or later versions, you can use the <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="9ef69-193">**Neutral valores de fecha y hora.**</span><span class="sxs-lookup"><span data-stu-id="9ef69-193">**Neutral Date/Time Values.**</span></span> <span data-ttu-id="9ef69-194">El [tipo de datos Date](../../../visual-basic/language-reference/data-types/date-data-type.md) siempre contiene información de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="9ef69-194">The [Date Data Type](../../../visual-basic/language-reference/data-types/date-data-type.md) always contains both date and time information.</span></span> <span data-ttu-id="9ef69-195">Para fines de conversión de tipos, Visual Basic considera 1/1/0001 (del 1 de enero del año 1) sea un *valor neutral* de fecha y 00:00:00 (medianoche) un valor neutral para el tiempo.</span><span class="sxs-lookup"><span data-stu-id="9ef69-195">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="9ef69-196">Si convierte un `Date` valor en una cadena, `CStr` no incluye valores neutrales en la cadena resultante.</span><span class="sxs-lookup"><span data-stu-id="9ef69-196">If you convert a `Date` value to a string, `CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="9ef69-197">Por ejemplo, si convierte `#January 1, 0001 9:30:00#` en una cadena, el resultado es "9:30:00 AM"; se suprime la información de fecha.</span><span class="sxs-lookup"><span data-stu-id="9ef69-197">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="9ef69-198">Sin embargo, la información de fecha aún está presente en el original `Date` valor y se pueden recuperar con funciones como <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> función.</span><span class="sxs-lookup"><span data-stu-id="9ef69-198">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> function.</span></span>  
  
-   <span data-ttu-id="9ef69-199">**Sensibilidad de la referencia cultural.**</span><span class="sxs-lookup"><span data-stu-id="9ef69-199">**Culture Sensitivity.**</span></span> <span data-ttu-id="9ef69-200">Las funciones de conversión de tipo que implican cadenas realizan conversiones en función de la configuración de la referencia cultural actual para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9ef69-200">The type conversion functions involving strings perform conversions based on the current culture settings for the application.</span></span> <span data-ttu-id="9ef69-201">Por ejemplo, `CDate` reconoce los formatos de fecha según la configuración regional del sistema.</span><span class="sxs-lookup"><span data-stu-id="9ef69-201">For example, `CDate` recognizes date formats according to the locale setting of your system.</span></span> <span data-ttu-id="9ef69-202">Debe proporcionar el día, mes y año en el orden correcto para la configuración regional o la fecha no se interpreten correctamente.</span><span class="sxs-lookup"><span data-stu-id="9ef69-202">You must provide the day, month, and year in the correct order for your locale, or the date might not be interpreted correctly.</span></span> <span data-ttu-id="9ef69-203">No se reconoce el formato de fecha larga si contiene una cadena de día de la semana, por ejemplo, "Wednesday".</span><span class="sxs-lookup"><span data-stu-id="9ef69-203">A long date format is not recognized if it contains a day-of-the-week string, such as "Wednesday".</span></span>  
  
     <span data-ttu-id="9ef69-204">Si necesita convertir hacia o desde una representación de cadena de un valor en un formato distinto al especificado por la configuración regional, no puede usar las funciones de conversión de tipo de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9ef69-204">If you need to convert to or from a string representation of a value in a format other than the one specified by your locale, you cannot use the Visual Basic type conversion functions.</span></span> <span data-ttu-id="9ef69-205">Para ello, use el `ToString(IFormatProvider)` y `Parse(String, IFormatProvider)` métodos de ese tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="9ef69-205">To do this, use the `ToString(IFormatProvider)` and `Parse(String, IFormatProvider)` methods of that value's type.</span></span> <span data-ttu-id="9ef69-206">Por ejemplo, usar <xref:System.Double.Parse%2A?displayProperty=nameWithType> al convertir una cadena en un `Double`y usar <xref:System.Double.ToString%2A?displayProperty=nameWithType> al convertir un valor de tipo `Double` en una cadena.</span><span class="sxs-lookup"><span data-stu-id="9ef69-206">For example, use <xref:System.Double.Parse%2A?displayProperty=nameWithType> when converting a string to a `Double`, and use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a string.</span></span>  
  
## <a name="ctype-function"></a><span data-ttu-id="9ef69-207">CType Function</span><span class="sxs-lookup"><span data-stu-id="9ef69-207">CType Function</span></span>  
 <span data-ttu-id="9ef69-208">El [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) toma un segundo argumento, `typename`y convierte `expression` a `typename`, donde `typename` puede ser cualquier tipo de datos, estructura, clase o interfaz a la que existe una conversión válida.</span><span class="sxs-lookup"><span data-stu-id="9ef69-208">The [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) takes a second argument, `typename`, and coerces `expression` to `typename`, where `typename` can be any data type, structure, class, or interface to which there exists a valid conversion.</span></span>  
  
 <span data-ttu-id="9ef69-209">Para obtener una comparación de `CType` con otro tipo palabras clave de conversión, consulte [DirectCast (operador)](../../../visual-basic/language-reference/operators/directcast-operator.md) y [TryCast (operador)](../../../visual-basic/language-reference/operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="9ef69-209">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span>  
  
## <a name="cbool-example"></a><span data-ttu-id="9ef69-210">Ejemplo de CBool</span><span class="sxs-lookup"><span data-stu-id="9ef69-210">CBool Example</span></span>  
 <span data-ttu-id="9ef69-211">En el ejemplo siguiente se usa el `CBool` función para convertir expresiones en `Boolean` valores.</span><span class="sxs-lookup"><span data-stu-id="9ef69-211">The following example uses the `CBool` function to convert expressions to `Boolean` values.</span></span> <span data-ttu-id="9ef69-212">Si una expresión se evalúa como un valor distinto de cero, `CBool` devuelve `True`; en caso contrario, devuelve `False`.</span><span class="sxs-lookup"><span data-stu-id="9ef69-212">If an expression evaluates to a nonzero value, `CBool` returns `True`; otherwise, it returns `False`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#1)]  
  
## <a name="cbyte-example"></a><span data-ttu-id="9ef69-213">Ejemplo de CByte</span><span class="sxs-lookup"><span data-stu-id="9ef69-213">CByte Example</span></span>  
 <span data-ttu-id="9ef69-214">En el ejemplo siguiente se usa el `CByte` función para convertir una expresión a un `Byte`.</span><span class="sxs-lookup"><span data-stu-id="9ef69-214">The following example uses the `CByte` function to convert an expression to a `Byte`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#2)]  
  
## <a name="cchar-example"></a><span data-ttu-id="9ef69-215">Ejemplo de CChar</span><span class="sxs-lookup"><span data-stu-id="9ef69-215">CChar Example</span></span>  
 <span data-ttu-id="9ef69-216">En el ejemplo siguiente se usa el `CChar` función para convertir el primer carácter de un `String` expresión a un `Char` tipo.</span><span class="sxs-lookup"><span data-stu-id="9ef69-216">The following example uses the `CChar` function to convert the first character of a `String` expression to a `Char` type.</span></span>  
  
 [!code-vb[VbVbalrFunctions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#3)]  
  
 <span data-ttu-id="9ef69-217">El argumento de entrada `CChar` debe ser del tipo de datos `Char` o `String`.</span><span class="sxs-lookup"><span data-stu-id="9ef69-217">The input argument to `CChar` must be of data type `Char` or `String`.</span></span> <span data-ttu-id="9ef69-218">No puede usar `CChar` para convertir un número en un carácter, porque `CChar` no acepta un tipo de datos numéricos.</span><span class="sxs-lookup"><span data-stu-id="9ef69-218">You cannot use `CChar` to convert a number to a character, because `CChar` cannot accept a numeric data type.</span></span> <span data-ttu-id="9ef69-219">El ejemplo siguiente obtiene un número que representa un punto de código (código de carácter) y lo convierte en el carácter correspondiente.</span><span class="sxs-lookup"><span data-stu-id="9ef69-219">The following example obtains a number representing a code point (character code) and converts it to the corresponding character.</span></span> <span data-ttu-id="9ef69-220">Usa el <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> función para obtener la cadena de dígitos, `CInt` para convertir la cadena al tipo `Integer`, y `ChrW` para convertir el número que se escriba `Char`.</span><span class="sxs-lookup"><span data-stu-id="9ef69-220">It uses the <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> function to obtain the string of digits, `CInt` to convert the string to type `Integer`, and `ChrW` to convert the number to type `Char`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#4)]  
  
## <a name="cdate-example"></a><span data-ttu-id="9ef69-221">Ejemplo de CDate</span><span class="sxs-lookup"><span data-stu-id="9ef69-221">CDate Example</span></span>  
 <span data-ttu-id="9ef69-222">En el ejemplo siguiente se usa el `CDate` función para convertir cadenas a `Date` valores.</span><span class="sxs-lookup"><span data-stu-id="9ef69-222">The following example uses the `CDate` function to convert strings to `Date` values.</span></span> <span data-ttu-id="9ef69-223">En general, no se recomienda codificar de forma rígida fechas y horas como cadenas (como se muestra en este ejemplo).</span><span class="sxs-lookup"><span data-stu-id="9ef69-223">In general, hard-coding dates and times as strings (as shown in this example) is not recommended.</span></span> <span data-ttu-id="9ef69-224">Utilice literales de fecha y hora, por ejemplo #Feb 12, 1969 # y # 4:45:23 PM # en su lugar.</span><span class="sxs-lookup"><span data-stu-id="9ef69-224">Use date literals and time literals, such as #Feb 12, 1969# and #4:45:23 PM#, instead.</span></span>  
  
 [!code-vb[VbVbalrFunctions#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#5)]  
  
## <a name="cdbl-example"></a><span data-ttu-id="9ef69-225">Ejemplo de CDbl</span><span class="sxs-lookup"><span data-stu-id="9ef69-225">CDbl Example</span></span>  
 [!code-vb[VbVbalrFunctions#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#6)]  
  
## <a name="cdec-example"></a><span data-ttu-id="9ef69-226">Ejemplo de CDec</span><span class="sxs-lookup"><span data-stu-id="9ef69-226">CDec Example</span></span>  
 <span data-ttu-id="9ef69-227">En el ejemplo siguiente se usa el `CDec` función para convertir un valor numérico para `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="9ef69-227">The following example uses the `CDec` function to convert a numeric value to `Decimal`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#7)]  
  
## <a name="cint-example"></a><span data-ttu-id="9ef69-228">Ejemplo de CInt</span><span class="sxs-lookup"><span data-stu-id="9ef69-228">CInt Example</span></span>  
 <span data-ttu-id="9ef69-229">En el ejemplo siguiente se usa el `CInt` función para convertir un valor a `Integer`.</span><span class="sxs-lookup"><span data-stu-id="9ef69-229">The following example uses the `CInt` function to convert a value to `Integer`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#8)]  

## <a name="clng-example"></a><span data-ttu-id="9ef69-230">Ejemplo de CLng</span><span class="sxs-lookup"><span data-stu-id="9ef69-230">CLng Example</span></span>
 <span data-ttu-id="9ef69-231">En el ejemplo siguiente se usa el `CLng` función para convertir los valores para `Long`.</span><span class="sxs-lookup"><span data-stu-id="9ef69-231">The following example uses the `CLng` function to convert values to `Long`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#9)]  
  
## <a name="cobj-example"></a><span data-ttu-id="9ef69-232">Ejemplo de CObj</span><span class="sxs-lookup"><span data-stu-id="9ef69-232">CObj Example</span></span>  
 <span data-ttu-id="9ef69-233">En el ejemplo siguiente se usa el `CObj` función para convertir un valor numérico para `Object`.</span><span class="sxs-lookup"><span data-stu-id="9ef69-233">The following example uses the `CObj` function to convert a numeric value to `Object`.</span></span> <span data-ttu-id="9ef69-234">El `Object` propia variable contiene sólo un puntero de cuatro bytes, que apunta a la `Double` valor asignado a él.</span><span class="sxs-lookup"><span data-stu-id="9ef69-234">The `Object` variable itself contains only a four-byte pointer, which points to the `Double` value assigned to it.</span></span>  
  
 [!code-vb[VbVbalrFunctions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#10)]  
  
## <a name="csbyte-example"></a><span data-ttu-id="9ef69-235">Ejemplo de CSByte</span><span class="sxs-lookup"><span data-stu-id="9ef69-235">CSByte Example</span></span>  
 <span data-ttu-id="9ef69-236">En el ejemplo siguiente se usa el `CSByte` función para convertir un valor numérico para `SByte`.</span><span class="sxs-lookup"><span data-stu-id="9ef69-236">The following example uses the `CSByte` function to convert a numeric value to `SByte`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#11)]  
  
## <a name="cshort-example"></a><span data-ttu-id="9ef69-237">Ejemplo de CShort</span><span class="sxs-lookup"><span data-stu-id="9ef69-237">CShort Example</span></span>  
 <span data-ttu-id="9ef69-238">En el ejemplo siguiente se usa el `CShort` función para convertir un valor numérico para `Short`.</span><span class="sxs-lookup"><span data-stu-id="9ef69-238">The following example uses the `CShort` function to convert a numeric value to `Short`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#12)]  
  
## <a name="csng-example"></a><span data-ttu-id="9ef69-239">Ejemplo de CSng</span><span class="sxs-lookup"><span data-stu-id="9ef69-239">CSng Example</span></span>  
 <span data-ttu-id="9ef69-240">En el ejemplo siguiente se usa el `CSng` función para convertir los valores para `Single`.</span><span class="sxs-lookup"><span data-stu-id="9ef69-240">The following example uses the `CSng` function to convert values to `Single`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#13)]  
  
## <a name="cstr-example"></a><span data-ttu-id="9ef69-241">Ejemplo de CStr</span><span class="sxs-lookup"><span data-stu-id="9ef69-241">CStr Example</span></span>  
 <span data-ttu-id="9ef69-242">En el ejemplo siguiente se usa el `CStr` función para convertir un valor numérico para `String`.</span><span class="sxs-lookup"><span data-stu-id="9ef69-242">The following example uses the `CStr` function to convert a numeric value to `String`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#14)]  
  
 <span data-ttu-id="9ef69-243">En el ejemplo siguiente se usa el `CStr` función para convertir `Date` valores `String` valores.</span><span class="sxs-lookup"><span data-stu-id="9ef69-243">The following example uses the `CStr` function to convert `Date` values to `String` values.</span></span>  
  
 [!code-vb[VbVbalrFunctions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#15)]  
  
 <span data-ttu-id="9ef69-244">`CStr` siempre presenta un `Date` valor en el formato abreviado estándar de la configuración regional, por ejemplo, "6/15/2003 4:35:47 P.M.".</span><span class="sxs-lookup"><span data-stu-id="9ef69-244">`CStr` always renders a `Date` value in the standard short format for the current locale, for example, "6/15/2003 4:35:47 PM".</span></span> <span data-ttu-id="9ef69-245">Sin embargo, `CStr` suprime la *valores neutrales* de 1/1/0001 para la fecha y 00:00:00 durante el tiempo.</span><span class="sxs-lookup"><span data-stu-id="9ef69-245">However, `CStr` suppresses the *neutral values* of 1/1/0001 for the date and 00:00:00 for the time.</span></span>  
  
 <span data-ttu-id="9ef69-246">Para más información sobre los valores devueltos por `CStr`, consulte [devolver valores para la función CStr](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span><span class="sxs-lookup"><span data-stu-id="9ef69-246">For more detail on the values returned by `CStr`, see [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>  
  
## <a name="cuint-example"></a><span data-ttu-id="9ef69-247">Ejemplo de CUInt</span><span class="sxs-lookup"><span data-stu-id="9ef69-247">CUInt Example</span></span>  
 <span data-ttu-id="9ef69-248">En el ejemplo siguiente se usa el `CUInt` función para convertir un valor numérico para `UInteger`.</span><span class="sxs-lookup"><span data-stu-id="9ef69-248">The following example uses the `CUInt` function to convert a numeric value to `UInteger`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#16)]  
  
## <a name="culng-example"></a><span data-ttu-id="9ef69-249">Ejemplo de CULng</span><span class="sxs-lookup"><span data-stu-id="9ef69-249">CULng Example</span></span>  
 <span data-ttu-id="9ef69-250">En el ejemplo siguiente se usa el `CULng` función para convertir un valor numérico para `ULong`.</span><span class="sxs-lookup"><span data-stu-id="9ef69-250">The following example uses the `CULng` function to convert a numeric value to `ULong`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#17)]  
  
## <a name="cushort-example"></a><span data-ttu-id="9ef69-251">Ejemplo de CUShort</span><span class="sxs-lookup"><span data-stu-id="9ef69-251">CUShort Example</span></span>  
 <span data-ttu-id="9ef69-252">En el ejemplo siguiente se usa el `CUShort` función para convertir un valor numérico para `UShort`.</span><span class="sxs-lookup"><span data-stu-id="9ef69-252">The following example uses the `CUShort` function to convert a numeric value to `UShort`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#18)]  
  
## <a name="see-also"></a><span data-ttu-id="9ef69-253">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ef69-253">See also</span></span>

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
- [<span data-ttu-id="9ef69-254">Funciones de conversión</span><span class="sxs-lookup"><span data-stu-id="9ef69-254">Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/conversion-functions.md)
- [<span data-ttu-id="9ef69-255">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9ef69-255">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)

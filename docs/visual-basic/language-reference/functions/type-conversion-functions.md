---
title: Funciones de conversión de tipos (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: c9222bdb31f4fd7c792d5a50c100067e29e9d537
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605087"
---
# <a name="type-conversion-functions-visual-basic"></a><span data-ttu-id="e079c-102">Funciones de conversión de tipos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e079c-102">Type Conversion Functions (Visual Basic)</span></span>
<span data-ttu-id="e079c-103">Estas funciones están compilados de forma alineada, lo que significa que el código de conversión forma parte del código que evalúa la expresión.</span><span class="sxs-lookup"><span data-stu-id="e079c-103">These functions are compiled inline, meaning the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="e079c-104">En ocasiones, no hay ninguna llamada a un procedimiento para realizar la conversión, lo que mejora el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="e079c-104">Sometimes there is no call to a procedure to accomplish the conversion, which improves performance.</span></span> <span data-ttu-id="e079c-105">Cada función convierte una expresión al tipo de datos específico.</span><span class="sxs-lookup"><span data-stu-id="e079c-105">Each function coerces an expression to a specific data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e079c-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e079c-106">Syntax</span></span>  
  
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
  
## <a name="part"></a><span data-ttu-id="e079c-107">Parte</span><span class="sxs-lookup"><span data-stu-id="e079c-107">Part</span></span>  
 `expression`  
 <span data-ttu-id="e079c-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="e079c-108">Required.</span></span> <span data-ttu-id="e079c-109">Cualquier expresión del tipo de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="e079c-109">Any expression of the source data type.</span></span>  
  
## <a name="return-value-data-type"></a><span data-ttu-id="e079c-110">Tipo de datos de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e079c-110">Return Value Data Type</span></span>  
 <span data-ttu-id="e079c-111">El nombre de la función determina el tipo de datos del valor que devuelve, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e079c-111">The function name determines the data type of the value it returns, as shown in the following table.</span></span>  
  
|<span data-ttu-id="e079c-112">Nombre de la función</span><span class="sxs-lookup"><span data-stu-id="e079c-112">Function name</span></span>|<span data-ttu-id="e079c-113">Tipo de datos devuelto</span><span class="sxs-lookup"><span data-stu-id="e079c-113">Return data type</span></span>|<span data-ttu-id="e079c-114">Intervalo para `expression` argumento</span><span class="sxs-lookup"><span data-stu-id="e079c-114">Range for `expression` argument</span></span>|  
|-------------------|----------------------|-------------------------------------|  
|`CBool`|[<span data-ttu-id="e079c-115">Boolean (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="e079c-115">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="e079c-116">Cualquier `Char` o `String` o expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="e079c-116">Any valid `Char` or `String` or numeric expression.</span></span>|  
|`CByte`|[<span data-ttu-id="e079c-117">Byte (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="e079c-117">Byte Data Type</span></span>](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="e079c-118">0 y 255 (sin signo); partes fraccionarias se redondean. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e079c-118">0 through 255 (unsigned); fractional parts are rounded.<sup>1</sup></span></span>|  
|`CChar`|[<span data-ttu-id="e079c-119">Char (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="e079c-119">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="e079c-120">Cualquier `Char` o `String` expresión; sólo primer carácter de un `String` se convierte; puede oscilar entre 0 y 65535 (sin signo).</span><span class="sxs-lookup"><span data-stu-id="e079c-120">Any valid `Char` or `String` expression; only first character of a `String` is converted; value can be 0 through 65535 (unsigned).</span></span>|  
|`CDate`|[<span data-ttu-id="e079c-121">Date (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="e079c-121">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="e079c-122">Cualquier representación válida de una fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="e079c-122">Any valid representation of a date and time.</span></span>|  
|`CDbl`|[<span data-ttu-id="e079c-123">Double (tipos de datos)</span><span class="sxs-lookup"><span data-stu-id="e079c-123">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)|<span data-ttu-id="e079c-124">-1, 79769313486231570E + 308 a - 4, 94065645841246544E-324 para valores negativos; 4, 94065645841246544E-324 a 1, 79769313486231570E + 308 para valores positivos.</span><span class="sxs-lookup"><span data-stu-id="e079c-124">-1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values; 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span>|  
|`CDec`|[<span data-ttu-id="e079c-125">Decimal (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="e079c-125">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="e079c-126">+/-79,228,162,514,264,337,593,543,950,335 para números a partir de cero, es decir, números sin decimales.</span><span class="sxs-lookup"><span data-stu-id="e079c-126">+/-79,228,162,514,264,337,593,543,950,335 for zero-scaled numbers, that is, numbers with no decimal places.</span></span> <span data-ttu-id="e079c-127">Para números con 28 posiciones decimales, el intervalo es +/-7,9228162514264337593543950335.</span><span class="sxs-lookup"><span data-stu-id="e079c-127">For numbers with 28 decimal places, the range is +/-7.9228162514264337593543950335.</span></span> <span data-ttu-id="e079c-128">El menor número posible distinto de cero es 0,0000000000000000000000000001 (+/-1E-28).</span><span class="sxs-lookup"><span data-stu-id="e079c-128">The smallest possible non-zero number is 0.0000000000000000000000000001 (+/-1E-28).</span></span>|  
|`CInt`|[<span data-ttu-id="e079c-129">Integer (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="e079c-129">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="e079c-130">-2.147.483.648 y 2.147.483.647; partes fraccionarias se redondean. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e079c-130">-2,147,483,648 through 2,147,483,647; fractional parts are rounded.<sup>1</sup></span></span>|  
|`CLng`|[<span data-ttu-id="e079c-131">Long (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="e079c-131">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="e079c-132">-9.223.372.036.854.775.808 a 9.223.372.036.854.775.807; partes fraccionarias se redondean. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e079c-132">-9,223,372,036,854,775,808 through 9,223,372,036,854,775,807; fractional parts are rounded.<sup>1</sup></span></span>|  
|`CObj`|[<span data-ttu-id="e079c-133">Tipo de objeto de datos</span><span class="sxs-lookup"><span data-stu-id="e079c-133">Object Data Type</span></span>](../../../visual-basic/language-reference/data-types/object-data-type.md)|<span data-ttu-id="e079c-134">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="e079c-134">Any valid expression.</span></span>|  
|`CSByte`|[<span data-ttu-id="e079c-135">SByte (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="e079c-135">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="e079c-136">-128 a 127; partes fraccionarias se redondean. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e079c-136">-128 through 127; fractional parts are rounded.<sup>1</sup></span></span>|  
|`CShort`|[<span data-ttu-id="e079c-137">Short (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="e079c-137">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="e079c-138">-32.768 a 32.767; partes fraccionarias se redondean. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e079c-138">-32,768 through 32,767; fractional parts are rounded.<sup>1</sup></span></span>|  
|`CSng`|[<span data-ttu-id="e079c-139">Single (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="e079c-139">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="e079c-140">-3, 402823E + 38 a - 1, 401298E-45 para los valores negativos; 1, 401298E-45 a 3, 402823E + 38 para valores positivos.</span><span class="sxs-lookup"><span data-stu-id="e079c-140">-3.402823E+38 through -1.401298E-45 for negative values; 1.401298E-45 through 3.402823E+38 for positive values.</span></span>|  
|`CStr`|[<span data-ttu-id="e079c-141">String (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="e079c-141">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)|<span data-ttu-id="e079c-142">Devuelve para `CStr` dependen de la `expression` argumento.</span><span class="sxs-lookup"><span data-stu-id="e079c-142">Returns for `CStr` depend on the `expression` argument.</span></span> <span data-ttu-id="e079c-143">Vea [valores devueltos para la función CStr](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span><span class="sxs-lookup"><span data-stu-id="e079c-143">See [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>|  
|`CUInt`|[<span data-ttu-id="e079c-144">UInteger (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="e079c-144">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="e079c-145">de 0 a 4.294.967.295 (sin signo); partes fraccionarias se redondean. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e079c-145">0 through 4,294,967,295 (unsigned); fractional parts are rounded.<sup>1</sup></span></span>|  
|`CULng`|[<span data-ttu-id="e079c-146">ULong (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="e079c-146">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="e079c-147">de 0 a 18.446.744.073.709.551.615 (sin signo); partes fraccionarias se redondean. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e079c-147">0 through 18,446,744,073,709,551,615 (unsigned); fractional parts are rounded.<sup>1</sup></span></span>|  
|`CUShort`|[<span data-ttu-id="e079c-148">UShort (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="e079c-148">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="e079c-149">de 0 a 65.535 (sin signo); partes fraccionarias se redondean. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e079c-149">0 through 65,535 (unsigned); fractional parts are rounded.<sup>1</sup></span></span>|  
  
 <span data-ttu-id="e079c-150"><sup>1</sup> partes fraccionarias pueden estar sujetas a un tipo especial de redondeo denominado *el redondeo bancario*.</span><span class="sxs-lookup"><span data-stu-id="e079c-150"><sup>1</sup> Fractional parts can be subject to a special type of rounding called *banker's rounding*.</span></span> <span data-ttu-id="e079c-151">Para obtener más información, vea "Comentarios".</span><span class="sxs-lookup"><span data-stu-id="e079c-151">See "Remarks" for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e079c-152">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e079c-152">Remarks</span></span>  
 <span data-ttu-id="e079c-153">Como norma, debe utilizar las funciones de conversión de tipo de Visual Basic con preferencia a los métodos de .NET Framework como `ToString()`, ya sea en la <xref:System.Convert> clase o de una clase o estructura individual de tipos.</span><span class="sxs-lookup"><span data-stu-id="e079c-153">As a rule, you should use the Visual Basic type conversion functions in preference to the .NET Framework methods such as `ToString()`, either on the <xref:System.Convert> class or on an individual type structure or class.</span></span> <span data-ttu-id="e079c-154">Las funciones de Visual Basic están diseñadas para la interacción óptima con código de Visual Basic, y también hacen que el código fuente más corto y más fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="e079c-154">The Visual Basic functions are designed for optimal interaction with Visual Basic code, and they also make your source code shorter and easier to read.</span></span> <span data-ttu-id="e079c-155">Además, los métodos de conversión de .NET Framework no siempre generan los mismos resultados que las funciones de Visual Basic, por ejemplo, al convertir `Boolean` a `Integer`.</span><span class="sxs-lookup"><span data-stu-id="e079c-155">In addition, the .NET Framework conversion methods do not always produce the same results as the Visual Basic functions, for example when converting `Boolean` to `Integer`.</span></span> <span data-ttu-id="e079c-156">Para obtener más información, consulte [solución de problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="e079c-156">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="e079c-157">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="e079c-157">Behavior</span></span>  
  
-   <span data-ttu-id="e079c-158">**Conversión.**</span><span class="sxs-lookup"><span data-stu-id="e079c-158">**Coercion.**</span></span> <span data-ttu-id="e079c-159">En general, puede utilizar las funciones de conversión de tipo de datos para convertir el resultado de una operación en un tipo de datos concreto en lugar de con el tipo de datos predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e079c-159">In general, you can use the data type conversion functions to coerce the result of an operation to a particular data type rather than the default data type.</span></span> <span data-ttu-id="e079c-160">Por ejemplo, utilice `CDec` para forzar la aritmética decimal en los casos donde se haría precisión sencilla, doble precisión o aritmética de enteros.</span><span class="sxs-lookup"><span data-stu-id="e079c-160">For example, use `CDec` to force decimal arithmetic in cases where single-precision, double-precision, or integer arithmetic would normally take place.</span></span>  
  
-   <span data-ttu-id="e079c-161">**Error en conversiones.**</span><span class="sxs-lookup"><span data-stu-id="e079c-161">**Failed Conversions.**</span></span> <span data-ttu-id="e079c-162">Si el `expression` pasa a la función es fuera del intervalo del tipo de datos donde es convertir, un <xref:System.OverflowException> se produce.</span><span class="sxs-lookup"><span data-stu-id="e079c-162">If the `expression` passed to the function is outside the range of the data type to which it is to be converted, an <xref:System.OverflowException> occurs.</span></span>  
  
-   <span data-ttu-id="e079c-163">**Partes fraccionarias.**</span><span class="sxs-lookup"><span data-stu-id="e079c-163">**Fractional Parts.**</span></span> <span data-ttu-id="e079c-164">Al convertir un valor no integral a un entero escriba, las funciones de conversión de enteros (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, y `CUShort`) quitar el fracciones de pieza y redondean el valor al entero más próximo.</span><span class="sxs-lookup"><span data-stu-id="e079c-164">When you convert a nonintegral value to an integral type, the integer conversion functions (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, and `CUShort`) remove the fractional part and round the value to the closest integer.</span></span>  
  
     <span data-ttu-id="e079c-165">Si la parte fraccionaria es exactamente 0,5, las funciones de conversión de enteros de ida y vuelta para el entero par más próximo.</span><span class="sxs-lookup"><span data-stu-id="e079c-165">If the fractional part is exactly 0.5, the integer conversion functions round it to the nearest even integer.</span></span> <span data-ttu-id="e079c-166">Por ejemplo, 0,5 se redondea a 0 y 1,5 y 2,5 se redondean a 2.</span><span class="sxs-lookup"><span data-stu-id="e079c-166">For example, 0.5 rounds to 0, and 1.5 and 2.5 both round to 2.</span></span> <span data-ttu-id="e079c-167">Esto se denomina a veces *el redondeo bancario*, y su finalidad es compensar una tendencia que se podría acumular al sumar muchos de estos números.</span><span class="sxs-lookup"><span data-stu-id="e079c-167">This is sometimes called *banker's rounding*, and its purpose is to compensate for a bias that could accumulate when adding many such numbers together.</span></span>  
  
     <span data-ttu-id="e079c-168">`CInt` y `CLng` diferencian el <xref:Microsoft.VisualBasic.Conversion.Int%2A> y <xref:Microsoft.VisualBasic.Conversion.Fix%2A> funciones, que se truncan en lugar de redondean, la parte fraccionaria de un número.</span><span class="sxs-lookup"><span data-stu-id="e079c-168">`CInt` and `CLng` differ from the <xref:Microsoft.VisualBasic.Conversion.Int%2A> and <xref:Microsoft.VisualBasic.Conversion.Fix%2A> functions, which truncate, rather than round, the fractional part of a number.</span></span> <span data-ttu-id="e079c-169">Además, `Fix` y `Int` siempre devuelven un valor del mismo tipo de datos que se pasa.</span><span class="sxs-lookup"><span data-stu-id="e079c-169">Also, `Fix` and `Int` always return a value of the same data type as you pass in.</span></span>  
  
-   <span data-ttu-id="e079c-170">**Conversiones de fecha y hora.**</span><span class="sxs-lookup"><span data-stu-id="e079c-170">**Date/Time Conversions.**</span></span> <span data-ttu-id="e079c-171">Use la <xref:Microsoft.VisualBasic.Information.IsDate%2A> función para determinar si se puede convertir un valor a una fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="e079c-171">Use the <xref:Microsoft.VisualBasic.Information.IsDate%2A> function to determine if a value can be converted to a date and time.</span></span> <span data-ttu-id="e079c-172">`CDate` reconoce literales de fecha y literales de tiempo pero no valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="e079c-172">`CDate` recognizes date literals and time literals but not numeric values.</span></span> <span data-ttu-id="e079c-173">Para convertir un Visual Basic 6.0 `Date` valor a un `Date` valor en Visual Basic 2005 o versiones posteriores, puede usar el <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="e079c-173">To convert a Visual Basic 6.0 `Date` value to a `Date` value in Visual Basic 2005 or later versions, you can use the <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="e079c-174">**Neutral valores de fecha y hora.**</span><span class="sxs-lookup"><span data-stu-id="e079c-174">**Neutral Date/Time Values.**</span></span> <span data-ttu-id="e079c-175">El [tipo de datos Date](../../../visual-basic/language-reference/data-types/date-data-type.md) siempre contiene información de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="e079c-175">The [Date Data Type](../../../visual-basic/language-reference/data-types/date-data-type.md) always contains both date and time information.</span></span> <span data-ttu-id="e079c-176">Para fines de conversión de tipos, Visual Basic considera 1/1/0001 (del 1 de enero del año 1) como un *valor neutral* de fecha y 00:00:00 (medianoche) un valor neutral por vez.</span><span class="sxs-lookup"><span data-stu-id="e079c-176">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="e079c-177">Si convierte un `Date` valor en una cadena, `CStr` no incluye valores neutrales en la cadena resultante.</span><span class="sxs-lookup"><span data-stu-id="e079c-177">If you convert a `Date` value to a string, `CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="e079c-178">Por ejemplo, si convierte `#January 1, 0001 9:30:00#` en una cadena, el resultado es "9:30:00 AM"; se suprime la información de fecha.</span><span class="sxs-lookup"><span data-stu-id="e079c-178">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="e079c-179">Sin embargo, la información de fecha aún está presente en la versión original `Date` valor y se pueden recuperar con funciones como <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> (función).</span><span class="sxs-lookup"><span data-stu-id="e079c-179">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> function.</span></span>  
  
-   <span data-ttu-id="e079c-180">**Distinción de referencias culturales.**</span><span class="sxs-lookup"><span data-stu-id="e079c-180">**Culture Sensitivity.**</span></span> <span data-ttu-id="e079c-181">Las funciones de conversión de tipos que implican cadenas realizan conversiones en función de la configuración de referencia cultural actual para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e079c-181">The type conversion functions involving strings perform conversions based on the current culture settings for the application.</span></span> <span data-ttu-id="e079c-182">Por ejemplo, `CDate` reconoce los formatos de fecha según la configuración regional del sistema.</span><span class="sxs-lookup"><span data-stu-id="e079c-182">For example, `CDate` recognizes date formats according to the locale setting of your system.</span></span> <span data-ttu-id="e079c-183">Debe proporcionar el día, mes y año en el orden correcto para la configuración regional o la fecha no se interpreten correctamente.</span><span class="sxs-lookup"><span data-stu-id="e079c-183">You must provide the day, month, and year in the correct order for your locale, or the date might not be interpreted correctly.</span></span> <span data-ttu-id="e079c-184">No se reconoce el formato de fecha largo si contiene una cadena de día de la semana, por ejemplo, "Miércoles".</span><span class="sxs-lookup"><span data-stu-id="e079c-184">A long date format is not recognized if it contains a day-of-the-week string, such as "Wednesday".</span></span>  
  
     <span data-ttu-id="e079c-185">Si necesita convertir hacia o desde una representación de cadena de un valor en un formato distinto al especificado por la configuración regional, no puede usar las funciones de conversión de tipo de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e079c-185">If you need to convert to or from a string representation of a value in a format other than the one specified by your locale, you cannot use the Visual Basic type conversion functions.</span></span> <span data-ttu-id="e079c-186">Para ello, use la `ToString(IFormatProvider)` y `Parse(String, IFormatProvider)` métodos de ese tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="e079c-186">To do this, use the `ToString(IFormatProvider)` and `Parse(String, IFormatProvider)` methods of that value's type.</span></span> <span data-ttu-id="e079c-187">Por ejemplo, utilice <xref:System.Double.Parse%2A?displayProperty=nameWithType> al convertir una cadena en un `Double`y usar <xref:System.Double.ToString%2A?displayProperty=nameWithType> al convertir un valor de tipo `Double` en una cadena.</span><span class="sxs-lookup"><span data-stu-id="e079c-187">For example, use <xref:System.Double.Parse%2A?displayProperty=nameWithType> when converting a string to a `Double`, and use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a string.</span></span>  
  
## <a name="ctype-function"></a><span data-ttu-id="e079c-188">CType Function</span><span class="sxs-lookup"><span data-stu-id="e079c-188">CType Function</span></span>  
 <span data-ttu-id="e079c-189">El [CType (función)](../../../visual-basic/language-reference/functions/ctype-function.md) toma un segundo argumento, `typename`y convierte `expression` a `typename`, donde `typename` puede ser cualquier tipo de datos, estructura, clase o interfaz a la que existe una conversión válida.</span><span class="sxs-lookup"><span data-stu-id="e079c-189">The [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) takes a second argument, `typename`, and coerces `expression` to `typename`, where `typename` can be any data type, structure, class, or interface to which there exists a valid conversion.</span></span>  
  
 <span data-ttu-id="e079c-190">Para obtener una comparación de `CType` con el otro tipo palabras clave para conversiones, vea [DirectCast (operador)](../../../visual-basic/language-reference/operators/directcast-operator.md) y [TryCast (operador)](../../../visual-basic/language-reference/operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="e079c-190">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span>  
  
## <a name="cbool-example"></a><span data-ttu-id="e079c-191">En el ejemplo se CBool</span><span class="sxs-lookup"><span data-stu-id="e079c-191">CBool Example</span></span>  
 <span data-ttu-id="e079c-192">En el ejemplo siguiente se usa el `CBool` función para convertir expresiones de `Boolean` valores.</span><span class="sxs-lookup"><span data-stu-id="e079c-192">The following example uses the `CBool` function to convert expressions to `Boolean` values.</span></span> <span data-ttu-id="e079c-193">Si una expresión se evalúa como un valor distinto de cero, `CBool` devuelve `True`; en caso contrario, devuelve `False`.</span><span class="sxs-lookup"><span data-stu-id="e079c-193">If an expression evaluates to a nonzero value, `CBool` returns `True`; otherwise, it returns `False`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#1](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_1.vb)]  
  
## <a name="cbyte-example"></a><span data-ttu-id="e079c-194">En el ejemplo se CByte</span><span class="sxs-lookup"><span data-stu-id="e079c-194">CByte Example</span></span>  
 <span data-ttu-id="e079c-195">En el ejemplo siguiente se usa el `CByte` función para convertir una expresión a un `Byte`.</span><span class="sxs-lookup"><span data-stu-id="e079c-195">The following example uses the `CByte` function to convert an expression to a `Byte`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#2](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_2.vb)]  
  
## <a name="cchar-example"></a><span data-ttu-id="e079c-196">En el ejemplo se CChar</span><span class="sxs-lookup"><span data-stu-id="e079c-196">CChar Example</span></span>  
 <span data-ttu-id="e079c-197">En el ejemplo siguiente se usa el `CChar` función para convertir el primer carácter de un `String` expresión a un `Char` tipo.</span><span class="sxs-lookup"><span data-stu-id="e079c-197">The following example uses the `CChar` function to convert the first character of a `String` expression to a `Char` type.</span></span>  
  
 [!code-vb[VbVbalrFunctions#3](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_3.vb)]  
  
 <span data-ttu-id="e079c-198">El argumento de entrada `CChar` debe ser del tipo de datos `Char` o `String`.</span><span class="sxs-lookup"><span data-stu-id="e079c-198">The input argument to `CChar` must be of data type `Char` or `String`.</span></span> <span data-ttu-id="e079c-199">No se puede utilizar `CChar` para convertir un número en un carácter, porque `CChar` no acepta un tipo de datos numéricos.</span><span class="sxs-lookup"><span data-stu-id="e079c-199">You cannot use `CChar` to convert a number to a character, because `CChar` cannot accept a numeric data type.</span></span> <span data-ttu-id="e079c-200">En el ejemplo siguiente se obtiene un número que representa un punto de código (código de carácter) y lo convierte en el carácter correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e079c-200">The following example obtains a number representing a code point (character code) and converts it to the corresponding character.</span></span> <span data-ttu-id="e079c-201">Usa el <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> función para obtener la cadena de dígitos, `CInt` para convertir la cadena al tipo `Integer`, y `ChrW` para convertir el número que escriba `Char`.</span><span class="sxs-lookup"><span data-stu-id="e079c-201">It uses the <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> function to obtain the string of digits, `CInt` to convert the string to type `Integer`, and `ChrW` to convert the number to type `Char`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#4](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_4.vb)]  
  
## <a name="cdate-example"></a><span data-ttu-id="e079c-202">En el ejemplo se CDate</span><span class="sxs-lookup"><span data-stu-id="e079c-202">CDate Example</span></span>  
 <span data-ttu-id="e079c-203">En el ejemplo siguiente se usa el `CDate` función para convertir cadenas a `Date` valores.</span><span class="sxs-lookup"><span data-stu-id="e079c-203">The following example uses the `CDate` function to convert strings to `Date` values.</span></span> <span data-ttu-id="e079c-204">En general, no se recomienda codificar de forma rígida fechas y horas como cadenas (como se muestra en este ejemplo).</span><span class="sxs-lookup"><span data-stu-id="e079c-204">In general, hard-coding dates and times as strings (as shown in this example) is not recommended.</span></span> <span data-ttu-id="e079c-205">Usar literales de fecha y hora, por ejemplo #Feb 12, 1969 # y # 4:45:23 P.M. # en su lugar.</span><span class="sxs-lookup"><span data-stu-id="e079c-205">Use date literals and time literals, such as #Feb 12, 1969# and #4:45:23 PM#, instead.</span></span>  
  
 [!code-vb[VbVbalrFunctions#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_5.vb)]  
  
## <a name="cdbl-example"></a><span data-ttu-id="e079c-206">En el ejemplo se CDbl</span><span class="sxs-lookup"><span data-stu-id="e079c-206">CDbl Example</span></span>  
 [!code-vb[VbVbalrFunctions#6](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_6.vb)]  
  
## <a name="cdec-example"></a><span data-ttu-id="e079c-207">En el ejemplo se CDec</span><span class="sxs-lookup"><span data-stu-id="e079c-207">CDec Example</span></span>  
 <span data-ttu-id="e079c-208">En el ejemplo siguiente se usa el `CDec` función para convertir un valor numérico y `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="e079c-208">The following example uses the `CDec` function to convert a numeric value to `Decimal`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#7](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_7.vb)]  
  
## <a name="cint-example"></a><span data-ttu-id="e079c-209">En el ejemplo se CInt</span><span class="sxs-lookup"><span data-stu-id="e079c-209">CInt Example</span></span>  
 <span data-ttu-id="e079c-210">En el ejemplo siguiente se usa el `CInt` función para convertir un valor a `Integer`.</span><span class="sxs-lookup"><span data-stu-id="e079c-210">The following example uses the `CInt` function to convert a value to `Integer`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#8](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_8.vb)]  
  
## <a name="clng-example"></a><span data-ttu-id="e079c-211">En el ejemplo se CLng</span><span class="sxs-lookup"><span data-stu-id="e079c-211">CLng Example</span></span>  
 <span data-ttu-id="e079c-212">En el ejemplo siguiente se usa el `CLng` función para convertir valores a `Long`.</span><span class="sxs-lookup"><span data-stu-id="e079c-212">The following example uses the `CLng` function to convert values to `Long`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#9](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_9.vb)]  
  
## <a name="cobj-example"></a><span data-ttu-id="e079c-213">En el ejemplo se CObj</span><span class="sxs-lookup"><span data-stu-id="e079c-213">CObj Example</span></span>  
 <span data-ttu-id="e079c-214">En el ejemplo siguiente se usa el `CObj` función para convertir un valor numérico y `Object`.</span><span class="sxs-lookup"><span data-stu-id="e079c-214">The following example uses the `CObj` function to convert a numeric value to `Object`.</span></span> <span data-ttu-id="e079c-215">El `Object` propia variable contiene sólo un puntero de cuatro bytes, que apunta a la `Double` valor asignado a él.</span><span class="sxs-lookup"><span data-stu-id="e079c-215">The `Object` variable itself contains only a four-byte pointer, which points to the `Double` value assigned to it.</span></span>  
  
 [!code-vb[VbVbalrFunctions#10](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_10.vb)]  
  
## <a name="csbyte-example"></a><span data-ttu-id="e079c-216">Ejemplo de CSByte</span><span class="sxs-lookup"><span data-stu-id="e079c-216">CSByte Example</span></span>  
 <span data-ttu-id="e079c-217">En el ejemplo siguiente se usa el `CSByte` función para convertir un valor numérico y `SByte`.</span><span class="sxs-lookup"><span data-stu-id="e079c-217">The following example uses the `CSByte` function to convert a numeric value to `SByte`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#11](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_11.vb)]  
  
## <a name="cshort-example"></a><span data-ttu-id="e079c-218">En el ejemplo se CShort</span><span class="sxs-lookup"><span data-stu-id="e079c-218">CShort Example</span></span>  
 <span data-ttu-id="e079c-219">En el ejemplo siguiente se usa el `CShort` función para convertir un valor numérico y `Short`.</span><span class="sxs-lookup"><span data-stu-id="e079c-219">The following example uses the `CShort` function to convert a numeric value to `Short`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#12](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_12.vb)]  
  
## <a name="csng-example"></a><span data-ttu-id="e079c-220">En el ejemplo se CSng</span><span class="sxs-lookup"><span data-stu-id="e079c-220">CSng Example</span></span>  
 <span data-ttu-id="e079c-221">En el ejemplo siguiente se usa el `CSng` función para convertir valores a `Single`.</span><span class="sxs-lookup"><span data-stu-id="e079c-221">The following example uses the `CSng` function to convert values to `Single`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#13](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_13.vb)]  
  
## <a name="cstr-example"></a><span data-ttu-id="e079c-222">En el ejemplo se CStr</span><span class="sxs-lookup"><span data-stu-id="e079c-222">CStr Example</span></span>  
 <span data-ttu-id="e079c-223">En el ejemplo siguiente se usa el `CStr` función para convertir un valor numérico y `String`.</span><span class="sxs-lookup"><span data-stu-id="e079c-223">The following example uses the `CStr` function to convert a numeric value to `String`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#14](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_14.vb)]  
  
 <span data-ttu-id="e079c-224">En el ejemplo siguiente se usa el `CStr` función para convertir `Date` valores `String` valores.</span><span class="sxs-lookup"><span data-stu-id="e079c-224">The following example uses the `CStr` function to convert `Date` values to `String` values.</span></span>  
  
 [!code-vb[VbVbalrFunctions#15](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_15.vb)]  
  
 <span data-ttu-id="e079c-225">`CStr` siempre presenta un `Date` valor en el formato corto estándar de la configuración regional, por ejemplo, "15/6/2003 4:35:47 P.M.".</span><span class="sxs-lookup"><span data-stu-id="e079c-225">`CStr` always renders a `Date` value in the standard short format for the current locale, for example, "6/15/2003 4:35:47 PM".</span></span> <span data-ttu-id="e079c-226">Sin embargo, `CStr` suprime la *valores neutrales* de 1/1/0001 para la fecha y 00:00:00 para la hora.</span><span class="sxs-lookup"><span data-stu-id="e079c-226">However, `CStr` suppresses the *neutral values* of 1/1/0001 for the date and 00:00:00 for the time.</span></span>  
  
 <span data-ttu-id="e079c-227">Para obtener más detalles sobre los valores devueltos por `CStr`, consulte [valores devueltos para la función CStr](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span><span class="sxs-lookup"><span data-stu-id="e079c-227">For more detail on the values returned by `CStr`, see [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>  
  
## <a name="cuint-example"></a><span data-ttu-id="e079c-228">Ejemplo de CUInt</span><span class="sxs-lookup"><span data-stu-id="e079c-228">CUInt Example</span></span>  
 <span data-ttu-id="e079c-229">En el ejemplo siguiente se usa el `CUInt` función para convertir un valor numérico y `UInteger`.</span><span class="sxs-lookup"><span data-stu-id="e079c-229">The following example uses the `CUInt` function to convert a numeric value to `UInteger`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#16](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_16.vb)]  
  
## <a name="culng-example"></a><span data-ttu-id="e079c-230">Ejemplo de CULng</span><span class="sxs-lookup"><span data-stu-id="e079c-230">CULng Example</span></span>  
 <span data-ttu-id="e079c-231">En el ejemplo siguiente se usa el `CULng` función para convertir un valor numérico y `ULong`.</span><span class="sxs-lookup"><span data-stu-id="e079c-231">The following example uses the `CULng` function to convert a numeric value to `ULong`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#17](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_17.vb)]  
  
## <a name="cushort-example"></a><span data-ttu-id="e079c-232">Ejemplo de CUShort</span><span class="sxs-lookup"><span data-stu-id="e079c-232">CUShort Example</span></span>  
 <span data-ttu-id="e079c-233">En el ejemplo siguiente se usa el `CUShort` función para convertir un valor numérico y `UShort`.</span><span class="sxs-lookup"><span data-stu-id="e079c-233">The following example uses the `CUShort` function to convert a numeric value to `UShort`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#18](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_18.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e079c-234">Vea también</span><span class="sxs-lookup"><span data-stu-id="e079c-234">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>  
 <xref:Microsoft.VisualBasic.Strings.Format%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Oct%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Str%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Val%2A>  
 [<span data-ttu-id="e079c-235">Funciones de conversión</span><span class="sxs-lookup"><span data-stu-id="e079c-235">Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/conversion-functions.md)  
 [<span data-ttu-id="e079c-236">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e079c-236">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)

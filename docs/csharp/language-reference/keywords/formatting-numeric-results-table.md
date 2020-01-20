---
title: 'Tabla de formatos de presentación para valores numéricos: Referencia de C#'
description: Obtenga información sobre las cadenas de formato numérico estándar de C#
ms.date: 09/20/2018
helpviewer_keywords:
- formatting [C#]
- numeric formatting [C#]
- String.Format method
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
ms.openlocfilehash: eb93f0a4f3c66e9f7b295366a77b9fb099fc3a1e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713509"
---
# <a name="formatting-numeric-results-table-c-reference"></a><span data-ttu-id="dcd93-103">Tabla de formatos de presentación para valores numéricos (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="dcd93-103">Formatting numeric results table (C# Reference)</span></span>

<span data-ttu-id="dcd93-104">La siguiente tabla muestra los especificadores de formato admitidos para dar formato a los resultados numéricos.</span><span class="sxs-lookup"><span data-stu-id="dcd93-104">The following table shows supported format specifiers for formatting numeric results.</span></span> <span data-ttu-id="dcd93-105">El resultado con formato de la última columna corresponde a la clase <xref:System.Globalization.CultureInfo> "en-US".</span><span class="sxs-lookup"><span data-stu-id="dcd93-105">The formatted result in the last column corresponds to the "en-US" <xref:System.Globalization.CultureInfo>.</span></span>

|<span data-ttu-id="dcd93-106">Especificador de formato</span><span class="sxs-lookup"><span data-stu-id="dcd93-106">Format specifier</span></span>|<span data-ttu-id="dcd93-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="dcd93-107">Description</span></span>|<span data-ttu-id="dcd93-108">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="dcd93-108">Examples</span></span>|<span data-ttu-id="dcd93-109">Resultado</span><span class="sxs-lookup"><span data-stu-id="dcd93-109">Result</span></span>|  
|----------------------|-----------------|--------------|------------|  
|<span data-ttu-id="dcd93-110">C o c</span><span class="sxs-lookup"><span data-stu-id="dcd93-110">C or c</span></span>|<span data-ttu-id="dcd93-111">Moneda</span><span class="sxs-lookup"><span data-stu-id="dcd93-111">Currency</span></span>|`string s = $"{2.5:C}";`<br /><br /> `string s = $"{-2.5:C}";`|<span data-ttu-id="dcd93-112">\\$2,50</span><span class="sxs-lookup"><span data-stu-id="dcd93-112">\\$2.50</span></span><br /><br /> <span data-ttu-id="dcd93-113">(\\$2,50)</span><span class="sxs-lookup"><span data-stu-id="dcd93-113">(\\$2.50)</span></span>|  
|<span data-ttu-id="dcd93-114">D o d</span><span class="sxs-lookup"><span data-stu-id="dcd93-114">D or d</span></span>|<span data-ttu-id="dcd93-115">Decimal</span><span class="sxs-lookup"><span data-stu-id="dcd93-115">Decimal</span></span>|`string s = $"{25:D5}";`|<span data-ttu-id="dcd93-116">00025</span><span class="sxs-lookup"><span data-stu-id="dcd93-116">00025</span></span>|  
|<span data-ttu-id="dcd93-117">E o e</span><span class="sxs-lookup"><span data-stu-id="dcd93-117">E or e</span></span>|<span data-ttu-id="dcd93-118">Exponencial</span><span class="sxs-lookup"><span data-stu-id="dcd93-118">Exponential</span></span>|`string s = $"{250000:E2}";`|<span data-ttu-id="dcd93-119">2.50E+005</span><span class="sxs-lookup"><span data-stu-id="dcd93-119">2.50E+005</span></span>|  
|<span data-ttu-id="dcd93-120">F o f</span><span class="sxs-lookup"><span data-stu-id="dcd93-120">F or f</span></span>|<span data-ttu-id="dcd93-121">Punto fijo</span><span class="sxs-lookup"><span data-stu-id="dcd93-121">Fixed-point</span></span>|`string s = $"{2.5:F2}";`<br /><br /> `string s = $"{2.5:F0}";`|<span data-ttu-id="dcd93-122">2.50</span><span class="sxs-lookup"><span data-stu-id="dcd93-122">2.50</span></span><br /><br /> <span data-ttu-id="dcd93-123">3</span><span class="sxs-lookup"><span data-stu-id="dcd93-123">3</span></span>|  
|<span data-ttu-id="dcd93-124">G o g</span><span class="sxs-lookup"><span data-stu-id="dcd93-124">G or g</span></span>|<span data-ttu-id="dcd93-125">General</span><span class="sxs-lookup"><span data-stu-id="dcd93-125">General</span></span>|`string s = $"{2.5:G}";`|<span data-ttu-id="dcd93-126">2.5</span><span class="sxs-lookup"><span data-stu-id="dcd93-126">2.5</span></span>|  
|<span data-ttu-id="dcd93-127">N o n</span><span class="sxs-lookup"><span data-stu-id="dcd93-127">N or n</span></span>|<span data-ttu-id="dcd93-128">Numérica</span><span class="sxs-lookup"><span data-stu-id="dcd93-128">Numeric</span></span>|`string s = $"{2500000:N}";`|<span data-ttu-id="dcd93-129">2,500,000.00</span><span class="sxs-lookup"><span data-stu-id="dcd93-129">2,500,000.00</span></span>|  
|<span data-ttu-id="dcd93-130">P o p</span><span class="sxs-lookup"><span data-stu-id="dcd93-130">P or p</span></span>|<span data-ttu-id="dcd93-131">Porcentaje</span><span class="sxs-lookup"><span data-stu-id="dcd93-131">Percent</span></span>|`string s = $"{0.25:P}";`|<span data-ttu-id="dcd93-132">25.00 %</span><span class="sxs-lookup"><span data-stu-id="dcd93-132">25.00%</span></span>|  
|<span data-ttu-id="dcd93-133">R o r</span><span class="sxs-lookup"><span data-stu-id="dcd93-133">R or r</span></span>|<span data-ttu-id="dcd93-134">Acción de ida y vuelta</span><span class="sxs-lookup"><span data-stu-id="dcd93-134">Round-trip</span></span>|`string s = $"{2.5:R}";`|<span data-ttu-id="dcd93-135">2.5</span><span class="sxs-lookup"><span data-stu-id="dcd93-135">2.5</span></span>|  
|<span data-ttu-id="dcd93-136">X o x</span><span class="sxs-lookup"><span data-stu-id="dcd93-136">X or x</span></span>|<span data-ttu-id="dcd93-137">Hexadecimal</span><span class="sxs-lookup"><span data-stu-id="dcd93-137">Hexadecimal</span></span>|`string s = $"{250:X}";`<br /><br /> `string s = $"{0xffff:X}";`|<span data-ttu-id="dcd93-138">FA</span><span class="sxs-lookup"><span data-stu-id="dcd93-138">FA</span></span><br /><br /> <span data-ttu-id="dcd93-139">FFFF</span><span class="sxs-lookup"><span data-stu-id="dcd93-139">FFFF</span></span>|  

## <a name="remarks"></a><span data-ttu-id="dcd93-140">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dcd93-140">Remarks</span></span>

<span data-ttu-id="dcd93-141">Use un especificador de formato para crear una cadena de formato.</span><span class="sxs-lookup"><span data-stu-id="dcd93-141">You use a format specifier to create a format string.</span></span> <span data-ttu-id="dcd93-142">La cadena de formato tiene el siguiente formato: `Axx`, donde</span><span class="sxs-lookup"><span data-stu-id="dcd93-142">The format string is of the following form: `Axx`, where</span></span>

- <span data-ttu-id="dcd93-143">`A` es el especificador de formato, que controla el tipo de formato aplicado al valor numérico.</span><span class="sxs-lookup"><span data-stu-id="dcd93-143">`A` is the format specifier, which controls the type of formatting applied to the numeric value.</span></span>
- <span data-ttu-id="dcd93-144">`xx` es el especificador de precisión, que afecta al número de dígitos del resultado con formato.</span><span class="sxs-lookup"><span data-stu-id="dcd93-144">`xx` is the precision specifier, which affects the number of digits in the formatted output.</span></span> <span data-ttu-id="dcd93-145">El valor de los intervalos del especificador de precisión comprende de 0 a 99.</span><span class="sxs-lookup"><span data-stu-id="dcd93-145">The value of the precision specifier ranges from 0 to 99.</span></span>

<span data-ttu-id="dcd93-146">Los especificadores de formato decimal ("D" o "d") y hexadecimal ("X" o "x") solo son compatibles con tipos enteros.</span><span class="sxs-lookup"><span data-stu-id="dcd93-146">The decimal ("D" or "d") and hexadecimal ("X" or "x") format specifiers are supported only for integral types.</span></span> <span data-ttu-id="dcd93-147">El especificador de formato del recorrido de ida y vuelta ("R" o "r") solo es compatible para los tipos <xref:System.Single>, <xref:System.Double> y <xref:System.Numerics.BigInteger>.</span><span class="sxs-lookup"><span data-stu-id="dcd93-147">The round-trip ("R" or "r") format specifier is supported only for <xref:System.Single>, <xref:System.Double>, and <xref:System.Numerics.BigInteger> types.</span></span>

<span data-ttu-id="dcd93-148">Las cadenas con formato numérico estándar son compatibles con:</span><span class="sxs-lookup"><span data-stu-id="dcd93-148">Standard numeric format strings are supported by:</span></span>

- <span data-ttu-id="dcd93-149">Algunas sobrecargas del método `ToString` de todos los tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="dcd93-149">Some overloads of the `ToString` method of all numeric types.</span></span> <span data-ttu-id="dcd93-150">Por ejemplo, se puede proporcionar una cadena de formato numérico a los métodos <xref:System.Int32.ToString%28System.String%29?displayProperty=nameWithType> y <xref:System.Int32.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dcd93-150">For example, you can supply a numeric format string to the <xref:System.Int32.ToString%28System.String%29?displayProperty=nameWithType> and <xref:System.Int32.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> methods.</span></span>

- <span data-ttu-id="dcd93-151">La [característica de formato compuesto](../../../standard/base-types/composite-formatting.md) de .NET, que es compatible con el método <xref:System.String.Format%2A?displayProperty=nameWithType>, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="dcd93-151">The .NET [composite formatting feature](../../../standard/base-types/composite-formatting.md), which is supported by the <xref:System.String.Format%2A?displayProperty=nameWithType> method, for example.</span></span>

- <span data-ttu-id="dcd93-152">[Cadenas interpoladas](../tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="dcd93-152">[Interpolated strings](../tokens/interpolated.md).</span></span>

<span data-ttu-id="dcd93-153">Para más información, vea [Cadenas de formato numérico estándar](../../../standard/base-types/standard-numeric-format-strings.md).</span><span class="sxs-lookup"><span data-stu-id="dcd93-153">For more information, see [Standard Numeric Format Strings](../../../standard/base-types/standard-numeric-format-strings.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dcd93-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="dcd93-154">See also</span></span>

- [<span data-ttu-id="dcd93-155">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="dcd93-155">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="dcd93-156">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="dcd93-156">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="dcd93-157">Aplicar formato a tipos</span><span class="sxs-lookup"><span data-stu-id="dcd93-157">Formatting types</span></span>](../../../standard/base-types/formatting-types.md)
- [<span data-ttu-id="dcd93-158">Formatos compuestos</span><span class="sxs-lookup"><span data-stu-id="dcd93-158">Composite formatting</span></span>](../../../standard/base-types/composite-formatting.md)
- [<span data-ttu-id="dcd93-159">Interpolación de cadenas</span><span class="sxs-lookup"><span data-stu-id="dcd93-159">String interpolation</span></span>](../tokens/interpolated.md)
- [<span data-ttu-id="dcd93-160">string</span><span class="sxs-lookup"><span data-stu-id="dcd93-160">string</span></span>](../builtin-types/reference-types.md)

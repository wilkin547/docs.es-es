---
title: "Tabla de formatos de presentación para valores numéricos (Referencia de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- formatting [C#]
- numeric formatting [C#]
- String.Format method
- Console.Write method
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 16976f5a59bd4eb0eca29553aff87d4fe0b1d247
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="formatting-numeric-results-table-c-reference"></a><span data-ttu-id="52ebb-102">Tabla de formatos de presentación para valores numéricos (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="52ebb-102">Formatting Numeric Results Table (C# Reference)</span></span>
<span data-ttu-id="52ebb-103">Se pueden aplicar formatos a los resultados numéricos mediante el método <xref:System.String.Format%2A?displayProperty=fullName>, o con el método <xref:System.Console.Write%2A?displayProperty=fullName> o <xref:System.Console.WriteLine%2A?displayProperty=fullName> que realiza una llamada a `String.Format`.</span><span class="sxs-lookup"><span data-stu-id="52ebb-103">You can format numeric results by using the <xref:System.String.Format%2A?displayProperty=fullName> method, or through the <xref:System.Console.Write%2A?displayProperty=fullName> or <xref:System.Console.WriteLine%2A?displayProperty=fullName> method, which calls `String.Format`.</span></span> <span data-ttu-id="52ebb-104">El formato se especifica mediante cadenas de formato.</span><span class="sxs-lookup"><span data-stu-id="52ebb-104">The format is specified by using format strings.</span></span> <span data-ttu-id="52ebb-105">La tabla siguiente contiene las cadenas de formato estándar admitidas.</span><span class="sxs-lookup"><span data-stu-id="52ebb-105">The following table contains the supported standard format strings.</span></span> <span data-ttu-id="52ebb-106">La cadena de formato toma la siguiente forma: `Axx`, donde `A` es el especificador de formato y `xx` es el especificador de precisión.</span><span class="sxs-lookup"><span data-stu-id="52ebb-106">The format string takes the following form: `Axx`, where `A` is the format specifier and `xx` is the precision specifier.</span></span> <span data-ttu-id="52ebb-107">El especificador de formato controla el tipo de formato aplicado al valor numérico, mientras que el especificador de precisión controla el número de dígitos significativos o posiciones decimales del resultado.</span><span class="sxs-lookup"><span data-stu-id="52ebb-107">The format specifier controls the type of formatting applied to the numeric value, and the precision specifier controls the number of significant digits or decimal places of the formatted output.</span></span> <span data-ttu-id="52ebb-108">El valor de los intervalos del especificador de precisión comprende de 0 a 99.</span><span class="sxs-lookup"><span data-stu-id="52ebb-108">The value of the precision specifier ranges from 0 to 99.</span></span>  
  
 <span data-ttu-id="52ebb-109">Para obtener más información sobre cadenas de formato estándar y personalizadas, vea [Aplicación de formato a tipo](../../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="52ebb-109">For more information about standard and custom formatting strings, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span> <span data-ttu-id="52ebb-110">Para obtener más información sobre el método `String.Format`, vea <xref:System.String.Format%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="52ebb-110">For more information about the `String.Format` method, see <xref:System.String.Format%2A?displayProperty=fullName>.</span></span>  
  
|<span data-ttu-id="52ebb-111">Especificador de formato</span><span class="sxs-lookup"><span data-stu-id="52ebb-111">Format Specifier</span></span>|<span data-ttu-id="52ebb-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="52ebb-112">Description</span></span>|<span data-ttu-id="52ebb-113">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="52ebb-113">Examples</span></span>|<span data-ttu-id="52ebb-114">Salida</span><span class="sxs-lookup"><span data-stu-id="52ebb-114">Output</span></span>|  
|----------------------|-----------------|--------------|------------|  
|<span data-ttu-id="52ebb-115">C o c</span><span class="sxs-lookup"><span data-stu-id="52ebb-115">C or c</span></span>|<span data-ttu-id="52ebb-116">Moneda</span><span class="sxs-lookup"><span data-stu-id="52ebb-116">Currency</span></span>|<span data-ttu-id="52ebb-117">Console.Write("{0:C}", 2.5);</span><span class="sxs-lookup"><span data-stu-id="52ebb-117">Console.Write("{0:C}", 2.5);</span></span><br /><br /> <span data-ttu-id="52ebb-118">Console.Write("{0:C}", -2.5);</span><span class="sxs-lookup"><span data-stu-id="52ebb-118">Console.Write("{0:C}", -2.5);</span></span>|<span data-ttu-id="52ebb-119">$2.50</span><span class="sxs-lookup"><span data-stu-id="52ebb-119">$2.50</span></span><br /><br /> <span data-ttu-id="52ebb-120">($2.50)</span><span class="sxs-lookup"><span data-stu-id="52ebb-120">($2.50)</span></span>|  
|<span data-ttu-id="52ebb-121">D o d</span><span class="sxs-lookup"><span data-stu-id="52ebb-121">D or d</span></span>|<span data-ttu-id="52ebb-122">Decimal</span><span class="sxs-lookup"><span data-stu-id="52ebb-122">Decimal</span></span>|<span data-ttu-id="52ebb-123">Console.Write("{0:D5}", 25);</span><span class="sxs-lookup"><span data-stu-id="52ebb-123">Console.Write("{0:D5}", 25);</span></span>|<span data-ttu-id="52ebb-124">00025</span><span class="sxs-lookup"><span data-stu-id="52ebb-124">00025</span></span>|  
|<span data-ttu-id="52ebb-125">E o e</span><span class="sxs-lookup"><span data-stu-id="52ebb-125">E or e</span></span>|<span data-ttu-id="52ebb-126">Científica</span><span class="sxs-lookup"><span data-stu-id="52ebb-126">Scientific</span></span>|<span data-ttu-id="52ebb-127">Console.Write("{0:E}", 250000);</span><span class="sxs-lookup"><span data-stu-id="52ebb-127">Console.Write("{0:E}", 250000);</span></span>|<span data-ttu-id="52ebb-128">2.500000E+005</span><span class="sxs-lookup"><span data-stu-id="52ebb-128">2.500000E+005</span></span>|  
|<span data-ttu-id="52ebb-129">F o f</span><span class="sxs-lookup"><span data-stu-id="52ebb-129">F or f</span></span>|<span data-ttu-id="52ebb-130">Punto fijo</span><span class="sxs-lookup"><span data-stu-id="52ebb-130">Fixed-point</span></span>|<span data-ttu-id="52ebb-131">Console.Write("{0:F2}", 25);</span><span class="sxs-lookup"><span data-stu-id="52ebb-131">Console.Write("{0:F2}", 25);</span></span><br /><br /> <span data-ttu-id="52ebb-132">Console.Write("{0:F0}", 25);</span><span class="sxs-lookup"><span data-stu-id="52ebb-132">Console.Write("{0:F0}", 25);</span></span>|<span data-ttu-id="52ebb-133">25.00</span><span class="sxs-lookup"><span data-stu-id="52ebb-133">25.00</span></span><br /><br /> <span data-ttu-id="52ebb-134">25</span><span class="sxs-lookup"><span data-stu-id="52ebb-134">25</span></span>|  
|<span data-ttu-id="52ebb-135">G o g</span><span class="sxs-lookup"><span data-stu-id="52ebb-135">G or g</span></span>|<span data-ttu-id="52ebb-136">General</span><span class="sxs-lookup"><span data-stu-id="52ebb-136">General</span></span>|<span data-ttu-id="52ebb-137">Console.Write("{0:G}", 2.5);</span><span class="sxs-lookup"><span data-stu-id="52ebb-137">Console.Write("{0:G}", 2.5);</span></span>|<span data-ttu-id="52ebb-138">2.5</span><span class="sxs-lookup"><span data-stu-id="52ebb-138">2.5</span></span>|  
|<span data-ttu-id="52ebb-139">N o n</span><span class="sxs-lookup"><span data-stu-id="52ebb-139">N or n</span></span>|<span data-ttu-id="52ebb-140">Número</span><span class="sxs-lookup"><span data-stu-id="52ebb-140">Number</span></span>|<span data-ttu-id="52ebb-141">Console.Write("{0:N}", 2500000);</span><span class="sxs-lookup"><span data-stu-id="52ebb-141">Console.Write("{0:N}", 2500000);</span></span>|<span data-ttu-id="52ebb-142">2,500,000.00</span><span class="sxs-lookup"><span data-stu-id="52ebb-142">2,500,000.00</span></span>|  
|<span data-ttu-id="52ebb-143">X o x</span><span class="sxs-lookup"><span data-stu-id="52ebb-143">X or x</span></span>|<span data-ttu-id="52ebb-144">Hexadecimal</span><span class="sxs-lookup"><span data-stu-id="52ebb-144">Hexadecimal</span></span>|<span data-ttu-id="52ebb-145">Console.Write("{0:X}", 250);</span><span class="sxs-lookup"><span data-stu-id="52ebb-145">Console.Write("{0:X}", 250);</span></span><br /><br /> <span data-ttu-id="52ebb-146">Console.Write("{0:X}", 0xffff);</span><span class="sxs-lookup"><span data-stu-id="52ebb-146">Console.Write("{0:X}", 0xffff);</span></span>|<span data-ttu-id="52ebb-147">FA</span><span class="sxs-lookup"><span data-stu-id="52ebb-147">FA</span></span><br /><br /> <span data-ttu-id="52ebb-148">FFFF</span><span class="sxs-lookup"><span data-stu-id="52ebb-148">FFFF</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="52ebb-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="52ebb-149">See Also</span></span>  
 <span data-ttu-id="52ebb-150">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="52ebb-150">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="52ebb-151">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="52ebb-151">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="52ebb-152">[Cadenas con formato numérico estándar](../../../standard/base-types/standard-numeric-format-strings.md) </span><span class="sxs-lookup"><span data-stu-id="52ebb-152">[Standard Numeric Format Strings](../../../standard/base-types/standard-numeric-format-strings.md) </span></span>  
 <span data-ttu-id="52ebb-153">[Tablas de referencia para tipos](../../../csharp/language-reference/keywords/reference-tables-for-types.md) </span><span class="sxs-lookup"><span data-stu-id="52ebb-153">[Reference Tables for Types](../../../csharp/language-reference/keywords/reference-tables-for-types.md) </span></span>  
 [<span data-ttu-id="52ebb-154">string</span><span class="sxs-lookup"><span data-stu-id="52ebb-154">string</span></span>](../../../csharp/language-reference/keywords/string.md)


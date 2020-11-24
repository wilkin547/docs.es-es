---
title: Procedimiento para rellenar un número con ceros a la izquierda
description: Aprenda a rellenar un número con ceros iniciales. Agregue ceros a la izquierda a números enteros o valores numéricos hasta una longitud total concreta o un número específico de ceros a la izquierda.
ms.date: 02/25/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- numeric format strings [.NET]
- formatting [.NET], numbers
- number formatting [.NET]
- numbers [.NET], format strings
ms.assetid: 0b2c2cb5-c580-4891-8d81-cb632f5ec384
ms.openlocfilehash: 911d6059d3594ca35eb1c1c3e2d29a5684bce738
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822053"
---
# <a name="how-to-pad-a-number-with-leading-zeros"></a><span data-ttu-id="d875c-104">Procedimiento para rellenar un número con ceros a la izquierda</span><span class="sxs-lookup"><span data-stu-id="d875c-104">How to: Pad a Number with Leading Zeros</span></span>

<span data-ttu-id="d875c-105">Si quiere agregar ceros a la izquierda de un entero, puede hacerlo mediante la [cadena de formato numérico estándar](standard-numeric-format-strings.md) "D" con un especificador de precisión.</span><span class="sxs-lookup"><span data-stu-id="d875c-105">You can add leading zeros to an integer by using the "D" [standard numeric format string](standard-numeric-format-strings.md) with a precision specifier.</span></span> <span data-ttu-id="d875c-106">Para agregar ceros a la izquierda tanto de enteros como de números de punto flotante, use una [cadena de formato numérico personalizada](custom-numeric-format-strings.md).</span><span class="sxs-lookup"><span data-stu-id="d875c-106">You can add leading zeros to both integer and floating-point numbers by using a [custom numeric format string](custom-numeric-format-strings.md).</span></span> <span data-ttu-id="d875c-107">En este artículo se explica cómo usar ambos métodos para rellenar un número con ceros a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="d875c-107">This article shows how to use both methods to pad a number with leading zeros.</span></span>

## <a name="to-pad-an-integer-with-leading-zeros-to-a-specific-length"></a><span data-ttu-id="d875c-108">Para rellenar un entero con ceros a la izquierda hasta una longitud concreta</span><span class="sxs-lookup"><span data-stu-id="d875c-108">To pad an integer with leading zeros to a specific length</span></span>

1. <span data-ttu-id="d875c-109">Determine el número mínimo de dígitos que desea que muestre el valor entero.</span><span class="sxs-lookup"><span data-stu-id="d875c-109">Determine the minimum number of digits you want the integer value to display.</span></span> <span data-ttu-id="d875c-110">Incluya los dígitos a la izquierda en este número.</span><span class="sxs-lookup"><span data-stu-id="d875c-110">Include any leading digits in this number.</span></span>

1. <span data-ttu-id="d875c-111">Determine si desea mostrar el entero como valor decimal o hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="d875c-111">Determine whether you want to display the integer as a decimal value or a hexadecimal value.</span></span>

    - <span data-ttu-id="d875c-112">Para mostrar el entero como valor decimal, llame a su método `ToString(String)` y pase la cadena "D *n*" como valor del parámetro `format`, donde *n* representa la longitud mínima de la cadena.</span><span class="sxs-lookup"><span data-stu-id="d875c-112">To display the integer as a decimal value, call its `ToString(String)` method, and pass the string "D *n*" as the value of the `format` parameter, where *n* represents the minimum length of the string.</span></span>

    - <span data-ttu-id="d875c-113">Para mostrar el entero como valor hexadecimal, llame a su método `ToString(String)` y pase la cadena "X *n*" como valor del parámetro format, donde *n* representa la longitud mínima de la cadena.</span><span class="sxs-lookup"><span data-stu-id="d875c-113">To display the integer as a hexadecimal value, call its `ToString(String)` method and pass the string "X *n*" as the value of the format parameter, where *n* represents the minimum length of the string.</span></span>

<span data-ttu-id="d875c-114">También puede usar la cadena de formato en una cadena interpolada en ambos, [C#](../../csharp/language-reference/tokens/interpolated.md) y [Visual Basic](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md), o puede llamar a un método, como <xref:System.String.Format%2A?displayProperty=nameWithType> o <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, que usa [formato compuesto](composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="d875c-114">You can also use the format string in an interpolated string in both [C#](../../csharp/language-reference/tokens/interpolated.md) and [Visual Basic](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md), or you can call a method, such as <xref:System.String.Format%2A?displayProperty=nameWithType> or <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, that uses [composite formatting](composite-formatting.md).</span></span>

<span data-ttu-id="d875c-115">En el ejemplo siguiente se aplica formato a varios valores enteros con ceros a la izquierda de modo que la longitud mínima total del número con formato sea de ocho caracteres.</span><span class="sxs-lookup"><span data-stu-id="d875c-115">The following example formats several integer values with leading zeros so that the total length of the formatted number is at least eight characters.</span></span>

[!code-csharp[Formatting.HowTo.PadNumber#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#1)]
[!code-vb[Formatting.HowTo.PadNumber#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#1)]

## <a name="to-pad-an-integer-with-a-specific-number-of-leading-zeros"></a><span data-ttu-id="d875c-116">Para rellenar un entero con una determinada cantidad de ceros a la izquierda</span><span class="sxs-lookup"><span data-stu-id="d875c-116">To pad an integer with a specific number of leading zeros</span></span>

1. <span data-ttu-id="d875c-117">Determine cuántos ceros a la izquierda desea que muestre el valor entero.</span><span class="sxs-lookup"><span data-stu-id="d875c-117">Determine how many leading zeros you want the integer value to display.</span></span>

1. <span data-ttu-id="d875c-118">Determine si desea mostrar el entero como valor decimal o hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="d875c-118">Determine whether you want to display the integer as a decimal value or a hexadecimal value.</span></span>

    - <span data-ttu-id="d875c-119">Para darle formato como valor decimal, se requiere que use el especificador de formato estándar "D".</span><span class="sxs-lookup"><span data-stu-id="d875c-119">Formatting it as a decimal value requires that you use the "D" standard format specifier.</span></span>

    - <span data-ttu-id="d875c-120">Para darle formato como valor hexadecimal, se requiere que use el especificador de formato estándar "X".</span><span class="sxs-lookup"><span data-stu-id="d875c-120">Formatting it as a hexadecimal value requires that you use the "X" standard format specifier.</span></span>

1. <span data-ttu-id="d875c-121">Determine la longitud de la cadena numérica sin rellenar mediante una llamada a los métodos `ToString("D").Length` o `ToString("X").Length` del valor entero.</span><span class="sxs-lookup"><span data-stu-id="d875c-121">Determine the length of the unpadded numeric string by calling the integer value's `ToString("D").Length` or `ToString("X").Length` method.</span></span>

1. <span data-ttu-id="d875c-122">Agregue el número de ceros a la izquierda que desea incluir en la cadena con formato a la longitud de la cadena numérica sin rellenar.</span><span class="sxs-lookup"><span data-stu-id="d875c-122">Add the number of leading zeros that you want to include in the formatted string to the length of the unpadded numeric string.</span></span> <span data-ttu-id="d875c-123">Al agregar el número de ceros iniciales se define la longitud total de la cadena rellenada.</span><span class="sxs-lookup"><span data-stu-id="d875c-123">Adding the number of leading zeros defines the total length of the padded string.</span></span>

1. <span data-ttu-id="d875c-124">Llame al método `ToString(String)` del valor entero y pase la cadena "D *n*" para cadenas decimales y "X *n*" para cadenas hexadecimales, donde *n* representa la longitud total de la cadena rellenada.</span><span class="sxs-lookup"><span data-stu-id="d875c-124">Call the integer value's `ToString(String)` method, and pass the string "D *n*" for decimal strings and "X *n*" for hexadecimal strings, where *n* represents the total length of the padded string.</span></span> <span data-ttu-id="d875c-125">También puede usar la cadena de formato "D *n*" o "X *n*" en un método que admita formato compuesto.</span><span class="sxs-lookup"><span data-stu-id="d875c-125">You can also use the "D *n*" or "X *n*" format string in a method that supports composite formatting.</span></span>

<span data-ttu-id="d875c-126">En el ejemplo siguiente se rellena un valor entero con cinco ceros a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="d875c-126">The following example pads an integer value with five leading zeros.</span></span>

[!code-csharp[Formatting.HowTo.PadNumber#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#2)]
[!code-vb[Formatting.HowTo.PadNumber#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#2)]

## <a name="to-pad-a-numeric-value-with-leading-zeros-to-a-specific-length"></a><span data-ttu-id="d875c-127">Para rellenar un valor numérico con ceros a la izquierda hasta una longitud concreta</span><span class="sxs-lookup"><span data-stu-id="d875c-127">To pad a numeric value with leading zeros to a specific length</span></span>

1. <span data-ttu-id="d875c-128">Determine con cuántos dígitos a la izquierda del decimal desea que se represente la cadena del número.</span><span class="sxs-lookup"><span data-stu-id="d875c-128">Determine how many digits to the left of the decimal you want the string representation of the number to have.</span></span> <span data-ttu-id="d875c-129">Incluya los ceros a la izquierda en este número total de dígitos.</span><span class="sxs-lookup"><span data-stu-id="d875c-129">Include any leading zeros in this total number of digits.</span></span>

1. <span data-ttu-id="d875c-130">Defina una cadena de formato numérico personalizado en la que se use el marcador de posición cero "0" para representar el número mínimo de ceros.</span><span class="sxs-lookup"><span data-stu-id="d875c-130">Define a custom numeric format string that uses the zero placeholder "0" to represent the minimum number of zeros.</span></span>

1. <span data-ttu-id="d875c-131">Llame al método `ToString(String)` del número y pase la cadena de formato personalizado.</span><span class="sxs-lookup"><span data-stu-id="d875c-131">Call the number's `ToString(String)` method and pass it the custom format string.</span></span> <span data-ttu-id="d875c-132">También puede usar la cadena de formato personalizado con interpolación de cadena o con un método que admita formato compuesto.</span><span class="sxs-lookup"><span data-stu-id="d875c-132">You can also use the custom format string with string interpolation or with a method that supports composite formatting.</span></span>

<span data-ttu-id="d875c-133">En el ejemplo siguiente se da formato a varios valores numéricos con ceros iniciales.</span><span class="sxs-lookup"><span data-stu-id="d875c-133">The following example formats several numeric values with leading zeros.</span></span> <span data-ttu-id="d875c-134">Como resultado, la longitud total del número con formato es de al menos ocho dígitos a la izquierda del separador decimal.</span><span class="sxs-lookup"><span data-stu-id="d875c-134">As a result, the total length of the formatted number is at least eight digits to the left of the decimal.</span></span>

[!code-csharp[Formatting.HowTo.PadNumber#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#3)]
[!code-vb[Formatting.HowTo.PadNumber#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#3)]

## <a name="to-pad-a-numeric-value-with-a-specific-number-of-leading-zeros"></a><span data-ttu-id="d875c-135">Para rellenar un valor numérico con una determinada cantidad de ceros a la izquierda</span><span class="sxs-lookup"><span data-stu-id="d875c-135">To pad a numeric value with a specific number of leading zeros</span></span>

1. <span data-ttu-id="d875c-136">Determine cuántos ceros a la izquierda desea que tenga el valor numérico.</span><span class="sxs-lookup"><span data-stu-id="d875c-136">Determine how many leading zeros you want the numeric value to have.</span></span>

1. <span data-ttu-id="d875c-137">Determine el número de dígitos a la izquierda del separador decimal que tendrá la cadena numérica sin rellenar:</span><span class="sxs-lookup"><span data-stu-id="d875c-137">Determine the number of digits to the left of the decimal in the unpadded numeric string:</span></span>

    1. <span data-ttu-id="d875c-138">Determine si la representación de cadena de un número incluye un símbolo de separador decimal.</span><span class="sxs-lookup"><span data-stu-id="d875c-138">Determine whether the string representation of a number includes a decimal point symbol.</span></span>

    1. <span data-ttu-id="d875c-139">Si incluye un símbolo de separador decimal, determine el número de caracteres a la izquierda del separador decimal.</span><span class="sxs-lookup"><span data-stu-id="d875c-139">If it does include a decimal point symbol, determine the number of characters to the left of the decimal point.</span></span>

         <span data-ttu-id="d875c-140">o bien</span><span class="sxs-lookup"><span data-stu-id="d875c-140">-or-</span></span>

         <span data-ttu-id="d875c-141">Si no incluye un símbolo de separador decimal, determine la longitud de la cadena.</span><span class="sxs-lookup"><span data-stu-id="d875c-141">If it doesn't include a decimal point symbol, determine the string's length.</span></span>

1. <span data-ttu-id="d875c-142">Cree una cadena de formato personalizado que utilice:</span><span class="sxs-lookup"><span data-stu-id="d875c-142">Create a custom format string that uses:</span></span>

    - <span data-ttu-id="d875c-143">El marcador de posición cero "0" para cada uno de los ceros a la izquierda que aparecen en la cadena.</span><span class="sxs-lookup"><span data-stu-id="d875c-143">The zero placeholder "0" for each of the leading zeros to appear in the string.</span></span>

    - <span data-ttu-id="d875c-144">El marcador de posición cero o el marcador de posición de dígito "#" para representar cada dígito en la cadena predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d875c-144">Either the zero placeholder or the digit placeholder "#" to represent each digit in the default string.</span></span>

1. <span data-ttu-id="d875c-145">Proporcione la cadena de formato personalizado como un parámetro bien al método `ToString(String)` del número, bien a un método que admita el formato compuesto.</span><span class="sxs-lookup"><span data-stu-id="d875c-145">Supply the custom format string as a parameter either to the number's `ToString(String)` method or to a method that supports composite formatting.</span></span>

<span data-ttu-id="d875c-146">En el ejemplo siguiente se rellenan dos valores <xref:System.Double> con cinco ceros a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="d875c-146">The following example pads two <xref:System.Double> values with five leading zeros.</span></span>

[!code-csharp[Formatting.HowTo.PadNumber#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#4)]
[!code-vb[Formatting.HowTo.PadNumber#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#4)]

## <a name="see-also"></a><span data-ttu-id="d875c-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="d875c-147">See also</span></span>

- [<span data-ttu-id="d875c-148">Cadenas con formato numérico personalizado</span><span class="sxs-lookup"><span data-stu-id="d875c-148">Custom Numeric Format Strings</span></span>](custom-numeric-format-strings.md)
- [<span data-ttu-id="d875c-149">Cadenas con formato numérico estándar</span><span class="sxs-lookup"><span data-stu-id="d875c-149">Standard Numeric Format Strings</span></span>](standard-numeric-format-strings.md)
- [<span data-ttu-id="d875c-150">Formatos compuestos</span><span class="sxs-lookup"><span data-stu-id="d875c-150">Composite Formatting</span></span>](composite-formatting.md)

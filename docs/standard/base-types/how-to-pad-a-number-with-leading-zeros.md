---
title: Procedimiento para rellenar un número con ceros a la izquierda
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- numeric format strings [.NET Framework]
- formatting [.NET Framework], numbers
- number formatting [.NET Framework]
- numbers [.NET Framework], format strings
ms.assetid: 0b2c2cb5-c580-4891-8d81-cb632f5ec384
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b48462e79c3e8ef3fdd6e0a91f5abecffc022b5c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54673041"
---
# <a name="how-to-pad-a-number-with-leading-zeros"></a><span data-ttu-id="d1d8e-102">Procedimiento para rellenar un número con ceros a la izquierda</span><span class="sxs-lookup"><span data-stu-id="d1d8e-102">How to: Pad a Number with Leading Zeros</span></span>
<span data-ttu-id="d1d8e-103">Si quiere agregar ceros a la izquierda de un entero, puede hacerlo mediante la [cadena de formato numérico estándar](../../../docs/standard/base-types/standard-numeric-format-strings.md) "D" con un especificador de precisión.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-103">You can add leading zeros to an integer by using the "D" [standard numeric format string](../../../docs/standard/base-types/standard-numeric-format-strings.md) with a precision specifier.</span></span> <span data-ttu-id="d1d8e-104">Para agregar ceros a la izquierda tanto de enteros como de números de punto flotante, use una [cadena de formato numérico personalizada](../../../docs/standard/base-types/custom-numeric-format-strings.md).</span><span class="sxs-lookup"><span data-stu-id="d1d8e-104">You can add leading zeros to both integer and floating-point numbers by using a [custom numeric format string](../../../docs/standard/base-types/custom-numeric-format-strings.md).</span></span> <span data-ttu-id="d1d8e-105">En este tema se explica cómo usar ambos métodos para rellenar un número con ceros a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-105">This topic shows how to use both methods to pad a number with leading zeros.</span></span>  
  
### <a name="to-pad-an-integer-with-leading-zeros-to-a-specific-length"></a><span data-ttu-id="d1d8e-106">Para rellenar un entero con ceros a la izquierda hasta una longitud concreta</span><span class="sxs-lookup"><span data-stu-id="d1d8e-106">To pad an integer with leading zeros to a specific length</span></span>  
  
1.  <span data-ttu-id="d1d8e-107">Determine el número mínimo de dígitos que desea que muestre el valor entero.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-107">Determine the minimum number of digits you want the integer value to display.</span></span> <span data-ttu-id="d1d8e-108">Incluya los dígitos a la izquierda en este número.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-108">Include any leading digits in this number.</span></span>  
  
2.  <span data-ttu-id="d1d8e-109">Determine si desea mostrar el entero como valor decimal o hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-109">Determine whether you want to display the integer as a decimal value or a hexadecimal value.</span></span>  
  
    -   <span data-ttu-id="d1d8e-110">Para mostrar el entero como valor decimal, llame a su método `ToString(String)` y pase la cadena "D*n*" como valor del parámetro `format`, donde *n* representa la longitud mínima de la cadena.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-110">To display the integer as a decimal value, call its `ToString(String)` method, and pass the string "D*n*" as the value of the `format` parameter, where *n* represents the minimum length of the string.</span></span>  
  
    -   <span data-ttu-id="d1d8e-111">Para mostrar el entero como valor hexadecimal, llame a su método `ToString(String)` y pase la cadena "X*n*" como valor del parámetro `format`, donde *n* representa la longitud mínima de la cadena.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-111">To display the integer as a hexadecimal value, call its `ToString(String)` method and pass the string "X*n*" as the value of the `format` parameter, where *n* represents the minimum length of the string.</span></span>  
  
     <span data-ttu-id="d1d8e-112">También puede usar la cadena de formato en un método como, por ejemplo, <xref:System.String.Format%2A> o <xref:System.Console.WriteLine%2A>, que usan [formato compuesto](../../../docs/standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="d1d8e-112">You can also use the format string in a method, such as <xref:System.String.Format%2A> or <xref:System.Console.WriteLine%2A>, that uses [composite formatting](../../../docs/standard/base-types/composite-formatting.md).</span></span>  
  
 <span data-ttu-id="d1d8e-113">En el ejemplo siguiente se aplica formato a varios valores enteros con ceros a la izquierda de modo que la longitud mínima total del número con formato sea de ocho caracteres.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-113">The following example formats several integer values with leading zeros so that the total length of the formatted number is at least eight characters.</span></span>  
  
 [!code-csharp[Formatting.HowTo.PadNumber#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#1)]
 [!code-vb[Formatting.HowTo.PadNumber#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#1)]  
  
### <a name="to-pad-an-integer-with-a-specific-number-of-leading-zeros"></a><span data-ttu-id="d1d8e-114">Para rellenar un entero con una determinada cantidad de ceros a la izquierda</span><span class="sxs-lookup"><span data-stu-id="d1d8e-114">To pad an integer with a specific number of leading zeros</span></span>  
  
1.  <span data-ttu-id="d1d8e-115">Determine cuántos ceros a la izquierda desea que muestre el valor entero.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-115">Determine how many leading zeros you want the integer value to display.</span></span>  
  
2.  <span data-ttu-id="d1d8e-116">Determine si desea mostrar el entero como valor decimal o hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-116">Determine whether you want to display the integer as a decimal value or a hexadecimal value.</span></span> <span data-ttu-id="d1d8e-117">Para aplicar el formato de valor decimal hay que usar el especificador de formato estándar “D”, mientras que para el valor hexadecimal hay que usar el especificador de formato estándar “X”.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-117">Formatting it as a decimal value requires that you use the "D" standard format specifier; formatting it as a hexadecimal value requires that you use the "X" standard format specifier.</span></span>  
  
3.  <span data-ttu-id="d1d8e-118">Determine la longitud de la cadena numérica sin rellenar mediante una llamada a los métodos `ToString("D").Length` o `ToString("X").Length` del valor entero.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-118">Determine the length of the unpadded numeric string by calling the integer value's `ToString("D").Length` or `ToString("X").Length` method.</span></span>  
  
4.  <span data-ttu-id="d1d8e-119">Agregue el número de ceros a la izquierda que desea incluir en la cadena con formato a la longitud de la cadena numérica sin rellenar.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-119">Add the number of leading zeros that you want to include in the formatted string to the length of the unpadded numeric string.</span></span> <span data-ttu-id="d1d8e-120">Esto define la longitud total de la cadena rellenada.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-120">This defines the total length of the padded string.</span></span>  
  
5.  <span data-ttu-id="d1d8e-121">Llame al método `ToString(String)` del valor entero y pase la cadena "D*n*" para cadenas decimales y "X*n*" para cadenas hexadecimales, donde *n* representa la longitud total de la cadena rellenada.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-121">Call the integer value's `ToString(String)` method, and pass the string "D*n*" for decimal strings and "X*n*" for hexadecimal strings, where *n* represents the total length of the padded string.</span></span> <span data-ttu-id="d1d8e-122">También puede usar la cadena de formato "D*n*" o "X*n*" en un método que admita formato compuesto.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-122">You can also use the "D*n*" or "X*n*" format string in a method that supports composite formatting.</span></span>  
  
 <span data-ttu-id="d1d8e-123">En el ejemplo siguiente se rellena un valor entero con cinco ceros a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-123">The following example pads an integer value with five leading zeros.</span></span>  
  
 [!code-csharp[Formatting.HowTo.PadNumber#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#2)]
 [!code-vb[Formatting.HowTo.PadNumber#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#2)]  
  
### <a name="to-pad-a-numeric-value-with-leading-zeros-to-a-specific-length"></a><span data-ttu-id="d1d8e-124">Para rellenar un valor numérico con ceros a la izquierda hasta una longitud concreta</span><span class="sxs-lookup"><span data-stu-id="d1d8e-124">To pad a numeric value with leading zeros to a specific length</span></span>  
  
1.  <span data-ttu-id="d1d8e-125">Determine con cuántos dígitos a la izquierda del decimal desea que se represente la cadena del número.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-125">Determine how many digits to the left of the decimal you want the string representation of the number to have.</span></span> <span data-ttu-id="d1d8e-126">Incluya los ceros a la izquierda en este número total de dígitos.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-126">Include any leading zeros in this total number of digits.</span></span>  
  
2.  <span data-ttu-id="d1d8e-127">Defina una cadena de formato numérico personalizado en la que se use el marcador de posición cero (“0”) para representar el número mínimo de ceros.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-127">Define a custom numeric format string that uses the zero placeholder ("0") to represent the minimum number of zeros.</span></span>  
  
3.  <span data-ttu-id="d1d8e-128">Llame al método `ToString(String)` del número y pase la cadena de formato personalizado.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-128">Call the number's `ToString(String)` method and pass it the custom format string.</span></span> <span data-ttu-id="d1d8e-129">También puede usar la cadena de formato personalizado con un método que admita formato compuesto.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-129">You can also use the custom format string with a method that supports composite formatting.</span></span>  
  
 <span data-ttu-id="d1d8e-130">En el ejemplo siguiente se aplica formato a varios valores numéricos con ceros a la izquierda de modo que la longitud total del número con formato sea de al menos ocho dígitos a la izquierda del decimal.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-130">The following example formats several numeric values with leading zeros so that the total length of the formatted number is at least eight digits to the left of the decimal.</span></span>  
  
 [!code-csharp[Formatting.HowTo.PadNumber#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#3)]
 [!code-vb[Formatting.HowTo.PadNumber#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#3)]  
  
### <a name="to-pad-a-numeric-value-with-a-specific-number-of-leading-zeros"></a><span data-ttu-id="d1d8e-131">Para rellenar un valor numérico con una determinada cantidad de ceros a la izquierda</span><span class="sxs-lookup"><span data-stu-id="d1d8e-131">To pad a numeric value with a specific number of leading zeros</span></span>  
  
1.  <span data-ttu-id="d1d8e-132">Determine cuántos ceros a la izquierda desea que tenga el valor numérico.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-132">Determine how many leading zeros you want the numeric value to have.</span></span>  
  
2.  <span data-ttu-id="d1d8e-133">Determine el número de dígitos a la izquierda del decimal que tendrá la cadena numérica sin rellenar.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-133">Determine the number of digits to the left of the decimal in the unpadded numeric string.</span></span> <span data-ttu-id="d1d8e-134">Para hacerlo:</span><span class="sxs-lookup"><span data-stu-id="d1d8e-134">To do this:</span></span>  
  
    1.  <span data-ttu-id="d1d8e-135">Determine si la representación de cadena de un número incluye un símbolo de separador decimal.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-135">Determine whether the string representation of a number includes a decimal point symbol.</span></span>  
  
    2.  <span data-ttu-id="d1d8e-136">Si incluye un símbolo de separador decimal, determine el número de caracteres a la izquierda del separador decimal.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-136">If it does include a decimal point symbol, determine the number of characters to the left of the decimal point.</span></span>  
  
         <span data-ttu-id="d1d8e-137">o bien</span><span class="sxs-lookup"><span data-stu-id="d1d8e-137">-or-</span></span>  
  
         <span data-ttu-id="d1d8e-138">Si no incluye un símbolo de separador decimal, determine la longitud de la cadena.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-138">If it does not include a decimal point symbol, determine the string's length.</span></span>  
  
3.  <span data-ttu-id="d1d8e-139">Cree una cadena de formato personalizado en la que se use el marcador de posición cero (“0”) para cada uno de los ceros a la izquierda que aparecen en la cadena, y en la que se use también el marcador de posición cero o el marcador de posición de dígitos (“#”) para representar cada uno de los dígitos de la cadena predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-139">Create a custom format string that uses the zero placeholder ("0") for each of the leading zeros to appear in the string, and that uses either the zero placeholder or the digit placeholder ("#") to represent each digit in the default string.</span></span>  
  
4.  <span data-ttu-id="d1d8e-140">Proporcione la cadena de formato personalizado como un parámetro bien al método `ToString(String)` del número, bien a un método que admita el formato compuesto.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-140">Supply the custom format string as a parameter either to the number's `ToString(String)` method or to a method that supports composite formatting.</span></span>  
  
 <span data-ttu-id="d1d8e-141">En el ejemplo siguiente se rellenan dos valores <xref:System.Double> con cinco ceros a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="d1d8e-141">The following example pads two <xref:System.Double> values with five leading zeros.</span></span>  
  
 [!code-csharp[Formatting.HowTo.PadNumber#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#4)]
 [!code-vb[Formatting.HowTo.PadNumber#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="d1d8e-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1d8e-142">See also</span></span>

- [<span data-ttu-id="d1d8e-143">Custom Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="d1d8e-143">Custom Numeric Format Strings</span></span>](../../../docs/standard/base-types/custom-numeric-format-strings.md)
- [<span data-ttu-id="d1d8e-144">Standard Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="d1d8e-144">Standard Numeric Format Strings</span></span>](../../../docs/standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="d1d8e-145">Formatos compuestos</span><span class="sxs-lookup"><span data-stu-id="d1d8e-145">Composite Formatting</span></span>](../../../docs/standard/base-types/composite-formatting.md)

---
title: Tipo de datos SByte
ms.date: 04/20/2017
f1_keywords:
- vb.sbyte
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- SByte data type
ms.assetid: 5c38374a-18a1-4cc2-b493-299e3dcaa60f
ms.openlocfilehash: 01a0a4a261213d7e6e2016bf49128092e5b22308
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401386"
---
# <a name="sbyte-data-type-visual-basic"></a><span data-ttu-id="cd87e-102">Tipo de datos SByte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cd87e-102">SByte data type (Visual Basic)</span></span>

<span data-ttu-id="cd87e-103">Contiene enteros de 8 bits (1 byte) con signo que oscilan en valor de -128 a 127.</span><span class="sxs-lookup"><span data-stu-id="cd87e-103">Holds signed 8-bit (1-byte) integers that range in value from -128 through 127.</span></span>

## <a name="remarks"></a><span data-ttu-id="cd87e-104">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cd87e-104">Remarks</span></span>

<span data-ttu-id="cd87e-105">Utilice `SByte` el tipo de datos para contener valores enteros `Integer` que no requieren `Short`el ancho de datos completo o incluso el medio ancho de datos de .</span><span class="sxs-lookup"><span data-stu-id="cd87e-105">Use the `SByte` data type to contain integer values that do not require the full data width of `Integer` or even the half data width of `Short`.</span></span> <span data-ttu-id="cd87e-106">En algunos casos, Common Language Runtime podría `SByte` empaquetar las variables estrechamente juntas y ahorrar consumo de memoria.</span><span class="sxs-lookup"><span data-stu-id="cd87e-106">In some cases, the common language runtime might be able to pack your `SByte` variables closely together and save memory consumption.</span></span>

<span data-ttu-id="cd87e-107">El valor predeterminado de `SByte` es 0.</span><span class="sxs-lookup"><span data-stu-id="cd87e-107">The default value of `SByte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="cd87e-108">Asignaciones literales</span><span class="sxs-lookup"><span data-stu-id="cd87e-108">Literal assignments</span></span>

<span data-ttu-id="cd87e-109">Puede declarar e `SByte` inicializar una variable asignándole un literal decimal, un literal hexadecimal, un literal octal o (a partir de Visual Basic 2017) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="cd87e-109">You can declare and initialize an `SByte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span>

<span data-ttu-id="cd87e-110">En el ejemplo siguiente, los enteros iguales a -102 que se representan `SByte` como literales decimales, hexadecimales y binarios se asignan a los valores.</span><span class="sxs-lookup"><span data-stu-id="cd87e-110">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are assigned to `SByte` values.</span></span> <span data-ttu-id="cd87e-111">En este ejemplo es necesario `/removeintchecks` compilar con el modificador del compilador.</span><span class="sxs-lookup"><span data-stu-id="cd87e-111">This example requires that you compile with the `/removeintchecks` compiler switch.</span></span>

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]

> [!NOTE]
> <span data-ttu-id="cd87e-112">Utilice el `&h` prefijo `&H` o para denotar un `&b` `&B` literal hexadecimal, el prefijo o `&o` `&O` para denotar un literal binario, y el prefijo o para denotar un literal octal.</span><span class="sxs-lookup"><span data-stu-id="cd87e-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="cd87e-113">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="cd87e-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="cd87e-114">A partir de Visual Basic 2017, también `_`puede usar el carácter de subrayado, , como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="cd87e-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]

<span data-ttu-id="cd87e-115">A partir de Visual Basic 15.5, también`_`puede usar el carácter de subrayado ( ) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios u octales.</span><span class="sxs-lookup"><span data-stu-id="cd87e-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="cd87e-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cd87e-116">For example:</span></span>

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="cd87e-117">Si el literal entero está fuera del intervalo de `SByte` (es decir, si es inferior a <xref:System.SByte.MinValue?displayProperty=nameWithType> o mayor que <xref:System.SByte.MaxValue?displayProperty=nameWithType>, se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="cd87e-117">If the integer literal is outside the range of `SByte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=nameWithType> or greater than <xref:System.SByte.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span> <span data-ttu-id="cd87e-118">Cuando un literal entero no tiene sufijo, se deduce un [entero.](integer-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="cd87e-118">When an integer literal has no suffix, an [Integer](integer-data-type.md) is inferred.</span></span> <span data-ttu-id="cd87e-119">Si el literal entero está `Integer` fuera del intervalo del tipo, se deduce un [Long.](long-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="cd87e-119">If the integer literal is outside the range of the `Integer` type, a [Long](long-data-type.md) is inferred.</span></span> <span data-ttu-id="cd87e-120">Esto significa que, en los ejemplos `0x9A` anteriores, los literales numéricos y `0b10011010` se interpretan como enteros <xref:System.SByte.MaxValue?displayProperty=nameWithType>con signo de 32 bits con un valor de 156, que supera .</span><span class="sxs-lookup"><span data-stu-id="cd87e-120">This means that, in the previous examples, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="cd87e-121">Para compilar correctamente código como este que asigna un `SByte`entero no decimal a un , puede realizar una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="cd87e-121">To successfully compile code like this that assigns a non-decimal integer to an `SByte`, you can do either of the following:</span></span>

- <span data-ttu-id="cd87e-122">Deshabilite las comprobaciones de límites `/removeintchecks` enteros compilando con el modificador del compilador.</span><span class="sxs-lookup"><span data-stu-id="cd87e-122">Disable integer bounds checks by compiling with the `/removeintchecks` compiler switch.</span></span>

- <span data-ttu-id="cd87e-123">Utilice un [carácter](../../programming-guide/language-features/data-types/type-characters.md) de tipo para definir explícitamente `SByte`el valor literal que desea asignar al archivo .</span><span class="sxs-lookup"><span data-stu-id="cd87e-123">Use a [type character](../../programming-guide/language-features/data-types/type-characters.md) to explicitly define the literal value that you want to assign to the `SByte`.</span></span> <span data-ttu-id="cd87e-124">En el ejemplo siguiente `Short` se asigna `SByte`un valor literal negativo a un archivo .</span><span class="sxs-lookup"><span data-stu-id="cd87e-124">The following example assigns a negative literal `Short` value to an `SByte`.</span></span> <span data-ttu-id="cd87e-125">Tenga en cuenta que, para los números negativos, se debe establecer el bit de orden superior de la palabra de orden superior del literal numérico.</span><span class="sxs-lookup"><span data-stu-id="cd87e-125">Note that, for negative numbers, the high-order bit of the high-order word of the numeric literal must be set.</span></span> <span data-ttu-id="cd87e-126">En el caso de nuestro ejemplo, este `Short` es el bit 15 del valor literal.</span><span class="sxs-lookup"><span data-stu-id="cd87e-126">In the case of our example, this is bit 15 of the literal `Short` value.</span></span>

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a><span data-ttu-id="cd87e-127">sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="cd87e-127">Programming tips</span></span>

- <span data-ttu-id="cd87e-128">**Cumplimiento de CLS.**</span><span class="sxs-lookup"><span data-stu-id="cd87e-128">**CLS Compliance.**</span></span> <span data-ttu-id="cd87e-129">El `SByte` tipo de datos no forma parte de [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), por lo que el código compatible con CLS no puede consumir un componente que lo utilice.</span><span class="sxs-lookup"><span data-stu-id="cd87e-129">The `SByte` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="cd87e-130">**Ampliación.**</span><span class="sxs-lookup"><span data-stu-id="cd87e-130">**Widening.**</span></span> <span data-ttu-id="cd87e-131">El `SByte` tipo de datos `Short` `Integer`se `Long` `Decimal`amplía `Single`a `Double`, , , , y .</span><span class="sxs-lookup"><span data-stu-id="cd87e-131">The `SByte` data type widens to `Short`, `Integer`, `Long`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="cd87e-132">Esto significa que `SByte` puede convertir a cualquiera <xref:System.OverflowException?displayProperty=nameWithType> de estos tipos sin encontrar un error.</span><span class="sxs-lookup"><span data-stu-id="cd87e-132">This means you can convert `SByte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="cd87e-133">**Escriba Caracteres.**</span><span class="sxs-lookup"><span data-stu-id="cd87e-133">**Type Characters.**</span></span> <span data-ttu-id="cd87e-134">`SByte`no tiene ningún carácter de tipo literal o carácter de tipo identificador.</span><span class="sxs-lookup"><span data-stu-id="cd87e-134">`SByte` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="cd87e-135">**Tipo de Framework.**</span><span class="sxs-lookup"><span data-stu-id="cd87e-135">**Framework Type.**</span></span> <span data-ttu-id="cd87e-136">El tipo correspondiente en .NET Framework es la estructura <xref:System.SByte?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cd87e-136">The corresponding type in the .NET Framework is the <xref:System.SByte?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="cd87e-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cd87e-137">See also</span></span>

- <xref:System.SByte?displayProperty=nameWithType>
- [<span data-ttu-id="cd87e-138">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="cd87e-138">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="cd87e-139">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="cd87e-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="cd87e-140">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="cd87e-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="cd87e-141">Short (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="cd87e-141">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [<span data-ttu-id="cd87e-142">Tipo de datos enteros</span><span class="sxs-lookup"><span data-stu-id="cd87e-142">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="cd87e-143">Long (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="cd87e-143">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [<span data-ttu-id="cd87e-144">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="cd87e-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)

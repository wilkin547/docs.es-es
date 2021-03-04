---
description: 'Más información acerca de: tipo de datos SByte (Visual Basic)'
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
ms.openlocfilehash: a6a63ec742cf4a93080c9cc2f9906c5c6c21f0a8
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102102898"
---
# <a name="sbyte-data-type-visual-basic"></a><span data-ttu-id="12924-103">SByte (tipo de datos, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="12924-103">SByte data type (Visual Basic)</span></span>

<span data-ttu-id="12924-104">Contiene enteros de 8 bits con signo (1 byte) que oscilan entre-128 y 127.</span><span class="sxs-lookup"><span data-stu-id="12924-104">Holds signed 8-bit (1-byte) integers that range in value from -128 through 127.</span></span>

## <a name="remarks"></a><span data-ttu-id="12924-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="12924-105">Remarks</span></span>

<span data-ttu-id="12924-106">Utilice el `SByte` tipo de datos para contener valores enteros que no requieran el ancho completo de los datos `Integer` o incluso el ancho medio de los datos `Short` .</span><span class="sxs-lookup"><span data-stu-id="12924-106">Use the `SByte` data type to contain integer values that do not require the full data width of `Integer` or even the half data width of `Short`.</span></span> <span data-ttu-id="12924-107">En algunos casos, es posible que el Common Language Runtime pueda empaquetar las `SByte` variables en estrecha colaboración y ahorrar consumo de memoria.</span><span class="sxs-lookup"><span data-stu-id="12924-107">In some cases, the common language runtime might be able to pack your `SByte` variables closely together and save memory consumption.</span></span>

<span data-ttu-id="12924-108">El valor predeterminado de `SByte` es 0.</span><span class="sxs-lookup"><span data-stu-id="12924-108">The default value of `SByte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="12924-109">Asignaciones literales</span><span class="sxs-lookup"><span data-stu-id="12924-109">Literal assignments</span></span>

<span data-ttu-id="12924-110">Puede declarar e inicializar una `SByte` variable asignándole un literal decimal, un literal hexadecimal, un literal octal o (empezando por Visual Basic 2017) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="12924-110">You can declare and initialize an `SByte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span>

<span data-ttu-id="12924-111">En el ejemplo siguiente, los enteros iguales a-102 que se representan como literales binarios, hexadecimales y decimales se asignan a `SByte` valores.</span><span class="sxs-lookup"><span data-stu-id="12924-111">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are assigned to `SByte` values.</span></span> <span data-ttu-id="12924-112">Este ejemplo requiere que se compile con el `/removeintchecks` modificador del compilador.</span><span class="sxs-lookup"><span data-stu-id="12924-112">This example requires that you compile with the `/removeintchecks` compiler switch.</span></span>

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]

> [!NOTE]
> <span data-ttu-id="12924-113">Use el prefijo `&h` o `&H` para denotar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario, y el prefijo `&o` o `&O` para denotar un literal octal.</span><span class="sxs-lookup"><span data-stu-id="12924-113">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="12924-114">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="12924-114">Decimal literals have no prefix.</span></span>

<span data-ttu-id="12924-115">A partir de Visual Basic 2017, también puede usar el carácter de subrayado, `_` , como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="12924-115">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]

<span data-ttu-id="12924-116">A partir de Visual Basic 15,5, también puede usar el carácter de subrayado ( `_` ) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios o octales.</span><span class="sxs-lookup"><span data-stu-id="12924-116">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="12924-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="12924-117">For example:</span></span>

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="12924-118">Si el literal entero está fuera del intervalo de `SByte` (es decir, si es inferior a <xref:System.SByte.MinValue?displayProperty=nameWithType> o mayor que <xref:System.SByte.MaxValue?displayProperty=nameWithType>, se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="12924-118">If the integer literal is outside the range of `SByte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=nameWithType> or greater than <xref:System.SByte.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span> <span data-ttu-id="12924-119">Cuando un literal entero no tiene sufijo, se infiere un [entero](integer-data-type.md) .</span><span class="sxs-lookup"><span data-stu-id="12924-119">When an integer literal has no suffix, an [Integer](integer-data-type.md) is inferred.</span></span> <span data-ttu-id="12924-120">Si el literal entero está fuera del intervalo del `Integer` tipo, se deduce un [valor Long](long-data-type.md) .</span><span class="sxs-lookup"><span data-stu-id="12924-120">If the integer literal is outside the range of the `Integer` type, a [Long](long-data-type.md) is inferred.</span></span> <span data-ttu-id="12924-121">Esto significa que, en los ejemplos anteriores, los literales numéricos `0x9A` y `0b10011010` se interpretan como enteros con signo de 32 bits con un valor de 156, que supera <xref:System.SByte.MaxValue?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="12924-121">This means that, in the previous examples, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="12924-122">Para compilar correctamente código como este que asigna un entero no decimal a un `SByte` , puede realizar una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="12924-122">To successfully compile code like this that assigns a non-decimal integer to an `SByte`, you can do either of the following:</span></span>

- <span data-ttu-id="12924-123">Deshabilite las comprobaciones de los límites de enteros compilando con el `/removeintchecks` modificador del compilador.</span><span class="sxs-lookup"><span data-stu-id="12924-123">Disable integer bounds checks by compiling with the `/removeintchecks` compiler switch.</span></span>

- <span data-ttu-id="12924-124">Use un [carácter de tipo](../../programming-guide/language-features/data-types/type-characters.md) para definir explícitamente el valor literal que desea asignar a `SByte` .</span><span class="sxs-lookup"><span data-stu-id="12924-124">Use a [type character](../../programming-guide/language-features/data-types/type-characters.md) to explicitly define the literal value that you want to assign to the `SByte`.</span></span> <span data-ttu-id="12924-125">En el ejemplo siguiente se asigna un valor literal negativo `Short` a un `SByte` .</span><span class="sxs-lookup"><span data-stu-id="12924-125">The following example assigns a negative literal `Short` value to an `SByte`.</span></span> <span data-ttu-id="12924-126">Tenga en cuenta que, para los números negativos, debe establecerse el bit de orden superior de la palabra de orden superior del literal numérico.</span><span class="sxs-lookup"><span data-stu-id="12924-126">Note that, for negative numbers, the high-order bit of the high-order word of the numeric literal must be set.</span></span> <span data-ttu-id="12924-127">En el caso de nuestro ejemplo, es el bit 15 del valor literal `Short` .</span><span class="sxs-lookup"><span data-stu-id="12924-127">In the case of our example, this is bit 15 of the literal `Short` value.</span></span>

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a><span data-ttu-id="12924-128">sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="12924-128">Programming tips</span></span>

- <span data-ttu-id="12924-129">**Conformidad con CLS.**</span><span class="sxs-lookup"><span data-stu-id="12924-129">**CLS Compliance.**</span></span> <span data-ttu-id="12924-130">El `SByte` tipo de datos no forma parte de la [Common Language Specification](https://www.ecma-international.org/publications-and-standards/standards/ecma-335/) (CLS), por lo que el código conforme a CLS no puede consumir un componente que lo utiliza.</span><span class="sxs-lookup"><span data-stu-id="12924-130">The `SByte` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications-and-standards/standards/ecma-335/) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="12924-131">**Ampliación.**</span><span class="sxs-lookup"><span data-stu-id="12924-131">**Widening.**</span></span> <span data-ttu-id="12924-132">El `SByte` tipo de datos se amplía a `Short` , `Integer` , `Long` , `Decimal` , `Single` y `Double` .</span><span class="sxs-lookup"><span data-stu-id="12924-132">The `SByte` data type widens to `Short`, `Integer`, `Long`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="12924-133">Esto significa que puede convertir `SByte` en cualquiera de estos tipos sin que se produzca un <xref:System.OverflowException?displayProperty=nameWithType> error.</span><span class="sxs-lookup"><span data-stu-id="12924-133">This means you can convert `SByte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="12924-134">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="12924-134">**Type Characters.**</span></span> <span data-ttu-id="12924-135">`SByte` no tiene un carácter de tipo literal o un carácter de tipo de identificador.</span><span class="sxs-lookup"><span data-stu-id="12924-135">`SByte` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="12924-136">**Tipo de Framework.**</span><span class="sxs-lookup"><span data-stu-id="12924-136">**Framework Type.**</span></span> <span data-ttu-id="12924-137">El tipo correspondiente en .NET Framework es la estructura <xref:System.SByte?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="12924-137">The corresponding type in the .NET Framework is the <xref:System.SByte?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="12924-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="12924-138">See also</span></span>

- <xref:System.SByte?displayProperty=nameWithType>
- [<span data-ttu-id="12924-139">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="12924-139">Data Types</span></span>](index.md)
- [<span data-ttu-id="12924-140">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="12924-140">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="12924-141">Resumen de las conversiones</span><span class="sxs-lookup"><span data-stu-id="12924-141">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="12924-142">Tipo de datos Short</span><span class="sxs-lookup"><span data-stu-id="12924-142">Short Data Type</span></span>](short-data-type.md)
- [<span data-ttu-id="12924-143">Tipo de datos Integer</span><span class="sxs-lookup"><span data-stu-id="12924-143">Integer Data Type</span></span>](integer-data-type.md)
- [<span data-ttu-id="12924-144">Tipo de datos Long</span><span class="sxs-lookup"><span data-stu-id="12924-144">Long Data Type</span></span>](long-data-type.md)
- [<span data-ttu-id="12924-145">Uso eficiente de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="12924-145">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)

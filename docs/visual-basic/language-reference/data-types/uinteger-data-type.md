---
title: UInteger (Tipo de datos)
ms.date: 01/31/2018
f1_keywords:
- vb.uinteger
helpviewer_keywords:
- numbers [Visual Basic], whole
- UInteger data type
- literal type characters [Visual Basic], UI
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- UI literal type characters [Visual Basic]
- data types [Visual Basic], integral
ms.assetid: db7ddd34-4f23-46f5-84dd-8b0f83bb8729
ms.openlocfilehash: ccff61608aed797734cb4f5ca0571d7ed73ba98b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343899"
---
# <a name="uinteger-data-type"></a><span data-ttu-id="b0e55-102">UInteger (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="b0e55-102">UInteger data type</span></span>

<span data-ttu-id="b0e55-103">Contiene enteros de 32 bits sin signo (4 bytes) con un valor comprendido entre 0 y 4.294.967.295.</span><span class="sxs-lookup"><span data-stu-id="b0e55-103">Holds unsigned 32-bit (4-byte) integers ranging in value from 0 through 4,294,967,295.</span></span>

## <a name="remarks"></a><span data-ttu-id="b0e55-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b0e55-104">Remarks</span></span>

<span data-ttu-id="b0e55-105">El tipo de datos `UInteger` proporciona el valor sin signo más grande en el ancho de datos más eficaz.</span><span class="sxs-lookup"><span data-stu-id="b0e55-105">The `UInteger` data type provides the largest unsigned value in the most efficient data width.</span></span>

<span data-ttu-id="b0e55-106">El valor predeterminado de `UInteger` es 0.</span><span class="sxs-lookup"><span data-stu-id="b0e55-106">The default value of `UInteger` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="b0e55-107">Asignaciones literales</span><span class="sxs-lookup"><span data-stu-id="b0e55-107">Literal assignments</span></span>

<span data-ttu-id="b0e55-108">Puede declarar e inicializar una variable de `UInteger` asignándole un literal decimal, un literal hexadecimal, un literal octal o (empezando por Visual Basic 2017) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="b0e55-108">You can declare and initialize a `UInteger` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="b0e55-109">Si el literal entero está fuera del intervalo de `UInteger` (es decir, si es inferior a <xref:System.UInt32.MinValue?displayProperty=nameWithType> o mayor que <xref:System.UInt32.MaxValue?displayProperty=nameWithType>), se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="b0e55-109">If the integer literal is outside the range of `UInteger` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="b0e55-110">En el ejemplo siguiente, los enteros que equivalen a 3 000 000 000 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `UInteger`.</span><span class="sxs-lookup"><span data-stu-id="b0e55-110">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `UInteger` values.</span></span>

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]

> [!NOTE]
> <span data-ttu-id="b0e55-111">Use el prefijo `&h` o `&H` para indicar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario y el prefijo `&o` o `&O` para denotar un literal octal.</span><span class="sxs-lookup"><span data-stu-id="b0e55-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="b0e55-112">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="b0e55-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="b0e55-113">A partir de Visual Basic 2017, también puede usar el carácter de subrayado, `_`, como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b0e55-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]

<span data-ttu-id="b0e55-114">A partir de Visual Basic 15,5, también puede usar el carácter de subrayado (`_`) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios o octales.</span><span class="sxs-lookup"><span data-stu-id="b0e55-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="b0e55-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b0e55-115">For example:</span></span>

```vb
Dim number As UInteger = &H_0F8C_0326
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="b0e55-116">Los literales numéricos también pueden incluir el [carácter de tipo](../../programming-guide/language-features/data-types/type-characters.md) `UI` o `ui` para indicar el tipo de datos `UInteger`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b0e55-116">Numeric literals can also include the `UI` or `ui` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `UInteger` data type, as the following example shows.</span></span>

```vb
Dim number = &H_0FAC_14D7ui
```

## <a name="programming-tips"></a><span data-ttu-id="b0e55-117">sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="b0e55-117">Programming tips</span></span>

<span data-ttu-id="b0e55-118">Los tipos de datos `UInteger` y `Integer` proporcionan un rendimiento óptimo en un procesador de 32 bits, porque los tipos enteros más pequeños (`UShort`, `Short`, `Byte`y `SByte`), aunque usen menos bits, tardarán más tiempo en cargarse, almacenarse y recuperarse.</span><span class="sxs-lookup"><span data-stu-id="b0e55-118">The `UInteger` and `Integer` data types provide optimal performance on a 32-bit processor, because the smaller integer types (`UShort`, `Short`, `Byte`, and `SByte`), even though they use fewer bits, take more time to load, store, and fetch.</span></span>

- <span data-ttu-id="b0e55-119">**Números negativos.**</span><span class="sxs-lookup"><span data-stu-id="b0e55-119">**Negative Numbers.**</span></span> <span data-ttu-id="b0e55-120">Dado que `UInteger` es un tipo sin signo, no puede representar un número negativo.</span><span class="sxs-lookup"><span data-stu-id="b0e55-120">Because `UInteger` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="b0e55-121">Si usa el operador unario menos (`-`) en una expresión que se evalúa como tipo `UInteger`, Visual Basic convierte la expresión en `Long` primero.</span><span class="sxs-lookup"><span data-stu-id="b0e55-121">If you use the unary minus (`-`) operator on an expression that evaluates to type `UInteger`, Visual Basic converts the expression to `Long` first.</span></span>

- <span data-ttu-id="b0e55-122">**Conformidad con CLS.**</span><span class="sxs-lookup"><span data-stu-id="b0e55-122">**CLS Compliance.**</span></span> <span data-ttu-id="b0e55-123">El tipo de datos `UInteger` no forma parte de la [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), por lo que el código conforme a CLS no puede consumir un componente que lo utiliza.</span><span class="sxs-lookup"><span data-stu-id="b0e55-123">The `UInteger` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="b0e55-124">**Consideraciones de interoperabilidad.**</span><span class="sxs-lookup"><span data-stu-id="b0e55-124">**Interop Considerations.**</span></span> <span data-ttu-id="b0e55-125">Si interactúa con componentes que no se han escrito para el .NET Framework, por ejemplo, objetos de automatización o COM, tenga en cuenta que los tipos como `uint` pueden tener un ancho de datos diferente (16 bits) en otros entornos.</span><span class="sxs-lookup"><span data-stu-id="b0e55-125">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `uint` can have a different data width (16 bits) in other environments.</span></span> <span data-ttu-id="b0e55-126">Si va a pasar un argumento de 16 bits a este componente, declárelo como `UShort` en lugar de `UInteger` en el código Visual Basic administrado.</span><span class="sxs-lookup"><span data-stu-id="b0e55-126">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>

- <span data-ttu-id="b0e55-127">**Ampliación.**</span><span class="sxs-lookup"><span data-stu-id="b0e55-127">**Widening.**</span></span> <span data-ttu-id="b0e55-128">El tipo de datos `UInteger` se amplía a `Long`, `ULong`, `Decimal`, `Single`y `Double`.</span><span class="sxs-lookup"><span data-stu-id="b0e55-128">The `UInteger` data type widens to `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="b0e55-129">Esto significa que puede convertir `UInteger` en cualquiera de estos tipos sin encontrar un error de <xref:System.OverflowException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b0e55-129">This means you can convert `UInteger` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="b0e55-130">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="b0e55-130">**Type Characters.**</span></span> <span data-ttu-id="b0e55-131">Anexar los caracteres de tipo literal `UI` a un literal lo convierte al tipo de datos `UInteger`.</span><span class="sxs-lookup"><span data-stu-id="b0e55-131">Appending the literal type characters `UI` to a literal forces it to the `UInteger` data type.</span></span> <span data-ttu-id="b0e55-132">`UInteger` no tiene ningún carácter de tipo de identificador.</span><span class="sxs-lookup"><span data-stu-id="b0e55-132">`UInteger` has no identifier type character.</span></span>

- <span data-ttu-id="b0e55-133">**Tipo de marco.**</span><span class="sxs-lookup"><span data-stu-id="b0e55-133">**Framework Type.**</span></span> <span data-ttu-id="b0e55-134">El tipo correspondiente en .NET Framework es la estructura <xref:System.UInt32?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b0e55-134">The corresponding type in the .NET Framework is the <xref:System.UInt32?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0e55-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0e55-135">See also</span></span>

- <xref:System.UInt32>
- [<span data-ttu-id="b0e55-136">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="b0e55-136">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="b0e55-137">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="b0e55-137">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="b0e55-138">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="b0e55-138">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="b0e55-139">Llamar a una función de Windows que adopta tipos sin signo</span><span class="sxs-lookup"><span data-stu-id="b0e55-139">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="b0e55-140">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="b0e55-140">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)

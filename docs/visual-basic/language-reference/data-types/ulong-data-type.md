---
description: 'Más información sobre: tipo de datos ULong (Visual Basic)'
title: Tipo de datos ULong
ms.date: 01/31/2018
f1_keywords:
- vb.ulong
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- literal type characters [Visual Basic], UL
- ULong data type
- UL literal type characters [Visual Basic]
ms.assetid: 017e0702-774e-44ae-bedc-786b424ca84e
ms.openlocfilehash: 5e47fc49e8e0a6df4d1fcc70174a8519752fd3e1
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102104827"
---
# <a name="ulong-data-type-visual-basic"></a><span data-ttu-id="202cb-103">ULong (tipo de datos) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="202cb-103">ULong data type (Visual Basic)</span></span>

<span data-ttu-id="202cb-104">Contiene enteros de 64 bits (8 bytes) sin signo que van en el valor de 0 a 18446744073709551615 (más de 1,84 veces 10 ^ 19).</span><span class="sxs-lookup"><span data-stu-id="202cb-104">Holds unsigned 64-bit (8-byte) integers ranging in value from 0 through 18,446,744,073,709,551,615 (more than 1.84 times 10 ^ 19).</span></span>

## <a name="remarks"></a><span data-ttu-id="202cb-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="202cb-105">Remarks</span></span>

<span data-ttu-id="202cb-106">Utilice el `ULong` tipo de datos para contener datos binarios demasiado grandes para `UInteger` o los valores enteros sin signo más grandes posibles.</span><span class="sxs-lookup"><span data-stu-id="202cb-106">Use the `ULong` data type to contain binary data too large for `UInteger`, or the largest possible unsigned integer values.</span></span>

<span data-ttu-id="202cb-107">El valor predeterminado de `ULong` es 0.</span><span class="sxs-lookup"><span data-stu-id="202cb-107">The default value of `ULong` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="202cb-108">Asignaciones literales</span><span class="sxs-lookup"><span data-stu-id="202cb-108">Literal assignments</span></span>

<span data-ttu-id="202cb-109">Puede declarar e inicializar una `ULong` variable asignándole un literal decimal, un literal hexadecimal, un literal octal o (empezando por Visual Basic 2017) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="202cb-109">You can declare and initialize a `ULong` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="202cb-110">Si el literal entero está fuera del intervalo de `ULong` (es decir, si es inferior a <xref:System.UInt64.MinValue?displayProperty=nameWithType> o mayor que <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="202cb-110">If the integer literal is outside the range of `ULong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="202cb-111">En el ejemplo siguiente, los enteros que equivalen a 7 934 076 125 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `ULong`.</span><span class="sxs-lookup"><span data-stu-id="202cb-111">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ULong` values.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE]
> <span data-ttu-id="202cb-112">Use el prefijo `&h` o `&H` para denotar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario, y el prefijo `&o` o `&O` para denotar un literal octal.</span><span class="sxs-lookup"><span data-stu-id="202cb-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="202cb-113">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="202cb-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="202cb-114">A partir de Visual Basic 2017, también puede usar el carácter de subrayado, `_` , como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="202cb-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="202cb-115">A partir de Visual Basic 15,5, también puede usar el carácter de subrayado ( `_` ) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios o octales.</span><span class="sxs-lookup"><span data-stu-id="202cb-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="202cb-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="202cb-116">For example:</span></span>

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="202cb-117">Los literales numéricos también pueden incluir el `UL` `ul` [carácter de tipo](../../programming-guide/language-features/data-types/type-characters.md) o para denotar el `ULong` tipo de datos, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="202cb-117">Numeric literals can also include the `UL` or `ul` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `ULong` data type, as the following example shows.</span></span>

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a><span data-ttu-id="202cb-118">sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="202cb-118">Programming tips</span></span>

- <span data-ttu-id="202cb-119">**Números negativos.**</span><span class="sxs-lookup"><span data-stu-id="202cb-119">**Negative Numbers.**</span></span> <span data-ttu-id="202cb-120">Dado `ULong` que es un tipo sin signo, no puede representar un número negativo.</span><span class="sxs-lookup"><span data-stu-id="202cb-120">Because `ULong` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="202cb-121">Si usa el operador unario menos ( `-` ) en una expresión que se evalúa como tipo `ULong` , Visual Basic convierte primero la expresión en `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="202cb-121">If you use the unary minus (`-`) operator on an expression that evaluates to type `ULong`, Visual Basic converts the expression to `Decimal` first.</span></span>

- <span data-ttu-id="202cb-122">**Conformidad con CLS.**</span><span class="sxs-lookup"><span data-stu-id="202cb-122">**CLS Compliance.**</span></span> <span data-ttu-id="202cb-123">El `ULong` tipo de datos no forma parte de la [Common Language Specification](https://www.ecma-international.org/publications-and-standards/standards/ecma-335/) (CLS), por lo que el código conforme a CLS no puede consumir un componente que lo utiliza.</span><span class="sxs-lookup"><span data-stu-id="202cb-123">The `ULong` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications-and-standards/standards/ecma-335/) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="202cb-124">**Consideraciones de interoperabilidad.**</span><span class="sxs-lookup"><span data-stu-id="202cb-124">**Interop Considerations.**</span></span> <span data-ttu-id="202cb-125">Si interactúa con componentes que no se han escrito para el .NET Framework, por ejemplo, objetos de automatización o COM, tenga en cuenta que los tipos como `ulong` pueden tener un ancho de datos diferente (32 bits) en otros entornos.</span><span class="sxs-lookup"><span data-stu-id="202cb-125">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `ulong` can have a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="202cb-126">Si va a pasar un argumento de 32 bits a este componente, declárelo como `UInteger` en lugar de `ULong` en el código de Visual Basic administrado.</span><span class="sxs-lookup"><span data-stu-id="202cb-126">If you are passing a 32-bit argument to such a component, declare it as `UInteger` instead of `ULong` in your managed Visual Basic code.</span></span>

  <span data-ttu-id="202cb-127">Además, Automation no admite enteros de 64 bits en Windows 95, Windows 98, Windows ME o Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="202cb-127">Furthermore, Automation does not support 64-bit integers on Windows 95, Windows 98, Windows ME, or Windows 2000.</span></span> <span data-ttu-id="202cb-128">No se puede pasar un `ULong` argumento Visual Basic a un componente de automatización en estas plataformas.</span><span class="sxs-lookup"><span data-stu-id="202cb-128">You cannot pass a Visual Basic `ULong` argument to an Automation component on these platforms.</span></span>

- <span data-ttu-id="202cb-129">**Ampliación.**</span><span class="sxs-lookup"><span data-stu-id="202cb-129">**Widening.**</span></span> <span data-ttu-id="202cb-130">El `ULong` tipo de datos se amplía a `Decimal` , `Single` y `Double` .</span><span class="sxs-lookup"><span data-stu-id="202cb-130">The `ULong` data type widens to `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="202cb-131">Esto significa que puede convertir `ULong` en cualquiera de estos tipos sin que se produzca un <xref:System.OverflowException?displayProperty=nameWithType> error.</span><span class="sxs-lookup"><span data-stu-id="202cb-131">This means you can convert `ULong` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="202cb-132">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="202cb-132">**Type Characters.**</span></span> <span data-ttu-id="202cb-133">Anexar los caracteres de tipo literal `UL` a un literal lo convierte al `ULong` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="202cb-133">Appending the literal type characters `UL` to a literal forces it to the `ULong` data type.</span></span> <span data-ttu-id="202cb-134">`ULong` no tiene ningún carácter de tipo de identificador.</span><span class="sxs-lookup"><span data-stu-id="202cb-134">`ULong` has no identifier type character.</span></span>

- <span data-ttu-id="202cb-135">**Tipo de Framework.**</span><span class="sxs-lookup"><span data-stu-id="202cb-135">**Framework Type.**</span></span> <span data-ttu-id="202cb-136">El tipo correspondiente en .NET Framework es la estructura <xref:System.UInt64?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="202cb-136">The corresponding type in the .NET Framework is the <xref:System.UInt64?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="202cb-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="202cb-137">See also</span></span>

- <xref:System.UInt64>
- [<span data-ttu-id="202cb-138">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="202cb-138">Data Types</span></span>](index.md)
- [<span data-ttu-id="202cb-139">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="202cb-139">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="202cb-140">Resumen de las conversiones</span><span class="sxs-lookup"><span data-stu-id="202cb-140">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="202cb-141">Procedimiento Llamada una función de Windows que adopta tipos sin signo</span><span class="sxs-lookup"><span data-stu-id="202cb-141">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="202cb-142">Uso eficiente de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="202cb-142">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)

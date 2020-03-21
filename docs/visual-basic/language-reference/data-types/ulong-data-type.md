---
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
ms.openlocfilehash: 3c6cd4086e08b808c158948756b4806f098196b9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401320"
---
# <a name="ulong-data-type-visual-basic"></a><span data-ttu-id="17bc4-102">Tipo de datos ULong (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="17bc4-102">ULong data type (Visual Basic)</span></span>

<span data-ttu-id="17bc4-103">Contiene enteros de 64 bits sin signo (8 bytes) que varían en valor de 0 a 18,446,744,073,709,551,615 (más de 1,84 veces 10 x 19).</span><span class="sxs-lookup"><span data-stu-id="17bc4-103">Holds unsigned 64-bit (8-byte) integers ranging in value from 0 through 18,446,744,073,709,551,615 (more than 1.84 times 10 ^ 19).</span></span>

## <a name="remarks"></a><span data-ttu-id="17bc4-104">Observaciones</span><span class="sxs-lookup"><span data-stu-id="17bc4-104">Remarks</span></span>

<span data-ttu-id="17bc4-105">Utilice `ULong` el tipo de datos para `UInteger`contener datos binarios demasiado grandes para , o los valores enteros sin signo más grandes posibles.</span><span class="sxs-lookup"><span data-stu-id="17bc4-105">Use the `ULong` data type to contain binary data too large for `UInteger`, or the largest possible unsigned integer values.</span></span>

<span data-ttu-id="17bc4-106">El valor predeterminado de `ULong` es 0.</span><span class="sxs-lookup"><span data-stu-id="17bc4-106">The default value of `ULong` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="17bc4-107">Asignaciones literales</span><span class="sxs-lookup"><span data-stu-id="17bc4-107">Literal assignments</span></span>

<span data-ttu-id="17bc4-108">Puede declarar e `ULong` inicializar una variable asignándole un literal decimal, un literal hexadecimal, un literal octal o (a partir de Visual Basic 2017) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="17bc4-108">You can declare and initialize a `ULong` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="17bc4-109">Si el literal entero está fuera del intervalo de `ULong` (es decir, si es inferior a <xref:System.UInt64.MinValue?displayProperty=nameWithType> o mayor que <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="17bc4-109">If the integer literal is outside the range of `ULong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="17bc4-110">En el ejemplo siguiente, los enteros que equivalen a 7 934 076 125 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `ULong`.</span><span class="sxs-lookup"><span data-stu-id="17bc4-110">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ULong` values.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE]
> <span data-ttu-id="17bc4-111">Utilice el `&h` prefijo `&H` o para denotar un `&b` `&B` literal hexadecimal, el prefijo o `&o` `&O` para denotar un literal binario, y el prefijo o para denotar un literal octal.</span><span class="sxs-lookup"><span data-stu-id="17bc4-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="17bc4-112">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="17bc4-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="17bc4-113">A partir de Visual Basic 2017, también `_`puede usar el carácter de subrayado, , como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="17bc4-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="17bc4-114">A partir de Visual Basic 15.5, también`_`puede usar el carácter de subrayado ( ) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios u octales.</span><span class="sxs-lookup"><span data-stu-id="17bc4-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="17bc4-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="17bc4-115">For example:</span></span>

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="17bc4-116">Los literales numéricos `UL` `ul` también pueden incluir `ULong` el [carácter](../../programming-guide/language-features/data-types/type-characters.md) o tipo para denotar el tipo de datos, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="17bc4-116">Numeric literals can also include the `UL` or `ul` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `ULong` data type, as the following example shows.</span></span>

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a><span data-ttu-id="17bc4-117">sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="17bc4-117">Programming tips</span></span>

- <span data-ttu-id="17bc4-118">**Números negativos.**</span><span class="sxs-lookup"><span data-stu-id="17bc4-118">**Negative Numbers.**</span></span> <span data-ttu-id="17bc4-119">Dado `ULong` que es un tipo sin signo, no puede representar un número negativo.</span><span class="sxs-lookup"><span data-stu-id="17bc4-119">Because `ULong` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="17bc4-120">Si utiliza el operador`-`unario menos ( ) en `ULong`una expresión que se `Decimal` evalúa como tipo , Visual Basic convierte la expresión en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="17bc4-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `ULong`, Visual Basic converts the expression to `Decimal` first.</span></span>

- <span data-ttu-id="17bc4-121">**Cumplimiento de CLS.**</span><span class="sxs-lookup"><span data-stu-id="17bc4-121">**CLS Compliance.**</span></span> <span data-ttu-id="17bc4-122">El `ULong` tipo de datos no forma parte de [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), por lo que el código compatible con CLS no puede consumir un componente que lo utilice.</span><span class="sxs-lookup"><span data-stu-id="17bc4-122">The `ULong` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="17bc4-123">**Consideraciones de interoperabilidad.**</span><span class="sxs-lookup"><span data-stu-id="17bc4-123">**Interop Considerations.**</span></span> <span data-ttu-id="17bc4-124">Si está interactuando con componentes no escritos para .NET Framework, por ejemplo, objetos de automatización o COM, tenga en cuenta que tipos como `ulong` pueden tener un ancho de datos diferente (32 bits) en otros entornos.</span><span class="sxs-lookup"><span data-stu-id="17bc4-124">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `ulong` can have a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="17bc4-125">Si va a pasar un argumento de 32 bits `UInteger` a `ULong` un componente de este tipo, declárelo como en lugar de en el código administrado de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="17bc4-125">If you are passing a 32-bit argument to such a component, declare it as `UInteger` instead of `ULong` in your managed Visual Basic code.</span></span>

  <span data-ttu-id="17bc4-126">Además, Automation no admite enteros de 64 bits en Windows 95, Windows 98, Windows ME o Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="17bc4-126">Furthermore, Automation does not support 64-bit integers on Windows 95, Windows 98, Windows ME, or Windows 2000.</span></span> <span data-ttu-id="17bc4-127">No se puede `ULong` pasar un argumento de Visual Basic a un componente de automatización en estas plataformas.</span><span class="sxs-lookup"><span data-stu-id="17bc4-127">You cannot pass a Visual Basic `ULong` argument to an Automation component on these platforms.</span></span>

- <span data-ttu-id="17bc4-128">**Ampliación.**</span><span class="sxs-lookup"><span data-stu-id="17bc4-128">**Widening.**</span></span> <span data-ttu-id="17bc4-129">El `ULong` tipo de datos `Decimal` `Single`se `Double`amplía a , , y .</span><span class="sxs-lookup"><span data-stu-id="17bc4-129">The `ULong` data type widens to `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="17bc4-130">Esto significa que `ULong` puede convertir a cualquiera <xref:System.OverflowException?displayProperty=nameWithType> de estos tipos sin encontrar un error.</span><span class="sxs-lookup"><span data-stu-id="17bc4-130">This means you can convert `ULong` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="17bc4-131">**Escriba Caracteres.**</span><span class="sxs-lookup"><span data-stu-id="17bc4-131">**Type Characters.**</span></span> <span data-ttu-id="17bc4-132">Anexar los caracteres `UL` de tipo literal `ULong` a un literal lo fuerza al tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="17bc4-132">Appending the literal type characters `UL` to a literal forces it to the `ULong` data type.</span></span> <span data-ttu-id="17bc4-133">`ULong`no tiene ningún carácter de tipo identificador.</span><span class="sxs-lookup"><span data-stu-id="17bc4-133">`ULong` has no identifier type character.</span></span>

- <span data-ttu-id="17bc4-134">**Tipo de Framework.**</span><span class="sxs-lookup"><span data-stu-id="17bc4-134">**Framework Type.**</span></span> <span data-ttu-id="17bc4-135">El tipo correspondiente en .NET Framework es la estructura <xref:System.UInt64?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="17bc4-135">The corresponding type in the .NET Framework is the <xref:System.UInt64?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="17bc4-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="17bc4-136">See also</span></span>

- <xref:System.UInt64>
- [<span data-ttu-id="17bc4-137">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="17bc4-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="17bc4-138">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="17bc4-138">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="17bc4-139">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="17bc4-139">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="17bc4-140">Llamar a una función de Windows que adopta tipos sin signo</span><span class="sxs-lookup"><span data-stu-id="17bc4-140">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="17bc4-141">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="17bc4-141">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)

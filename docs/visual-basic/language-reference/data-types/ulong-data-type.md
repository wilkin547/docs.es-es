---
title: ULong (Tipo de datos, Visual Basic)
ms.date: 01/31/2018
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 606e0ef87b209bb2e75e28223f27d081713c1b7e
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2018
---
# <a name="ulong-data-type-visual-basic"></a><span data-ttu-id="a88e5-102">Tipo de datos ULong (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a88e5-102">ULong data type (Visual Basic)</span></span>

<span data-ttu-id="a88e5-103">Contiene enteros de (8 bytes) de 64 bits sin signo que van de un valor de 0 a 18.446.744.073.709.551.615 (más de 1,84 veces 10 ^ 19).</span><span class="sxs-lookup"><span data-stu-id="a88e5-103">Holds unsigned 64-bit (8-byte) integers ranging in value from 0 through 18,446,744,073,709,551,615 (more than 1.84 times 10 ^ 19).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a88e5-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a88e5-104">Remarks</span></span>

<span data-ttu-id="a88e5-105">Use la `ULong` tipo de datos para contener datos binarios demasiado grandes para `UInteger`, o valores enteros sin signo de mayor tamaño posible.</span><span class="sxs-lookup"><span data-stu-id="a88e5-105">Use the `ULong` data type to contain binary data too large for `UInteger`, or the largest possible unsigned integer values.</span></span>  
  
<span data-ttu-id="a88e5-106">El valor predeterminado de `ULong` es 0.</span><span class="sxs-lookup"><span data-stu-id="a88e5-106">The default value of `ULong` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="a88e5-107">Asignaciones de literales</span><span class="sxs-lookup"><span data-stu-id="a88e5-107">Literal assignments</span></span>

<span data-ttu-id="a88e5-108">Puede declarar e inicializar un `ULong` variable asignarle un decimal literal, un literal hexadecimal, un literal octal, o (a partir de Visual Basic de 2017) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="a88e5-108">You can declare and initialize a `ULong` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="a88e5-109">Si el literal entero está fuera del intervalo de `ULong` (es decir, si es inferior a <xref:System.UInt64.MinValue?displayProperty=nameWithType> o mayor que <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="a88e5-109">If the integer literal is outside the range of `ULong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="a88e5-110">En el ejemplo siguiente, los enteros que equivalen a 7 934 076 125 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `ULong`.</span><span class="sxs-lookup"><span data-stu-id="a88e5-110">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ULong` values.</span></span>
  
[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE] 
> <span data-ttu-id="a88e5-111">Use el prefijo `&h` o `&H` para denotar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario y el prefijo `&o` o `&O` para denotar un literal octal.</span><span class="sxs-lookup"><span data-stu-id="a88e5-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="a88e5-112">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="a88e5-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="a88e5-113">A partir de Visual Basic de 2017, también puede utilizar el carácter de subrayado, `_`, como un separador de dígitos para mejorar la legibilidad, como en el ejemplo siguiente se muestra.</span><span class="sxs-lookup"><span data-stu-id="a88e5-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="a88e5-114">A partir de Visual Basic 15,5, también puede utilizar el carácter de subrayado (`_`) como separador inicial entre el prefijo y los dígitos hexadecimales, octales o binarios.</span><span class="sxs-lookup"><span data-stu-id="a88e5-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="a88e5-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a88e5-115">For example:</span></span>

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="a88e5-116">También pueden incluir literales numéricos el `UL` o `ul` [escriba carácter](../../programming-guide\language-features\data-types/type-characters.md) para denotar el `ULong` tipo de datos, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a88e5-116">Numeric literals can also include the `UL` or `ul` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `ULong` data type, as the following example shows.</span></span>

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a><span data-ttu-id="a88e5-117">Sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="a88e5-117">Programming tips</span></span>
  
-   <span data-ttu-id="a88e5-118">**Números negativos.**</span><span class="sxs-lookup"><span data-stu-id="a88e5-118">**Negative Numbers.**</span></span> <span data-ttu-id="a88e5-119">Dado que `ULong` es un tipo sin signo, no puede representar un número negativo.</span><span class="sxs-lookup"><span data-stu-id="a88e5-119">Because `ULong` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="a88e5-120">Si se utiliza el operador unario menos (`-`) operador en una expresión que se evalúa como tipo `ULong`, Visual Basic convierte la expresión `Decimal` primero.</span><span class="sxs-lookup"><span data-stu-id="a88e5-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `ULong`, Visual Basic converts the expression to `Decimal` first.</span></span>  
  
-   <span data-ttu-id="a88e5-121">**Conformidad con CLS.**</span><span class="sxs-lookup"><span data-stu-id="a88e5-121">**CLS Compliance.**</span></span> <span data-ttu-id="a88e5-122">El `ULong` tipo de datos no es parte de la [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), por lo que el código conforme a CLS no puede utilizar un componente que lo utiliza.</span><span class="sxs-lookup"><span data-stu-id="a88e5-122">The `ULong` data type is not part of the [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>  
  
-   <span data-ttu-id="a88e5-123">**Consideraciones de interoperabilidad.**</span><span class="sxs-lookup"><span data-stu-id="a88e5-123">**Interop Considerations.**</span></span> <span data-ttu-id="a88e5-124">Si interactúa con componentes no se han escrito para .NET Framework, por ejemplo objetos de automatización o COM, tenga en cuenta que los tipos como `ulong` puede tener un ancho de datos diferente (32 bits) en otros entornos.</span><span class="sxs-lookup"><span data-stu-id="a88e5-124">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `ulong` can have a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="a88e5-125">Al pasar un argumento de 32 bits a esos componentes, declárelo como `UInteger` en lugar de `ULong` en el código administrado de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a88e5-125">If you are passing a 32-bit argument to such a component, declare it as `UInteger` instead of `ULong` in your managed Visual Basic code.</span></span>  
  
     <span data-ttu-id="a88e5-126">Además, la automatización no admite enteros de 64 bits en Windows 95, Windows 98, Windows Millennium Edition o Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="a88e5-126">Furthermore, Automation does not support 64-bit integers on Windows 95, Windows 98, Windows ME, or Windows 2000.</span></span> <span data-ttu-id="a88e5-127">No se puede pasar un de Visual Basic `ULong` argumento pasado a un componente de automatización en estas plataformas.</span><span class="sxs-lookup"><span data-stu-id="a88e5-127">You cannot pass a Visual Basic `ULong` argument to an Automation component on these platforms.</span></span>  
  
-   <span data-ttu-id="a88e5-128">**De ampliación.**</span><span class="sxs-lookup"><span data-stu-id="a88e5-128">**Widening.**</span></span> <span data-ttu-id="a88e5-129">El `ULong` tipo de datos se amplía a `Decimal`, `Single`, y `Double`.</span><span class="sxs-lookup"><span data-stu-id="a88e5-129">The `ULong` data type widens to `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="a88e5-130">Esto significa que se puede convertir `ULong` a cualquiera de estos tipos sin que se produzca una <xref:System.OverflowException?displayProperty=nameWithType> error.</span><span class="sxs-lookup"><span data-stu-id="a88e5-130">This means you can convert `ULong` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="a88e5-131">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="a88e5-131">**Type Characters.**</span></span> <span data-ttu-id="a88e5-132">Anexar los caracteres de tipo literal `UL` a un literal, se convierte a la `ULong` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="a88e5-132">Appending the literal type characters `UL` to a literal forces it to the `ULong` data type.</span></span> <span data-ttu-id="a88e5-133">`ULong`no tiene ningún carácter de tipo identificador.</span><span class="sxs-lookup"><span data-stu-id="a88e5-133">`ULong` has no identifier type character.</span></span>
  
-   <span data-ttu-id="a88e5-134">**Tipo de Framework.**</span><span class="sxs-lookup"><span data-stu-id="a88e5-134">**Framework Type.**</span></span> <span data-ttu-id="a88e5-135">El tipo correspondiente en .NET Framework es la estructura <xref:System.UInt64?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a88e5-135">The corresponding type in the .NET Framework is the <xref:System.UInt64?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a88e5-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="a88e5-136">See also</span></span>

 <xref:System.UInt64>  
 [<span data-ttu-id="a88e5-137">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="a88e5-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="a88e5-138">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="a88e5-138">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="a88e5-139">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="a88e5-139">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="a88e5-140">Llamar a una función de Windows que adopta tipos sin signo</span><span class="sxs-lookup"><span data-stu-id="a88e5-140">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="a88e5-141">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="a88e5-141">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)

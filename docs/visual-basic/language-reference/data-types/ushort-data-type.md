---
description: 'Más información sobre: tipo de datos UShort (Visual Basic)'
title: Tipo de datos UShort
ms.date: 01/31/2018
f1_keywords:
- vb.ushort
helpviewer_keywords:
- numbers [Visual Basic], whole
- literal type characters [Visual Basic], US
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- UShort data type
- US literal type characters [Visual Basic]
ms.assetid: 138db892-665d-4ba8-9cae-d8d91c4a8f39
ms.openlocfilehash: 43c18bad3e24e14c28d2ca3d5d88170d584e55a8
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102106649"
---
# <a name="ushort-data-type-visual-basic"></a><span data-ttu-id="ed5eb-103">Tipo de datos UShort (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed5eb-103">UShort data type (Visual Basic)</span></span>

<span data-ttu-id="ed5eb-104">Contiene enteros de 16 bits sin signo (2 bytes) con un valor comprendido entre 0 y 65.535.</span><span class="sxs-lookup"><span data-stu-id="ed5eb-104">Holds unsigned 16-bit (2-byte) integers ranging in value from 0 through 65,535.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed5eb-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ed5eb-105">Remarks</span></span>

 <span data-ttu-id="ed5eb-106">Utilice el `UShort` tipo de datos para contener datos binarios demasiado grandes para `Byte` .</span><span class="sxs-lookup"><span data-stu-id="ed5eb-106">Use the `UShort` data type to contain binary data too large for `Byte`.</span></span>  
  
 <span data-ttu-id="ed5eb-107">El valor predeterminado de `UShort` es 0.</span><span class="sxs-lookup"><span data-stu-id="ed5eb-107">The default value of `UShort` is 0.</span></span>  

## <a name="literal-assignments"></a><span data-ttu-id="ed5eb-108">Asignaciones literales</span><span class="sxs-lookup"><span data-stu-id="ed5eb-108">Literal assignments</span></span>

<span data-ttu-id="ed5eb-109">Puede declarar e inicializar una `UShort` variable asignándole un literal decimal, un literal hexadecimal, un literal octal o (empezando por Visual Basic 2017) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="ed5eb-109">You can declare and initialize a `UShort` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="ed5eb-110">Si el literal entero está fuera del intervalo de `UShort` (es decir, si es inferior a <xref:System.UInt16.MinValue?displayProperty=nameWithType> o mayor que <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="ed5eb-110">If the integer literal is outside the range of `UShort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="ed5eb-111">En el ejemplo siguiente, los enteros que equivalen a 65.034 que se representan como literales binarios, hexadecimales y decimales se asignan a `UShort` valores.</span><span class="sxs-lookup"><span data-stu-id="ed5eb-111">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are assigned to `UShort` values.</span></span>
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> <span data-ttu-id="ed5eb-112">Use el prefijo `&h` o `&H` para denotar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario, y el prefijo `&o` o `&O` para denotar un literal octal.</span><span class="sxs-lookup"><span data-stu-id="ed5eb-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="ed5eb-113">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="ed5eb-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="ed5eb-114">A partir de Visual Basic 2017, también puede usar el carácter de subrayado, `_` , como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ed5eb-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

<span data-ttu-id="ed5eb-115">A partir de Visual Basic 15,5, también puede usar el carácter de subrayado ( `_` ) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios o octales.</span><span class="sxs-lookup"><span data-stu-id="ed5eb-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="ed5eb-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ed5eb-116">For example:</span></span>

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="ed5eb-117">Los literales numéricos también pueden incluir el `US` `us` [carácter de tipo](../../programming-guide/language-features/data-types/type-characters.md) o para denotar el `UShort` tipo de datos, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ed5eb-117">Numeric literals can also include the `US` or `us` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `UShort` data type, as the following example shows.</span></span>

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a><span data-ttu-id="ed5eb-118">sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="ed5eb-118">Programming tips</span></span>
  
- <span data-ttu-id="ed5eb-119">**Números negativos.**</span><span class="sxs-lookup"><span data-stu-id="ed5eb-119">**Negative Numbers.**</span></span> <span data-ttu-id="ed5eb-120">Dado `UShort` que es un tipo sin signo, no puede representar un número negativo.</span><span class="sxs-lookup"><span data-stu-id="ed5eb-120">Because `UShort` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="ed5eb-121">Si usa el operador unario menos ( `-` ) en una expresión que se evalúa como tipo `UShort` , Visual Basic convierte primero la expresión en `Integer` .</span><span class="sxs-lookup"><span data-stu-id="ed5eb-121">If you use the unary minus (`-`) operator on an expression that evaluates to type `UShort`, Visual Basic converts the expression to `Integer` first.</span></span>  
  
- <span data-ttu-id="ed5eb-122">**Conformidad con CLS.**</span><span class="sxs-lookup"><span data-stu-id="ed5eb-122">**CLS Compliance.**</span></span> <span data-ttu-id="ed5eb-123">El `UShort` tipo de datos no forma parte de la [Common Language Specification](https://www.ecma-international.org/publications-and-standards/standards/ecma-335/) (CLS), por lo que el código conforme a CLS no puede consumir un componente que lo utiliza.</span><span class="sxs-lookup"><span data-stu-id="ed5eb-123">The `UShort` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications-and-standards/standards/ecma-335/) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
- <span data-ttu-id="ed5eb-124">**Ampliación.**</span><span class="sxs-lookup"><span data-stu-id="ed5eb-124">**Widening.**</span></span> <span data-ttu-id="ed5eb-125">El `UShort` tipo de datos se amplía a `Integer` , `UInteger` , `Long` ,,, `ULong` `Decimal` `Single` y `Double` .</span><span class="sxs-lookup"><span data-stu-id="ed5eb-125">The `UShort` data type widens to `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="ed5eb-126">Esto significa que puede convertir `UShort` en cualquiera de estos tipos sin que se produzca un <xref:System.OverflowException?displayProperty=nameWithType> error.</span><span class="sxs-lookup"><span data-stu-id="ed5eb-126">This means you can convert `UShort` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="ed5eb-127">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="ed5eb-127">**Type Characters.**</span></span> <span data-ttu-id="ed5eb-128">Anexar los caracteres de tipo literal `US` a un literal lo convierte al `UShort` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="ed5eb-128">Appending the literal type characters `US` to a literal forces it to the `UShort` data type.</span></span> <span data-ttu-id="ed5eb-129">`UShort` no tiene ningún carácter de tipo de identificador.</span><span class="sxs-lookup"><span data-stu-id="ed5eb-129">`UShort` has no identifier type character.</span></span>  
  
- <span data-ttu-id="ed5eb-130">**Tipo de Framework.**</span><span class="sxs-lookup"><span data-stu-id="ed5eb-130">**Framework Type.**</span></span> <span data-ttu-id="ed5eb-131">El tipo correspondiente en .NET Framework es la estructura <xref:System.UInt16?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ed5eb-131">The corresponding type in the .NET Framework is the <xref:System.UInt16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed5eb-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ed5eb-132">See also</span></span>

- <xref:System.UInt16>
- [<span data-ttu-id="ed5eb-133">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ed5eb-133">Data Types</span></span>](index.md)
- [<span data-ttu-id="ed5eb-134">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="ed5eb-134">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="ed5eb-135">Resumen de las conversiones</span><span class="sxs-lookup"><span data-stu-id="ed5eb-135">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="ed5eb-136">Procedimiento Llamada una función de Windows que adopta tipos sin signo</span><span class="sxs-lookup"><span data-stu-id="ed5eb-136">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="ed5eb-137">Uso eficiente de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="ed5eb-137">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)

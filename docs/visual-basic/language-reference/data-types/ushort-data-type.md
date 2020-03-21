---
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
ms.openlocfilehash: 7cdbd5fb192fd5cc1be6260dcdcdb1f30cf3f865
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401314"
---
# <a name="ushort-data-type-visual-basic"></a><span data-ttu-id="0b65a-102">Tipo de datos UShort (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b65a-102">UShort data type (Visual Basic)</span></span>

<span data-ttu-id="0b65a-103">Contiene enteros de 16 bits sin signo (2 bytes) que varían en valor de 0 a 65.535.</span><span class="sxs-lookup"><span data-stu-id="0b65a-103">Holds unsigned 16-bit (2-byte) integers ranging in value from 0 through 65,535.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b65a-104">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0b65a-104">Remarks</span></span>

 <span data-ttu-id="0b65a-105">Utilice `UShort` el tipo de datos para `Byte`contener datos binarios demasiado grandes para .</span><span class="sxs-lookup"><span data-stu-id="0b65a-105">Use the `UShort` data type to contain binary data too large for `Byte`.</span></span>  
  
 <span data-ttu-id="0b65a-106">El valor predeterminado de `UShort` es 0.</span><span class="sxs-lookup"><span data-stu-id="0b65a-106">The default value of `UShort` is 0.</span></span>  

## <a name="literal-assignments"></a><span data-ttu-id="0b65a-107">Asignaciones literales</span><span class="sxs-lookup"><span data-stu-id="0b65a-107">Literal assignments</span></span>

<span data-ttu-id="0b65a-108">Puede declarar e `UShort` inicializar una variable asignándole un literal decimal, un literal hexadecimal, un literal octal o (a partir de Visual Basic 2017) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="0b65a-108">You can declare and initialize a `UShort` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="0b65a-109">Si el literal entero está fuera del intervalo de `UShort` (es decir, si es inferior a <xref:System.UInt16.MinValue?displayProperty=nameWithType> o mayor que <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="0b65a-109">If the integer literal is outside the range of `UShort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="0b65a-110">En el ejemplo siguiente, los enteros iguales a 65.034 que se representan `UShort` como literales decimales, hexadecimales y binarios se asignan a los valores.</span><span class="sxs-lookup"><span data-stu-id="0b65a-110">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are assigned to `UShort` values.</span></span>
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> <span data-ttu-id="0b65a-111">Utilice el `&h` prefijo `&H` o para denotar un `&b` `&B` literal hexadecimal, el prefijo o `&o` `&O` para denotar un literal binario, y el prefijo o para denotar un literal octal.</span><span class="sxs-lookup"><span data-stu-id="0b65a-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="0b65a-112">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="0b65a-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="0b65a-113">A partir de Visual Basic 2017, también `_`puede usar el carácter de subrayado, , como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="0b65a-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

<span data-ttu-id="0b65a-114">A partir de Visual Basic 15.5, también`_`puede usar el carácter de subrayado ( ) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios u octales.</span><span class="sxs-lookup"><span data-stu-id="0b65a-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="0b65a-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0b65a-115">For example:</span></span>

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="0b65a-116">Los literales numéricos `US` `us` también pueden incluir `UShort` el [carácter](../../programming-guide/language-features/data-types/type-characters.md) o tipo para denotar el tipo de datos, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="0b65a-116">Numeric literals can also include the `US` or `us` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `UShort` data type, as the following example shows.</span></span>

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a><span data-ttu-id="0b65a-117">sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="0b65a-117">Programming tips</span></span>
  
- <span data-ttu-id="0b65a-118">**Números negativos.**</span><span class="sxs-lookup"><span data-stu-id="0b65a-118">**Negative Numbers.**</span></span> <span data-ttu-id="0b65a-119">Dado `UShort` que es un tipo sin signo, no puede representar un número negativo.</span><span class="sxs-lookup"><span data-stu-id="0b65a-119">Because `UShort` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="0b65a-120">Si utiliza el operador`-`unario menos ( ) en `UShort`una expresión que se `Integer` evalúa como tipo , Visual Basic convierte la expresión en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="0b65a-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `UShort`, Visual Basic converts the expression to `Integer` first.</span></span>  
  
- <span data-ttu-id="0b65a-121">**Cumplimiento de CLS.**</span><span class="sxs-lookup"><span data-stu-id="0b65a-121">**CLS Compliance.**</span></span> <span data-ttu-id="0b65a-122">El `UShort` tipo de datos no forma parte de [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), por lo que el código compatible con CLS no puede consumir un componente que lo utilice.</span><span class="sxs-lookup"><span data-stu-id="0b65a-122">The `UShort` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
- <span data-ttu-id="0b65a-123">**Ampliación.**</span><span class="sxs-lookup"><span data-stu-id="0b65a-123">**Widening.**</span></span> <span data-ttu-id="0b65a-124">El `UShort` tipo de datos `Integer` `UInteger`se `Long` `ULong`amplía `Decimal` `Single`a `Double`, , , , , y .</span><span class="sxs-lookup"><span data-stu-id="0b65a-124">The `UShort` data type widens to `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="0b65a-125">Esto significa que `UShort` puede convertir a cualquiera <xref:System.OverflowException?displayProperty=nameWithType> de estos tipos sin encontrar un error.</span><span class="sxs-lookup"><span data-stu-id="0b65a-125">This means you can convert `UShort` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="0b65a-126">**Escriba Caracteres.**</span><span class="sxs-lookup"><span data-stu-id="0b65a-126">**Type Characters.**</span></span> <span data-ttu-id="0b65a-127">Anexar los caracteres `US` de tipo literal `UShort` a un literal lo fuerza al tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="0b65a-127">Appending the literal type characters `US` to a literal forces it to the `UShort` data type.</span></span> <span data-ttu-id="0b65a-128">`UShort`no tiene ningún carácter de tipo identificador.</span><span class="sxs-lookup"><span data-stu-id="0b65a-128">`UShort` has no identifier type character.</span></span>  
  
- <span data-ttu-id="0b65a-129">**Tipo de Framework.**</span><span class="sxs-lookup"><span data-stu-id="0b65a-129">**Framework Type.**</span></span> <span data-ttu-id="0b65a-130">El tipo correspondiente en .NET Framework es la estructura <xref:System.UInt16?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0b65a-130">The corresponding type in the .NET Framework is the <xref:System.UInt16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b65a-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0b65a-131">See also</span></span>

- <xref:System.UInt16>
- [<span data-ttu-id="0b65a-132">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="0b65a-132">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="0b65a-133">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="0b65a-133">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="0b65a-134">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="0b65a-134">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="0b65a-135">Llamar a una función de Windows que adopta tipos sin signo</span><span class="sxs-lookup"><span data-stu-id="0b65a-135">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="0b65a-136">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="0b65a-136">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)

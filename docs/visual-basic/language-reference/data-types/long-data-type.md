---
title: Tipo de datos Long
ms.date: 01/31/2018
f1_keywords:
- vb.Long
helpviewer_keywords:
- identifier type characters [Visual Basic], &
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- '& identifier type character'
- integer numbers
- literal type characters [Visual Basic], L
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- L literal type character [Visual Basic]
- integers [Visual Basic], types
- Long keyword [Visual Basic]
- data types [Visual Basic], integral
- data types [Visual Basic], assigning
- Long data type
ms.assetid: b4770c34-1804-4f8c-b512-c10b0893e516
ms.openlocfilehash: 16d7409c802e97b1f33474d810134db4d9f0ad6c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401404"
---
# <a name="long-data-type-visual-basic"></a><span data-ttu-id="83f22-102">Tipo de datos long (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83f22-102">Long data type (Visual Basic)</span></span>

<span data-ttu-id="83f22-103">Contiene enteros de 64 bits (8 bytes) firmados que van en valor de -9,223,372,036,854,775,808 a 9,223,372,036,854,775,807 (9.2...E+18).</span><span class="sxs-lookup"><span data-stu-id="83f22-103">Holds signed 64-bit (8-byte) integers ranging in value from -9,223,372,036,854,775,808 through 9,223,372,036,854,775,807 (9.2...E+18).</span></span>

## <a name="remarks"></a><span data-ttu-id="83f22-104">Observaciones</span><span class="sxs-lookup"><span data-stu-id="83f22-104">Remarks</span></span>

<span data-ttu-id="83f22-105">Utilice `Long` el tipo de datos para contener números `Integer` enteros que son demasiado grandes para caber en el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="83f22-105">Use the `Long` data type to contain integer numbers that are too large to fit in the `Integer` data type.</span></span>

<span data-ttu-id="83f22-106">El valor predeterminado de `Long` es 0.</span><span class="sxs-lookup"><span data-stu-id="83f22-106">The default value of `Long` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="83f22-107">Asignaciones literales</span><span class="sxs-lookup"><span data-stu-id="83f22-107">Literal assignments</span></span>

<span data-ttu-id="83f22-108">Puede declarar e `Long` inicializar una variable asignándole un literal decimal, un literal hexadecimal, un literal octal o (a partir de Visual Basic 2017) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="83f22-108">You can declare and initialize a `Long` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="83f22-109">Si el literal entero está fuera del intervalo de `Long` (es decir, si es inferior a <xref:System.Int64.MinValue?displayProperty=nameWithType> o mayor que <xref:System.Int64.MaxValue?displayProperty=nameWithType>, se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="83f22-109">If the integer literal is outside the range of `Long` (that is, if it is less than <xref:System.Int64.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="83f22-110">En el ejemplo siguiente, los enteros que equivalen a 4 294 967 296 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `Long`.</span><span class="sxs-lookup"><span data-stu-id="83f22-110">In the following example, integers equal to 4,294,967,296 that are represented as decimal, hexadecimal, and binary literals are assigned to `Long` values.</span></span>

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]

> [!NOTE]
> <span data-ttu-id="83f22-111">Utilice el `&h` prefijo `&H` o para denotar un `&b` `&B` literal hexadecimal, el prefijo o `&o` `&O` para denotar un literal binario, y el prefijo o para denotar un literal octal.</span><span class="sxs-lookup"><span data-stu-id="83f22-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="83f22-112">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="83f22-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="83f22-113">A partir de Visual Basic 2017, también `_`puede usar el carácter de subrayado, , como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="83f22-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="83f22-114">A partir de Visual Basic 15.5, también`_`puede usar el carácter de subrayado ( ) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios u octales.</span><span class="sxs-lookup"><span data-stu-id="83f22-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="83f22-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="83f22-115">For example:</span></span>

```vb
Dim number As Long = &H_0FAC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="83f22-116">Los literales numéricos `L` también pueden incluir `Long` el [carácter de tipo](../../programming-guide/language-features/data-types/type-characters.md) para denotar el tipo de datos, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="83f22-116">Numeric literals can also include the `L` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Long` data type, as the following example shows.</span></span>

```vb
Dim number = &H_0FAC_0326_1489_D68CL
```

## <a name="programming-tips"></a><span data-ttu-id="83f22-117">sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="83f22-117">Programming tips</span></span>

- <span data-ttu-id="83f22-118">**Consideraciones de interoperabilidad.**</span><span class="sxs-lookup"><span data-stu-id="83f22-118">**Interop Considerations.**</span></span> <span data-ttu-id="83f22-119">Si está interactuando con componentes no escritos para .NET Framework, por ejemplo, objetos de automatización o COM, recuerde que `Long` tiene un ancho de datos diferente (32 bits) en otros entornos.</span><span class="sxs-lookup"><span data-stu-id="83f22-119">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that `Long` has a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="83f22-120">Si va a pasar un argumento de 32 bits `Integer` a `Long` un componente de este tipo, declárelo como en lugar de en el nuevo código de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="83f22-120">If you are passing a 32-bit argument to such a component, declare it as `Integer` instead of `Long` in your new Visual Basic code.</span></span>

- <span data-ttu-id="83f22-121">**Ampliación.**</span><span class="sxs-lookup"><span data-stu-id="83f22-121">**Widening.**</span></span> <span data-ttu-id="83f22-122">El `Long` tipo de datos `Decimal` `Single`se `Double`amplía a , , o .</span><span class="sxs-lookup"><span data-stu-id="83f22-122">The `Long` data type widens to `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="83f22-123">Esto significa que puede convertir un tipo de datos `Long` en cualquiera de estos tipos sin que se produzca un error <xref:System.OverflowException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="83f22-123">This means you can convert `Long` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="83f22-124">**Escriba Caracteres.**</span><span class="sxs-lookup"><span data-stu-id="83f22-124">**Type Characters.**</span></span> <span data-ttu-id="83f22-125">Al agregar el carácter de tipo literal `L` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Long`.</span><span class="sxs-lookup"><span data-stu-id="83f22-125">Appending the literal type character `L` to a literal forces it to the `Long` data type.</span></span> <span data-ttu-id="83f22-126">Si se agrega el carácter de tipo identificador `&` a cualquier identificador, se convierte forzosamente al tipo `Long`.</span><span class="sxs-lookup"><span data-stu-id="83f22-126">Appending the identifier type character `&` to any identifier forces it to `Long`.</span></span>

- <span data-ttu-id="83f22-127">**Tipo de Framework.**</span><span class="sxs-lookup"><span data-stu-id="83f22-127">**Framework Type.**</span></span> <span data-ttu-id="83f22-128">El tipo correspondiente en .NET Framework es la estructura <xref:System.Int64?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="83f22-128">The corresponding type in the .NET Framework is the <xref:System.Int64?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="83f22-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="83f22-129">See also</span></span>

- <xref:System.Int64>
- [<span data-ttu-id="83f22-130">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="83f22-130">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="83f22-131">Tipo de datos enteros</span><span class="sxs-lookup"><span data-stu-id="83f22-131">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="83f22-132">Short (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="83f22-132">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [<span data-ttu-id="83f22-133">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="83f22-133">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="83f22-134">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="83f22-134">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="83f22-135">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="83f22-135">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)

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
ms.openlocfilehash: 7c076cd2198c85560f7c63c69e051697966c9524
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415601"
---
# <a name="long-data-type-visual-basic"></a><span data-ttu-id="44340-102">Long (tipo de datos) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="44340-102">Long data type (Visual Basic)</span></span>

<span data-ttu-id="44340-103">Contiene enteros de 64 bits (8 bytes) con signo comprendido entre-9.223.372.036.854.775.808 y 9.223.372.036.854.775.807 (9.2... E + 18).</span><span class="sxs-lookup"><span data-stu-id="44340-103">Holds signed 64-bit (8-byte) integers ranging in value from -9,223,372,036,854,775,808 through 9,223,372,036,854,775,807 (9.2...E+18).</span></span>

## <a name="remarks"></a><span data-ttu-id="44340-104">Observaciones</span><span class="sxs-lookup"><span data-stu-id="44340-104">Remarks</span></span>

<span data-ttu-id="44340-105">Utilice el `Long` tipo de datos para incluir números enteros demasiado grandes como para caber en el `Integer` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="44340-105">Use the `Long` data type to contain integer numbers that are too large to fit in the `Integer` data type.</span></span>

<span data-ttu-id="44340-106">El valor predeterminado de `Long` es 0.</span><span class="sxs-lookup"><span data-stu-id="44340-106">The default value of `Long` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="44340-107">Asignaciones literales</span><span class="sxs-lookup"><span data-stu-id="44340-107">Literal assignments</span></span>

<span data-ttu-id="44340-108">Puede declarar e inicializar una `Long` variable asignándole un literal decimal, un literal hexadecimal, un literal octal o (empezando por Visual Basic 2017) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="44340-108">You can declare and initialize a `Long` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="44340-109">Si el literal entero está fuera del intervalo de `Long` (es decir, si es inferior a <xref:System.Int64.MinValue?displayProperty=nameWithType> o mayor que <xref:System.Int64.MaxValue?displayProperty=nameWithType>, se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="44340-109">If the integer literal is outside the range of `Long` (that is, if it is less than <xref:System.Int64.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="44340-110">En el ejemplo siguiente, los enteros que equivalen a 4 294 967 296 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `Long`.</span><span class="sxs-lookup"><span data-stu-id="44340-110">In the following example, integers equal to 4,294,967,296 that are represented as decimal, hexadecimal, and binary literals are assigned to `Long` values.</span></span>

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]

> [!NOTE]
> <span data-ttu-id="44340-111">Use el prefijo `&h` o `&H` para denotar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario, y el prefijo `&o` o `&O` para denotar un literal octal.</span><span class="sxs-lookup"><span data-stu-id="44340-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="44340-112">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="44340-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="44340-113">A partir de Visual Basic 2017, también puede usar el carácter de subrayado, `_` , como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="44340-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="44340-114">A partir de Visual Basic 15,5, también puede usar el carácter de subrayado ( `_` ) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios o octales.</span><span class="sxs-lookup"><span data-stu-id="44340-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="44340-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="44340-115">For example:</span></span>

```vb
Dim number As Long = &H_0FAC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="44340-116">Los literales numéricos también pueden incluir el `L` [carácter de tipo](../../programming-guide/language-features/data-types/type-characters.md) para denotar el `Long` tipo de datos, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="44340-116">Numeric literals can also include the `L` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Long` data type, as the following example shows.</span></span>

```vb
Dim number = &H_0FAC_0326_1489_D68CL
```

## <a name="programming-tips"></a><span data-ttu-id="44340-117">sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="44340-117">Programming tips</span></span>

- <span data-ttu-id="44340-118">**Consideraciones de interoperabilidad.**</span><span class="sxs-lookup"><span data-stu-id="44340-118">**Interop Considerations.**</span></span> <span data-ttu-id="44340-119">Si interactúa con componentes que no se han escrito para el .NET Framework, por ejemplo, objetos de automatización o COM, recuerde que `Long` tiene un ancho de datos diferente (32 bits) en otros entornos.</span><span class="sxs-lookup"><span data-stu-id="44340-119">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that `Long` has a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="44340-120">Si va a pasar un argumento de 32 bits a este componente, declárelo como `Integer` en lugar de `Long` en el nuevo código de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="44340-120">If you are passing a 32-bit argument to such a component, declare it as `Integer` instead of `Long` in your new Visual Basic code.</span></span>

- <span data-ttu-id="44340-121">**Ampliación.**</span><span class="sxs-lookup"><span data-stu-id="44340-121">**Widening.**</span></span> <span data-ttu-id="44340-122">El `Long` tipo de datos se amplía a `Decimal` , `Single` o `Double` .</span><span class="sxs-lookup"><span data-stu-id="44340-122">The `Long` data type widens to `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="44340-123">Esto significa que puede convertir un tipo de datos `Long` en cualquiera de estos tipos sin que se produzca un error <xref:System.OverflowException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="44340-123">This means you can convert `Long` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="44340-124">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="44340-124">**Type Characters.**</span></span> <span data-ttu-id="44340-125">Al agregar el carácter de tipo literal `L` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Long`.</span><span class="sxs-lookup"><span data-stu-id="44340-125">Appending the literal type character `L` to a literal forces it to the `Long` data type.</span></span> <span data-ttu-id="44340-126">Si se agrega el carácter de tipo identificador `&` a cualquier identificador, se convierte forzosamente al tipo `Long`.</span><span class="sxs-lookup"><span data-stu-id="44340-126">Appending the identifier type character `&` to any identifier forces it to `Long`.</span></span>

- <span data-ttu-id="44340-127">**Tipo de Framework.**</span><span class="sxs-lookup"><span data-stu-id="44340-127">**Framework Type.**</span></span> <span data-ttu-id="44340-128">El tipo correspondiente en .NET Framework es la estructura <xref:System.Int64?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="44340-128">The corresponding type in the .NET Framework is the <xref:System.Int64?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="44340-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="44340-129">See also</span></span>

- <xref:System.Int64>
- [<span data-ttu-id="44340-130">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="44340-130">Data Types</span></span>](index.md)
- [<span data-ttu-id="44340-131">Tipo de datos Integer</span><span class="sxs-lookup"><span data-stu-id="44340-131">Integer Data Type</span></span>](integer-data-type.md)
- [<span data-ttu-id="44340-132">Tipo de datos Short</span><span class="sxs-lookup"><span data-stu-id="44340-132">Short Data Type</span></span>](short-data-type.md)
- [<span data-ttu-id="44340-133">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="44340-133">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="44340-134">Resumen de las conversiones</span><span class="sxs-lookup"><span data-stu-id="44340-134">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="44340-135">Uso eficiente de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="44340-135">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)

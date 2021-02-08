---
description: 'Más información acerca de: tipo de datos Short (Visual Basic)'
title: Tipo de datos Short
ms.date: 01/31/2018
f1_keywords:
- vb.Short
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- S literal type character [Visual Basic]
- Short data type
- literal type characters [Visual Basic], S
ms.assetid: 65fcbcf3-a841-400e-885e-301497729a8b
ms.openlocfilehash: 8c6bee45355548b3a32d74d059159918b4009fbb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792146"
---
# <a name="short-data-type-visual-basic"></a><span data-ttu-id="a678e-103">Short (tipo de datos) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a678e-103">Short data type (Visual Basic)</span></span>

<span data-ttu-id="a678e-104">Contiene enteros de 16 bits con signo (2 bytes) que se encuentran entre-32.768 y 32.767.</span><span class="sxs-lookup"><span data-stu-id="a678e-104">Holds signed 16-bit (2-byte) integers that range in value from -32,768 through 32,767.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a678e-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a678e-105">Remarks</span></span>  

 <span data-ttu-id="a678e-106">Utilice el `Short` tipo de datos para contener valores enteros que no requieran el ancho completo de los datos de `Integer` .</span><span class="sxs-lookup"><span data-stu-id="a678e-106">Use the `Short` data type to contain integer values that do not require the full data width of `Integer`.</span></span> <span data-ttu-id="a678e-107">En algunos casos, el Common Language Runtime puede empaquetar las `Short` variables en estrecha colaboración y ahorrar consumo de memoria.</span><span class="sxs-lookup"><span data-stu-id="a678e-107">In some cases, the common language runtime can pack your `Short` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="a678e-108">El valor predeterminado de `Short` es 0.</span><span class="sxs-lookup"><span data-stu-id="a678e-108">The default value of `Short` is 0.</span></span>  
  
## <a name="literal-assignments"></a><span data-ttu-id="a678e-109">Asignaciones literales</span><span class="sxs-lookup"><span data-stu-id="a678e-109">Literal assignments</span></span>

<span data-ttu-id="a678e-110">Puede declarar e inicializar una `Short` variable asignándole un literal decimal, un literal hexadecimal, un literal octal o (empezando por Visual Basic 2017) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="a678e-110">You can declare and initialize a `Short` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="a678e-111">Si el literal entero está fuera del intervalo de `Short` (es decir, si es inferior a <xref:System.Int16.MinValue?displayProperty=nameWithType> o mayor que <xref:System.Int16.MaxValue?displayProperty=nameWithType>, se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="a678e-111">If the integer literal is outside the range of `Short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="a678e-112">En el ejemplo siguiente, los enteros que equivalen a 1.034 que se representan como literales binarios, hexadecimales y decimales se convierten implícitamente de [enteros](integer-data-type.md) a `Short` valores.</span><span class="sxs-lookup"><span data-stu-id="a678e-112">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `Short` values.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> <span data-ttu-id="a678e-113">Use el prefijo `&h` o `&H` para denotar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario, y el prefijo `&o` o `&O` para denotar un literal octal.</span><span class="sxs-lookup"><span data-stu-id="a678e-113">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="a678e-114">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="a678e-114">Decimal literals have no prefix.</span></span>

<span data-ttu-id="a678e-115">A partir de Visual Basic 2017, también puede usar el carácter de subrayado, `_` , como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a678e-115">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

<span data-ttu-id="a678e-116">A partir de Visual Basic 15,5, también puede usar el carácter de subrayado ( `_` ) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios o octales.</span><span class="sxs-lookup"><span data-stu-id="a678e-116">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="a678e-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a678e-117">For example:</span></span>

```vb
Dim number As Short = &H_3264
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="a678e-118">Los literales numéricos también pueden incluir el `S` [carácter de tipo](../../programming-guide/language-features/data-types/type-characters.md) para denotar el `Short` tipo de datos, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a678e-118">Numeric literals can also include the `S` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Short` data type, as the following example shows.</span></span>

```vb
Dim number = &H_3264S
```

## <a name="programming-tips"></a><span data-ttu-id="a678e-119">sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="a678e-119">Programming tips</span></span>

- <span data-ttu-id="a678e-120">**Ampliación.**</span><span class="sxs-lookup"><span data-stu-id="a678e-120">**Widening.**</span></span> <span data-ttu-id="a678e-121">El `Short` tipo de datos se amplía a `Integer` , `Long` , `Decimal` , `Single` o `Double` .</span><span class="sxs-lookup"><span data-stu-id="a678e-121">The `Short` data type widens to `Integer`, `Long`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="a678e-122">Esto significa que puede convertir un tipo de datos `Short` en cualquiera de estos tipos sin que se produzca un error <xref:System.OverflowException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a678e-122">This means you can convert `Short` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="a678e-123">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="a678e-123">**Type Characters.**</span></span> <span data-ttu-id="a678e-124">Al agregar el carácter de tipo literal `S` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Short`.</span><span class="sxs-lookup"><span data-stu-id="a678e-124">Appending the literal type character `S` to a literal forces it to the `Short` data type.</span></span> <span data-ttu-id="a678e-125">`Short` no tiene ningún carácter de tipo de identificador.</span><span class="sxs-lookup"><span data-stu-id="a678e-125">`Short` has no identifier type character.</span></span>  
  
- <span data-ttu-id="a678e-126">**Tipo de Framework.**</span><span class="sxs-lookup"><span data-stu-id="a678e-126">**Framework Type.**</span></span> <span data-ttu-id="a678e-127">El tipo correspondiente en .NET Framework es la estructura <xref:System.Int16?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a678e-127">The corresponding type in the .NET Framework is the <xref:System.Int16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a678e-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="a678e-128">See also</span></span>

- <xref:System.Int16?displayProperty=nameWithType>
- [<span data-ttu-id="a678e-129">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="a678e-129">Data Types</span></span>](index.md)
- [<span data-ttu-id="a678e-130">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="a678e-130">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="a678e-131">Resumen de las conversiones</span><span class="sxs-lookup"><span data-stu-id="a678e-131">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="a678e-132">Tipo de datos Integer</span><span class="sxs-lookup"><span data-stu-id="a678e-132">Integer Data Type</span></span>](integer-data-type.md)
- [<span data-ttu-id="a678e-133">Tipo de datos Long</span><span class="sxs-lookup"><span data-stu-id="a678e-133">Long Data Type</span></span>](long-data-type.md)
- [<span data-ttu-id="a678e-134">Uso eficiente de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="a678e-134">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)

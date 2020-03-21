---
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
ms.openlocfilehash: 8dfdfb56de32e4b3a96729b09ccf46a6fee9a424
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401344"
---
# <a name="short-data-type-visual-basic"></a><span data-ttu-id="c0f23-102">Tipo de datos corto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c0f23-102">Short data type (Visual Basic)</span></span>

<span data-ttu-id="c0f23-103">Contiene enteros de 16 bits (2 bytes) con signo que oscilan en valor de -32.768 a 32.767.</span><span class="sxs-lookup"><span data-stu-id="c0f23-103">Holds signed 16-bit (2-byte) integers that range in value from -32,768 through 32,767.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0f23-104">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c0f23-104">Remarks</span></span>  

 <span data-ttu-id="c0f23-105">Utilice `Short` el tipo de datos para contener valores enteros `Integer`que no requieren el ancho de datos completo de .</span><span class="sxs-lookup"><span data-stu-id="c0f23-105">Use the `Short` data type to contain integer values that do not require the full data width of `Integer`.</span></span> <span data-ttu-id="c0f23-106">En algunos casos, Common Language `Short` Runtime puede empaquetar las variables estrechamente juntas y ahorrar consumo de memoria.</span><span class="sxs-lookup"><span data-stu-id="c0f23-106">In some cases, the common language runtime can pack your `Short` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="c0f23-107">El valor predeterminado de `Short` es 0.</span><span class="sxs-lookup"><span data-stu-id="c0f23-107">The default value of `Short` is 0.</span></span>  
  
## <a name="literal-assignments"></a><span data-ttu-id="c0f23-108">Asignaciones literales</span><span class="sxs-lookup"><span data-stu-id="c0f23-108">Literal assignments</span></span>

<span data-ttu-id="c0f23-109">Puede declarar e `Short` inicializar una variable asignándole un literal decimal, un literal hexadecimal, un literal octal o (a partir de Visual Basic 2017) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="c0f23-109">You can declare and initialize a `Short` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="c0f23-110">Si el literal entero está fuera del intervalo de `Short` (es decir, si es inferior a <xref:System.Int16.MinValue?displayProperty=nameWithType> o mayor que <xref:System.Int16.MaxValue?displayProperty=nameWithType>, se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="c0f23-110">If the integer literal is outside the range of `Short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="c0f23-111">En el ejemplo siguiente, los enteros iguales a 1.034 que se representan como [Integer](integer-data-type.md) literales `Short` decimales, hexadecimales y binarios se convierten implícitamente de Entero a valores.</span><span class="sxs-lookup"><span data-stu-id="c0f23-111">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `Short` values.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> <span data-ttu-id="c0f23-112">Utilice el `&h` prefijo `&H` o para denotar un `&b` `&B` literal hexadecimal, el prefijo o `&o` `&O` para denotar un literal binario, y el prefijo o para denotar un literal octal.</span><span class="sxs-lookup"><span data-stu-id="c0f23-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="c0f23-113">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="c0f23-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="c0f23-114">A partir de Visual Basic 2017, también `_`puede usar el carácter de subrayado, , como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c0f23-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

<span data-ttu-id="c0f23-115">A partir de Visual Basic 15.5, también`_`puede usar el carácter de subrayado ( ) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios u octales.</span><span class="sxs-lookup"><span data-stu-id="c0f23-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="c0f23-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c0f23-116">For example:</span></span>

```vb
Dim number As Short = &H_3264
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="c0f23-117">Los literales numéricos `S` también pueden incluir `Short` el [carácter de tipo](../../programming-guide/language-features/data-types/type-characters.md) para denotar el tipo de datos, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c0f23-117">Numeric literals can also include the `S` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Short` data type, as the following example shows.</span></span>

```vb
Dim number = &H_3264S
```

## <a name="programming-tips"></a><span data-ttu-id="c0f23-118">sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="c0f23-118">Programming tips</span></span>

- <span data-ttu-id="c0f23-119">**Ampliación.**</span><span class="sxs-lookup"><span data-stu-id="c0f23-119">**Widening.**</span></span> <span data-ttu-id="c0f23-120">El `Short` tipo de datos `Integer` `Long`se `Decimal` `Single`amplía `Double`a , , , o .</span><span class="sxs-lookup"><span data-stu-id="c0f23-120">The `Short` data type widens to `Integer`, `Long`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="c0f23-121">Esto significa que puede convertir un tipo de datos `Short` en cualquiera de estos tipos sin que se produzca un error <xref:System.OverflowException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c0f23-121">This means you can convert `Short` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="c0f23-122">**Escriba Caracteres.**</span><span class="sxs-lookup"><span data-stu-id="c0f23-122">**Type Characters.**</span></span> <span data-ttu-id="c0f23-123">Al agregar el carácter de tipo literal `S` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Short`.</span><span class="sxs-lookup"><span data-stu-id="c0f23-123">Appending the literal type character `S` to a literal forces it to the `Short` data type.</span></span> <span data-ttu-id="c0f23-124">`Short`no tiene ningún carácter de tipo identificador.</span><span class="sxs-lookup"><span data-stu-id="c0f23-124">`Short` has no identifier type character.</span></span>  
  
- <span data-ttu-id="c0f23-125">**Tipo de Framework.**</span><span class="sxs-lookup"><span data-stu-id="c0f23-125">**Framework Type.**</span></span> <span data-ttu-id="c0f23-126">El tipo correspondiente en .NET Framework es la estructura <xref:System.Int16?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c0f23-126">The corresponding type in the .NET Framework is the <xref:System.Int16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0f23-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c0f23-127">See also</span></span>

- <xref:System.Int16?displayProperty=nameWithType>
- [<span data-ttu-id="c0f23-128">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="c0f23-128">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="c0f23-129">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="c0f23-129">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="c0f23-130">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="c0f23-130">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="c0f23-131">Tipo de datos enteros</span><span class="sxs-lookup"><span data-stu-id="c0f23-131">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="c0f23-132">Long (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="c0f23-132">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [<span data-ttu-id="c0f23-133">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="c0f23-133">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)

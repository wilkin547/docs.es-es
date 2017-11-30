---
title: SByte (Tipo de datos, Visual Basic)
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.sbyte
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- SByte data type
ms.assetid: 5c38374a-18a1-4cc2-b493-299e3dcaa60f
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2bcd00665ec5b8651089811a61212bfa302fe95d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="sbyte-data-type-visual-basic"></a><span data-ttu-id="0e3d5-102">Tipo de datos SByte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e3d5-102">SByte data type (Visual Basic)</span></span>

<span data-ttu-id="0e3d5-103">Contiene enteros con signo 8 bits (1-bytes que van de un valor de -128 a 127).</span><span class="sxs-lookup"><span data-stu-id="0e3d5-103">Holds signed 8-bit (1-byte) integers that range in value from -128 through 127.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e3d5-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0e3d5-104">Remarks</span></span>

<span data-ttu-id="0e3d5-105">Use la `SByte` tipo de datos para contener valores enteros que no requieren el ancho completo de datos de `Integer` o incluso el ancho de la mitad de los datos de `Short`.</span><span class="sxs-lookup"><span data-stu-id="0e3d5-105">Use the `SByte` data type to contain integer values that do not require the full data width of `Integer` or even the half data width of `Short`.</span></span> <span data-ttu-id="0e3d5-106">En algunos casos, common language runtime puede empaquetar su `SByte` variables estrecha colaboración y ahorre consumo de memoria.</span><span class="sxs-lookup"><span data-stu-id="0e3d5-106">In some cases, the common language runtime might be able to pack your `SByte` variables closely together and save memory consumption.</span></span>

<span data-ttu-id="0e3d5-107">El valor predeterminado de `SByte` es 0.</span><span class="sxs-lookup"><span data-stu-id="0e3d5-107">The default value of `SByte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="0e3d5-108">Asignaciones de literales</span><span class="sxs-lookup"><span data-stu-id="0e3d5-108">Literal assignments</span></span>
  
<span data-ttu-id="0e3d5-109">Puede declarar e inicializar un `SByte` variable asignarle un decimal literal, un literal hexadecimal, un literal octal, o (a partir de Visual Basic de 2017) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="0e3d5-109">You can declare and initialize an `SByte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span>

<span data-ttu-id="0e3d5-110">En el siguiente ejemplo, enteros es igual a-102 que se representan como decimal, hexadecimal, y literales binarios se asignan a `SByte` valores.</span><span class="sxs-lookup"><span data-stu-id="0e3d5-110">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are assigned to `SByte` values.</span></span> <span data-ttu-id="0e3d5-111">Este ejemplo requiere que se compilen con la `/removeintchecks` modificador del compilador.</span><span class="sxs-lookup"><span data-stu-id="0e3d5-111">This example requires that you compile with the `/removeintchecks` compiler switch.</span></span>

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]  

> [!NOTE] 
> <span data-ttu-id="0e3d5-112">Use el prefijo `&h` o `&H` para denotar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario y el prefijo `&o` o `&O` para denotar un literal octal.</span><span class="sxs-lookup"><span data-stu-id="0e3d5-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="0e3d5-113">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="0e3d5-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="0e3d5-114">A partir de Visual Basic de 2017, también puede utilizar el carácter de subrayado, `_`, como un separador de dígitos para mejorar la legibilidad, como en el ejemplo siguiente se muestra.</span><span class="sxs-lookup"><span data-stu-id="0e3d5-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]  

<span data-ttu-id="0e3d5-115">Si el literal entero está fuera del intervalo de `SByte` (es decir, si es inferior a <xref:System.SByte.MinValue?displayProperty=nameWithType> o mayor que <xref:System.SByte.MaxValue?displayProperty=nameWithType>, se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="0e3d5-115">If the integer literal is outside the range of `SByte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=nameWithType> or greater than <xref:System.SByte.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span> <span data-ttu-id="0e3d5-116">Cuando un literal entero no tiene sufijo, un [entero](integer-data-type.md) se deduce.</span><span class="sxs-lookup"><span data-stu-id="0e3d5-116">When an integer literal has no suffix, an [Integer](integer-data-type.md) is inferred.</span></span> <span data-ttu-id="0e3d5-117">Si el literal entero está fuera del intervalo de la `Integer` tipo, un [largo](long-data-type.md) se deduce.</span><span class="sxs-lookup"><span data-stu-id="0e3d5-117">If the integer literal is outside the range of the `Integer` type, a [Long](long-data-type.md) is inferred.</span></span> <span data-ttu-id="0e3d5-118">Esto significa que, en los ejemplos anteriores, los literales numéricos `0x9A` y `0b10011010` se interpretan como enteros con signo de 32 bits con un valor de 156, lo cual supera <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0e3d5-118">This means that, in the previous examples, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0e3d5-119">Para compilar correctamente el código como el siguiente que asigna un entero no decimales en un `SByte`, puede realizar cualquiera de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="0e3d5-119">To successfully compile code like this that assigns a non-decimal integer to an `SByte`, you can do either of the following:</span></span>

- <span data-ttu-id="0e3d5-120">Deshabilitar las comprobaciones de límites de enteros a la compilación con el `/removeintchecks` modificador del compilador.</span><span class="sxs-lookup"><span data-stu-id="0e3d5-120">Disable integer bounds checks by compiling with the `/removeintchecks` compiler switch.</span></span>

- <span data-ttu-id="0e3d5-121">Use un [escriba carácter](../../programming-guide\language-features\data-types/type-characters.md) para definir explícitamente el valor literal que se desea asignar a la `SByte`.</span><span class="sxs-lookup"><span data-stu-id="0e3d5-121">Use a [type character](../../programming-guide\language-features\data-types/type-characters.md) to explicitly define the literal value that you want to assign to the `SByte`.</span></span> <span data-ttu-id="0e3d5-122">En el ejemplo siguiente se asigna un literal negativo `Short` valor a un `SByte`.</span><span class="sxs-lookup"><span data-stu-id="0e3d5-122">The following example assigns a negative literal `Short` value to an `SByte`.</span></span> <span data-ttu-id="0e3d5-123">Tenga en cuenta que, para los números negativos, se debe establecer el bit de orden superior de la palabra de orden superior del literal numérico.</span><span class="sxs-lookup"><span data-stu-id="0e3d5-123">Note that, for negative numbers, the high-order bit of the high-order word of the numeric literal must be set.</span></span> <span data-ttu-id="0e3d5-124">En el caso de nuestro ejemplo, esto es de tipo bit 15 del literal `Short` valor.</span><span class="sxs-lookup"><span data-stu-id="0e3d5-124">In the case of our example, this is bit 15 of the literal `Short` value.</span></span>

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a><span data-ttu-id="0e3d5-125">Sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="0e3d5-125">Programming tips</span></span>
  
-   <span data-ttu-id="0e3d5-126">**Conformidad con CLS.**</span><span class="sxs-lookup"><span data-stu-id="0e3d5-126">**CLS Compliance.**</span></span> <span data-ttu-id="0e3d5-127">El `SByte` tipo de datos no es parte de la [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), por lo que el código conforme a CLS no puede utilizar un componente que lo utiliza.</span><span class="sxs-lookup"><span data-stu-id="0e3d5-127">The `SByte` data type is not part of the [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

-   <span data-ttu-id="0e3d5-128">**De ampliación.**</span><span class="sxs-lookup"><span data-stu-id="0e3d5-128">**Widening.**</span></span> <span data-ttu-id="0e3d5-129">El `SByte` tipo de datos se amplía a `Short`, `Integer`, `Long`, `Decimal`, `Single`, y `Double`.</span><span class="sxs-lookup"><span data-stu-id="0e3d5-129">The `SByte` data type widens to `Short`, `Integer`, `Long`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="0e3d5-130">Esto significa que se puede convertir `SByte` a cualquiera de estos tipos sin que se produzca una <xref:System.OverflowException?displayProperty=nameWithType> error.</span><span class="sxs-lookup"><span data-stu-id="0e3d5-130">This means you can convert `SByte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
-   <span data-ttu-id="0e3d5-131">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="0e3d5-131">**Type Characters.**</span></span> <span data-ttu-id="0e3d5-132">`SByte`no tiene ningún carácter de tipo literal ni caracteres de tipo identificador.</span><span class="sxs-lookup"><span data-stu-id="0e3d5-132">`SByte` has no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="0e3d5-133">**Tipo de Framework.**</span><span class="sxs-lookup"><span data-stu-id="0e3d5-133">**Framework Type.**</span></span> <span data-ttu-id="0e3d5-134">El tipo correspondiente en .NET Framework es la estructura <xref:System.SByte?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0e3d5-134">The corresponding type in the .NET Framework is the <xref:System.SByte?displayProperty=nameWithType> structure.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0e3d5-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e3d5-135">See also</span></span>

 <xref:System.SByte?displayProperty=nameWithType>  
 [<span data-ttu-id="0e3d5-136">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="0e3d5-136">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="0e3d5-137">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="0e3d5-137">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="0e3d5-138">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="0e3d5-138">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="0e3d5-139">Short (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="0e3d5-139">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)  
 [<span data-ttu-id="0e3d5-140">Integer (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="0e3d5-140">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [<span data-ttu-id="0e3d5-141">Long (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="0e3d5-141">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [<span data-ttu-id="0e3d5-142">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="0e3d5-142">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)

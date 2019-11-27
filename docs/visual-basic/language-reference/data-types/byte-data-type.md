---
title: Byte (Tipo de datos)
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
ms.openlocfilehash: 347d7e7d0f09e089886bc81bd0be659deaca9b46
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344077"
---
# <a name="byte-data-type-visual-basic"></a><span data-ttu-id="1b775-102">Byte (tipo de datos) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1b775-102">Byte data type (Visual Basic)</span></span>

<span data-ttu-id="1b775-103">Contiene enteros de 8 bits sin signo (1 byte) que oscilan entre 0 y 255.</span><span class="sxs-lookup"><span data-stu-id="1b775-103">Holds unsigned 8-bit (1-byte) integers that range in value from 0 through 255.</span></span>

## <a name="remarks"></a><span data-ttu-id="1b775-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1b775-104">Remarks</span></span>

<span data-ttu-id="1b775-105">Utilice el tipo de datos `Byte` para contener datos binarios.</span><span class="sxs-lookup"><span data-stu-id="1b775-105">Use the `Byte` data type to contain binary data.</span></span>  
  
<span data-ttu-id="1b775-106">El valor predeterminado de `Byte` es 0.</span><span class="sxs-lookup"><span data-stu-id="1b775-106">The default value of `Byte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="1b775-107">Asignaciones literales</span><span class="sxs-lookup"><span data-stu-id="1b775-107">Literal assignments</span></span>

<span data-ttu-id="1b775-108">Puede declarar e inicializar una variable de `Byte` asignándole un literal decimal, un literal hexadecimal, un literal octal o (empezando por Visual Basic 2017) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="1b775-108">You can declare and initialize a `Byte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="1b775-109">Si el literal entero está fuera del intervalo de una `Byte` (es decir, si es menor que <xref:System.Byte.MinValue?displayProperty=nameWithType> o mayor que <xref:System.Byte.MaxValue?displayProperty=nameWithType>), se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="1b775-109">If the integral literal is outside the range of a `Byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="1b775-110">En el ejemplo siguiente, los enteros que equivalen a 201 que se representan como literales binarios, hexadecimales y decimales se convierten implícitamente de un [entero](integer-data-type.md) a `byte` valores.</span><span class="sxs-lookup"><span data-stu-id="1b775-110">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `byte` values.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> <span data-ttu-id="1b775-111">Use el prefijo `&h` o `&H` para indicar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario y el prefijo `&o` o `&O` para denotar un literal octal.</span><span class="sxs-lookup"><span data-stu-id="1b775-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="1b775-112">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="1b775-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="1b775-113">A partir de Visual Basic 2017, también puede usar el carácter de subrayado, `_`, como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="1b775-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

<span data-ttu-id="1b775-114">A partir de Visual Basic 15,5, también puede usar el carácter de subrayado (`_`) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios o octales.</span><span class="sxs-lookup"><span data-stu-id="1b775-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="1b775-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1b775-115">For example:</span></span>

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a><span data-ttu-id="1b775-116">sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="1b775-116">Programming tips</span></span>

- <span data-ttu-id="1b775-117">**Números negativos.**</span><span class="sxs-lookup"><span data-stu-id="1b775-117">**Negative Numbers.**</span></span> <span data-ttu-id="1b775-118">Dado que `Byte` es un tipo sin signo, no puede representar un número negativo.</span><span class="sxs-lookup"><span data-stu-id="1b775-118">Because `Byte` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="1b775-119">Si usa el operador unario menos (`-`) en una expresión que se evalúa como tipo `Byte`, Visual Basic convierte la expresión en `Short` primero.</span><span class="sxs-lookup"><span data-stu-id="1b775-119">If you use the unary minus (`-`) operator on an expression that evaluates to type `Byte`, Visual Basic converts the expression to `Short` first.</span></span>
  
- <span data-ttu-id="1b775-120">**Conversiones de formato.**</span><span class="sxs-lookup"><span data-stu-id="1b775-120">**Format Conversions.**</span></span> <span data-ttu-id="1b775-121">Cuando Visual Basic lee o escribe archivos, o cuando llama a archivos dll, métodos y propiedades, puede convertir automáticamente entre formatos de datos.</span><span class="sxs-lookup"><span data-stu-id="1b775-121">When Visual Basic reads or writes files, or when it calls DLLs, methods, and properties, it can automatically convert between data formats.</span></span> <span data-ttu-id="1b775-122">Los datos binarios almacenados en `Byte` variables y matrices se conservan durante las conversiones de formato.</span><span class="sxs-lookup"><span data-stu-id="1b775-122">Binary data stored in `Byte` variables and arrays is preserved during such format conversions.</span></span> <span data-ttu-id="1b775-123">No debe utilizar una variable `String` para los datos binarios, porque su contenido se puede dañar durante la conversión entre los formatos ANSI y Unicode.</span><span class="sxs-lookup"><span data-stu-id="1b775-123">You should not use a `String` variable for binary data, because its contents can be corrupted during conversion between ANSI and Unicode formats.</span></span>

- <span data-ttu-id="1b775-124">**Ampliación.**</span><span class="sxs-lookup"><span data-stu-id="1b775-124">**Widening.**</span></span> <span data-ttu-id="1b775-125">El tipo de datos `Byte` se amplía a `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`o `Double`.</span><span class="sxs-lookup"><span data-stu-id="1b775-125">The `Byte` data type widens to `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="1b775-126">Esto significa que puede convertir `Byte` en cualquiera de estos tipos sin encontrar un error de <xref:System.OverflowException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1b775-126">This means you can convert `Byte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
- <span data-ttu-id="1b775-127">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="1b775-127">**Type Characters.**</span></span> <span data-ttu-id="1b775-128">`Byte` no tiene un carácter de tipo literal o un carácter de tipo de identificador.</span><span class="sxs-lookup"><span data-stu-id="1b775-128">`Byte` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="1b775-129">**Tipo de marco.**</span><span class="sxs-lookup"><span data-stu-id="1b775-129">**Framework Type.**</span></span> <span data-ttu-id="1b775-130">El tipo correspondiente en .NET Framework es la estructura <xref:System.Byte?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1b775-130">The corresponding type in the .NET Framework is the <xref:System.Byte?displayProperty=nameWithType> structure.</span></span>

## <a name="example"></a><span data-ttu-id="1b775-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1b775-131">Example</span></span>

 <span data-ttu-id="1b775-132">En el ejemplo siguiente, `b` es una variable de `Byte`.</span><span class="sxs-lookup"><span data-stu-id="1b775-132">In the following example, `b` is a `Byte` variable.</span></span> <span data-ttu-id="1b775-133">Las instrucciones muestran el intervalo de la variable y la aplicación de los operadores de desplazamiento de bits a ella.</span><span class="sxs-lookup"><span data-stu-id="1b775-133">The statements demonstrate the range of the variable and the application of bit-shift operators to it.</span></span>

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a><span data-ttu-id="1b775-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b775-134">See also</span></span>

- <xref:System.Byte?displayProperty=nameWithType>
- [<span data-ttu-id="1b775-135">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="1b775-135">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="1b775-136">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="1b775-136">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="1b775-137">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="1b775-137">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="1b775-138">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="1b775-138">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)

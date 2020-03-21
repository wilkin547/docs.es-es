---
title: Tipo de datos Byte
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
ms.openlocfilehash: 347d7e7d0f09e089886bc81bd0be659deaca9b46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401356"
---
# <a name="byte-data-type-visual-basic"></a><span data-ttu-id="6ac46-102">Tipo de datos byte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6ac46-102">Byte data type (Visual Basic)</span></span>

<span data-ttu-id="6ac46-103">Contiene enteros sin signo de 8 bits (1 byte) que oscilan en valor de 0 a 255.</span><span class="sxs-lookup"><span data-stu-id="6ac46-103">Holds unsigned 8-bit (1-byte) integers that range in value from 0 through 255.</span></span>

## <a name="remarks"></a><span data-ttu-id="6ac46-104">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6ac46-104">Remarks</span></span>

<span data-ttu-id="6ac46-105">Utilice `Byte` el tipo de datos para contener datos binarios.</span><span class="sxs-lookup"><span data-stu-id="6ac46-105">Use the `Byte` data type to contain binary data.</span></span>  
  
<span data-ttu-id="6ac46-106">El valor predeterminado de `Byte` es 0.</span><span class="sxs-lookup"><span data-stu-id="6ac46-106">The default value of `Byte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="6ac46-107">Asignaciones literales</span><span class="sxs-lookup"><span data-stu-id="6ac46-107">Literal assignments</span></span>

<span data-ttu-id="6ac46-108">Puede declarar e `Byte` inicializar una variable asignándole un literal decimal, un literal hexadecimal, un literal octal o (a partir de Visual Basic 2017) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="6ac46-108">You can declare and initialize a `Byte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="6ac46-109">Si el literal entero está `Byte` fuera del intervalo de a <xref:System.Byte.MinValue?displayProperty=nameWithType> (es <xref:System.Byte.MaxValue?displayProperty=nameWithType>decir, si es menor o mayor que ), se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="6ac46-109">If the integral literal is outside the range of a `Byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="6ac46-110">En el ejemplo siguiente, los enteros iguales a 201 que se representan como [Integer](integer-data-type.md) literales `byte` decimales, hexadecimales y binarios se convierten implícitamente de Entero a valores.</span><span class="sxs-lookup"><span data-stu-id="6ac46-110">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `byte` values.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> <span data-ttu-id="6ac46-111">Utilice el `&h` prefijo `&H` o para denotar un `&b` `&B` literal hexadecimal, el prefijo o `&o` `&O` para denotar un literal binario, y el prefijo o para denotar un literal octal.</span><span class="sxs-lookup"><span data-stu-id="6ac46-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="6ac46-112">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="6ac46-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="6ac46-113">A partir de Visual Basic 2017, también `_`puede usar el carácter de subrayado, , como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="6ac46-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

<span data-ttu-id="6ac46-114">A partir de Visual Basic 15.5, también`_`puede usar el carácter de subrayado ( ) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios u octales.</span><span class="sxs-lookup"><span data-stu-id="6ac46-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="6ac46-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6ac46-115">For example:</span></span>

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a><span data-ttu-id="6ac46-116">sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="6ac46-116">Programming tips</span></span>

- <span data-ttu-id="6ac46-117">**Números negativos.**</span><span class="sxs-lookup"><span data-stu-id="6ac46-117">**Negative Numbers.**</span></span> <span data-ttu-id="6ac46-118">Dado `Byte` que es un tipo sin signo, no puede representar un número negativo.</span><span class="sxs-lookup"><span data-stu-id="6ac46-118">Because `Byte` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="6ac46-119">Si utiliza el operador`-`unario menos ( ) en `Byte`una expresión que se `Short` evalúa como tipo , Visual Basic convierte la expresión en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="6ac46-119">If you use the unary minus (`-`) operator on an expression that evaluates to type `Byte`, Visual Basic converts the expression to `Short` first.</span></span>
  
- <span data-ttu-id="6ac46-120">**Conversiones de formato.**</span><span class="sxs-lookup"><span data-stu-id="6ac46-120">**Format Conversions.**</span></span> <span data-ttu-id="6ac46-121">Cuando Visual Basic lee o escribe archivos, o cuando llama a archivos DLL, métodos y propiedades, puede convertir automáticamente entre formatos de datos.</span><span class="sxs-lookup"><span data-stu-id="6ac46-121">When Visual Basic reads or writes files, or when it calls DLLs, methods, and properties, it can automatically convert between data formats.</span></span> <span data-ttu-id="6ac46-122">Los datos `Byte` binarios almacenados en variables y matrices se conservan durante dichas conversiones de formato.</span><span class="sxs-lookup"><span data-stu-id="6ac46-122">Binary data stored in `Byte` variables and arrays is preserved during such format conversions.</span></span> <span data-ttu-id="6ac46-123">No debe utilizar `String` una variable para los datos binarios, ya que su contenido puede dañarse durante la conversión entre formatos ANSI y Unicode.</span><span class="sxs-lookup"><span data-stu-id="6ac46-123">You should not use a `String` variable for binary data, because its contents can be corrupted during conversion between ANSI and Unicode formats.</span></span>

- <span data-ttu-id="6ac46-124">**Ampliación.**</span><span class="sxs-lookup"><span data-stu-id="6ac46-124">**Widening.**</span></span> <span data-ttu-id="6ac46-125">El `Byte` tipo de datos `Short` `UShort`se `Integer` `UInteger`amplía `Long` `ULong`a `Decimal` `Single`, `Double`, , , , , , o .</span><span class="sxs-lookup"><span data-stu-id="6ac46-125">The `Byte` data type widens to `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="6ac46-126">Esto significa que `Byte` puede convertir a cualquiera <xref:System.OverflowException?displayProperty=nameWithType> de estos tipos sin encontrar un error.</span><span class="sxs-lookup"><span data-stu-id="6ac46-126">This means you can convert `Byte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
- <span data-ttu-id="6ac46-127">**Escriba Caracteres.**</span><span class="sxs-lookup"><span data-stu-id="6ac46-127">**Type Characters.**</span></span> <span data-ttu-id="6ac46-128">`Byte`no tiene ningún carácter de tipo literal o carácter de tipo identificador.</span><span class="sxs-lookup"><span data-stu-id="6ac46-128">`Byte` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="6ac46-129">**Tipo de Framework.**</span><span class="sxs-lookup"><span data-stu-id="6ac46-129">**Framework Type.**</span></span> <span data-ttu-id="6ac46-130">El tipo correspondiente en .NET Framework es la estructura <xref:System.Byte?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6ac46-130">The corresponding type in the .NET Framework is the <xref:System.Byte?displayProperty=nameWithType> structure.</span></span>

## <a name="example"></a><span data-ttu-id="6ac46-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6ac46-131">Example</span></span>

 <span data-ttu-id="6ac46-132">En el ejemplo `b` siguiente, es una `Byte` variable.</span><span class="sxs-lookup"><span data-stu-id="6ac46-132">In the following example, `b` is a `Byte` variable.</span></span> <span data-ttu-id="6ac46-133">Las instrucciones muestran el rango de la variable y la aplicación de operadores de desplazamiento de bits a ella.</span><span class="sxs-lookup"><span data-stu-id="6ac46-133">The statements demonstrate the range of the variable and the application of bit-shift operators to it.</span></span>

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a><span data-ttu-id="6ac46-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6ac46-134">See also</span></span>

- <xref:System.Byte?displayProperty=nameWithType>
- [<span data-ttu-id="6ac46-135">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="6ac46-135">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="6ac46-136">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="6ac46-136">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="6ac46-137">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="6ac46-137">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="6ac46-138">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="6ac46-138">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)

---
description: 'Más información sobre: tipo de datos CHAR (Visual Basic)'
title: Tipo de datos Char
ms.date: 07/20/2015
f1_keywords:
- vb.Char
helpviewer_keywords:
- literal type characters [Visual Basic], C
- Char data type
- C literal type character [Visual Basic]
- data types [Visual Basic], assigning
- Char data type [Visual Basic], character literals
ms.assetid: cd7547a9-7855-4e8e-b216-35d74a362657
ms.openlocfilehash: 371244ee4eae6d7dde20487dd7f38c09f3929cd8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792250"
---
# <a name="char-data-type-visual-basic"></a><span data-ttu-id="5690e-103">Char (Tipo de datos, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5690e-103">Char Data Type (Visual Basic)</span></span>

<span data-ttu-id="5690e-104">Contiene puntos de código sin signo de 16 bits (2 bytes) con un valor comprendido entre 0 y 65535.</span><span class="sxs-lookup"><span data-stu-id="5690e-104">Holds unsigned 16-bit (2-byte) code points ranging in value from 0 through 65535.</span></span> <span data-ttu-id="5690e-105">Cada *punto de código*, o código de carácter, representa un único carácter Unicode.</span><span class="sxs-lookup"><span data-stu-id="5690e-105">Each *code point*, or character code, represents a single Unicode character.</span></span>

## <a name="remarks"></a><span data-ttu-id="5690e-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5690e-106">Remarks</span></span>

<span data-ttu-id="5690e-107">Utilice el `Char` tipo de datos cuando necesite contener un solo carácter y no necesite la sobrecarga de `String` .</span><span class="sxs-lookup"><span data-stu-id="5690e-107">Use the `Char` data type when you need to hold only a single character and do not need the overhead of `String`.</span></span> <span data-ttu-id="5690e-108">En algunos casos puede usar `Char()` , una matriz de `Char` elementos, para contener varios caracteres.</span><span class="sxs-lookup"><span data-stu-id="5690e-108">In some cases you can use `Char()`, an array of `Char` elements, to hold multiple characters.</span></span>

<span data-ttu-id="5690e-109">El valor predeterminado de `Char` es el carácter con un punto de código de 0.</span><span class="sxs-lookup"><span data-stu-id="5690e-109">The default value of `Char` is the character with a code point of 0.</span></span>

## <a name="unicode-characters"></a><span data-ttu-id="5690e-110">Caracteres Unicode</span><span class="sxs-lookup"><span data-stu-id="5690e-110">Unicode Characters</span></span>

<span data-ttu-id="5690e-111">Los primeros 128 puntos de código (0 – 127) de Unicode corresponden a las letras y símbolos de un teclado estándar de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="5690e-111">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="5690e-112">Estos primeros 128 puntos de código son los mismos que los que define el juego de caracteres ASCII.</span><span class="sxs-lookup"><span data-stu-id="5690e-112">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="5690e-113">Los dos puntos de código 128 (128 – 255) representan caracteres especiales, como Letras de alfabetos basados en latín, acentos, símbolos de moneda y fracciones.</span><span class="sxs-lookup"><span data-stu-id="5690e-113">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="5690e-114">Unicode usa los puntos de código restantes (256-65535) para una amplia variedad de símbolos, incluidos los caracteres de texto en todo el mundo, los signos diacríticos y los símbolos matemáticos y técnicos.</span><span class="sxs-lookup"><span data-stu-id="5690e-114">Unicode uses the remaining code points (256-65535) for a wide variety of symbols, including worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>

<span data-ttu-id="5690e-115">Puede usar métodos como <xref:System.Char.IsDigit%2A> y <xref:System.Char.IsPunctuation%2A> en una `Char` variable para determinar su clasificación Unicode.</span><span class="sxs-lookup"><span data-stu-id="5690e-115">You can use methods like <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on a `Char` variable to determine its Unicode classification.</span></span>

## <a name="type-conversions"></a><span data-ttu-id="5690e-116">Conversiones de tipos</span><span class="sxs-lookup"><span data-stu-id="5690e-116">Type Conversions</span></span>

<span data-ttu-id="5690e-117">Visual Basic no convierte directamente entre `Char` y los tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="5690e-117">Visual Basic does not convert directly between `Char` and the numeric types.</span></span> <span data-ttu-id="5690e-118">Puede usar la <xref:Microsoft.VisualBasic.Strings.Asc%2A> función o <xref:Microsoft.VisualBasic.Strings.AscW%2A> para convertir un `Char` valor en un `Integer` que represente su punto de código.</span><span class="sxs-lookup"><span data-stu-id="5690e-118">You can use the <xref:Microsoft.VisualBasic.Strings.Asc%2A> or <xref:Microsoft.VisualBasic.Strings.AscW%2A> function to convert a `Char` value to an `Integer` that represents its code point.</span></span> <span data-ttu-id="5690e-119">Puede usar la <xref:Microsoft.VisualBasic.Strings.Chr%2A> función o <xref:Microsoft.VisualBasic.Strings.ChrW%2A> para convertir un `Integer` valor en un `Char` que tiene ese punto de código.</span><span class="sxs-lookup"><span data-stu-id="5690e-119">You can use the <xref:Microsoft.VisualBasic.Strings.Chr%2A> or <xref:Microsoft.VisualBasic.Strings.ChrW%2A> function to convert an `Integer` value to a `Char` that has that code point.</span></span>

<span data-ttu-id="5690e-120">Si el modificador de comprobación de tipo ( [Option Strict Statement](../statements/option-strict-statement.md)) está activado, debe anexar el carácter de tipo literal a un literal de cadena de un solo carácter para identificarlo como el `Char` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="5690e-120">If the type checking switch (the [Option Strict Statement](../statements/option-strict-statement.md)) is on, you must append the literal type character to a single-character string literal to identify it as the `Char` data type.</span></span> <span data-ttu-id="5690e-121">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5690e-121">The following example illustrates this.</span></span> <span data-ttu-id="5690e-122">La primera asignación a la `charVar` variable genera el error del compilador [BC30512](../../misc/bc30512.md) porque `Option Strict` es on.</span><span class="sxs-lookup"><span data-stu-id="5690e-122">The first assignment to the `charVar` variable generates compiler error [BC30512](../../misc/bc30512.md) because `Option Strict` is on.</span></span> <span data-ttu-id="5690e-123">La segunda se compila correctamente porque el `c` carácter de tipo literal identifica el literal como un `Char` valor.</span><span class="sxs-lookup"><span data-stu-id="5690e-123">The second compiles successfully because the `c` literal type character identifies the literal as a `Char` value.</span></span>

```vb
Option Strict On

Module CharType
    Public Sub Main()
        Dim charVar As Char

        ' This statement generates compiler error BC30512 because Option Strict is On.  
        charVar = "Z"  

        ' The following statement succeeds because it specifies a Char literal.  
        charVar = "Z"c
    End Sub
End Module
```

## <a name="programming-tips"></a><span data-ttu-id="5690e-124">Sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="5690e-124">Programming Tips</span></span>

- <span data-ttu-id="5690e-125">**Números negativos.**</span><span class="sxs-lookup"><span data-stu-id="5690e-125">**Negative Numbers.**</span></span> <span data-ttu-id="5690e-126">`Char` es un tipo sin signo y no puede representar un valor negativo.</span><span class="sxs-lookup"><span data-stu-id="5690e-126">`Char` is an unsigned type and cannot represent a negative value.</span></span> <span data-ttu-id="5690e-127">En cualquier caso, no debe usar `Char` para contener valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="5690e-127">In any case, you should not use `Char` to hold numeric values.</span></span>

- <span data-ttu-id="5690e-128">**Consideraciones de interoperabilidad.**</span><span class="sxs-lookup"><span data-stu-id="5690e-128">**Interop Considerations.**</span></span> <span data-ttu-id="5690e-129">Si la interfaz con componentes no escritos para el .NET Framework, por ejemplo, objetos de automatización o COM, recuerde que los tipos de caracteres tienen un ancho de datos diferente (8 bits) en otros entornos.</span><span class="sxs-lookup"><span data-stu-id="5690e-129">If you interface with components not written for the .NET Framework, for example Automation or COM objects, remember that character types have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="5690e-130">Si pasa un argumento de 8 bits a este componente, declárelo como `Byte` en lugar de `Char` en el nuevo código de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5690e-130">If you pass an 8-bit argument to such a component, declare it as `Byte` instead of `Char` in your new Visual Basic code.</span></span>

- <span data-ttu-id="5690e-131">**Ampliación.**</span><span class="sxs-lookup"><span data-stu-id="5690e-131">**Widening.**</span></span> <span data-ttu-id="5690e-132">El `Char` tipo de datos se amplía a `String` .</span><span class="sxs-lookup"><span data-stu-id="5690e-132">The `Char` data type widens to `String`.</span></span> <span data-ttu-id="5690e-133">Esto significa que puede convertir `Char` a `String` y no encontrará <xref:System.OverflowException?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="5690e-133">This means you can convert `Char` to `String` and will not encounter a <xref:System.OverflowException?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="5690e-134">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="5690e-134">**Type Characters.**</span></span> <span data-ttu-id="5690e-135">Anexar el carácter de tipo literal `C` a un literal de cadena de un solo carácter lo convierte al `Char` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="5690e-135">Appending the literal type character `C` to a single-character string literal forces it to the `Char` data type.</span></span> <span data-ttu-id="5690e-136">`Char` no tiene ningún carácter de tipo de identificador.</span><span class="sxs-lookup"><span data-stu-id="5690e-136">`Char` has no identifier type character.</span></span>

- <span data-ttu-id="5690e-137">**Tipo de Framework.**</span><span class="sxs-lookup"><span data-stu-id="5690e-137">**Framework Type.**</span></span> <span data-ttu-id="5690e-138">El tipo correspondiente en .NET Framework es la estructura <xref:System.Char?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5690e-138">The corresponding type in the .NET Framework is the <xref:System.Char?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="5690e-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="5690e-139">See also</span></span>

- <xref:System.Char?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [<span data-ttu-id="5690e-140">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="5690e-140">Data Types</span></span>](index.md)
- [<span data-ttu-id="5690e-141">String (Tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="5690e-141">String Data Type</span></span>](string-data-type.md)
- [<span data-ttu-id="5690e-142">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="5690e-142">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="5690e-143">Resumen de las conversiones</span><span class="sxs-lookup"><span data-stu-id="5690e-143">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="5690e-144">Procedimiento Llamada una función de Windows que adopta tipos sin signo</span><span class="sxs-lookup"><span data-stu-id="5690e-144">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="5690e-145">Uso eficiente de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="5690e-145">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)

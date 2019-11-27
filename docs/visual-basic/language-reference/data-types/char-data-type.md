---
title: Char (Tipo de datos)
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
ms.openlocfilehash: 1ed5b19a307d094fc1d5a6bb0251c57052dc9bc1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344049"
---
# <a name="char-data-type-visual-basic"></a><span data-ttu-id="30adb-102">Char (Tipo de datos, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="30adb-102">Char Data Type (Visual Basic)</span></span>

<span data-ttu-id="30adb-103">Contiene puntos de código sin signo de 16 bits (2 bytes) con un valor comprendido entre 0 y 65535.</span><span class="sxs-lookup"><span data-stu-id="30adb-103">Holds unsigned 16-bit (2-byte) code points ranging in value from 0 through 65535.</span></span> <span data-ttu-id="30adb-104">Cada *punto de código*, o código de carácter, representa un único carácter Unicode.</span><span class="sxs-lookup"><span data-stu-id="30adb-104">Each *code point*, or character code, represents a single Unicode character.</span></span>

## <a name="remarks"></a><span data-ttu-id="30adb-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="30adb-105">Remarks</span></span>

<span data-ttu-id="30adb-106">Utilice el tipo de datos `Char` cuando necesite contener un solo carácter y no necesite la sobrecarga de `String`.</span><span class="sxs-lookup"><span data-stu-id="30adb-106">Use the `Char` data type when you need to hold only a single character and do not need the overhead of `String`.</span></span> <span data-ttu-id="30adb-107">En algunos casos, puede usar `Char()`, una matriz de elementos `Char`, para contener varios caracteres.</span><span class="sxs-lookup"><span data-stu-id="30adb-107">In some cases you can use `Char()`, an array of `Char` elements, to hold multiple characters.</span></span>

<span data-ttu-id="30adb-108">El valor predeterminado de `Char` es el carácter con un punto de código de 0.</span><span class="sxs-lookup"><span data-stu-id="30adb-108">The default value of `Char` is the character with a code point of 0.</span></span>

## <a name="unicode-characters"></a><span data-ttu-id="30adb-109">Caracteres Unicode</span><span class="sxs-lookup"><span data-stu-id="30adb-109">Unicode Characters</span></span>

<span data-ttu-id="30adb-110">Los primeros 128 puntos de código (0 – 127) de Unicode corresponden a las letras y símbolos de un teclado estándar de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="30adb-110">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="30adb-111">Estos primeros 128 puntos de código son los mismos que los que define el juego de caracteres ASCII.</span><span class="sxs-lookup"><span data-stu-id="30adb-111">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="30adb-112">Los dos puntos de código 128 (128 – 255) representan caracteres especiales, como Letras de alfabetos basados en latín, acentos, símbolos de moneda y fracciones.</span><span class="sxs-lookup"><span data-stu-id="30adb-112">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="30adb-113">Unicode usa los puntos de código restantes (256-65535) para una amplia variedad de símbolos, incluidos los caracteres de texto en todo el mundo, los signos diacríticos y los símbolos matemáticos y técnicos.</span><span class="sxs-lookup"><span data-stu-id="30adb-113">Unicode uses the remaining code points (256-65535) for a wide variety of symbols, including worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>

<span data-ttu-id="30adb-114">Puede usar métodos como <xref:System.Char.IsDigit%2A> y <xref:System.Char.IsPunctuation%2A> en una variable de `Char` para determinar su clasificación Unicode.</span><span class="sxs-lookup"><span data-stu-id="30adb-114">You can use methods like <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on a `Char` variable to determine its Unicode classification.</span></span>

## <a name="type-conversions"></a><span data-ttu-id="30adb-115">Conversiones de tipos</span><span class="sxs-lookup"><span data-stu-id="30adb-115">Type Conversions</span></span>

<span data-ttu-id="30adb-116">Visual Basic no convierte directamente entre `Char` y los tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="30adb-116">Visual Basic does not convert directly between `Char` and the numeric types.</span></span> <span data-ttu-id="30adb-117">Puede usar la función <xref:Microsoft.VisualBasic.Strings.Asc%2A> o <xref:Microsoft.VisualBasic.Strings.AscW%2A> para convertir un valor de `Char` en un `Integer` que representa su punto de código.</span><span class="sxs-lookup"><span data-stu-id="30adb-117">You can use the <xref:Microsoft.VisualBasic.Strings.Asc%2A> or <xref:Microsoft.VisualBasic.Strings.AscW%2A> function to convert a `Char` value to an `Integer` that represents its code point.</span></span> <span data-ttu-id="30adb-118">Puede usar la función <xref:Microsoft.VisualBasic.Strings.Chr%2A> o <xref:Microsoft.VisualBasic.Strings.ChrW%2A> para convertir un valor de `Integer` en un `Char` que tenga ese punto de código.</span><span class="sxs-lookup"><span data-stu-id="30adb-118">You can use the <xref:Microsoft.VisualBasic.Strings.Chr%2A> or <xref:Microsoft.VisualBasic.Strings.ChrW%2A> function to convert an `Integer` value to a `Char` that has that code point.</span></span>

<span data-ttu-id="30adb-119">Si el modificador de comprobación de tipo ( [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)) está activado, debe anexar el carácter de tipo literal a un literal de cadena de un solo carácter para identificarlo como el tipo de datos `Char`.</span><span class="sxs-lookup"><span data-stu-id="30adb-119">If the type checking switch (the [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)) is on, you must append the literal type character to a single-character string literal to identify it as the `Char` data type.</span></span> <span data-ttu-id="30adb-120">En el ejemplo siguiente se ilustra esto.</span><span class="sxs-lookup"><span data-stu-id="30adb-120">The following example illustrates this.</span></span> <span data-ttu-id="30adb-121">La primera asignación a la variable `charVar` genera el error del compilador [BC30512](../../misc/bc30512.md) porque `Option Strict` está activada.</span><span class="sxs-lookup"><span data-stu-id="30adb-121">The first assignment to the `charVar` variable generates compiler error [BC30512](../../misc/bc30512.md) because `Option Strict` is on.</span></span> <span data-ttu-id="30adb-122">La segunda se compila correctamente porque el carácter de tipo literal `c` identifica el literal como un valor de `Char`.</span><span class="sxs-lookup"><span data-stu-id="30adb-122">The second compiles successfully because the `c` literal type character identifies the literal as a `Char` value.</span></span>

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

## <a name="programming-tips"></a><span data-ttu-id="30adb-123">Sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="30adb-123">Programming Tips</span></span>

- <span data-ttu-id="30adb-124">**Números negativos.**</span><span class="sxs-lookup"><span data-stu-id="30adb-124">**Negative Numbers.**</span></span> <span data-ttu-id="30adb-125">`Char` es un tipo sin signo y no puede representar un valor negativo.</span><span class="sxs-lookup"><span data-stu-id="30adb-125">`Char` is an unsigned type and cannot represent a negative value.</span></span> <span data-ttu-id="30adb-126">En cualquier caso, no debe utilizar `Char` para contener valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="30adb-126">In any case, you should not use `Char` to hold numeric values.</span></span>

- <span data-ttu-id="30adb-127">**Consideraciones de interoperabilidad.**</span><span class="sxs-lookup"><span data-stu-id="30adb-127">**Interop Considerations.**</span></span> <span data-ttu-id="30adb-128">Si la interfaz con componentes no escritos para el .NET Framework, por ejemplo, objetos de automatización o COM, recuerde que los tipos de caracteres tienen un ancho de datos diferente (8 bits) en otros entornos.</span><span class="sxs-lookup"><span data-stu-id="30adb-128">If you interface with components not written for the .NET Framework, for example Automation or COM objects, remember that character types have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="30adb-129">Si pasa un argumento de 8 bits a este componente, declárelo como `Byte` en lugar de `Char` en el nuevo código de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="30adb-129">If you pass an 8-bit argument to such a component, declare it as `Byte` instead of `Char` in your new Visual Basic code.</span></span>

- <span data-ttu-id="30adb-130">**Ampliación.**</span><span class="sxs-lookup"><span data-stu-id="30adb-130">**Widening.**</span></span> <span data-ttu-id="30adb-131">El tipo de datos `Char` se amplía a `String`.</span><span class="sxs-lookup"><span data-stu-id="30adb-131">The `Char` data type widens to `String`.</span></span> <span data-ttu-id="30adb-132">Esto significa que puede convertir `Char` en `String` y no encontrará un <xref:System.OverflowException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="30adb-132">This means you can convert `Char` to `String` and will not encounter a <xref:System.OverflowException?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="30adb-133">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="30adb-133">**Type Characters.**</span></span> <span data-ttu-id="30adb-134">Si se anexa el carácter de tipo literal `C` a un literal de cadena de un solo carácter, se convierte al tipo de datos `Char`.</span><span class="sxs-lookup"><span data-stu-id="30adb-134">Appending the literal type character `C` to a single-character string literal forces it to the `Char` data type.</span></span> <span data-ttu-id="30adb-135">`Char` no tiene ningún carácter de tipo de identificador.</span><span class="sxs-lookup"><span data-stu-id="30adb-135">`Char` has no identifier type character.</span></span>

- <span data-ttu-id="30adb-136">**Tipo de marco.**</span><span class="sxs-lookup"><span data-stu-id="30adb-136">**Framework Type.**</span></span> <span data-ttu-id="30adb-137">El tipo correspondiente en .NET Framework es la estructura <xref:System.Char?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="30adb-137">The corresponding type in the .NET Framework is the <xref:System.Char?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="30adb-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="30adb-138">See also</span></span>

- <xref:System.Char?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [<span data-ttu-id="30adb-139">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="30adb-139">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="30adb-140">String (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="30adb-140">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)
- [<span data-ttu-id="30adb-141">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="30adb-141">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="30adb-142">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="30adb-142">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="30adb-143">Llamar a una función de Windows que adopta tipos sin signo</span><span class="sxs-lookup"><span data-stu-id="30adb-143">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="30adb-144">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="30adb-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)

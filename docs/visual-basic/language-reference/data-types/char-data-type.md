---
title: Char (Tipo de datos, Visual Basic)
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
ms.openlocfilehash: b50c902f69f7602dbad4663dc35bf0a2b932973f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796986"
---
# <a name="char-data-type-visual-basic"></a><span data-ttu-id="f748f-102">Char (Tipo de datos, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f748f-102">Char Data Type (Visual Basic)</span></span>
<span data-ttu-id="f748f-103">Contiene puntos de código (2 bytes) de 16 bits sin signo cuyo valor oscila de 0 a 65535.</span><span class="sxs-lookup"><span data-stu-id="f748f-103">Holds unsigned 16-bit (2-byte) code points ranging in value from 0 through 65535.</span></span> <span data-ttu-id="f748f-104">Cada *punto de código*, o código de carácter representa un único carácter Unicode.</span><span class="sxs-lookup"><span data-stu-id="f748f-104">Each *code point*, or character code, represents a single Unicode character.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f748f-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f748f-105">Remarks</span></span>  
 <span data-ttu-id="f748f-106">Use la `Char` cuando deba contener sólo un único tipo de datos de caracteres y no es necesario que la sobrecarga de `String`.</span><span class="sxs-lookup"><span data-stu-id="f748f-106">Use the `Char` data type when you need to hold only a single character and do not need the overhead of `String`.</span></span> <span data-ttu-id="f748f-107">En algunos casos puede usar `Char()`, una matriz de `Char` elementos para contener varios caracteres.</span><span class="sxs-lookup"><span data-stu-id="f748f-107">In some cases you can use `Char()`, an array of `Char` elements, to hold multiple characters.</span></span>  
  
 <span data-ttu-id="f748f-108">El valor predeterminado de `Char` es el carácter con un punto de código de 0.</span><span class="sxs-lookup"><span data-stu-id="f748f-108">The default value of `Char` is the character with a code point of 0.</span></span>  
  
## <a name="unicode-characters"></a><span data-ttu-id="f748f-109">Caracteres Unicode</span><span class="sxs-lookup"><span data-stu-id="f748f-109">Unicode Characters</span></span>  
 <span data-ttu-id="f748f-110">Los primeros puntos de 128 código (0 – 127) de Unicode corresponden a las letras y símbolos en un teclado US estándar.</span><span class="sxs-lookup"><span data-stu-id="f748f-110">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="f748f-111">Estos primeros puntos de 128 código son los mismos que los define el juego de caracteres ASCII.</span><span class="sxs-lookup"><span data-stu-id="f748f-111">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="f748f-112">El segundo 128 puntos de código (128-255) representan caracteres especiales, como letras del alfabeto latino, acentos, símbolos de moneda y fracciones.</span><span class="sxs-lookup"><span data-stu-id="f748f-112">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="f748f-113">Unicode utiliza los puntos de código restantes (256-65535) para una amplia variedad de símbolos, incluidos los caracteres de texto de todo el mundo, los signos diacríticos y símbolos técnicos y matemáticos.</span><span class="sxs-lookup"><span data-stu-id="f748f-113">Unicode uses the remaining code points (256-65535) for a wide variety of symbols, including worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>  
  
 <span data-ttu-id="f748f-114">Puede utilizar métodos como <xref:System.Char.IsDigit%2A> y <xref:System.Char.IsPunctuation%2A> en un `Char` variable para determinar su clasificación Unicode.</span><span class="sxs-lookup"><span data-stu-id="f748f-114">You can use methods like <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on a `Char` variable to determine its Unicode classification.</span></span>  
  
## <a name="type-conversions"></a><span data-ttu-id="f748f-115">Conversiones de tipos</span><span class="sxs-lookup"><span data-stu-id="f748f-115">Type Conversions</span></span>  
 <span data-ttu-id="f748f-116">Visual Basic no convertir directamente entre `Char` y los tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="f748f-116">Visual Basic does not convert directly between `Char` and the numeric types.</span></span> <span data-ttu-id="f748f-117">Puede usar el <xref:Microsoft.VisualBasic.Strings.Asc%2A> o <xref:Microsoft.VisualBasic.Strings.AscW%2A> función para convertir un `Char` valor a un `Integer` que representa su punto de código.</span><span class="sxs-lookup"><span data-stu-id="f748f-117">You can use the <xref:Microsoft.VisualBasic.Strings.Asc%2A> or <xref:Microsoft.VisualBasic.Strings.AscW%2A> function to convert a `Char` value to an `Integer` that represents its code point.</span></span> <span data-ttu-id="f748f-118">Puede usar el <xref:Microsoft.VisualBasic.Strings.Chr%2A> o <xref:Microsoft.VisualBasic.Strings.ChrW%2A> función para convertir un `Integer` valor a un `Char` que tenga ese punto de código.</span><span class="sxs-lookup"><span data-stu-id="f748f-118">You can use the <xref:Microsoft.VisualBasic.Strings.Chr%2A> or <xref:Microsoft.VisualBasic.Strings.ChrW%2A> function to convert an `Integer` value to a `Char` that has that code point.</span></span>  
  
 <span data-ttu-id="f748f-119">Si el modificador de comprobación de tipo ([Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)) está activado, debe anexar el carácter de tipo literal a un solo carácter literal de cadena para identificarla como la `Char` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="f748f-119">If the type checking switch ([Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)) is on, you must append the literal type character to a single-character string literal to identify it as the `Char` data type.</span></span> <span data-ttu-id="f748f-120">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f748f-120">The following example illustrates this.</span></span>  
  
```  
Option Strict On  
Dim charVar As Char  
' The following statement attempts to convert a String literal to Char.  
' Because Option Strict is On, it generates a compiler error.  
charVar = "Z"  
' The following statement succeeds because it specifies a Char literal.  
charVar = "Z"C  
```  
  
## <a name="programming-tips"></a><span data-ttu-id="f748f-121">Sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="f748f-121">Programming Tips</span></span>  
  
- <span data-ttu-id="f748f-122">**Números negativos.**</span><span class="sxs-lookup"><span data-stu-id="f748f-122">**Negative Numbers.**</span></span> <span data-ttu-id="f748f-123">`Char` es un tipo sin signo y no puede representar un valor negativo.</span><span class="sxs-lookup"><span data-stu-id="f748f-123">`Char` is an unsigned type and cannot represent a negative value.</span></span> <span data-ttu-id="f748f-124">En cualquier caso, no debe utilizar `Char` para contener valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="f748f-124">In any case, you should not use `Char` to hold numeric values.</span></span>  
  
- <span data-ttu-id="f748f-125">**Consideraciones de interoperabilidad.**</span><span class="sxs-lookup"><span data-stu-id="f748f-125">**Interop Considerations.**</span></span> <span data-ttu-id="f748f-126">Si interactúa con componentes no escritos para .NET Framework, por ejemplo objetos de automatización o COM, recuerde que los tipos de caracteres tienen un ancho de datos diferentes (8 bits) en otros entornos.</span><span class="sxs-lookup"><span data-stu-id="f748f-126">If you interface with components not written for the .NET Framework, for example Automation or COM objects, remember that character types have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="f748f-127">Si se pasa un argumento de 8 bits a esos componentes, declárelo como `Byte` en lugar de `Char` en el nuevo código de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f748f-127">If you pass an 8-bit argument to such a component, declare it as `Byte` instead of `Char` in your new Visual Basic code.</span></span>  
  
- <span data-ttu-id="f748f-128">**Ampliación.**</span><span class="sxs-lookup"><span data-stu-id="f748f-128">**Widening.**</span></span> <span data-ttu-id="f748f-129">El `Char` tipo de datos se amplía a `String`.</span><span class="sxs-lookup"><span data-stu-id="f748f-129">The `Char` data type widens to `String`.</span></span> <span data-ttu-id="f748f-130">Esto significa que se puede convertir `Char` a `String` y no se encontrará con un <xref:System.OverflowException?displayProperty=nameWithType> error.</span><span class="sxs-lookup"><span data-stu-id="f748f-130">This means you can convert `Char` to `String` and will not encounter a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="f748f-131">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="f748f-131">**Type Characters.**</span></span> <span data-ttu-id="f748f-132">Anexar el carácter de tipo literal `C` en una cadena de caracteres de un solo literal, convierte a la `Char` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="f748f-132">Appending the literal type character `C` to a single-character string literal forces it to the `Char` data type.</span></span> <span data-ttu-id="f748f-133">`Char` no tiene ningún carácter de tipo identificador.</span><span class="sxs-lookup"><span data-stu-id="f748f-133">`Char` has no identifier type character.</span></span>  
  
- <span data-ttu-id="f748f-134">**Tipo de marco de trabajo.**</span><span class="sxs-lookup"><span data-stu-id="f748f-134">**Framework Type.**</span></span> <span data-ttu-id="f748f-135">El tipo correspondiente en .NET Framework es la estructura <xref:System.Char?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f748f-135">The corresponding type in the .NET Framework is the <xref:System.Char?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f748f-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="f748f-136">See also</span></span>

- <xref:System.Char?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [<span data-ttu-id="f748f-137">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="f748f-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="f748f-138">String (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="f748f-138">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)
- [<span data-ttu-id="f748f-139">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="f748f-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="f748f-140">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="f748f-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="f748f-141">Cómo: Llamar a una función de Windows que adopta tipos sin signo</span><span class="sxs-lookup"><span data-stu-id="f748f-141">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="f748f-142">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="f748f-142">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)

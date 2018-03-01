---
title: Char (Tipo de datos, Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Char
helpviewer_keywords:
- literal type characters [Visual Basic], C
- Char data type
- C literal type character [Visual Basic]
- data types [Visual Basic], assigning
- Char data type [Visual Basic], character literals
ms.assetid: cd7547a9-7855-4e8e-b216-35d74a362657
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 16ff547fccbf4481d31ca79537962cc7090fc9b0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="char-data-type-visual-basic"></a><span data-ttu-id="807f8-102">Char (Tipo de datos, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="807f8-102">Char Data Type (Visual Basic)</span></span>
<span data-ttu-id="807f8-103">Contiene puntos de código de (2 bytes) de 16 bits sin signo comprendidos entre valor comprendido entre 0 y 65535.</span><span class="sxs-lookup"><span data-stu-id="807f8-103">Holds unsigned 16-bit (2-byte) code points ranging in value from 0 through 65535.</span></span> <span data-ttu-id="807f8-104">Cada *punto de código*, o el código de carácter, representa un único carácter Unicode.</span><span class="sxs-lookup"><span data-stu-id="807f8-104">Each *code point*, or character code, represents a single Unicode character.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="807f8-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="807f8-105">Remarks</span></span>  
 <span data-ttu-id="807f8-106">Use la `Char` cuando deba contener solo un único tipo de datos de caracteres y no es necesario que la sobrecarga de `String`.</span><span class="sxs-lookup"><span data-stu-id="807f8-106">Use the `Char` data type when you need to hold only a single character and do not need the overhead of `String`.</span></span> <span data-ttu-id="807f8-107">En algunos casos puede usar `Char()`, una matriz de `Char` elementos, para contener varios caracteres.</span><span class="sxs-lookup"><span data-stu-id="807f8-107">In some cases you can use `Char()`, an array of `Char` elements, to hold multiple characters.</span></span>  
  
 <span data-ttu-id="807f8-108">El valor predeterminado de `Char` es el carácter con un punto de código de 0.</span><span class="sxs-lookup"><span data-stu-id="807f8-108">The default value of `Char` is the character with a code point of 0.</span></span>  
  
## <a name="unicode-characters"></a><span data-ttu-id="807f8-109">Caracteres Unicode</span><span class="sxs-lookup"><span data-stu-id="807f8-109">Unicode Characters</span></span>  
 <span data-ttu-id="807f8-110">Los primeros puntos de 128 código (0 – 127) de Unicode corresponden a las letras y símbolos de un teclado estándar de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="807f8-110">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="807f8-111">Estos primeros puntos de 128 código son las mismas que las define el juego de caracteres ASCII.</span><span class="sxs-lookup"><span data-stu-id="807f8-111">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="807f8-112">Los siguientes puntos de 128 código (128 – 255) representan caracteres especiales, como letras de alfabetos latinos, acentos, símbolos de moneda y fracciones.</span><span class="sxs-lookup"><span data-stu-id="807f8-112">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="807f8-113">Unicode utiliza los puntos de código restantes (256-65535) para una amplia variedad de símbolos, incluidos los caracteres de texto en todo el mundo, signos diacríticos y símbolos matemáticos y técnicos.</span><span class="sxs-lookup"><span data-stu-id="807f8-113">Unicode uses the remaining code points (256-65535) for a wide variety of symbols, including worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>  
  
 <span data-ttu-id="807f8-114">Puede usar métodos como <xref:System.Char.IsDigit%2A> y <xref:System.Char.IsPunctuation%2A> en un `Char` variable para determinar su clasificación Unicode.</span><span class="sxs-lookup"><span data-stu-id="807f8-114">You can use methods like <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on a `Char` variable to determine its Unicode classification.</span></span>  
  
## <a name="type-conversions"></a><span data-ttu-id="807f8-115">Conversiones de tipos</span><span class="sxs-lookup"><span data-stu-id="807f8-115">Type Conversions</span></span>  
 <span data-ttu-id="807f8-116">Visual Basic no convertir directamente entre `Char` y los tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="807f8-116">Visual Basic does not convert directly between `Char` and the numeric types.</span></span> <span data-ttu-id="807f8-117">Puede usar el <xref:Microsoft.VisualBasic.Strings.Asc%2A> o <xref:Microsoft.VisualBasic.Strings.AscW%2A> función para convertir un `Char` valor a un `Integer` que representa su punto de código.</span><span class="sxs-lookup"><span data-stu-id="807f8-117">You can use the <xref:Microsoft.VisualBasic.Strings.Asc%2A> or <xref:Microsoft.VisualBasic.Strings.AscW%2A> function to convert a `Char` value to an `Integer` that represents its code point.</span></span> <span data-ttu-id="807f8-118">Puede usar el <xref:Microsoft.VisualBasic.Strings.Chr%2A> o <xref:Microsoft.VisualBasic.Strings.ChrW%2A> función para convertir un `Integer` valor a un `Char` que tenga ese punto de código.</span><span class="sxs-lookup"><span data-stu-id="807f8-118">You can use the <xref:Microsoft.VisualBasic.Strings.Chr%2A> or <xref:Microsoft.VisualBasic.Strings.ChrW%2A> function to convert an `Integer` value to a `Char` that has that code point.</span></span>  
  
 <span data-ttu-id="807f8-119">Si la comprobación de tipos cambia ([Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md)) está activado, debe agregar el carácter de tipo literal a un solo carácter literal de cadena para identificarlo como el `Char` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="807f8-119">If the type checking switch ([Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)) is on, you must append the literal type character to a single-character string literal to identify it as the `Char` data type.</span></span> <span data-ttu-id="807f8-120">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="807f8-120">The following example illustrates this.</span></span>  
  
```  
Option Strict On  
Dim charVar As Char  
' The following statement attempts to convert a String literal to Char.  
' Because Option Strict is On, it generates a compiler error.  
charVar = "Z"  
' The following statement succeeds because it specifies a Char literal.  
charVar = "Z"C  
```  
  
## <a name="programming-tips"></a><span data-ttu-id="807f8-121">Sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="807f8-121">Programming Tips</span></span>  
  
-   <span data-ttu-id="807f8-122">**Números negativos.**</span><span class="sxs-lookup"><span data-stu-id="807f8-122">**Negative Numbers.**</span></span> <span data-ttu-id="807f8-123">`Char`es un tipo sin signo y no puede representar un valor negativo.</span><span class="sxs-lookup"><span data-stu-id="807f8-123">`Char` is an unsigned type and cannot represent a negative value.</span></span> <span data-ttu-id="807f8-124">En cualquier caso, no debe usar `Char` para contener valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="807f8-124">In any case, you should not use `Char` to hold numeric values.</span></span>  
  
-   <span data-ttu-id="807f8-125">**Consideraciones de interoperabilidad.**</span><span class="sxs-lookup"><span data-stu-id="807f8-125">**Interop Considerations.**</span></span> <span data-ttu-id="807f8-126">Si se interactúa con componentes que no se han escrito para .NET Framework, por ejemplo objetos de automatización o COM, recuerde que los tipos de caracteres tienen un ancho de datos distinto (8 bits) en otros entornos.</span><span class="sxs-lookup"><span data-stu-id="807f8-126">If you interface with components not written for the .NET Framework, for example Automation or COM objects, remember that character types have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="807f8-127">Si se pasa un argumento de 8 bits a esos componentes, declárelo como `Byte` en lugar de `Char` en el código de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="807f8-127">If you pass an 8-bit argument to such a component, declare it as `Byte` instead of `Char` in your new Visual Basic code.</span></span>  
  
-   <span data-ttu-id="807f8-128">**De ampliación.**</span><span class="sxs-lookup"><span data-stu-id="807f8-128">**Widening.**</span></span> <span data-ttu-id="807f8-129">El `Char` tipo de datos se amplía a `String`.</span><span class="sxs-lookup"><span data-stu-id="807f8-129">The `Char` data type widens to `String`.</span></span> <span data-ttu-id="807f8-130">Esto significa que se puede convertir `Char` a `String` y no se producirán un <xref:System.OverflowException?displayProperty=nameWithType> error.</span><span class="sxs-lookup"><span data-stu-id="807f8-130">This means you can convert `Char` to `String` and will not encounter a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="807f8-131">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="807f8-131">**Type Characters.**</span></span> <span data-ttu-id="807f8-132">Si se agrega el carácter de tipo literal `C` en una cadena de carácter único literal fuerza que el `Char` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="807f8-132">Appending the literal type character `C` to a single-character string literal forces it to the `Char` data type.</span></span> <span data-ttu-id="807f8-133">`Char`no tiene ningún carácter de tipo identificador.</span><span class="sxs-lookup"><span data-stu-id="807f8-133">`Char` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="807f8-134">**Tipo de Framework.**</span><span class="sxs-lookup"><span data-stu-id="807f8-134">**Framework Type.**</span></span> <span data-ttu-id="807f8-135">El tipo correspondiente en .NET Framework es la estructura <xref:System.Char?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="807f8-135">The corresponding type in the .NET Framework is the <xref:System.Char?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="807f8-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="807f8-136">See Also</span></span>  
 <xref:System.Char?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 [<span data-ttu-id="807f8-137">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="807f8-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="807f8-138">String (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="807f8-138">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)  
 [<span data-ttu-id="807f8-139">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="807f8-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="807f8-140">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="807f8-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="807f8-141">Llamar a una función de Windows que adopta tipos sin signo</span><span class="sxs-lookup"><span data-stu-id="807f8-141">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="807f8-142">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="807f8-142">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)

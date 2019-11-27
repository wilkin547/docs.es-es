---
title: String (Tipo de datos)
ms.date: 07/20/2015
f1_keywords:
- vb.String
helpviewer_keywords:
- strings [Visual Basic], character
- strings [Visual Basic], fixed-length
- string keyword [Visual Basic]
- fixed-length strings [Visual Basic], string data type
- literals [Visual Basic], string
- text [Visual Basic], String data type
- $ identifier type character
- String data type
- fixed-length strings
- string literals [Visual Basic]
- data types [Visual Basic], assigning
- String literals [Visual Basic]
- identifier type characters [Visual Basic], $
ms.assetid: 15ac03f5-cabd-42cc-a754-1df3893c25d9
ms.openlocfilehash: c2c6f9632646c432abb7b6da8887253e526cc994
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343913"
---
# <a name="string-data-type-visual-basic"></a><span data-ttu-id="cbf9a-102">String (Tipo de datos, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cbf9a-102">String Data Type (Visual Basic)</span></span>

<span data-ttu-id="cbf9a-103">Contiene secuencias de puntos de código sin signo de 16 bits (2 bytes) que van desde 0 hasta 65535.</span><span class="sxs-lookup"><span data-stu-id="cbf9a-103">Holds sequences of unsigned 16-bit (2-byte) code points that range in value from 0 through 65535.</span></span> <span data-ttu-id="cbf9a-104">Cada *punto de código*, o código de carácter, representa un único carácter Unicode.</span><span class="sxs-lookup"><span data-stu-id="cbf9a-104">Each *code point*, or character code, represents a single Unicode character.</span></span> <span data-ttu-id="cbf9a-105">Una cadena puede contener entre 0 y aproximadamente 2 mil millones (2 ^ 31) caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="cbf9a-105">A string can contain from 0 to approximately two billion (2 ^ 31) Unicode characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbf9a-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cbf9a-106">Remarks</span></span>  

 <span data-ttu-id="cbf9a-107">Utilice el tipo de datos `String` para contener varios caracteres sin la sobrecarga de administración de la matriz de `Char()`, una matriz de elementos `Char`.</span><span class="sxs-lookup"><span data-stu-id="cbf9a-107">Use the `String` data type to hold multiple characters without the array management overhead of `Char()`, an array of `Char` elements.</span></span>  
  
 <span data-ttu-id="cbf9a-108">El valor predeterminado de `String` es `Nothing` (una referencia nula).</span><span class="sxs-lookup"><span data-stu-id="cbf9a-108">The default value of `String` is `Nothing` (a null reference).</span></span> <span data-ttu-id="cbf9a-109">Tenga en cuenta que esto no es lo mismo que la cadena vacía (valor `""`).</span><span class="sxs-lookup"><span data-stu-id="cbf9a-109">Note that this is not the same as the empty string (value `""`).</span></span>  
  
## <a name="unicode-characters"></a><span data-ttu-id="cbf9a-110">Caracteres Unicode</span><span class="sxs-lookup"><span data-stu-id="cbf9a-110">Unicode Characters</span></span>  

 <span data-ttu-id="cbf9a-111">Los primeros 128 puntos de código (0 – 127) de Unicode corresponden a las letras y símbolos de un teclado estándar de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="cbf9a-111">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="cbf9a-112">Estos primeros 128 puntos de código son los mismos que los que define el juego de caracteres ASCII.</span><span class="sxs-lookup"><span data-stu-id="cbf9a-112">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="cbf9a-113">Los dos puntos de código 128 (128 – 255) representan caracteres especiales, como Letras de alfabetos basados en latín, acentos, símbolos de moneda y fracciones.</span><span class="sxs-lookup"><span data-stu-id="cbf9a-113">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="cbf9a-114">Unicode utiliza el resto de puntos de código (256-65535) para una amplia variedad de símbolos.</span><span class="sxs-lookup"><span data-stu-id="cbf9a-114">Unicode uses the remaining code points (256-65535) for a wide variety of symbols.</span></span> <span data-ttu-id="cbf9a-115">Esto incluye los caracteres de texto, los signos diacríticos y los símbolos matemáticos y técnicos del mundo.</span><span class="sxs-lookup"><span data-stu-id="cbf9a-115">This includes worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>  
  
 <span data-ttu-id="cbf9a-116">Puede utilizar métodos como <xref:System.Char.IsDigit%2A> y <xref:System.Char.IsPunctuation%2A> en un carácter individual de una variable de `String` para determinar su clasificación Unicode.</span><span class="sxs-lookup"><span data-stu-id="cbf9a-116">You can use methods such as <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on an individual character in a `String` variable to determine its Unicode classification.</span></span>  
  
## <a name="format-requirements"></a><span data-ttu-id="cbf9a-117">Requisitos de formato</span><span class="sxs-lookup"><span data-stu-id="cbf9a-117">Format Requirements</span></span>  

 <span data-ttu-id="cbf9a-118">Debe incluir un literal de `String` entre comillas (`" "`).</span><span class="sxs-lookup"><span data-stu-id="cbf9a-118">You must enclose a `String` literal within quotation marks (`" "`).</span></span> <span data-ttu-id="cbf9a-119">Si debe incluir una comilla tipográfica como uno de los caracteres de la cadena, utilice dos comillas contiguas (`""`).</span><span class="sxs-lookup"><span data-stu-id="cbf9a-119">If you must include a quotation mark as one of the characters in the string, you use two contiguous quotation marks (`""`).</span></span> <span data-ttu-id="cbf9a-120">En el ejemplo siguiente se ilustra esto.</span><span class="sxs-lookup"><span data-stu-id="cbf9a-120">The following example illustrates this.</span></span>  
  
```vb  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 <span data-ttu-id="cbf9a-121">Tenga en cuenta que las comillas contiguas que representan una comilla en la cadena son independientes de las comillas que comienzan y finalizan el literal `String`.</span><span class="sxs-lookup"><span data-stu-id="cbf9a-121">Note that the contiguous quotation marks that represent a quotation mark in the string are independent of the quotation marks that begin and end the `String` literal.</span></span>  
  
## <a name="string-manipulations"></a><span data-ttu-id="cbf9a-122">Manipulaciones de cadenas</span><span class="sxs-lookup"><span data-stu-id="cbf9a-122">String Manipulations</span></span>  

 <span data-ttu-id="cbf9a-123">Una vez que se asigna una cadena a una variable `String`, esa cadena es *inmutable*, lo que significa que no se puede cambiar su longitud o su contenido.</span><span class="sxs-lookup"><span data-stu-id="cbf9a-123">Once you assign a string to a `String` variable, that string is *immutable*, which means you cannot change its length or contents.</span></span> <span data-ttu-id="cbf9a-124">Al modificar una cadena de alguna manera, Visual Basic crea una nueva cadena y abandona la anterior.</span><span class="sxs-lookup"><span data-stu-id="cbf9a-124">When you alter a string in any way, Visual Basic creates a new string and abandons the previous one.</span></span> <span data-ttu-id="cbf9a-125">A continuación, la variable `String` señala a la nueva cadena.</span><span class="sxs-lookup"><span data-stu-id="cbf9a-125">The `String` variable then points to the new string.</span></span>  
  
 <span data-ttu-id="cbf9a-126">Puede manipular el contenido de una variable de `String` mediante una variedad de funciones de cadena.</span><span class="sxs-lookup"><span data-stu-id="cbf9a-126">You can manipulate the contents of a `String` variable by using a variety of string functions.</span></span> <span data-ttu-id="cbf9a-127">En el ejemplo siguiente se muestra la función <xref:Microsoft.VisualBasic.Strings.Left%2A></span><span class="sxs-lookup"><span data-stu-id="cbf9a-127">The following example illustrates the <xref:Microsoft.VisualBasic.Strings.Left%2A> function</span></span>  
  
```vb  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 <span data-ttu-id="cbf9a-128">Una cadena creada por otro componente se puede rellenar con espacios iniciales o finales.</span><span class="sxs-lookup"><span data-stu-id="cbf9a-128">A string created by another component might be padded with leading or trailing spaces.</span></span> <span data-ttu-id="cbf9a-129">Si recibe este tipo de cadena, puede usar las funciones <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>y <xref:Microsoft.VisualBasic.Strings.RTrim%2A> para quitar estos espacios.</span><span class="sxs-lookup"><span data-stu-id="cbf9a-129">If you receive such a string, you can use the <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, and <xref:Microsoft.VisualBasic.Strings.RTrim%2A> functions to remove these spaces.</span></span>  
  
 <span data-ttu-id="cbf9a-130">Para obtener más información sobre las manipulaciones de cadenas, vea [cadenas](../../../visual-basic/programming-guide/language-features/strings/index.md).</span><span class="sxs-lookup"><span data-stu-id="cbf9a-130">For more information about string manipulations, see [Strings](../../../visual-basic/programming-guide/language-features/strings/index.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="cbf9a-131">Sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="cbf9a-131">Programming Tips</span></span>  
  
- <span data-ttu-id="cbf9a-132">**Números negativos.**</span><span class="sxs-lookup"><span data-stu-id="cbf9a-132">**Negative Numbers.**</span></span> <span data-ttu-id="cbf9a-133">Recuerde que los caracteres que contiene `String` no están firmados y no pueden representar valores negativos.</span><span class="sxs-lookup"><span data-stu-id="cbf9a-133">Remember that the characters held by `String` are unsigned and cannot represent negative values.</span></span> <span data-ttu-id="cbf9a-134">En cualquier caso, no debe utilizar `String` para contener valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="cbf9a-134">In any case, you should not use `String` to hold numeric values.</span></span>  
  
- <span data-ttu-id="cbf9a-135">**Consideraciones de interoperabilidad.**</span><span class="sxs-lookup"><span data-stu-id="cbf9a-135">**Interop Considerations.**</span></span> <span data-ttu-id="cbf9a-136">Si interactúa con componentes que no se han escrito para el .NET Framework, por ejemplo, objetos de automatización o COM, recuerde que los caracteres de cadena tienen un ancho de datos diferente (8 bits) en otros entornos.</span><span class="sxs-lookup"><span data-stu-id="cbf9a-136">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that string characters have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="cbf9a-137">Si va a pasar un argumento de cadena de caracteres de 8 bits a este componente, declárelo como `Byte()`, una matriz de elementos `Byte`, en lugar de `String` en el nuevo código de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="cbf9a-137">If you are passing a string argument of 8-bit characters to such a component, declare it as `Byte()`, an array of `Byte` elements, instead of `String` in your new Visual Basic code.</span></span>  
  
- <span data-ttu-id="cbf9a-138">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="cbf9a-138">**Type Characters.**</span></span> <span data-ttu-id="cbf9a-139">Anexar el carácter de tipo de identificador `$` a cualquier identificador lo convierte al tipo de datos `String`.</span><span class="sxs-lookup"><span data-stu-id="cbf9a-139">Appending the identifier type character `$` to any identifier forces it to the `String` data type.</span></span> <span data-ttu-id="cbf9a-140">`String` no tiene un carácter de tipo literal.</span><span class="sxs-lookup"><span data-stu-id="cbf9a-140">`String` has no literal type character.</span></span> <span data-ttu-id="cbf9a-141">Sin embargo, el compilador trata los literales entre comillas (`" "`) como `String`.</span><span class="sxs-lookup"><span data-stu-id="cbf9a-141">However, the compiler treats literals enclosed in quotation marks (`" "`) as `String`.</span></span>  
  
- <span data-ttu-id="cbf9a-142">**Tipo de marco.**</span><span class="sxs-lookup"><span data-stu-id="cbf9a-142">**Framework Type.**</span></span> <span data-ttu-id="cbf9a-143">El tipo correspondiente en el .NET Framework es la clase <xref:System.String?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cbf9a-143">The corresponding type in the .NET Framework is the <xref:System.String?displayProperty=nameWithType> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbf9a-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="cbf9a-144">See also</span></span>

- <xref:System.String?displayProperty=nameWithType>
- [<span data-ttu-id="cbf9a-145">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="cbf9a-145">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="cbf9a-146">Char (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="cbf9a-146">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="cbf9a-147">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="cbf9a-147">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="cbf9a-148">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="cbf9a-148">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="cbf9a-149">Llamar a una función de Windows que adopta tipos sin signo</span><span class="sxs-lookup"><span data-stu-id="cbf9a-149">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="cbf9a-150">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="cbf9a-150">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)

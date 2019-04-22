---
title: String (Tipo de datos, Visual Basic)
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
ms.openlocfilehash: 3e87dc6527b4351467b1155439ee8266157c16ff
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58842296"
---
# <a name="string-data-type-visual-basic"></a><span data-ttu-id="3dc71-102">String (Tipo de datos, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3dc71-102">String Data Type (Visual Basic)</span></span>
<span data-ttu-id="3dc71-103">Contiene secuencias de puntos de código (2 bytes) de 16 bits sin signo de ese intervalo de valor comprendido entre 0 y 65535.</span><span class="sxs-lookup"><span data-stu-id="3dc71-103">Holds sequences of unsigned 16-bit (2-byte) code points that range in value from 0 through 65535.</span></span> <span data-ttu-id="3dc71-104">Cada *punto de código*, o código de carácter representa un único carácter Unicode.</span><span class="sxs-lookup"><span data-stu-id="3dc71-104">Each *code point*, or character code, represents a single Unicode character.</span></span> <span data-ttu-id="3dc71-105">Puede contener una cadena de 0 a dos mil millones (2 ^ 31) caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="3dc71-105">A string can contain from 0 to approximately two billion (2 ^ 31) Unicode characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3dc71-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3dc71-106">Remarks</span></span>  
 <span data-ttu-id="3dc71-107">Use la `String` tipo de datos que contenga varios caracteres sin la sobrecarga de administración de la matriz de `Char()`, una matriz de `Char` elementos.</span><span class="sxs-lookup"><span data-stu-id="3dc71-107">Use the `String` data type to hold multiple characters without the array management overhead of `Char()`, an array of `Char` elements.</span></span>  
  
 <span data-ttu-id="3dc71-108">El valor predeterminado de `String` es `Nothing` (una referencia nula).</span><span class="sxs-lookup"><span data-stu-id="3dc71-108">The default value of `String` is `Nothing` (a null reference).</span></span> <span data-ttu-id="3dc71-109">Tenga en cuenta que esto no es igual que la cadena vacía (valor `""`).</span><span class="sxs-lookup"><span data-stu-id="3dc71-109">Note that this is not the same as the empty string (value `""`).</span></span>  
  
## <a name="unicode-characters"></a><span data-ttu-id="3dc71-110">Caracteres Unicode</span><span class="sxs-lookup"><span data-stu-id="3dc71-110">Unicode Characters</span></span>  
 <span data-ttu-id="3dc71-111">Los primeros puntos de 128 código (0 – 127) de Unicode corresponden a las letras y símbolos en un teclado US estándar.</span><span class="sxs-lookup"><span data-stu-id="3dc71-111">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="3dc71-112">Estos primeros puntos de 128 código son los mismos que los define el juego de caracteres ASCII.</span><span class="sxs-lookup"><span data-stu-id="3dc71-112">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="3dc71-113">El segundo 128 puntos de código (128-255) representan caracteres especiales, como letras del alfabeto latino, acentos, símbolos de moneda y fracciones.</span><span class="sxs-lookup"><span data-stu-id="3dc71-113">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="3dc71-114">Unicode utiliza los puntos de código restantes (256-65535) para una amplia variedad de símbolos.</span><span class="sxs-lookup"><span data-stu-id="3dc71-114">Unicode uses the remaining code points (256-65535) for a wide variety of symbols.</span></span> <span data-ttu-id="3dc71-115">Esto incluye caracteres de texto de todo el mundo, los signos diacríticos y símbolos técnicos y matemáticos.</span><span class="sxs-lookup"><span data-stu-id="3dc71-115">This includes worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>  
  
 <span data-ttu-id="3dc71-116">Puede usar métodos como <xref:System.Char.IsDigit%2A> y <xref:System.Char.IsPunctuation%2A> en un carácter individual en un `String` variable para determinar su clasificación Unicode.</span><span class="sxs-lookup"><span data-stu-id="3dc71-116">You can use methods such as <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on an individual character in a `String` variable to determine its Unicode classification.</span></span>  
  
## <a name="format-requirements"></a><span data-ttu-id="3dc71-117">Requisitos de formato</span><span class="sxs-lookup"><span data-stu-id="3dc71-117">Format Requirements</span></span>  
 <span data-ttu-id="3dc71-118">Debe incluir un `String` literal entre comillas (`" "`).</span><span class="sxs-lookup"><span data-stu-id="3dc71-118">You must enclose a `String` literal within quotation marks (`" "`).</span></span> <span data-ttu-id="3dc71-119">Si se debe incluir una comilla como uno de los caracteres de la cadena, utilice dos comillas contiguas (`""`).</span><span class="sxs-lookup"><span data-stu-id="3dc71-119">If you must include a quotation mark as one of the characters in the string, you use two contiguous quotation marks (`""`).</span></span> <span data-ttu-id="3dc71-120">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3dc71-120">The following example illustrates this.</span></span>  
  
```  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 <span data-ttu-id="3dc71-121">Tenga en cuenta que las comillas contiguas que representan una comilla en la cadena son independientes de las comillas que comienzan y terminan la `String` literal.</span><span class="sxs-lookup"><span data-stu-id="3dc71-121">Note that the contiguous quotation marks that represent a quotation mark in the string are independent of the quotation marks that begin and end the `String` literal.</span></span>  
  
## <a name="string-manipulations"></a><span data-ttu-id="3dc71-122">Manipulaciones de cadenas</span><span class="sxs-lookup"><span data-stu-id="3dc71-122">String Manipulations</span></span>  
 <span data-ttu-id="3dc71-123">Una vez que asigne una cadena a un `String` variable, esa cadena es *inmutable*, lo que significa que no puede cambiar su longitud ni su contenido.</span><span class="sxs-lookup"><span data-stu-id="3dc71-123">Once you assign a string to a `String` variable, that string is *immutable*, which means you cannot change its length or contents.</span></span> <span data-ttu-id="3dc71-124">Cuando se modifica una cadena de cualquier manera, Visual Basic crea una nueva cadena y abandona la anterior.</span><span class="sxs-lookup"><span data-stu-id="3dc71-124">When you alter a string in any way, Visual Basic creates a new string and abandons the previous one.</span></span> <span data-ttu-id="3dc71-125">El `String` variable apunta a la nueva cadena.</span><span class="sxs-lookup"><span data-stu-id="3dc71-125">The `String` variable then points to the new string.</span></span>  
  
 <span data-ttu-id="3dc71-126">Puede manipular el contenido de un `String` variable mediante una variedad de funciones de cadena.</span><span class="sxs-lookup"><span data-stu-id="3dc71-126">You can manipulate the contents of a `String` variable by using a variety of string functions.</span></span> <span data-ttu-id="3dc71-127">El siguiente ejemplo ilustra el <xref:Microsoft.VisualBasic.Strings.Left%2A> (función)</span><span class="sxs-lookup"><span data-stu-id="3dc71-127">The following example illustrates the <xref:Microsoft.VisualBasic.Strings.Left%2A> function</span></span>  
  
```  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 <span data-ttu-id="3dc71-128">Una cadena creada por otro componente podría estar rellena con espacios iniciales o finales.</span><span class="sxs-lookup"><span data-stu-id="3dc71-128">A string created by another component might be padded with leading or trailing spaces.</span></span> <span data-ttu-id="3dc71-129">Si recibe este tipo de cadena, puede usar el <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, y <xref:Microsoft.VisualBasic.Strings.RTrim%2A> funciones para quitar estos espacios.</span><span class="sxs-lookup"><span data-stu-id="3dc71-129">If you receive such a string, you can use the <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, and <xref:Microsoft.VisualBasic.Strings.RTrim%2A> functions to remove these spaces.</span></span>  
  
 <span data-ttu-id="3dc71-130">Para obtener más información acerca de las manipulaciones de cadenas, vea [cadenas](../../../visual-basic/programming-guide/language-features/strings/index.md).</span><span class="sxs-lookup"><span data-stu-id="3dc71-130">For more information about string manipulations, see [Strings](../../../visual-basic/programming-guide/language-features/strings/index.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="3dc71-131">Sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="3dc71-131">Programming Tips</span></span>  
  
-   <span data-ttu-id="3dc71-132">**Números negativos.**</span><span class="sxs-lookup"><span data-stu-id="3dc71-132">**Negative Numbers.**</span></span> <span data-ttu-id="3dc71-133">Recuerde que los caracteres mantienen por `String` están firmados y no puede representar los valores negativos.</span><span class="sxs-lookup"><span data-stu-id="3dc71-133">Remember that the characters held by `String` are unsigned and cannot represent negative values.</span></span> <span data-ttu-id="3dc71-134">En cualquier caso, no debe utilizar `String` para contener valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="3dc71-134">In any case, you should not use `String` to hold numeric values.</span></span>  
  
-   <span data-ttu-id="3dc71-135">**Consideraciones de interoperabilidad.**</span><span class="sxs-lookup"><span data-stu-id="3dc71-135">**Interop Considerations.**</span></span> <span data-ttu-id="3dc71-136">Si interactúa con componentes no escritos para .NET Framework, por ejemplo objetos de automatización o COM, recuerde que los caracteres de cadena tienen un ancho de datos diferentes (8 bits) en otros entornos.</span><span class="sxs-lookup"><span data-stu-id="3dc71-136">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that string characters have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="3dc71-137">Si se pasa un argumento de cadena de caracteres de 8 bits a esos componentes, declárelo como `Byte()`, una matriz de `Byte` elementos, en lugar de `String` en el nuevo código de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3dc71-137">If you are passing a string argument of 8-bit characters to such a component, declare it as `Byte()`, an array of `Byte` elements, instead of `String` in your new Visual Basic code.</span></span>  
  
-   <span data-ttu-id="3dc71-138">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="3dc71-138">**Type Characters.**</span></span> <span data-ttu-id="3dc71-139">Anexar el carácter de tipo identificador `$` a cualquier identificador lo fuerza a la `String` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="3dc71-139">Appending the identifier type character `$` to any identifier forces it to the `String` data type.</span></span> <span data-ttu-id="3dc71-140">`String` no tiene ningún carácter de tipo literal.</span><span class="sxs-lookup"><span data-stu-id="3dc71-140">`String` has no literal type character.</span></span> <span data-ttu-id="3dc71-141">Sin embargo, el compilador trata los literales incluidos entre comillas (`" "`) como `String`.</span><span class="sxs-lookup"><span data-stu-id="3dc71-141">However, the compiler treats literals enclosed in quotation marks (`" "`) as `String`.</span></span>  
  
-   <span data-ttu-id="3dc71-142">**Tipo de marco de trabajo.**</span><span class="sxs-lookup"><span data-stu-id="3dc71-142">**Framework Type.**</span></span> <span data-ttu-id="3dc71-143">El tipo correspondiente en .NET Framework es la <xref:System.String?displayProperty=nameWithType> clase.</span><span class="sxs-lookup"><span data-stu-id="3dc71-143">The corresponding type in the .NET Framework is the <xref:System.String?displayProperty=nameWithType> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dc71-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="3dc71-144">See also</span></span>

- <xref:System.String?displayProperty=nameWithType>
- [<span data-ttu-id="3dc71-145">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="3dc71-145">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="3dc71-146">Char (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="3dc71-146">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="3dc71-147">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="3dc71-147">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="3dc71-148">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="3dc71-148">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="3dc71-149">Cómo: Llamar a una función de Windows que adopta tipos sin signo</span><span class="sxs-lookup"><span data-stu-id="3dc71-149">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="3dc71-150">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="3dc71-150">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)

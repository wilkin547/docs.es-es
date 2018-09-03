---
title: Tipos de datos de caracteres (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
ms.openlocfilehash: 3b031c6e3dc04637128f95ca8e922d3298981287
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2018
ms.locfileid: "43462428"
---
# <a name="character-data-types-visual-basic"></a><span data-ttu-id="f6d3c-102">Tipos de datos de caracteres (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6d3c-102">Character Data Types (Visual Basic)</span></span>
<span data-ttu-id="f6d3c-103">Visual Basic ofrece *tipos de datos de caracteres* para tratar con caracteres que se puede mostrar e imprimir.</span><span class="sxs-lookup"><span data-stu-id="f6d3c-103">Visual Basic provides *character data types* to deal with printable and displayable characters.</span></span> <span data-ttu-id="f6d3c-104">Aunque ambas tienen que ver con los caracteres Unicode, `Char` contiene un único carácter, mientras que `String` contiene un número indefinido de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f6d3c-104">While they both deal with Unicode characters, `Char` holds a single character whereas `String` contains an indefinite number of characters.</span></span>  
  
 <span data-ttu-id="f6d3c-105">Para una tabla que muestra una comparación en paralelo de los tipos de datos de Visual Basic, vea [tipos de datos](../../../../visual-basic/language-reference/data-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="f6d3c-105">For a table that displays a side-by-side comparison of the Visual Basic data types, see [Data Types](../../../../visual-basic/language-reference/data-types/index.md).</span></span>  
  
## <a name="char-type"></a><span data-ttu-id="f6d3c-106">Tipo char</span><span class="sxs-lookup"><span data-stu-id="f6d3c-106">Char Type</span></span>  
 <span data-ttu-id="f6d3c-107">El `Char` tipo de datos es un único carácter Unicode de dos bytes (16 bits).</span><span class="sxs-lookup"><span data-stu-id="f6d3c-107">The `Char` data type is a single two-byte (16-bit) Unicode character.</span></span> <span data-ttu-id="f6d3c-108">Si una variable siempre almacena exactamente un carácter, declárelo como `Char`.</span><span class="sxs-lookup"><span data-stu-id="f6d3c-108">If a variable always stores exactly one character, declare it as `Char`.</span></span> <span data-ttu-id="f6d3c-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f6d3c-109">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#1)]
  
 <span data-ttu-id="f6d3c-110">Cada valor posible en un `Char` o `String` variable es un *punto de código*, o el código en el juego de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="f6d3c-110">Each possible value in a `Char` or `String` variable is a *code point*, or character code, in the Unicode character set.</span></span> <span data-ttu-id="f6d3c-111">Los caracteres Unicode incluyen el juego de caracteres ASCII básico, diversas otras letras del alfabeto, acentos, símbolos de moneda, fracciones, los signos diacríticos y símbolos técnicos y matemáticos.</span><span class="sxs-lookup"><span data-stu-id="f6d3c-111">Unicode characters include the basic ASCII character set, various other alphabet letters, accents, currency symbols, fractions, diacritics, and mathematical and technical symbols.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6d3c-112">Juego de caracteres Unicode recursos en reserva en los puntos de código D800 a DFFF (55296 a 55551 decimales) para *pares suplentes*, que requiere dos valores de 16 bits para representar un único punto de código.</span><span class="sxs-lookup"><span data-stu-id="f6d3c-112">The Unicode character set reserves the code points D800 through DFFF (55296 through 55551 decimal) for *surrogate pairs*, which require two 16-bit values to represent a single code point.</span></span> <span data-ttu-id="f6d3c-113">Un `Char` variable no puede contener un par suplente y un `String` utiliza dos posiciones que contiene un par de este tipo.</span><span class="sxs-lookup"><span data-stu-id="f6d3c-113">A `Char` variable cannot hold a surrogate pair, and a `String` uses two positions to hold such a pair.</span></span>  
  
 <span data-ttu-id="f6d3c-114">Para obtener más información, consulte [tipo de datos Char](../../../../visual-basic/language-reference/data-types/char-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="f6d3c-114">For more information, see [Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md).</span></span>  
  
## <a name="string-type"></a><span data-ttu-id="f6d3c-115">Tipo de cadena</span><span class="sxs-lookup"><span data-stu-id="f6d3c-115">String Type</span></span>  
 <span data-ttu-id="f6d3c-116">El `String` tipo de datos es una secuencia de cero o más caracteres Unicode de dos bytes (16 bits).</span><span class="sxs-lookup"><span data-stu-id="f6d3c-116">The `String` data type is a sequence of zero or more two-byte (16-bit) Unicode characters.</span></span> <span data-ttu-id="f6d3c-117">Si una variable puede contener un número indefinido de caracteres, declárelo como `String`.</span><span class="sxs-lookup"><span data-stu-id="f6d3c-117">If a variable can contain an indefinite number of characters, declare it as `String`.</span></span> <span data-ttu-id="f6d3c-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f6d3c-118">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#2)]
  
 <span data-ttu-id="f6d3c-119">Para obtener más información, consulte [tipo de datos String](../../../../visual-basic/language-reference/data-types/string-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="f6d3c-119">For more information, see [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6d3c-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6d3c-120">See Also</span></span>  
 [<span data-ttu-id="f6d3c-121">Tipos de datos básicos</span><span class="sxs-lookup"><span data-stu-id="f6d3c-121">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="f6d3c-122">Tipos de datos compuestos</span><span class="sxs-lookup"><span data-stu-id="f6d3c-122">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [<span data-ttu-id="f6d3c-123">Tipos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f6d3c-123">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="f6d3c-124">Tipos de valores y tipos de referencias</span><span class="sxs-lookup"><span data-stu-id="f6d3c-124">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="f6d3c-125">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f6d3c-125">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="f6d3c-126">Solución de problemas de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="f6d3c-126">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="f6d3c-127">Caracteres de tipo</span><span class="sxs-lookup"><span data-stu-id="f6d3c-127">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)

---
description: 'Más información sobre: tipos de datos de caracteres (Visual Basic)'
title: Tipos de datos de caracteres
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
ms.openlocfilehash: 2197c0210cb0c2287baff9856889334f5f95bd4d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466398"
---
# <a name="character-data-types-visual-basic"></a><span data-ttu-id="c57c9-103">Tipos de datos de caracteres (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c57c9-103">Character Data Types (Visual Basic)</span></span>

<span data-ttu-id="c57c9-104">Visual Basic proporciona *tipos de datos de caracteres* para tratar con caracteres imprimibles y que se pueda mostrar.</span><span class="sxs-lookup"><span data-stu-id="c57c9-104">Visual Basic provides *character data types* to deal with printable and displayable characters.</span></span> <span data-ttu-id="c57c9-105">Aunque ambos tratan con caracteres Unicode, `Char` contiene un solo carácter, mientras que `String` contiene un número indefinido de caracteres.</span><span class="sxs-lookup"><span data-stu-id="c57c9-105">While they both deal with Unicode characters, `Char` holds a single character whereas `String` contains an indefinite number of characters.</span></span>  
  
 <span data-ttu-id="c57c9-106">Para obtener una tabla en la que se muestra una comparación en paralelo de los tipos de datos Visual Basic, vea [tipos de datos](../../../language-reference/data-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="c57c9-106">For a table that displays a side-by-side comparison of the Visual Basic data types, see [Data Types](../../../language-reference/data-types/index.md).</span></span>  
  
## <a name="char-type"></a><span data-ttu-id="c57c9-107">Char (tipo)</span><span class="sxs-lookup"><span data-stu-id="c57c9-107">Char Type</span></span>  

 <span data-ttu-id="c57c9-108">El `Char` tipo de datos es un único carácter Unicode de dos bytes (16 bits).</span><span class="sxs-lookup"><span data-stu-id="c57c9-108">The `Char` data type is a single two-byte (16-bit) Unicode character.</span></span> <span data-ttu-id="c57c9-109">Si una variable siempre almacena exactamente un carácter, declárelo como `Char` .</span><span class="sxs-lookup"><span data-stu-id="c57c9-109">If a variable always stores exactly one character, declare it as `Char`.</span></span> <span data-ttu-id="c57c9-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c57c9-110">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#1)]
  
 <span data-ttu-id="c57c9-111">Cada valor posible de una `Char` `String` variable o es un *punto de código*, o código de carácter, en el juego de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="c57c9-111">Each possible value in a `Char` or `String` variable is a *code point*, or character code, in the Unicode character set.</span></span> <span data-ttu-id="c57c9-112">Los caracteres Unicode incluyen el juego de caracteres ASCII básico, otras letras, acentos, símbolos de moneda, fracciones, diacríticos y símbolos matemáticos y técnicos.</span><span class="sxs-lookup"><span data-stu-id="c57c9-112">Unicode characters include the basic ASCII character set, various other alphabet letters, accents, currency symbols, fractions, diacritics, and mathematical and technical symbols.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c57c9-113">El juego de caracteres Unicode reserva los puntos de código D800 a DFFF (de 55296 a 55551 decimal) para los *pares suplentes*, que requieren valores de 2 16 bits para representar un solo punto de código.</span><span class="sxs-lookup"><span data-stu-id="c57c9-113">The Unicode character set reserves the code points D800 through DFFF (55296 through 55551 decimal) for *surrogate pairs*, which require two 16-bit values to represent a single code point.</span></span> <span data-ttu-id="c57c9-114">Una `Char` variable no puede contener un par suplente y `String` usa dos posiciones para contener este tipo de par.</span><span class="sxs-lookup"><span data-stu-id="c57c9-114">A `Char` variable cannot hold a surrogate pair, and a `String` uses two positions to hold such a pair.</span></span>  
  
 <span data-ttu-id="c57c9-115">Para obtener más información, vea [Char (tipo de datos](../../../language-reference/data-types/char-data-type.md)).</span><span class="sxs-lookup"><span data-stu-id="c57c9-115">For more information, see [Char Data Type](../../../language-reference/data-types/char-data-type.md).</span></span>  
  
## <a name="string-type"></a><span data-ttu-id="c57c9-116">Tipo de cadena</span><span class="sxs-lookup"><span data-stu-id="c57c9-116">String Type</span></span>  

 <span data-ttu-id="c57c9-117">El `String` tipo de datos es una secuencia de cero o más caracteres Unicode de dos bytes (16 bits).</span><span class="sxs-lookup"><span data-stu-id="c57c9-117">The `String` data type is a sequence of zero or more two-byte (16-bit) Unicode characters.</span></span> <span data-ttu-id="c57c9-118">Si una variable puede contener un número indefinido de caracteres, declárelo como `String` .</span><span class="sxs-lookup"><span data-stu-id="c57c9-118">If a variable can contain an indefinite number of characters, declare it as `String`.</span></span> <span data-ttu-id="c57c9-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c57c9-119">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#2)]
  
 <span data-ttu-id="c57c9-120">Para obtener más información, vea [String (tipo de datos](../../../language-reference/data-types/string-data-type.md)).</span><span class="sxs-lookup"><span data-stu-id="c57c9-120">For more information, see [String Data Type](../../../language-reference/data-types/string-data-type.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c57c9-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c57c9-121">See also</span></span>

- [<span data-ttu-id="c57c9-122">Tipos de datos básicos</span><span class="sxs-lookup"><span data-stu-id="c57c9-122">Elementary Data Types</span></span>](elementary-data-types.md)
- [<span data-ttu-id="c57c9-123">Tipos de datos compuestos</span><span class="sxs-lookup"><span data-stu-id="c57c9-123">Composite Data Types</span></span>](composite-data-types.md)
- [<span data-ttu-id="c57c9-124">Tipos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c57c9-124">Generic Types in Visual Basic</span></span>](generic-types.md)
- [<span data-ttu-id="c57c9-125">Tipos de valor y tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="c57c9-125">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="c57c9-126">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c57c9-126">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="c57c9-127">Solución de problemas de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="c57c9-127">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="c57c9-128">Caracteres de tipo</span><span class="sxs-lookup"><span data-stu-id="c57c9-128">Type Characters</span></span>](type-characters.md)

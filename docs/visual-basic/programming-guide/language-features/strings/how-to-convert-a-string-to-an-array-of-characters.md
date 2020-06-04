---
title: Procedimiento para convertir una cadena en una matriz de caracteres
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: eca8cd7be8da1f6149dadf1e9edeab5e5225ab9f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360675"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a><span data-ttu-id="d3c46-102">Cómo: Convertir una cadena en una matriz de caracteres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d3c46-102">How to: Convert a String to an Array of Characters in Visual Basic</span></span>
<span data-ttu-id="d3c46-103">A veces resulta útil tener datos sobre los caracteres de la cadena y las posiciones de esos caracteres dentro de la cadena, como cuando se analiza una cadena.</span><span class="sxs-lookup"><span data-stu-id="d3c46-103">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string, such as when you are parsing a string.</span></span> <span data-ttu-id="d3c46-104">En este ejemplo se muestra cómo se puede obtener una matriz de los caracteres de una cadena mediante una llamada al método de la cadena <xref:System.String.ToCharArray%2A> .</span><span class="sxs-lookup"><span data-stu-id="d3c46-104">This example shows how you can get an array of the characters in a string by calling the string's <xref:System.String.ToCharArray%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3c46-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d3c46-105">Example</span></span>  
 <span data-ttu-id="d3c46-106">En este ejemplo se muestra cómo dividir una cadena en una `Char` matriz y cómo dividir una cadena en una `String` matriz de sus caracteres de texto Unicode.</span><span class="sxs-lookup"><span data-stu-id="d3c46-106">This example demonstrates how to split a string into a `Char` array, and how to split a string into a `String` array of its Unicode text characters.</span></span> <span data-ttu-id="d3c46-107">La razón de esta distinción es que los caracteres de texto Unicode pueden estar compuestos de dos o más `Char` caracteres (por ejemplo, un par suplente o una secuencia de caracteres de combinación).</span><span class="sxs-lookup"><span data-stu-id="d3c46-107">The reason for this distinction is that Unicode text characters can be composed of two or more `Char` characters (such as a surrogate pair or a combining character sequence).</span></span> <span data-ttu-id="d3c46-108">Para obtener más información, vea <xref:System.Globalization.TextElementEnumerator> y [el estándar Unicode](https://www.unicode.org/standard/standard.html).</span><span class="sxs-lookup"><span data-stu-id="d3c46-108">For more information, see <xref:System.Globalization.TextElementEnumerator> and [The Unicode Standard](https://www.unicode.org/standard/standard.html).</span></span>  
  
 [!code-vb[VbVbalrStrings#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#75)]  
  
## <a name="example"></a><span data-ttu-id="d3c46-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d3c46-109">Example</span></span>  
 <span data-ttu-id="d3c46-110">Es más difícil dividir una cadena en sus caracteres de texto Unicode, pero esto es necesario si necesita información sobre la representación visual de una cadena.</span><span class="sxs-lookup"><span data-stu-id="d3c46-110">It is more difficult to split a string into its Unicode text characters, but this is necessary if you need information about the visual representation of a string.</span></span> <span data-ttu-id="d3c46-111">En este ejemplo se utiliza el <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> método para obtener información sobre los caracteres de texto Unicode que componen una cadena.</span><span class="sxs-lookup"><span data-stu-id="d3c46-111">This example uses the <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> method to get information about the Unicode text characters that make up a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#76)]  
  
## <a name="see-also"></a><span data-ttu-id="d3c46-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d3c46-112">See also</span></span>

- <xref:System.String.Chars%2A>
- <xref:System.Globalization.StringInfo?displayProperty=nameWithType>
- [<span data-ttu-id="d3c46-113">Procedimiento para obtener acceso a caracteres de cadenas</span><span class="sxs-lookup"><span data-stu-id="d3c46-113">How to: Access Characters in Strings</span></span>](how-to-access-characters-in-strings.md)
- [<span data-ttu-id="d3c46-114">Conversión entre cadenas y otros tipos de datos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d3c46-114">Converting Between Strings and Other Data Types in Visual Basic</span></span>](converting-between-strings-and-other-data-types.md)
- [<span data-ttu-id="d3c46-115">Cadenas</span><span class="sxs-lookup"><span data-stu-id="d3c46-115">Strings</span></span>](index.md)

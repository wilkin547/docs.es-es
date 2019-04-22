---
title: Procedimiento Convertir una cadena en una matriz de caracteres en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: 921d7ad62545d3a29870aee6c6b354fdadeb0500
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58823316"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a><span data-ttu-id="3ea7a-102">Procedimiento Convertir una cadena en una matriz de caracteres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3ea7a-102">How to: Convert a String to an Array of Characters in Visual Basic</span></span>
<span data-ttu-id="3ea7a-103">A veces resulta útil tener información sobre los caracteres de la cadena y las posiciones de los caracteres dentro de la cadena, como cuando se está analizando una cadena.</span><span class="sxs-lookup"><span data-stu-id="3ea7a-103">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string, such as when you are parsing a string.</span></span> <span data-ttu-id="3ea7a-104">En este ejemplo muestra cómo puede obtener una matriz de los caracteres en una cadena mediante una llamada a la cadena <xref:System.String.ToCharArray%2A> método.</span><span class="sxs-lookup"><span data-stu-id="3ea7a-104">This example shows how you can get an array of the characters in a string by calling the string's <xref:System.String.ToCharArray%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ea7a-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3ea7a-105">Example</span></span>  
 <span data-ttu-id="3ea7a-106">En este ejemplo se muestra cómo dividir una cadena en un `Char` matriz y cómo dividir una cadena en un `String` matriz de sus caracteres de texto Unicode.</span><span class="sxs-lookup"><span data-stu-id="3ea7a-106">This example demonstrates how to split a string into a `Char` array, and how to split a string into a `String` array of its Unicode text characters.</span></span> <span data-ttu-id="3ea7a-107">La razón de esta distinción es que los caracteres de texto Unicode pueden estar compuestos de dos o más `Char` caracteres (por ejemplo, un par suplente o una combinación secuencia de caracteres).</span><span class="sxs-lookup"><span data-stu-id="3ea7a-107">The reason for this distinction is that Unicode text characters can be composed of two or more `Char` characters (such as a surrogate pair or a combining character sequence).</span></span> <span data-ttu-id="3ea7a-108">Para obtener más información, consulte <xref:System.Globalization.TextElementEnumerator> y [el estándar Unicode](https://www.unicode.org/standard/standard.html).</span><span class="sxs-lookup"><span data-stu-id="3ea7a-108">For more information, see <xref:System.Globalization.TextElementEnumerator> and [The Unicode Standard](https://www.unicode.org/standard/standard.html).</span></span>  
  
 [!code-vb[VbVbalrStrings#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#75)]  
  
## <a name="example"></a><span data-ttu-id="3ea7a-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3ea7a-109">Example</span></span>  
 <span data-ttu-id="3ea7a-110">Es más difícil dividir una cadena en sus caracteres de texto Unicode, pero esto es necesario si necesita información sobre la representación visual de una cadena.</span><span class="sxs-lookup"><span data-stu-id="3ea7a-110">It is more difficult to split a string into its Unicode text characters, but this is necessary if you need information about the visual representation of a string.</span></span> <span data-ttu-id="3ea7a-111">Este ejemplo se usa el <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> método para obtener información acerca de los caracteres de texto Unicode que componen una cadena.</span><span class="sxs-lookup"><span data-stu-id="3ea7a-111">This example uses the <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> method to get information about the Unicode text characters that make up a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#76)]  
  
## <a name="see-also"></a><span data-ttu-id="3ea7a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ea7a-112">See also</span></span>

- <xref:System.String.Chars%2A>
- <xref:System.Globalization.StringInfo?displayProperty=nameWithType>
- [<span data-ttu-id="3ea7a-113">Cómo: Acceso a caracteres en cadenas</span><span class="sxs-lookup"><span data-stu-id="3ea7a-113">How to: Access Characters in Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)
- [<span data-ttu-id="3ea7a-114">Conversión entre cadenas y otros tipos de datos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3ea7a-114">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [<span data-ttu-id="3ea7a-115">Cadenas</span><span class="sxs-lookup"><span data-stu-id="3ea7a-115">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)

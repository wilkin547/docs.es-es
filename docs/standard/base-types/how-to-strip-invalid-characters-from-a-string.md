---
title: 'Cómo: Quitar caracteres no válidos de una cadena'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regular expressions, examples
- cleaning input
- user input, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- Regex.Replace method
- stripping invalid characters
- Replace method
- validating user input
ms.assetid: b4319c8a-9032-4129-a9d5-6f6fc28e7f32
ms.openlocfilehash: cc90e6609f9335b7e2f08271e5540b182901e8c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73127652"
---
# <a name="how-to-strip-invalid-characters-from-a-string"></a><span data-ttu-id="23c4b-102">Cómo: Quitar caracteres no válidos de una cadena</span><span class="sxs-lookup"><span data-stu-id="23c4b-102">How to: Strip Invalid Characters from a String</span></span>
<span data-ttu-id="23c4b-103">En el ejemplo siguiente se usa el método estático <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> para quitar caracteres no válidos de una cadena.</span><span class="sxs-lookup"><span data-stu-id="23c4b-103">The following example uses the static <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> method to strip invalid characters from a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23c4b-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="23c4b-104">Example</span></span>  
 <span data-ttu-id="23c4b-105">Puede usar el método `CleanInput` definido en este ejemplo para quitar caracteres potencialmente perjudiciales que se hayan escrito en un campo de texto que acepta datos del usuario.</span><span class="sxs-lookup"><span data-stu-id="23c4b-105">You can use the `CleanInput` method defined in this example to strip potentially harmful characters that have been entered into a text field that accepts user input.</span></span> <span data-ttu-id="23c4b-106">En este caso, `CleanInput` elimina todos los caracteres no alfanuméricos excepto puntos (.), símbolos de arroba (@) y guiones (-), y devuelve la cadena restante.</span><span class="sxs-lookup"><span data-stu-id="23c4b-106">In this case, `CleanInput` strips out all nonalphanumeric characters except periods (.), at symbols (@), and hyphens (-), and returns the remaining string.</span></span> <span data-ttu-id="23c4b-107">Pero puede modificar el patrón de expresión regular para que elimine todos los caracteres que no deban incluirse en una cadena de entrada.</span><span class="sxs-lookup"><span data-stu-id="23c4b-107">However, you can modify the regular expression pattern so that it strips out any characters that should not be included in an input string.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/vb/Example.vb#1)]  
  
 <span data-ttu-id="23c4b-108">El patrón de expresión regular `[^\w\.@-]` coincide con cualquier carácter que no sea un carácter de palabra, un punto, un símbolo @ o un guion.</span><span class="sxs-lookup"><span data-stu-id="23c4b-108">The regular expression pattern `[^\w\.@-]` matches any character that is not a word character, a period, an @ symbol, or a hyphen.</span></span> <span data-ttu-id="23c4b-109">Un carácter de palabra es cualquier letra, dígito decimal o conector de puntuación, como un guion bajo.</span><span class="sxs-lookup"><span data-stu-id="23c4b-109">A word character is any letter, decimal digit, or punctuation connector such as an underscore.</span></span> <span data-ttu-id="23c4b-110">Cualquier carácter que coincida con este patrón se sustituye por <xref:System.String.Empty?displayProperty=nameWithType>, que es la cadena definida por el modelo de reemplazo.</span><span class="sxs-lookup"><span data-stu-id="23c4b-110">Any character that matches this pattern is replaced by <xref:System.String.Empty?displayProperty=nameWithType>, which is the string defined by the replacement pattern.</span></span> <span data-ttu-id="23c4b-111">Para permitir caracteres adicionales en la entrada de usuario, agregue esos caracteres a la clase de caracteres en el patrón de la expresión regular.</span><span class="sxs-lookup"><span data-stu-id="23c4b-111">To allow additional characters in user input, add those characters to the character class in the regular expression pattern.</span></span> <span data-ttu-id="23c4b-112">Por ejemplo, el patrón de expresión regular `[^\w\.@-\\%]`también permite un símbolo de porcentaje y una barra diagonal inversa en la cadena de entrada.</span><span class="sxs-lookup"><span data-stu-id="23c4b-112">For example, the regular expression pattern `[^\w\.@-\\%]` also allows a percentage symbol and a backslash in an input string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23c4b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="23c4b-113">See also</span></span>

- [<span data-ttu-id="23c4b-114">Expresiones regulares de .NET</span><span class="sxs-lookup"><span data-stu-id="23c4b-114">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)

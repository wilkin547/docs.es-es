---
title: Procedimiento para quitar caracteres no válidos de una cadena
description: Vea un ejemplo en el que se muestra cómo quitar caracteres potencialmente peligrosos de una cadena mediante el método estático Regex.Replace.
ms.date: 06/30/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regular expressions, examples
- cleaning input
- user input, examples
- .NET regular expressions, examples
- regular expressions [.NET], examples
- Regex.Replace method
- stripping invalid characters
- Replace method
- validating user input
ms.assetid: b4319c8a-9032-4129-a9d5-6f6fc28e7f32
ms.openlocfilehash: 3d89a4697b58222cb218c11fe713a87c9b0fbdb8
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94823048"
---
# <a name="how-to-strip-invalid-characters-from-a-string"></a><span data-ttu-id="ca592-103">Procedimiento para quitar caracteres no válidos de una cadena</span><span class="sxs-lookup"><span data-stu-id="ca592-103">How to: Strip Invalid Characters from a String</span></span>
<span data-ttu-id="ca592-104">En el ejemplo siguiente se usa el método estático <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> para quitar caracteres no válidos de una cadena.</span><span class="sxs-lookup"><span data-stu-id="ca592-104">The following example uses the static <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> method to strip invalid characters from a string.</span></span>  

[!INCLUDE [regex](../../../includes/regex.md)]

## <a name="example"></a><span data-ttu-id="ca592-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ca592-105">Example</span></span>  
 <span data-ttu-id="ca592-106">Puede usar el método `CleanInput` definido en este ejemplo para quitar caracteres potencialmente perjudiciales que se hayan escrito en un campo de texto que acepta datos del usuario.</span><span class="sxs-lookup"><span data-stu-id="ca592-106">You can use the `CleanInput` method defined in this example to strip potentially harmful characters that have been entered into a text field that accepts user input.</span></span> <span data-ttu-id="ca592-107">En este caso, `CleanInput` elimina todos los caracteres no alfanuméricos excepto puntos (.), símbolos de arroba (@) y guiones (-), y devuelve la cadena restante.</span><span class="sxs-lookup"><span data-stu-id="ca592-107">In this case, `CleanInput` strips out all nonalphanumeric characters except periods (.), at symbols (@), and hyphens (-), and returns the remaining string.</span></span> <span data-ttu-id="ca592-108">Pero puede modificar el patrón de expresión regular para que elimine todos los caracteres que no deban incluirse en una cadena de entrada.</span><span class="sxs-lookup"><span data-stu-id="ca592-108">However, you can modify the regular expression pattern so that it strips out any characters that should not be included in an input string.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/vb/Example.vb#1)]  
  
 <span data-ttu-id="ca592-109">El patrón de expresión regular `[^\w\.@-]` coincide con cualquier carácter que no sea un carácter de palabra, un punto, un símbolo @ o un guion.</span><span class="sxs-lookup"><span data-stu-id="ca592-109">The regular expression pattern `[^\w\.@-]` matches any character that is not a word character, a period, an @ symbol, or a hyphen.</span></span> <span data-ttu-id="ca592-110">Un carácter de palabra es cualquier letra, dígito decimal o conector de puntuación, como un guion bajo.</span><span class="sxs-lookup"><span data-stu-id="ca592-110">A word character is any letter, decimal digit, or punctuation connector such as an underscore.</span></span> <span data-ttu-id="ca592-111">Cualquier carácter que coincida con este patrón se sustituye por <xref:System.String.Empty?displayProperty=nameWithType>, que es la cadena definida por el modelo de reemplazo.</span><span class="sxs-lookup"><span data-stu-id="ca592-111">Any character that matches this pattern is replaced by <xref:System.String.Empty?displayProperty=nameWithType>, which is the string defined by the replacement pattern.</span></span> <span data-ttu-id="ca592-112">Para permitir caracteres adicionales en la entrada de usuario, agregue esos caracteres a la clase de caracteres en el patrón de la expresión regular.</span><span class="sxs-lookup"><span data-stu-id="ca592-112">To allow additional characters in user input, add those characters to the character class in the regular expression pattern.</span></span> <span data-ttu-id="ca592-113">Por ejemplo, el patrón de expresión regular `[^\w\.@-\\%]`también permite un símbolo de porcentaje y una barra diagonal inversa en la cadena de entrada.</span><span class="sxs-lookup"><span data-stu-id="ca592-113">For example, the regular expression pattern `[^\w\.@-\\%]` also allows a percentage symbol and a backslash in an input string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca592-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca592-114">See also</span></span>

- [<span data-ttu-id="ca592-115">Expresiones regulares de .NET</span><span class="sxs-lookup"><span data-stu-id="ca592-115">.NET Regular Expressions</span></span>](regular-expressions.md)

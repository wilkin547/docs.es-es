---
title: "Cómo: Analizar cadenas mediante String.Split (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: d74c1d0760d4e776c2cf4c7dea1dac060c85a83c
ms.openlocfilehash: e25dbf6b86c82808622377c0618cd956541c6e09
ms.contentlocale: es-es
ms.lasthandoff: 09/05/2017

---
# <a name="how-to-parse-strings-using-stringsplit-c-programming-guide"></a><span data-ttu-id="6377f-102">Cómo: Analizar cadenas mediante String.Split (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="6377f-102">How to: Parse Strings Using String.Split (C# Programming Guide)</span></span>
<span data-ttu-id="6377f-103">En el ejemplo de código siguiente se muestra cómo se puede analizar una consulta mediante el método <xref:System.String.Split%2A?displayProperty=fullName> .</span><span class="sxs-lookup"><span data-stu-id="6377f-103">The following code example demonstrates how a string can be parsed using the <xref:System.String.Split%2A?displayProperty=fullName> method.</span></span> <span data-ttu-id="6377f-104">Como entrada, <xref:System.String.Split%2A> toma una matriz de caracteres que indica qué caracteres separan las cadenas sub interesantes de la cadena de destino.</span><span class="sxs-lookup"><span data-stu-id="6377f-104">As input, <xref:System.String.Split%2A> takes an array of characters that indicate which characters separate interesting sub strings of the target string.</span></span>  <span data-ttu-id="6377f-105">La función devuelve una matriz de cadenas sub.</span><span class="sxs-lookup"><span data-stu-id="6377f-105">The function returns an array of the sub strings.</span></span>  
  
 <span data-ttu-id="6377f-106">Este ejemplo usa espacios, comas, puntos, dos puntos y tabulaciones pasados en una matriz que contiene estos caracteres de separación <xref:System.String.Split%2A>.</span><span class="sxs-lookup"><span data-stu-id="6377f-106">This example uses spaces, commas, periods, colons, and tabs, all passed in an array containing these separating characters to <xref:System.String.Split%2A>.</span></span>  <span data-ttu-id="6377f-107">Cada palabra de la frase de la cadena de destino se muestra por separado de la matriz de cadenas resultante.</span><span class="sxs-lookup"><span data-stu-id="6377f-107">Each word in the target string's sentence displays separately from the resulting array of strings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6377f-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6377f-108">Example</span></span>  
 <span data-ttu-id="6377f-109">[!code-cs[csProgGuideStrings#16](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-parse-strings-using-string-split_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6377f-109">[!code-cs[csProgGuideStrings#16](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-parse-strings-using-string-split_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="6377f-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6377f-110">Example</span></span>  
 <span data-ttu-id="6377f-111">De forma predeterminada, String.Split devuelve las cadenas vacías cuando dos caracteres de separación aparecen de manera contigua en la cadena de destino.</span><span class="sxs-lookup"><span data-stu-id="6377f-111">By default, String.Split returns empty strings when two separating characters appear contiguously in the target string.</span></span>  <span data-ttu-id="6377f-112">Puede pasar un parámetro StringSplitOptions.RemoveEmptyEntries opcional para excluir las cadenas vacías en la salida.</span><span class="sxs-lookup"><span data-stu-id="6377f-112">You can pass an optional StringSplitOptions.RemoveEmptyEntries parameter to exclude any empty strings in the output.</span></span>  
  
 <span data-ttu-id="6377f-113">String.Split puede tomar una matriz de cadenas (secuencias de caracteres que actúan como separadores para analizar la cadena de destino, en lugar de caracteres individuales).</span><span class="sxs-lookup"><span data-stu-id="6377f-113">String.Split can take an array of strings (character sequences that act as separators for parsing the target string, instead of single characters).</span></span>  
  
```csharp  
class TestStringSplit  
{  
    static void Main()  
    {  
        string[] separatingChars = { "<<", "..." };  
  
        string text = "one<<two......three<four";  
        System.Console.WriteLine("Original text: '{0}'", text);  
  
        string[] words = text.Split(separatingChars, System.StringSplitOptions.RemoveEmptyEntries );  
        System.Console.WriteLine("{0} substrings in text:", words.Length);  
  
        foreach (string s in words)  
        {  
            System.Console.WriteLine(s);  
        }  
  
        // Keep the console window open in debug mode.  
        System.Console.WriteLine("Press any key to exit.");  
        System.Console.ReadKey();  
    }  
}  
/* Output:  
    Original text: 'one<<two......three<four'  
    3 words in text:  
    one  
    two  
    three<four  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="6377f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="6377f-114">See Also</span></span>  
 <span data-ttu-id="6377f-115">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6377f-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="6377f-116">[Cadenas](../../../csharp/programming-guide/strings/index.md) </span><span class="sxs-lookup"><span data-stu-id="6377f-116">[Strings](../../../csharp/programming-guide/strings/index.md) </span></span>  
 [<span data-ttu-id="6377f-117">Expresiones regulares de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6377f-117">.NET Framework Regular Expressions</span></span>](https://msdn.microsoft.com/library/hs600312)


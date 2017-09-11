---
title: "Cómo: Buscar cadenas mediante expresiones regulares (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- searching strings [C#]
- strings [C#], searching with RegEx
ms.assetid: dcab2150-a4a2-4fe4-87e3-83b83b58d84a
caps.latest.revision: 19
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
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: fb05d1702c75be8fd224ee0f34d7d8d3fe71f207
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-search-strings-using-regular-expressions-c-programming-guide"></a><span data-ttu-id="d39a4-102">Cómo: Buscar cadenas mediante expresiones regulares (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="d39a4-102">How to: Search Strings Using Regular Expressions (C# Programming Guide)</span></span>
<span data-ttu-id="d39a4-103">La clase <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> se puede usar para buscar cadenas.</span><span class="sxs-lookup"><span data-stu-id="d39a4-103">The <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> class can be used to search strings.</span></span> <span data-ttu-id="d39a4-104">Estas búsquedas pueden tener distinta complejidad, desde ser muy sencillas hasta hacer un gran uso de expresiones regulares.</span><span class="sxs-lookup"><span data-stu-id="d39a4-104">These searches can range in complexity from very simple to making full use of regular expressions.</span></span> <span data-ttu-id="d39a4-105">A continuación se ofrecen dos ejemplos de búsqueda de cadenas usando la clase <xref:System.Text.RegularExpressions.Regex>.</span><span class="sxs-lookup"><span data-stu-id="d39a4-105">The following are two examples of string searching by using the <xref:System.Text.RegularExpressions.Regex> class.</span></span> <span data-ttu-id="d39a4-106">Para obtener más información, vea [Expresiones regulares de .NET Framework](https://msdn.microsoft.com/library/hs600312).</span><span class="sxs-lookup"><span data-stu-id="d39a4-106">For more information, see [.NET Framework Regular Expressions](https://msdn.microsoft.com/library/hs600312).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d39a4-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d39a4-107">Example</span></span>  
 <span data-ttu-id="d39a4-108">El código siguiente es una aplicación de consola que realiza una búsqueda simple de cadenas sin distinción entre mayúsculas y minúsculas en una matriz.</span><span class="sxs-lookup"><span data-stu-id="d39a4-108">The following code is a console application that performs a simple case-insensitive search of the strings in an array.</span></span> <span data-ttu-id="d39a4-109">El método estático <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=fullName> realiza la búsqueda a partir de la cadena de búsqueda y de una cadena que contiene el modelo de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d39a4-109">The static method <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=fullName> performs the search given the string to search and a string that contains the search pattern.</span></span> <span data-ttu-id="d39a4-110">En este caso, se usa un tercer argumento para indicar que no se debe distinguir entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="d39a4-110">In this case, a third argument is used to indicate that case should be ignored.</span></span> <span data-ttu-id="d39a4-111">Para obtener más información, consulta <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="d39a4-111">For more information, see <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="d39a4-112">[!code-cs[csProgGuideStrings#17](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d39a4-112">[!code-cs[csProgGuideStrings#17](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="d39a4-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d39a4-113">Example</span></span>  
 <span data-ttu-id="d39a4-114">El código siguiente es una aplicación de consola que usa expresiones regulares para validar el formato de cada cadena de una matriz.</span><span class="sxs-lookup"><span data-stu-id="d39a4-114">The following code is a console application that uses regular expressions to validate the format of each string in an array.</span></span> <span data-ttu-id="d39a4-115">La validación requiere que cada cadena tenga la forma de un número de teléfono en el que tres grupos de dígitos se separan por guiones. Los dos primeros grupos contienen tres dígitos, y el tercero, cuatro.</span><span class="sxs-lookup"><span data-stu-id="d39a4-115">The validation requires that each string take the form of a telephone number in which three groups of digits are separated by dashes, the first two groups contain three digits, and the third group contains four digits.</span></span> <span data-ttu-id="d39a4-116">Para ello, se usa la expresión regular `^\\d{3}-\\d{3}-\\d{4}$`.</span><span class="sxs-lookup"><span data-stu-id="d39a4-116">This is done by using the regular expression `^\\d{3}-\\d{3}-\\d{4}$`.</span></span> <span data-ttu-id="d39a4-117">Para obtener más información, consulte [Lenguaje de expresiones regulares: Referencia rápida](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c).</span><span class="sxs-lookup"><span data-stu-id="d39a4-117">For more information, see [Regular Expression Language - Quick Reference](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c).</span></span>  
  
 <span data-ttu-id="d39a4-118">[!code-cs[csProgGuideStrings#18](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="d39a4-118">[!code-cs[csProgGuideStrings#18](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d39a4-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="d39a4-119">See Also</span></span>  
 <span data-ttu-id="d39a4-120"><xref:System.Text.RegularExpressions.Regex?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d39a4-120"><xref:System.Text.RegularExpressions.Regex?displayProperty=fullName></span></span>   
 <span data-ttu-id="d39a4-121">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d39a4-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d39a4-122">[Cadenas](../../../csharp/programming-guide/strings/index.md) </span><span class="sxs-lookup"><span data-stu-id="d39a4-122">[Strings](../../../csharp/programming-guide/strings/index.md) </span></span>  
 <span data-ttu-id="d39a4-123">[Expresiones regulares de .NET Framework](https://msdn.microsoft.com/library/hs600312) </span><span class="sxs-lookup"><span data-stu-id="d39a4-123">[.NET Framework Regular Expressions](https://msdn.microsoft.com/library/hs600312) </span></span>  
 [<span data-ttu-id="d39a4-124">Lenguaje de expresiones regulares: referencia rápida</span><span class="sxs-lookup"><span data-stu-id="d39a4-124">Regular Expression Language - Quick Reference</span></span>](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c)


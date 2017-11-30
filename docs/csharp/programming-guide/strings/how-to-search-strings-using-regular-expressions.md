---
title: "Cómo: Buscar cadenas mediante expresiones regulares (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- searching strings [C#]
- strings [C#], searching with RegEx
ms.assetid: dcab2150-a4a2-4fe4-87e3-83b83b58d84a
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c851c57b44f1343816b905db002e530121fb6c0a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-search-strings-using-regular-expressions-c-programming-guide"></a><span data-ttu-id="5b2e5-102">Cómo: Buscar cadenas mediante expresiones regulares (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="5b2e5-102">How to: Search Strings Using Regular Expressions (C# Programming Guide)</span></span>
<span data-ttu-id="5b2e5-103">La clase <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> se puede usar para buscar cadenas.</span><span class="sxs-lookup"><span data-stu-id="5b2e5-103">The <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> class can be used to search strings.</span></span> <span data-ttu-id="5b2e5-104">Estas búsquedas pueden tener distinta complejidad, desde ser muy sencillas hasta hacer un gran uso de expresiones regulares.</span><span class="sxs-lookup"><span data-stu-id="5b2e5-104">These searches can range in complexity from very simple to making full use of regular expressions.</span></span> <span data-ttu-id="5b2e5-105">A continuación se ofrecen dos ejemplos de búsqueda de cadenas usando la clase <xref:System.Text.RegularExpressions.Regex>.</span><span class="sxs-lookup"><span data-stu-id="5b2e5-105">The following are two examples of string searching by using the <xref:System.Text.RegularExpressions.Regex> class.</span></span> <span data-ttu-id="5b2e5-106">Para obtener más información, vea [Expresiones regulares de .NET Framework](https://msdn.microsoft.com/library/hs600312).</span><span class="sxs-lookup"><span data-stu-id="5b2e5-106">For more information, see [.NET Framework Regular Expressions](https://msdn.microsoft.com/library/hs600312).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b2e5-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5b2e5-107">Example</span></span>  
 <span data-ttu-id="5b2e5-108">El código siguiente es una aplicación de consola que realiza una búsqueda simple de cadenas sin distinción entre mayúsculas y minúsculas en una matriz.</span><span class="sxs-lookup"><span data-stu-id="5b2e5-108">The following code is a console application that performs a simple case-insensitive search of the strings in an array.</span></span> <span data-ttu-id="5b2e5-109">El método estático <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> realiza la búsqueda a partir de la cadena de búsqueda y de una cadena que contiene el modelo de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="5b2e5-109">The static method <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> performs the search given the string to search and a string that contains the search pattern.</span></span> <span data-ttu-id="5b2e5-110">En este caso, se usa un tercer argumento para indicar que no se debe distinguir entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="5b2e5-110">In this case, a third argument is used to indicate that case should be ignored.</span></span> <span data-ttu-id="5b2e5-111">Para obtener más información, consulta <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5b2e5-111">For more information, see <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType>.</span></span>  
  
 [!code-csharp[csProgGuideStrings#17](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="5b2e5-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5b2e5-112">Example</span></span>  
 <span data-ttu-id="5b2e5-113">El código siguiente es una aplicación de consola que usa expresiones regulares para validar el formato de cada cadena de una matriz.</span><span class="sxs-lookup"><span data-stu-id="5b2e5-113">The following code is a console application that uses regular expressions to validate the format of each string in an array.</span></span> <span data-ttu-id="5b2e5-114">La validación requiere que cada cadena tenga la forma de un número de teléfono en el que tres grupos de dígitos se separan por guiones. Los dos primeros grupos contienen tres dígitos, y el tercero, cuatro.</span><span class="sxs-lookup"><span data-stu-id="5b2e5-114">The validation requires that each string take the form of a telephone number in which three groups of digits are separated by dashes, the first two groups contain three digits, and the third group contains four digits.</span></span> <span data-ttu-id="5b2e5-115">Para ello, se usa la expresión regular `^\\d{3}-\\d{3}-\\d{4}$`.</span><span class="sxs-lookup"><span data-stu-id="5b2e5-115">This is done by using the regular expression `^\\d{3}-\\d{3}-\\d{4}$`.</span></span> <span data-ttu-id="5b2e5-116">Para obtener más información, consulte [Lenguaje de expresiones regulares: Referencia rápida](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c).</span><span class="sxs-lookup"><span data-stu-id="5b2e5-116">For more information, see [Regular Expression Language - Quick Reference](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c).</span></span>  
  
 [!code-csharp[csProgGuideStrings#18](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="5b2e5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b2e5-117">See Also</span></span>  
 <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType>  
 [<span data-ttu-id="5b2e5-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="5b2e5-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5b2e5-119">Cadenas</span><span class="sxs-lookup"><span data-stu-id="5b2e5-119">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)  
 [<span data-ttu-id="5b2e5-120">Expresiones regulares de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5b2e5-120">.NET Framework Regular Expressions</span></span>](https://msdn.microsoft.com/library/hs600312)  
 [<span data-ttu-id="5b2e5-121">Lenguaje de expresiones regulares: referencia rápida</span><span class="sxs-lookup"><span data-stu-id="5b2e5-121">Regular Expression Language - Quick Reference</span></span>](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c)

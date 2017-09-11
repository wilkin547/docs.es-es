---
title: "Cómo: Concatenar varias cadenas (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b191a61258a496115a4d7045046f9b4a2dbee58c
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-concatenate-multiple-strings-c-programming-guide"></a><span data-ttu-id="059b4-102">Cómo: Concatenar varias cadenas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="059b4-102">How to: Concatenate Multiple Strings (C# Programming Guide)</span></span>
<span data-ttu-id="059b4-103">*Concatenación* es el proceso de anexar una cadena al final de otra cadena.</span><span class="sxs-lookup"><span data-stu-id="059b4-103">*Concatenation* is the process of appending one string to the end of another string.</span></span> <span data-ttu-id="059b4-104">Cuando concatena literales de cadena o constantes de cadena con el operador `+`, el compilador crea una cadena única.</span><span class="sxs-lookup"><span data-stu-id="059b4-104">When you concatenate string literals or string constants by using the `+` operator, the compiler creates a single string.</span></span> <span data-ttu-id="059b4-105">No se produce ninguna concatenación en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="059b4-105">No run time concatenation occurs.</span></span> <span data-ttu-id="059b4-106">En cambio, las variables de cadena pueden concatenarse solo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="059b4-106">However, string variables can be concatenated only at run time.</span></span> <span data-ttu-id="059b4-107">En este caso, debe entender las implicaciones de rendimiento de los diversos enfoques.</span><span class="sxs-lookup"><span data-stu-id="059b4-107">In this case, you should understand the performance implications of the various approaches.</span></span>  
  
## <a name="example"></a><span data-ttu-id="059b4-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="059b4-108">Example</span></span>  
 <span data-ttu-id="059b4-109">En el ejemplo siguiente se muestra cómo dividir un literal de cadena larga en cadenas más pequeñas para mejorar la legibilidad en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="059b4-109">The following example shows how to split a long string literal into smaller strings in order to improve readability in the source code.</span></span> <span data-ttu-id="059b4-110">Estas partes se concatenarán en una sola cadena en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="059b4-110">These parts will be concatenated into a single string at compile time.</span></span> <span data-ttu-id="059b4-111">No existe ningún costo de rendimiento en tiempo de ejecución independientemente del número de cadenas implicadas.</span><span class="sxs-lookup"><span data-stu-id="059b4-111">There is no run time performance cost regardless of the number of strings involved.</span></span>  
  
 <span data-ttu-id="059b4-112">[!code-cs[csProgGuideStrings#30](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="059b4-112">[!code-cs[csProgGuideStrings#30](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="059b4-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="059b4-113">Example</span></span>  
 <span data-ttu-id="059b4-114">Para concatenar variables de cadena, puede usar los operadores `+` o `+=`, o los métodos <xref:System.String.Concat%2A?displayProperty=fullName>, <xref:System.String.Format%2A?displayProperty=fullName> o <xref:System.Text.StringBuilder.Append%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="059b4-114">To concatenate string variables, you can use the `+` or `+=` operators, or the <xref:System.String.Concat%2A?displayProperty=fullName>, <xref:System.String.Format%2A?displayProperty=fullName> or <xref:System.Text.StringBuilder.Append%2A?displayProperty=fullName> methods.</span></span> <span data-ttu-id="059b4-115">El operador `+` es sencillo de usar y genera un código intuitivo.</span><span class="sxs-lookup"><span data-stu-id="059b4-115">The `+` operator is easy to use and makes for intuitive code.</span></span> <span data-ttu-id="059b4-116">Incluso si usa varios operadores + en una instrucción, el contenido de la cadena se copia solo una vez.</span><span class="sxs-lookup"><span data-stu-id="059b4-116">Even if you use several + operators in one statement, the string content is copied only once.</span></span> <span data-ttu-id="059b4-117">Pero si repite esta operación varias veces, por ejemplo en un bucle, puede provocar problemas de eficacia.</span><span class="sxs-lookup"><span data-stu-id="059b4-117">But if you repeat this operation multiple times, for example in a loop, it might cause efficiency problems.</span></span> <span data-ttu-id="059b4-118">Por ejemplo, observe el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="059b4-118">For example, note the following code:</span></span>  
  
 <span data-ttu-id="059b4-119">[!code-cs[csProgGuideStrings#23](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="059b4-119">[!code-cs[csProgGuideStrings#23](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_2.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="059b4-120">En operaciones de concatenación de cadenas, el compilador de C# trata una cadena NULL igual que una cadena vacía, pero no convierte el valor de la cadena NULL original.</span><span class="sxs-lookup"><span data-stu-id="059b4-120">In string concatenation operations, the C# compiler treats a null string the same as an empty string, but it does not convert the value of the original null string.</span></span>  
  
 <span data-ttu-id="059b4-121">Si no está concatenando un gran número de cadenas (por ejemplo, en un bucle), el costo de rendimiento de este código probablemente no sea significante.</span><span class="sxs-lookup"><span data-stu-id="059b4-121">If you are not concatenating large numbers of strings (for example, in a loop), the performance cost of this code is probably not significant.</span></span> <span data-ttu-id="059b4-122">Lo mismo se cumple para los métodos <xref:System.String.Concat%2A?displayProperty=fullName> y <xref:System.String.Format%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="059b4-122">The same is true for the <xref:System.String.Concat%2A?displayProperty=fullName> and <xref:System.String.Format%2A?displayProperty=fullName> methods.</span></span>  
  
 <span data-ttu-id="059b4-123">En cambio, cuando el rendimiento es importante, siempre debe usar la clase <xref:System.Text.StringBuilder> para concatenar cadenas.</span><span class="sxs-lookup"><span data-stu-id="059b4-123">However, when performance is important, you should always use the <xref:System.Text.StringBuilder> class to concatenate strings.</span></span> <span data-ttu-id="059b4-124">En el código siguiente se usa el método <xref:System.Text.StringBuilder.Append%2A> de la clase <xref:System.Text.StringBuilder> para concatenar cadenas sin el efecto de encadenamiento del operador `+`.</span><span class="sxs-lookup"><span data-stu-id="059b4-124">The following code uses the <xref:System.Text.StringBuilder.Append%2A> method of the <xref:System.Text.StringBuilder> class to concatenate strings without the chaining effect of the `+` operator.</span></span>  
  
 <span data-ttu-id="059b4-125">[!code-cs[csProgGuideStrings#22](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="059b4-125">[!code-cs[csProgGuideStrings#22](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="059b4-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="059b4-126">See Also</span></span>  
 <span data-ttu-id="059b4-127"><xref:System.String></span><span class="sxs-lookup"><span data-stu-id="059b4-127"><xref:System.String></span></span>   
 <span data-ttu-id="059b4-128"><xref:System.Text.StringBuilder></span><span class="sxs-lookup"><span data-stu-id="059b4-128"><xref:System.Text.StringBuilder></span></span>   
 <span data-ttu-id="059b4-129">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="059b4-129">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="059b4-130">Cadenas</span><span class="sxs-lookup"><span data-stu-id="059b4-130">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)


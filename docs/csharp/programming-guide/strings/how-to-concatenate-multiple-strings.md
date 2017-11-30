---
title: "Cómo: Concatenar varias cadenas (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ca240523e2483289e11433fd58d9630a31721b33
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-concatenate-multiple-strings-c-programming-guide"></a><span data-ttu-id="05e07-102">Cómo: Concatenar varias cadenas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="05e07-102">How to: Concatenate Multiple Strings (C# Programming Guide)</span></span>
<span data-ttu-id="05e07-103">*Concatenación* es el proceso de anexar una cadena al final de otra cadena.</span><span class="sxs-lookup"><span data-stu-id="05e07-103">*Concatenation* is the process of appending one string to the end of another string.</span></span> <span data-ttu-id="05e07-104">Cuando concatena literales de cadena o constantes de cadena con el operador `+`, el compilador crea una cadena única.</span><span class="sxs-lookup"><span data-stu-id="05e07-104">When you concatenate string literals or string constants by using the `+` operator, the compiler creates a single string.</span></span> <span data-ttu-id="05e07-105">No se produce ninguna concatenación en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="05e07-105">No run time concatenation occurs.</span></span> <span data-ttu-id="05e07-106">En cambio, las variables de cadena pueden concatenarse solo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="05e07-106">However, string variables can be concatenated only at run time.</span></span> <span data-ttu-id="05e07-107">En este caso, debe entender las implicaciones de rendimiento de los diversos enfoques.</span><span class="sxs-lookup"><span data-stu-id="05e07-107">In this case, you should understand the performance implications of the various approaches.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05e07-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="05e07-108">Example</span></span>  
 <span data-ttu-id="05e07-109">En el ejemplo siguiente se muestra cómo dividir un literal de cadena larga en cadenas más pequeñas para mejorar la legibilidad en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="05e07-109">The following example shows how to split a long string literal into smaller strings in order to improve readability in the source code.</span></span> <span data-ttu-id="05e07-110">Estas partes se concatenarán en una sola cadena en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="05e07-110">These parts will be concatenated into a single string at compile time.</span></span> <span data-ttu-id="05e07-111">No existe ningún costo de rendimiento en tiempo de ejecución independientemente del número de cadenas implicadas.</span><span class="sxs-lookup"><span data-stu-id="05e07-111">There is no run time performance cost regardless of the number of strings involved.</span></span>  
  
 [!code-csharp[csProgGuideStrings#30](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="05e07-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="05e07-112">Example</span></span>  
 <span data-ttu-id="05e07-113">Para concatenar variables de cadena, puede usar los operadores `+` o `+=`, o los métodos <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Format%2A?displayProperty=nameWithType> o <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="05e07-113">To concatenate string variables, you can use the `+` or `+=` operators, or the <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Format%2A?displayProperty=nameWithType> or <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="05e07-114">El operador `+` es sencillo de usar y genera un código intuitivo.</span><span class="sxs-lookup"><span data-stu-id="05e07-114">The `+` operator is easy to use and makes for intuitive code.</span></span> <span data-ttu-id="05e07-115">Incluso si usa varios operadores + en una instrucción, el contenido de la cadena se copia solo una vez.</span><span class="sxs-lookup"><span data-stu-id="05e07-115">Even if you use several + operators in one statement, the string content is copied only once.</span></span> <span data-ttu-id="05e07-116">Pero si repite esta operación varias veces, por ejemplo en un bucle, puede provocar problemas de eficacia.</span><span class="sxs-lookup"><span data-stu-id="05e07-116">But if you repeat this operation multiple times, for example in a loop, it might cause efficiency problems.</span></span> <span data-ttu-id="05e07-117">Por ejemplo, observe el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="05e07-117">For example, note the following code:</span></span>  
  
 [!code-csharp[csProgGuideStrings#23](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_2.cs)]  
  
> [!NOTE]
>  <span data-ttu-id="05e07-118">En operaciones de concatenación de cadenas, el compilador de C# trata una cadena NULL igual que una cadena vacía, pero no convierte el valor de la cadena NULL original.</span><span class="sxs-lookup"><span data-stu-id="05e07-118">In string concatenation operations, the C# compiler treats a null string the same as an empty string, but it does not convert the value of the original null string.</span></span>  
  
 <span data-ttu-id="05e07-119">Si no está concatenando un gran número de cadenas (por ejemplo, en un bucle), el costo de rendimiento de este código probablemente no sea significante.</span><span class="sxs-lookup"><span data-stu-id="05e07-119">If you are not concatenating large numbers of strings (for example, in a loop), the performance cost of this code is probably not significant.</span></span> <span data-ttu-id="05e07-120">Lo mismo se cumple para los métodos <xref:System.String.Concat%2A?displayProperty=nameWithType> y <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="05e07-120">The same is true for the <xref:System.String.Concat%2A?displayProperty=nameWithType> and <xref:System.String.Format%2A?displayProperty=nameWithType> methods.</span></span>  
  
 <span data-ttu-id="05e07-121">En cambio, cuando el rendimiento es importante, siempre debe usar la clase <xref:System.Text.StringBuilder> para concatenar cadenas.</span><span class="sxs-lookup"><span data-stu-id="05e07-121">However, when performance is important, you should always use the <xref:System.Text.StringBuilder> class to concatenate strings.</span></span> <span data-ttu-id="05e07-122">En el código siguiente se usa el método <xref:System.Text.StringBuilder.Append%2A> de la clase <xref:System.Text.StringBuilder> para concatenar cadenas sin el efecto de encadenamiento del operador `+`.</span><span class="sxs-lookup"><span data-stu-id="05e07-122">The following code uses the <xref:System.Text.StringBuilder.Append%2A> method of the <xref:System.Text.StringBuilder> class to concatenate strings without the chaining effect of the `+` operator.</span></span>  
  
 [!code-csharp[csProgGuideStrings#22](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="05e07-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="05e07-123">See Also</span></span>  
 <xref:System.String>  
 <xref:System.Text.StringBuilder>  
 [<span data-ttu-id="05e07-124">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="05e07-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="05e07-125">Cadenas</span><span class="sxs-lookup"><span data-stu-id="05e07-125">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)

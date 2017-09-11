---
title: goto (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- goto_CSharpKeyword
- goto
dev_langs:
- CSharp
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
caps.latest.revision: 22
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
ms.openlocfilehash: cd298809ab883f425f3bb88239f2951ab98cc03e
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="goto-c-reference"></a><span data-ttu-id="a9f50-102">goto (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="a9f50-102">goto (C# Reference)</span></span>
<span data-ttu-id="a9f50-103">La instrucción `goto` transfiere el control del programa directamente a una instrucción con etiqueta.</span><span class="sxs-lookup"><span data-stu-id="a9f50-103">The `goto` statement transfers the program control directly to a labeled statement.</span></span>  
  
 <span data-ttu-id="a9f50-104">Un uso común de `goto` consiste en transferir el control a una etiqueta de switch case específica o a la etiqueta predeterminada en una instrucción `switch`.</span><span class="sxs-lookup"><span data-stu-id="a9f50-104">A common use of `goto` is to transfer control to a specific switch-case label or the default label in a `switch` statement.</span></span>  
  
 <span data-ttu-id="a9f50-105">La instrucción `goto` también es útil para salir de bucles demasiado anidados.</span><span class="sxs-lookup"><span data-stu-id="a9f50-105">The `goto` statement is also useful to get out of deeply nested loops.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9f50-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a9f50-106">Example</span></span>  
 <span data-ttu-id="a9f50-107">En el ejemplo siguiente se muestra cómo usar `goto` en una instrucción [switch](../../../csharp/language-reference/keywords/switch.md).</span><span class="sxs-lookup"><span data-stu-id="a9f50-107">The following example demonstrates using `goto` in a [switch](../../../csharp/language-reference/keywords/switch.md) statement.</span></span>  
  
 <span data-ttu-id="a9f50-108">[!code-cs[csrefKeywordsJump#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a9f50-108">[!code-cs[csrefKeywordsJump#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9f50-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a9f50-109">Example</span></span>  
 <span data-ttu-id="a9f50-110">En el ejemplo siguiente se muestra cómo usar `goto` para salir de bucles anidados.</span><span class="sxs-lookup"><span data-stu-id="a9f50-110">The following example demonstrates using `goto` to break out from nested loops.</span></span>  
  
 <span data-ttu-id="a9f50-111">[!code-cs[csrefKeywordsJump#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="a9f50-111">[!code-cs[csrefKeywordsJump#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="a9f50-112">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="a9f50-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a9f50-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9f50-113">See Also</span></span>  
 <span data-ttu-id="a9f50-114">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="a9f50-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="a9f50-115">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a9f50-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a9f50-116">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="a9f50-116">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="a9f50-117">[goto (instrucción)](/cpp/cpp/goto-statement-cpp) </span><span class="sxs-lookup"><span data-stu-id="a9f50-117">[goto Statement](/cpp/cpp/goto-statement-cpp) </span></span>  
 [<span data-ttu-id="a9f50-118">Instrucciones de salto</span><span class="sxs-lookup"><span data-stu-id="a9f50-118">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)


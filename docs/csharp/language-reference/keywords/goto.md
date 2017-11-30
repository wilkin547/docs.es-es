---
title: goto (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords: goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
caps.latest.revision: "22"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: aa12a7547cfcd4a2076b5b0a308139f8a823f482
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="goto-c-reference"></a><span data-ttu-id="d4c80-102">goto (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="d4c80-102">goto (C# Reference)</span></span>
<span data-ttu-id="d4c80-103">La instrucción `goto` transfiere el control del programa directamente a una instrucción con etiqueta.</span><span class="sxs-lookup"><span data-stu-id="d4c80-103">The `goto` statement transfers the program control directly to a labeled statement.</span></span>  
  
 <span data-ttu-id="d4c80-104">Un uso común de `goto` consiste en transferir el control a una etiqueta de switch case específica o a la etiqueta predeterminada en una instrucción `switch`.</span><span class="sxs-lookup"><span data-stu-id="d4c80-104">A common use of `goto` is to transfer control to a specific switch-case label or the default label in a `switch` statement.</span></span>  
  
 <span data-ttu-id="d4c80-105">La instrucción `goto` también es útil para salir de bucles demasiado anidados.</span><span class="sxs-lookup"><span data-stu-id="d4c80-105">The `goto` statement is also useful to get out of deeply nested loops.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4c80-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d4c80-106">Example</span></span>  
 <span data-ttu-id="d4c80-107">En el ejemplo siguiente se muestra cómo usar `goto` en una instrucción [switch](../../../csharp/language-reference/keywords/switch.md).</span><span class="sxs-lookup"><span data-stu-id="d4c80-107">The following example demonstrates using `goto` in a [switch](../../../csharp/language-reference/keywords/switch.md) statement.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="d4c80-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d4c80-108">Example</span></span>  
 <span data-ttu-id="d4c80-109">En el ejemplo siguiente se muestra cómo usar `goto` para salir de bucles anidados.</span><span class="sxs-lookup"><span data-stu-id="d4c80-109">The following example demonstrates using `goto` to break out from nested loops.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="d4c80-110">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="d4c80-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d4c80-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4c80-111">See Also</span></span>  
 [<span data-ttu-id="d4c80-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="d4c80-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="d4c80-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d4c80-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d4c80-114">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="d4c80-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="d4c80-115">goto (instrucción)</span><span class="sxs-lookup"><span data-stu-id="d4c80-115">goto Statement</span></span>](/cpp/cpp/goto-statement-cpp)  
 [<span data-ttu-id="d4c80-116">Instrucciones de salto</span><span class="sxs-lookup"><span data-stu-id="d4c80-116">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)

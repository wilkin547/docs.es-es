---
title: return (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 90c84b51c6ee57864eac552bc488c9f9c15e9394
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="return-c-reference"></a><span data-ttu-id="9fa3e-102">return (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="9fa3e-102">return (C# Reference)</span></span>
<span data-ttu-id="9fa3e-103">La instrucción `return` termina la ejecución del método en el que aparece y devuelve el control al método de llamada.</span><span class="sxs-lookup"><span data-stu-id="9fa3e-103">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="9fa3e-104">También puede devolver un valor opcional.</span><span class="sxs-lookup"><span data-stu-id="9fa3e-104">It can also return an optional value.</span></span> <span data-ttu-id="9fa3e-105">Si el método es del tipo `void`, la instrucción `return` se puede omitir.</span><span class="sxs-lookup"><span data-stu-id="9fa3e-105">If the method is a `void` type, the `return` statement can be omitted.</span></span>  
  
 <span data-ttu-id="9fa3e-106">Si la instrucción return está incluida en un bloque `try`, el bloque `finally`, si existe, se ejecutará antes de que el control se devuelva al método de llamada.</span><span class="sxs-lookup"><span data-stu-id="9fa3e-106">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fa3e-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9fa3e-107">Example</span></span>  
 <span data-ttu-id="9fa3e-108">En el ejemplo siguiente, el método `CalculateArea()` devuelve la variable local `area` como un [doble](../../../csharp/language-reference/keywords/double.md) valor.</span><span class="sxs-lookup"><span data-stu-id="9fa3e-108">In the following example, the method `CalculateArea()` returns the local variable `area` as a [double](../../../csharp/language-reference/keywords/double.md) value.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/return_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="9fa3e-109">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="9fa3e-109">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9fa3e-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="9fa3e-110">See Also</span></span>  
 [<span data-ttu-id="9fa3e-111">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="9fa3e-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="9fa3e-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9fa3e-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9fa3e-113">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="9fa3e-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="9fa3e-114">return (instrucción)</span><span class="sxs-lookup"><span data-stu-id="9fa3e-114">return Statement</span></span>](/cpp/cpp/return-statement-cpp)  
 [<span data-ttu-id="9fa3e-115">Instrucciones de salto</span><span class="sxs-lookup"><span data-stu-id="9fa3e-115">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)

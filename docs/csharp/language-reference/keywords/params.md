---
title: params (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
caps.latest.revision: "24"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e66cfc8e7b131a4443ee227df5e39c7e3b775324
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="params-c-reference"></a><span data-ttu-id="dfb35-102">params (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="dfb35-102">params (C# Reference)</span></span>
<span data-ttu-id="dfb35-103">Mediante el uso de la palabra clave `params`, puede especificar un [parámetro de método](../../../csharp/language-reference/keywords/method-parameters.md) que toma un número variable de argumentos.</span><span class="sxs-lookup"><span data-stu-id="dfb35-103">By using the `params` keyword, you can specify a [method parameter](../../../csharp/language-reference/keywords/method-parameters.md) that takes a variable number of arguments.</span></span>  
  
 <span data-ttu-id="dfb35-104">Puede enviar una lista separada por comas de argumentos del tipo especificado en la declaración de parámetro o una matriz de argumentos del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="dfb35-104">You can send a comma-separated list of arguments of the type specified in the parameter declaration or an array of arguments of the specified type.</span></span> <span data-ttu-id="dfb35-105">También puede no enviar ningún argumento.</span><span class="sxs-lookup"><span data-stu-id="dfb35-105">You also can send no arguments.</span></span> <span data-ttu-id="dfb35-106">Si no envía ningún argumento, la longitud de la lista `params` es cero.</span><span class="sxs-lookup"><span data-stu-id="dfb35-106">If you send no arguments, the length of the `params` list is zero.</span></span>  
  
 <span data-ttu-id="dfb35-107">No se permiten parámetros adicionales después de la palabra clave `params` en una declaración de método, y solo se permite una palabra clave `params` en una declaración de método.</span><span class="sxs-lookup"><span data-stu-id="dfb35-107">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfb35-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dfb35-108">Example</span></span>  
 <span data-ttu-id="dfb35-109">En el ejemplo siguiente se muestran varias maneras de enviar argumentos a un parámetro `params`.</span><span class="sxs-lookup"><span data-stu-id="dfb35-109">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>  
  
 [!code-csharp[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="dfb35-110">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="dfb35-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dfb35-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfb35-111">See Also</span></span>  
 [<span data-ttu-id="dfb35-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="dfb35-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="dfb35-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="dfb35-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="dfb35-114">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="dfb35-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="dfb35-115">Parámetros de métodos</span><span class="sxs-lookup"><span data-stu-id="dfb35-115">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)

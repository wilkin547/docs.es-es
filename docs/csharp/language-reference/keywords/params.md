---
title: params (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- params_CSharpKeyword
- params
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
caps.latest.revision: 24
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
ms.openlocfilehash: 5999911b96d17c710096e74c8f3da65223e778fc
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="params-c-reference"></a><span data-ttu-id="0646a-102">params (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="0646a-102">params (C# Reference)</span></span>
<span data-ttu-id="0646a-103">Mediante el uso de la palabra clave `params`, puede especificar un [parámetro de método](../../../csharp/language-reference/keywords/method-parameters.md) que toma un número variable de argumentos.</span><span class="sxs-lookup"><span data-stu-id="0646a-103">By using the `params` keyword, you can specify a [method parameter](../../../csharp/language-reference/keywords/method-parameters.md) that takes a variable number of arguments.</span></span>  
  
 <span data-ttu-id="0646a-104">Puede enviar una lista separada por comas de argumentos del tipo especificado en la declaración de parámetro o una matriz de argumentos del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="0646a-104">You can send a comma-separated list of arguments of the type specified in the parameter declaration or an array of arguments of the specified type.</span></span> <span data-ttu-id="0646a-105">También puede no enviar ningún argumento.</span><span class="sxs-lookup"><span data-stu-id="0646a-105">You also can send no arguments.</span></span> <span data-ttu-id="0646a-106">Si no envía ningún argumento, la longitud de la lista `params` es cero.</span><span class="sxs-lookup"><span data-stu-id="0646a-106">If you send no arguments, the length of the `params` list is zero.</span></span>  
  
 <span data-ttu-id="0646a-107">No se permiten parámetros adicionales después de la palabra clave `params` en una declaración de método, y solo se permite una palabra clave `params` en una declaración de método.</span><span class="sxs-lookup"><span data-stu-id="0646a-107">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0646a-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0646a-108">Example</span></span>  
 <span data-ttu-id="0646a-109">En el ejemplo siguiente se muestran varias maneras de enviar argumentos a un parámetro `params`.</span><span class="sxs-lookup"><span data-stu-id="0646a-109">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>  
  
 <span data-ttu-id="0646a-110">[!code-cs[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="0646a-110">[!code-cs[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="0646a-111">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="0646a-111">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0646a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="0646a-112">See Also</span></span>  
 <span data-ttu-id="0646a-113">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="0646a-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="0646a-114">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0646a-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="0646a-115">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="0646a-115">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 [<span data-ttu-id="0646a-116">Parámetros de métodos</span><span class="sxs-lookup"><span data-stu-id="0646a-116">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)


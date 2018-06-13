---
title: params (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: d7e0094d0f60aa201ae7229983f3e4b9764d2cbc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33265475"
---
# <a name="params-c-reference"></a><span data-ttu-id="b9488-102">params (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="b9488-102">params (C# Reference)</span></span>
<span data-ttu-id="b9488-103">Mediante el uso de la palabra clave `params`, puede especificar un [parámetro de método](../../../csharp/language-reference/keywords/method-parameters.md) que toma un número variable de argumentos.</span><span class="sxs-lookup"><span data-stu-id="b9488-103">By using the `params` keyword, you can specify a [method parameter](../../../csharp/language-reference/keywords/method-parameters.md) that takes a variable number of arguments.</span></span>  
  
 <span data-ttu-id="b9488-104">Puede enviar una lista separada por comas de argumentos del tipo especificado en la declaración de parámetro o una matriz de argumentos del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="b9488-104">You can send a comma-separated list of arguments of the type specified in the parameter declaration or an array of arguments of the specified type.</span></span> <span data-ttu-id="b9488-105">También puede no enviar ningún argumento.</span><span class="sxs-lookup"><span data-stu-id="b9488-105">You also can send no arguments.</span></span> <span data-ttu-id="b9488-106">Si no envía ningún argumento, la longitud de la lista `params` es cero.</span><span class="sxs-lookup"><span data-stu-id="b9488-106">If you send no arguments, the length of the `params` list is zero.</span></span>  
  
 <span data-ttu-id="b9488-107">No se permiten parámetros adicionales después de la palabra clave `params` en una declaración de método, y solo se permite una palabra clave `params` en una declaración de método.</span><span class="sxs-lookup"><span data-stu-id="b9488-107">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9488-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b9488-108">Example</span></span>  
 <span data-ttu-id="b9488-109">En el ejemplo siguiente se muestran varias maneras de enviar argumentos a un parámetro `params`.</span><span class="sxs-lookup"><span data-stu-id="b9488-109">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>  
  
 [!code-csharp[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="b9488-110">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="b9488-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b9488-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9488-111">See Also</span></span>  
 [<span data-ttu-id="b9488-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="b9488-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="b9488-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="b9488-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b9488-114">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="b9488-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="b9488-115">Parámetros de métodos</span><span class="sxs-lookup"><span data-stu-id="b9488-115">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)

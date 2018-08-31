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
ms.openlocfilehash: 692c2f61ae99f1c1c8e04a5a1bcad08814d286fe
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2018
ms.locfileid: "42752036"
---
# <a name="params-c-reference"></a><span data-ttu-id="ccd83-102">params (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="ccd83-102">params (C# Reference)</span></span>
<span data-ttu-id="ccd83-103">Mediante el uso de la palabra clave `params`, puede especificar un [parámetro de método](../../../csharp/language-reference/keywords/method-parameters.md) que toma un número variable de argumentos.</span><span class="sxs-lookup"><span data-stu-id="ccd83-103">By using the `params` keyword, you can specify a [method parameter](../../../csharp/language-reference/keywords/method-parameters.md) that takes a variable number of arguments.</span></span>  
  
 <span data-ttu-id="ccd83-104">Puede enviar una lista separada por comas de argumentos del tipo especificado en la declaración de parámetro o una matriz de argumentos del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="ccd83-104">You can send a comma-separated list of arguments of the type specified in the parameter declaration or an array of arguments of the specified type.</span></span> <span data-ttu-id="ccd83-105">También puede no enviar ningún argumento.</span><span class="sxs-lookup"><span data-stu-id="ccd83-105">You also can send no arguments.</span></span> <span data-ttu-id="ccd83-106">Si no envía ningún argumento, la longitud de la lista `params` es cero.</span><span class="sxs-lookup"><span data-stu-id="ccd83-106">If you send no arguments, the length of the `params` list is zero.</span></span>  
  
 <span data-ttu-id="ccd83-107">No se permiten parámetros adicionales después de la palabra clave `params` en una declaración de método, y solo se permite una palabra clave `params` en una declaración de método.</span><span class="sxs-lookup"><span data-stu-id="ccd83-107">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>  
 
 <span data-ttu-id="ccd83-108">El tipo declarado del parámetro `params` debe ser una matriz unidimensional, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ccd83-108">The declared type of the `params` parameter must be a single-dimensional array, as the following example shows.</span></span> <span data-ttu-id="ccd83-109">En caso contrario, se produce un error del compilador [CS0225](../../../csharp/misc/cs0225.md).</span><span class="sxs-lookup"><span data-stu-id="ccd83-109">Otherwise, a compiler error [CS0225](../../../csharp/misc/cs0225.md) occurs.</span></span>
  
## <a name="example"></a><span data-ttu-id="ccd83-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ccd83-110">Example</span></span>  
 <span data-ttu-id="ccd83-111">En el ejemplo siguiente se muestran varias maneras de enviar argumentos a un parámetro `params`.</span><span class="sxs-lookup"><span data-stu-id="ccd83-111">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>  
  
 [!code-csharp[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="ccd83-112">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="ccd83-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ccd83-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ccd83-113">See Also</span></span>  
 [<span data-ttu-id="ccd83-114">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="ccd83-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="ccd83-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ccd83-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ccd83-116">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="ccd83-116">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="ccd83-117">Parámetros de métodos</span><span class="sxs-lookup"><span data-stu-id="ccd83-117">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)

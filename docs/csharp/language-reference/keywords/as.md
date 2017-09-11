---
title: as (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- as_CSharpKeyword
- as
dev_langs:
- CSharp
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
caps.latest.revision: 24
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
ms.openlocfilehash: 7a55c696ac295eee8d5d35ed56038f3c4a90b215
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="as-c-reference"></a><span data-ttu-id="d9ad7-102">as (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="d9ad7-102">as (C# Reference)</span></span>
<span data-ttu-id="d9ad7-103">Se puede usar el operador `as` para realizar ciertos tipos de conversiones entre tipos de referencia compatibles o [tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="d9ad7-103">You can use the `as` operator to perform certain types of conversions between compatible reference types or [nullable types](../../../csharp/programming-guide/nullable-types/index.md).</span></span> <span data-ttu-id="d9ad7-104">En el código siguiente se muestra un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d9ad7-104">The following code shows an example.</span></span>  
  
 <span data-ttu-id="d9ad7-105">[!code-cs[csrefKeywordsOperator#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d9ad7-105">[!code-cs[csrefKeywordsOperator#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_1.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9ad7-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d9ad7-106">Remarks</span></span>  
 <span data-ttu-id="d9ad7-107">El operador `as` es como una operación de conversión.</span><span class="sxs-lookup"><span data-stu-id="d9ad7-107">The `as` operator is like a cast operation.</span></span> <span data-ttu-id="d9ad7-108">Pero si la conversión no es posible, `as` devuelve `null` en lugar de generar una excepción.</span><span class="sxs-lookup"><span data-stu-id="d9ad7-108">However, if the conversion isn't possible, `as` returns `null` instead of raising an exception.</span></span> <span data-ttu-id="d9ad7-109">Considere el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d9ad7-109">Consider the following example:</span></span>  
  
```  
expression as type  
```  
  
 <span data-ttu-id="d9ad7-110">El código es equivalente a la siguiente expresión, salvo que la variable `expression` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="d9ad7-110">The code is equivalent to the following expression except that the `expression` variable is evaluated only one time.</span></span>  
  
```  
expression is type ? (type)expression : (type)null  
```  
  
 <span data-ttu-id="d9ad7-111">Tenga en cuenta que el operador `as` realiza solo las conversiones de referencia, las conversiones que aceptan valores NULL y las conversiones boxing.</span><span class="sxs-lookup"><span data-stu-id="d9ad7-111">Note that the `as` operator performs only reference conversions, nullable conversions, and boxing conversions.</span></span> <span data-ttu-id="d9ad7-112">El operador `as` no puede realizar otras conversiones, como las conversiones definidas por el usuario, que en su lugar se deben realizar mediante expresiones de conversión.</span><span class="sxs-lookup"><span data-stu-id="d9ad7-112">The `as` operator can't perform other conversions, such as user-defined conversions, which should instead be performed by using cast expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9ad7-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d9ad7-113">Example</span></span>  
 <span data-ttu-id="d9ad7-114">[!code-cs[csrefKeywordsOperator#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="d9ad7-114">[!code-cs[csrefKeywordsOperator#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d9ad7-115">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="d9ad7-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d9ad7-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9ad7-116">See Also</span></span>  
 <span data-ttu-id="d9ad7-117">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d9ad7-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d9ad7-118">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d9ad7-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d9ad7-119">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="d9ad7-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="d9ad7-120">[is](../../../csharp/language-reference/keywords/is.md) </span><span class="sxs-lookup"><span data-stu-id="d9ad7-120">[is](../../../csharp/language-reference/keywords/is.md) </span></span>  
 <span data-ttu-id="d9ad7-121">[Operador ?](../../../csharp/language-reference/operators/conditional-operator.md) </span><span class="sxs-lookup"><span data-stu-id="d9ad7-121">[?: Operator](../../../csharp/language-reference/operators/conditional-operator.md) </span></span>  
 [<span data-ttu-id="d9ad7-122">Palabras clave de operador</span><span class="sxs-lookup"><span data-stu-id="d9ad7-122">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)


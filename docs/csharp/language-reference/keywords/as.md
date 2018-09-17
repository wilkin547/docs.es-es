---
title: as (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- as_CSharpKeyword
- as
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
ms.openlocfilehash: aee80b3262ccd9432d7c311dddec47185b66d05f
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45648400"
---
# <a name="as-c-reference"></a><span data-ttu-id="69fb6-102">as (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="69fb6-102">as (C# Reference)</span></span>
<span data-ttu-id="69fb6-103">Se puede usar el operador `as` para realizar ciertos tipos de conversiones entre tipos de referencia compatibles o [tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="69fb6-103">You can use the `as` operator to perform certain types of conversions between compatible reference types or [nullable types](../../../csharp/programming-guide/nullable-types/index.md).</span></span> <span data-ttu-id="69fb6-104">En el código siguiente se muestra un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="69fb6-104">The following code shows an example.</span></span>  
  
[!code-csharp[csrefKeywordsOperator#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#1)]
  
## <a name="remarks"></a><span data-ttu-id="69fb6-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="69fb6-105">Remarks</span></span>  
 <span data-ttu-id="69fb6-106">El operador `as` es como una operación de conversión.</span><span class="sxs-lookup"><span data-stu-id="69fb6-106">The `as` operator is like a cast operation.</span></span> <span data-ttu-id="69fb6-107">Pero si la conversión no es posible, `as` devuelve `null` en lugar de generar una excepción.</span><span class="sxs-lookup"><span data-stu-id="69fb6-107">However, if the conversion isn't possible, `as` returns `null` instead of raising an exception.</span></span> <span data-ttu-id="69fb6-108">Considere el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="69fb6-108">Consider the following example:</span></span>  
  
```csharp  
expression as type  
```  
  
 <span data-ttu-id="69fb6-109">El código es equivalente a la siguiente expresión, salvo que la variable `expression` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="69fb6-109">The code is equivalent to the following expression except that the `expression` variable is evaluated only one time.</span></span>  
  
```csharp  
expression is type ? (type)expression : (type)null  
```  
  
 <span data-ttu-id="69fb6-110">Tenga en cuenta que el operador `as` realiza solo las conversiones de referencia, las conversiones que aceptan valores NULL y las conversiones boxing.</span><span class="sxs-lookup"><span data-stu-id="69fb6-110">Note that the `as` operator performs only reference conversions, nullable conversions, and boxing conversions.</span></span> <span data-ttu-id="69fb6-111">El operador `as` no puede realizar otras conversiones, como las conversiones definidas por el usuario, que en su lugar se deben realizar mediante expresiones de conversión.</span><span class="sxs-lookup"><span data-stu-id="69fb6-111">The `as` operator can't perform other conversions, such as user-defined conversions, which should instead be performed by using cast expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69fb6-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="69fb6-112">Example</span></span>  

[!code-csharp[csrefKeywordsOperator#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#2)]
  
## <a name="c-language-specification"></a><span data-ttu-id="69fb6-113">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="69fb6-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="69fb6-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="69fb6-114">See Also</span></span>  
- [<span data-ttu-id="69fb6-115">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="69fb6-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="69fb6-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="69fb6-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="69fb6-117">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="69fb6-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="69fb6-118">is</span><span class="sxs-lookup"><span data-stu-id="69fb6-118">is</span></span>](../../../csharp/language-reference/keywords/is.md)  
- [<span data-ttu-id="69fb6-119">Operador ?</span><span class="sxs-lookup"><span data-stu-id="69fb6-119">?: Operator</span></span>](../../../csharp/language-reference/operators/conditional-operator.md)  
- [<span data-ttu-id="69fb6-120">Palabras clave de operador</span><span class="sxs-lookup"><span data-stu-id="69fb6-120">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)

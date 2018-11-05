---
title: as (Referencia de C#)
ms.date: 10/11/2018
f1_keywords:
- as_CSharpKeyword
- as
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
ms.openlocfilehash: ce3163f7d957df96a5c0304adc0b3083d8e20104
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2018
ms.locfileid: "49122734"
---
# <a name="as-c-reference"></a><span data-ttu-id="9bee8-102">as (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="9bee8-102">as (C# Reference)</span></span>
<span data-ttu-id="9bee8-103">Se puede usar el operador `as` para realizar ciertos tipos de conversiones entre tipos de referencia compatibles o [tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="9bee8-103">You can use the `as` operator to perform certain types of conversions between compatible reference types or [nullable types](../../../csharp/programming-guide/nullable-types/index.md).</span></span> <span data-ttu-id="9bee8-104">En el código siguiente se muestra un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9bee8-104">The following code shows an example.</span></span>  
  
[!code-csharp[csrefKeywordsOperator#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#1)]

<span data-ttu-id="9bee8-105">Como se muestra en el ejemplo, se necesita comparar el resultado de la expresión `as` con `null` para comprobar si una conversión es correcta.</span><span class="sxs-lookup"><span data-stu-id="9bee8-105">As the example shows, you need to compare the result of the `as` expression with `null` to check if a conversion is successful.</span></span> <span data-ttu-id="9bee8-106">A partir C# 7.0, puede usar la expresión [is](is.md) para tanto para probar que una conversión se realiza correctamente, como para asignar condicionalmente una variable cuando la conversión se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="9bee8-106">Beginning with C# 7.0, you can use the [is](is.md) expression both to test that a conversion succeeds and conditionally assign a variable when the conversion succeeds.</span></span> <span data-ttu-id="9bee8-107">En muchos escenarios, es más conciso que el uso del operador `as`.</span><span class="sxs-lookup"><span data-stu-id="9bee8-107">In many scenarios, it's more concise than using the `as` operator.</span></span> <span data-ttu-id="9bee8-108">Para más información, consulte sección [Patrón de tipo](is.md#type)del artículo de [`is` (operador)](is.md).</span><span class="sxs-lookup"><span data-stu-id="9bee8-108">For more information, see the [Type pattern](is.md#type) section of the [`is` operator](is.md) article.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="9bee8-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9bee8-109">Remarks</span></span>  
 <span data-ttu-id="9bee8-110">El operador `as` es como una operación de conversión.</span><span class="sxs-lookup"><span data-stu-id="9bee8-110">The `as` operator is like a cast operation.</span></span> <span data-ttu-id="9bee8-111">Pero si la conversión no es posible, `as` devuelve `null` en lugar de generar una excepción.</span><span class="sxs-lookup"><span data-stu-id="9bee8-111">However, if the conversion isn't possible, `as` returns `null` instead of raising an exception.</span></span> <span data-ttu-id="9bee8-112">Considere el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9bee8-112">Consider the following example:</span></span>  
  
```csharp  
expression as type  
```  
  
 <span data-ttu-id="9bee8-113">El código es equivalente a la siguiente expresión, salvo que la variable `expression` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="9bee8-113">The code is equivalent to the following expression except that the `expression` variable is evaluated only one time.</span></span>  
  
```csharp  
expression is type ? (type)expression : (type)null  
```  
  
 <span data-ttu-id="9bee8-114">Tenga en cuenta que el operador `as` realiza solo las conversiones de referencia, las conversiones que aceptan valores NULL y las conversiones boxing.</span><span class="sxs-lookup"><span data-stu-id="9bee8-114">Note that the `as` operator performs only reference conversions, nullable conversions, and boxing conversions.</span></span> <span data-ttu-id="9bee8-115">El operador `as` no puede realizar otras conversiones, como las conversiones definidas por el usuario, que en su lugar se deben realizar mediante expresiones de conversión.</span><span class="sxs-lookup"><span data-stu-id="9bee8-115">The `as` operator can't perform other conversions, such as user-defined conversions, which should instead be performed by using cast expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9bee8-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9bee8-116">Example</span></span>  

[!code-csharp[csrefKeywordsOperator#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#2)]
  
## <a name="c-language-specification"></a><span data-ttu-id="9bee8-117">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="9bee8-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9bee8-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="9bee8-118">See Also</span></span>  
- [<span data-ttu-id="9bee8-119">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="9bee8-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="9bee8-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9bee8-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="9bee8-121">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="9bee8-121">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="9bee8-122">is</span><span class="sxs-lookup"><span data-stu-id="9bee8-122">is</span></span>](../../../csharp/language-reference/keywords/is.md)  
- [<span data-ttu-id="9bee8-123">Operador ?</span><span class="sxs-lookup"><span data-stu-id="9bee8-123">?: Operator</span></span>](../../../csharp/language-reference/operators/conditional-operator.md)  
- [<span data-ttu-id="9bee8-124">Palabras clave de operador</span><span class="sxs-lookup"><span data-stu-id="9bee8-124">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)

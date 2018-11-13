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
ms.openlocfilehash: d6c9d44ff22881e6e5e7a542e1df41bbf77b23d8
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2018
ms.locfileid: "49122734"
---
# <a name="as-c-reference"></a><span data-ttu-id="bf625-102">as (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="bf625-102">as (C# Reference)</span></span>
<span data-ttu-id="bf625-103">Se puede usar el operador `as` para realizar ciertos tipos de conversiones entre tipos de referencia compatibles o [tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="bf625-103">You can use the `as` operator to perform certain types of conversions between compatible reference types or [nullable types](../../../csharp/programming-guide/nullable-types/index.md).</span></span> <span data-ttu-id="bf625-104">En el código siguiente se muestra un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="bf625-104">The following code shows an example.</span></span>  
  
[!code-csharp[csrefKeywordsOperator#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#1)]

<span data-ttu-id="bf625-105">Como se muestra en el ejemplo, se necesita comparar el resultado de la expresión `as` con `null` para comprobar si una conversión es correcta.</span><span class="sxs-lookup"><span data-stu-id="bf625-105">As the example shows, you need to compare the result of the `as` expression with `null` to check if a conversion is successful.</span></span> <span data-ttu-id="bf625-106">A partir C# 7.0, puede usar la expresión [is](is.md) para tanto para probar que una conversión se realiza correctamente, como para asignar condicionalmente una variable cuando la conversión se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="bf625-106">Beginning with C# 7.0, you can use the [is](is.md) expression both to test that a conversion succeeds and conditionally assign a variable when the conversion succeeds.</span></span> <span data-ttu-id="bf625-107">En muchos escenarios, es más conciso que el uso del operador `as`.</span><span class="sxs-lookup"><span data-stu-id="bf625-107">In many scenarios, it's more concise than using the `as` operator.</span></span> <span data-ttu-id="bf625-108">Para más información, consulte sección [Patrón de tipo](is.md#type)del artículo de [`is` (operador)](is.md).</span><span class="sxs-lookup"><span data-stu-id="bf625-108">For more information, see the [Type pattern](is.md#type) section of the [`is` operator](is.md) article.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="bf625-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bf625-109">Remarks</span></span>  
 <span data-ttu-id="bf625-110">El operador `as` es como una operación de conversión.</span><span class="sxs-lookup"><span data-stu-id="bf625-110">The `as` operator is like a cast operation.</span></span> <span data-ttu-id="bf625-111">Pero si la conversión no es posible, `as` devuelve `null` en lugar de generar una excepción.</span><span class="sxs-lookup"><span data-stu-id="bf625-111">However, if the conversion isn't possible, `as` returns `null` instead of raising an exception.</span></span> <span data-ttu-id="bf625-112">Considere el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bf625-112">Consider the following example:</span></span>  
  
```csharp  
expression as type  
```  
  
 <span data-ttu-id="bf625-113">El código es equivalente a la siguiente expresión, salvo que la variable `expression` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="bf625-113">The code is equivalent to the following expression except that the `expression` variable is evaluated only one time.</span></span>  
  
```csharp  
expression is type ? (type)expression : (type)null  
```  
  
 <span data-ttu-id="bf625-114">Tenga en cuenta que el operador `as` realiza solo las conversiones de referencia, las conversiones que aceptan valores NULL y las conversiones boxing.</span><span class="sxs-lookup"><span data-stu-id="bf625-114">Note that the `as` operator performs only reference conversions, nullable conversions, and boxing conversions.</span></span> <span data-ttu-id="bf625-115">El operador `as` no puede realizar otras conversiones, como las conversiones definidas por el usuario, que en su lugar se deben realizar mediante expresiones de conversión.</span><span class="sxs-lookup"><span data-stu-id="bf625-115">The `as` operator can't perform other conversions, such as user-defined conversions, which should instead be performed by using cast expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf625-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bf625-116">Example</span></span>  

[!code-csharp[csrefKeywordsOperator#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#2)]
  
## <a name="c-language-specification"></a><span data-ttu-id="bf625-117">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="bf625-117">C# Language Specification</span></span>  

<span data-ttu-id="bf625-118">Para obtener más información, vea la sección [El operador as](~/_csharplang/spec/expressions.md#the-as-operator) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="bf625-118">For more information, see [The as operator](~/_csharplang/spec/expressions.md#the-as-operator) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="bf625-119">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="bf625-119">The language specification is the definitive source for C# syntax and usage.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="bf625-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf625-120">See Also</span></span>  
- [<span data-ttu-id="bf625-121">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="bf625-121">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="bf625-122">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="bf625-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="bf625-123">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="bf625-123">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="bf625-124">is</span><span class="sxs-lookup"><span data-stu-id="bf625-124">is</span></span>](../../../csharp/language-reference/keywords/is.md)  
- [<span data-ttu-id="bf625-125">Operador ?</span><span class="sxs-lookup"><span data-stu-id="bf625-125">?: Operator</span></span>](../../../csharp/language-reference/operators/conditional-operator.md)  
- [<span data-ttu-id="bf625-126">Palabras clave de operador</span><span class="sxs-lookup"><span data-stu-id="bf625-126">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)

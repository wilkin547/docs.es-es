---
title: 'Operador ?: (Referencia de C#)'
ms.date: 07/20/2015
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 3e45ff6eaaefa5829c3ed9415abe1a12b7a1d069
ms.sourcegitcommit: 4bca8f7e172fd019ef437a4803bf5895c6bc4781
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2018
ms.locfileid: "50980627"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="a8ffb-102">Operador ?: (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="a8ffb-102">?: Operator (C# Reference)</span></span>

<span data-ttu-id="a8ffb-103">El operador condicional (`?:`), normalmente conocido como un operador condicional ternario, devuelve uno de dos valores según el valor de una expresión booleana.</span><span class="sxs-lookup"><span data-stu-id="a8ffb-103">The conditional operator (`?:`), commonly known as the ternary conditional operator, returns one of two values depending on the value of a Boolean expression.</span></span> <span data-ttu-id="a8ffb-104">A continuación se muestra la sintaxis del operador condicional.</span><span class="sxs-lookup"><span data-stu-id="a8ffb-104">Following is the syntax for the conditional operator.</span></span>  

```csharp
condition ? first_expression : second_expression;  
```

<span data-ttu-id="a8ffb-105">A partir C# 7.2, `first_expression` y `second_expression` pueden ser [ expresiones `ref`](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.2/conditional-ref.md):</span><span class="sxs-lookup"><span data-stu-id="a8ffb-105">Beginning with C# 7.2, the `first_expression` and `second_expression` my be [`ref` expressions](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.2/conditional-ref.md):</span></span>

```csharp
ref condition ? ref first_expression : ref second_expression;  
```

<span data-ttu-id="a8ffb-106">El resultado se puede asignar a una variable `ref` o `ref readonly`, o bien a una variable sin ninguno de los modificadores.</span><span class="sxs-lookup"><span data-stu-id="a8ffb-106">The result may be assigned to a `ref` or `ref readonly` variable, or to a variable with neither modifier.</span></span>

## <a name="remarks"></a><span data-ttu-id="a8ffb-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a8ffb-107">Remarks</span></span>

<span data-ttu-id="a8ffb-108">`condition` debe evaluarse como `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="a8ffb-108">The `condition` must evaluate to `true` or `false`.</span></span> <span data-ttu-id="a8ffb-109">Si `condition` es `true`, `first_expression` se evalúa y se convierte en el resultado.</span><span class="sxs-lookup"><span data-stu-id="a8ffb-109">If `condition` is `true`, `first_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="a8ffb-110">Si `condition` es `false`, `second_expression` se evalúa y se convierte en el resultado.</span><span class="sxs-lookup"><span data-stu-id="a8ffb-110">If `condition` is `false`, `second_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="a8ffb-111">Solo se evalúa una de las dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="a8ffb-111">Only one of the two expressions is evaluated.</span></span> <span data-ttu-id="a8ffb-112">Esto es especialmente importante para las expresiones donde el resultado es `ref`, como en el ejemplo siguiente válido:</span><span class="sxs-lookup"><span data-stu-id="a8ffb-112">This is particularly important for expressions where the result is a `ref`, as the following is valid:</span></span>

```csharp
ref (storage != null) ? ref storage[3] : ref defaultValue;
```

<span data-ttu-id="a8ffb-113">La referencia a `storage` no se evalúa cuando `storage` es NULL.</span><span class="sxs-lookup"><span data-stu-id="a8ffb-113">The reference to `storage` is not evaluated when `storage` is null.</span></span>

<span data-ttu-id="a8ffb-114">Cuando el resultado es un valor, el tipo de `first_expression` y `second_expression` debe coincidir, o bien debe existir una conversión implícita de un tipo al otro.</span><span class="sxs-lookup"><span data-stu-id="a8ffb-114">When the result is a value, the type of `first_expression` and `second_expression` must be the same, or there must be an implicit conversion from one type to the other.</span></span> <span data-ttu-id="a8ffb-115">Cuando el resultado es `ref`, el tipo de `first_expression` y `second_expression` debe ser el mismo.</span><span class="sxs-lookup"><span data-stu-id="a8ffb-115">When the result is a `ref`, the type of `first_expression` and `second_expression` must be the same.</span></span>

<span data-ttu-id="a8ffb-116">Puede expresar cálculos que, de lo contrario, podrían requerir una construcción `if-else` más concisa mediante el operador condicional.</span><span class="sxs-lookup"><span data-stu-id="a8ffb-116">You can express calculations that might otherwise require an `if-else` construction more concisely by using the conditional operator.</span></span> <span data-ttu-id="a8ffb-117">Por ejemplo, el código siguiente usa primero una instrucción `if` y después un operador condicional para clasificar un entero como positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="a8ffb-117">For example, the following code uses first an `if` statement and then a conditional operator to classify an integer as positive or negative.</span></span>

```csharp
int input = Convert.ToInt32(Console.ReadLine());  
string classify;  
  
// if-else construction.  
if (input > 0)  
    classify = "positive";  
else  
    classify = "negative";  
  
// ?: conditional operator.  
classify = (input > 0) ? "positive" : "negative";  
```

<span data-ttu-id="a8ffb-118">El operador condicional es asociativo a la derecha.</span><span class="sxs-lookup"><span data-stu-id="a8ffb-118">The conditional operator is right-associative.</span></span> <span data-ttu-id="a8ffb-119">La expresión `a ? b : c ? d : e` se evalúa como `a ? b : (c ? d : e)`, no como `(a ? b : c) ? d : e`.</span><span class="sxs-lookup"><span data-stu-id="a8ffb-119">The expression `a ? b : c ? d : e` is evaluated as `a ? b : (c ? d : e)`, not as `(a ? b : c) ? d : e`.</span></span>  
  
<span data-ttu-id="a8ffb-120">El operador condicional no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="a8ffb-120">The conditional operator cannot be overloaded.</span></span>
  
## <a name="example"></a><span data-ttu-id="a8ffb-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8ffb-121">Example</span></span>

<span data-ttu-id="a8ffb-122">En el ejemplo siguiente se muestra el operador condicional cuyo resultado es un valor:</span><span class="sxs-lookup"><span data-stu-id="a8ffb-122">The following example shows the conditional operator whose result is a value:</span></span>

[!code-csharp[csRefOperators?:](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalValue)]

<span data-ttu-id="a8ffb-123">En el ejemplo siguiente alternativo se muestra el operador condicional cuando el resultado es una referencia:</span><span class="sxs-lookup"><span data-stu-id="a8ffb-123">The following alternative shows the conditional operator where the result is a reference:</span></span>

[!code-csharp[csRefOperatorsRef?:](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalRef)]

## <a name="see-also"></a><span data-ttu-id="a8ffb-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8ffb-124">See Also</span></span>

- [<span data-ttu-id="a8ffb-125">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="a8ffb-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="a8ffb-126">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="a8ffb-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a8ffb-127">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="a8ffb-127">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="a8ffb-128">if-else</span><span class="sxs-lookup"><span data-stu-id="a8ffb-128">if-else</span></span>](../../../csharp/language-reference/keywords/if-else.md)  
- <span data-ttu-id="a8ffb-129">[Operadores ?. y ?[]](../../../csharp/language-reference/operators/null-conditional-operators.md)</span><span class="sxs-lookup"><span data-stu-id="a8ffb-129">[?. and ?[] Operators](../../../csharp/language-reference/operators/null-conditional-operators.md)</span></span>  
- [<span data-ttu-id="a8ffb-130">Operador !</span><span class="sxs-lookup"><span data-stu-id="a8ffb-130">?? Operator</span></span>](../../../csharp/language-reference/operators/null-coalescing-operator.md)

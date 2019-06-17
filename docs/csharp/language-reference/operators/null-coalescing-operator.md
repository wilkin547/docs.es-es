---
title: '?? operador: Referencia de C#'
ms.custom: seodec18
ms.date: 06/07/2019
f1_keywords:
- ??_CSharpKeyword
helpviewer_keywords:
- null-coalescing operator [C#]
- ?? operator [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: 8ca97261b348b7813ab179abbc1f2c5f535966a1
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816008"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="14ddc-103">??</span><span class="sxs-lookup"><span data-stu-id="14ddc-103">??</span></span> <span data-ttu-id="14ddc-104">operator (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="14ddc-104">operator (C# Reference)</span></span>

<span data-ttu-id="14ddc-105">El operador de uso combinado de NULL `??` devuelve el valor del operando izquierdo si no es `null`; en caso contrario, evalúa el operando derecho y devuelve su resultado.</span><span class="sxs-lookup"><span data-stu-id="14ddc-105">The null-coalescing operator `??` returns the value of its left-hand operand if it isn't `null`; otherwise, it evaluates the right-hand operand and returns its result.</span></span> <span data-ttu-id="14ddc-106">El operador `??` no evalúa su operando derecho si el operando izquierdo se evalúa como no NULL.</span><span class="sxs-lookup"><span data-stu-id="14ddc-106">The `??` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

<span data-ttu-id="14ddc-107">El operador de uso combinado de NULL es asociativo a la derecha, es decir, una expresión de la forma.</span><span class="sxs-lookup"><span data-stu-id="14ddc-107">The null-coalescing operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ?? b ?? c
```

<span data-ttu-id="14ddc-108">se evalúa como</span><span class="sxs-lookup"><span data-stu-id="14ddc-108">is evaluated as</span></span>

```csharp
a ?? (b ?? c)
```

<span data-ttu-id="14ddc-109">El operador `??` puede resultar útil en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="14ddc-109">The `??` operator can be useful in the following scenarios:</span></span>

- <span data-ttu-id="14ddc-110">En expresiones con los [operadores no condicionales ? y ?[]](member-access-operators.md#null-conditional-operators--and-), puede usar el operador de uso combinado de NULL para proporcionar una expresión alternativa para evaluar en caso de que el resultado de la expresión con la operación condicional NULL sea `null`:</span><span class="sxs-lookup"><span data-stu-id="14ddc-110">In expressions with the [null-conditional operators ?. and ?[]](member-access-operators.md#null-conditional-operators--and-), you can use the null-coalescing operator to provide an alternative expression to evaluate in case the result of the expression with null-conditional operations is `null`:</span></span>

  [!code-csharp-interactive[with null-conditional](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullConditional)]

- <span data-ttu-id="14ddc-111">Cuando trabaja con [tipos de valor que aceptan valores NULL](../../programming-guide/nullable-types/index.md) y necesita proporcionar un valor de un tipo de valor subyacente, use el operador de uso combinado de NULL para especificar el valor para proporcionar en caso de que un valor de tipo que acepta valores NULL sea `null`:</span><span class="sxs-lookup"><span data-stu-id="14ddc-111">When you work with [nullable value types](../../programming-guide/nullable-types/index.md) and need to provide a value of an underlying value type, use the null-coalescing operator to specify the value to provide in case a nullable type value is `null`:</span></span>

  [!code-csharp-interactive[with nullable types](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullableTypes)]

  <span data-ttu-id="14ddc-112">Use el método <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> si el valor que se va usar cuando un valor de tipo que acepta valores NULL es `null` debe ser el valor predeterminado del tipo de valor subyacente.</span><span class="sxs-lookup"><span data-stu-id="14ddc-112">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a nullable type value is `null` should be the default value of the underlying value type.</span></span>

- <span data-ttu-id="14ddc-113">A partir de C# 7.0, puede usar una [expresión `throw`](../keywords/throw.md#the-throw-expression) como el operando derecho del operador de uso combinado de NULL para hacer el código de comprobación de argumentos más conciso:</span><span class="sxs-lookup"><span data-stu-id="14ddc-113">Starting with C# 7.0, you can use a [`throw` expression](../keywords/throw.md#the-throw-expression) as the right-hand operand of the null-coalescing operator to make the argument-checking code more concise:</span></span>

  [!code-csharp[with throw expression](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithThrowExpression)]

  <span data-ttu-id="14ddc-114">El ejemplo anterior también muestra cómo usar [miembros con forma de expresión](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) para definir una propiedad.</span><span class="sxs-lookup"><span data-stu-id="14ddc-114">The preceding example also demonstrates how to use [expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) to define a property.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="14ddc-115">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="14ddc-115">Operator overloadability</span></span>

<span data-ttu-id="14ddc-116">El operador de uso combinado de NULL no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="14ddc-116">The null-coalescing operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="14ddc-117">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="14ddc-117">C# language specification</span></span>

<span data-ttu-id="14ddc-118">Para obtener más información, vea la sección [El operador de uso combinado de NULL](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="14ddc-118">For more information, see [The null coalescing operator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="14ddc-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="14ddc-119">See also</span></span>

- [<span data-ttu-id="14ddc-120">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="14ddc-120">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="14ddc-121">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="14ddc-121">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="14ddc-122">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="14ddc-122">C# operators</span></span>](index.md)
- <span data-ttu-id="14ddc-123">[Operadores ?. y ?[]](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="14ddc-123">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="14ddc-124">Operador ?:</span><span class="sxs-lookup"><span data-stu-id="14ddc-124">?: operator</span></span>](conditional-operator.md)

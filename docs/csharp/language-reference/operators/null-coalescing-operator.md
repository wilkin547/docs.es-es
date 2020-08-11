---
title: ?? Operadores ?? y ?? - Referencia de C#
ms.date: 09/10/2019
f1_keywords:
- ??_CSharpKeyword
- ??=_CSharpKeyword
helpviewer_keywords:
- null-coalescing operator [C#]
- ?? operator [C#]
- null-coalescing assignment [C#]
- ??= operator [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: 58c60dad3badc62f850f737a3d210ec486809272
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916744"
---
# <a name="-and--operators-c-reference"></a><span data-ttu-id="7507b-103">??</span><span class="sxs-lookup"><span data-stu-id="7507b-103">??</span></span> <span data-ttu-id="7507b-104">Operadores ?? y ?? (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="7507b-104">and ??= operators (C# reference)</span></span>

<span data-ttu-id="7507b-105">El operador de uso combinado de NULL `??` devuelve el valor del operando izquierdo si no es `null`; en caso contrario, evalúa el operando derecho y devuelve su resultado.</span><span class="sxs-lookup"><span data-stu-id="7507b-105">The null-coalescing operator `??` returns the value of its left-hand operand if it isn't `null`; otherwise, it evaluates the right-hand operand and returns its result.</span></span> <span data-ttu-id="7507b-106">El operador `??` no evalúa su operando derecho si el operando izquierdo se evalúa como no NULL.</span><span class="sxs-lookup"><span data-stu-id="7507b-106">The `??` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

<span data-ttu-id="7507b-107">Disponible en C# 8.0 y versiones posteriores, el operador de asignación de uso combinado de NULL `??=` asigna el valor de su operando derecho al operando izquierdo solo si el operando izquierdo se evalúa como `null`.</span><span class="sxs-lookup"><span data-stu-id="7507b-107">Available in C# 8.0 and later, the null-coalescing assignment operator `??=` assigns the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to `null`.</span></span> <span data-ttu-id="7507b-108">El operador `??=` no evalúa su operando derecho si el operando izquierdo se evalúa como no NULL.</span><span class="sxs-lookup"><span data-stu-id="7507b-108">The `??=` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

[!code-csharp[null-coalescing assignment](snippets/shared/NullCoalescingOperator.cs#Assignment)]

<span data-ttu-id="7507b-109">El operando izquierdo del operador `??=` debe ser una variable, una [propiedad](../../programming-guide/classes-and-structs/properties.md) o un elemento de [indizador](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="7507b-109">The left-hand operand of the `??=` operator must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../programming-guide/indexers/index.md) element.</span></span>

<span data-ttu-id="7507b-110">En C# 7.3 y versiones anteriores, el tipo del operando izquierdo del operador `??` debe ser un [tipo de referencia](../keywords/reference-types.md) o un [tipo de valor que acepta valores NULL](../builtin-types/nullable-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="7507b-110">In C# 7.3 and earlier, the type of the left-hand operand of the `??` operator must be either a [reference type](../keywords/reference-types.md) or a [nullable value type](../builtin-types/nullable-value-types.md).</span></span> <span data-ttu-id="7507b-111">A partir C# 8.0, ese requisito se reemplaza por lo siguiente: el tipo del operando izquierdo de los operadores `??` y `??=` no puede ser un tipo de valor que no acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="7507b-111">Beginning with C# 8.0, that requirement is replaced with the following: the type of the left-hand operand of the `??` and `??=` operators cannot be a non-nullable value type.</span></span> <span data-ttu-id="7507b-112">En concreto, a partir de C# 8.0 puede usar los operadores de fusión de NULL con parámetros de tipo sin restricciones:</span><span class="sxs-lookup"><span data-stu-id="7507b-112">In particular, beginning with C# 8.0, you can use the null-coalescing operators with unconstrained type parameters:</span></span>

[!code-csharp[unconstrained type parameter](snippets/shared/NullCoalescingOperator.cs#UnconstrainedType)]

<span data-ttu-id="7507b-113">Los operadores de uso combinado de NULL son asociativos a la derecha.</span><span class="sxs-lookup"><span data-stu-id="7507b-113">The null-coalescing operators are right-associative.</span></span> <span data-ttu-id="7507b-114">Es decir, las expresiones del formulario</span><span class="sxs-lookup"><span data-stu-id="7507b-114">That is, expressions of the form</span></span>

```csharp
a ?? b ?? c
d ??= e ??= f
```

<span data-ttu-id="7507b-115">se evalúan como</span><span class="sxs-lookup"><span data-stu-id="7507b-115">are evaluated as</span></span>

```csharp
a ?? (b ?? c)
d ??= (e ??= f)
```

## <a name="examples"></a><span data-ttu-id="7507b-116">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7507b-116">Examples</span></span>

<span data-ttu-id="7507b-117">Los operadores `??` y `??=` puede resultar útiles en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="7507b-117">The `??` and `??=` operators can be useful in the following scenarios:</span></span>

- <span data-ttu-id="7507b-118">En expresiones con los [operadores no condicionales ? y ?[]](member-access-operators.md#null-conditional-operators--and-), puede usar el operador `??` para proporcionar una expresión alternativa para evaluar en caso de que el resultado de la expresión con la operación condicional NULL sea `null`:</span><span class="sxs-lookup"><span data-stu-id="7507b-118">In expressions with the [null-conditional operators ?. and ?[]](member-access-operators.md#null-conditional-operators--and-), you can use the `??` operator to provide an alternative expression to evaluate in case the result of the expression with null-conditional operations is `null`:</span></span>

  [!code-csharp-interactive[with null-conditional](snippets/shared/NullCoalescingOperator.cs#WithNullConditional)]

- <span data-ttu-id="7507b-119">Cuando trabaja con [tipos de valor que aceptan valores NULL](../builtin-types/nullable-value-types.md) y necesita proporcionar un valor de un tipo de valor subyacente, use el operador `??` para especificar el valor para proporcionar en caso de que un valor de tipo que acepta valores NULL sea `null`:</span><span class="sxs-lookup"><span data-stu-id="7507b-119">When you work with [nullable value types](../builtin-types/nullable-value-types.md) and need to provide a value of an underlying value type, use the `??` operator to specify the value to provide in case a nullable type value is `null`:</span></span>

  [!code-csharp-interactive[with nullable types](snippets/shared/NullCoalescingOperator.cs#WithNullableTypes)]

  <span data-ttu-id="7507b-120">Use el método <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> si el valor que se va usar cuando un valor de tipo que acepta valores NULL es `null` debe ser el valor predeterminado del tipo de valor subyacente.</span><span class="sxs-lookup"><span data-stu-id="7507b-120">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a nullable type value is `null` should be the default value of the underlying value type.</span></span>

- <span data-ttu-id="7507b-121">A partir de C# 7.0, puede usar una [expresión `throw`](../keywords/throw.md#the-throw-expression) como el operando derecho del operador `??` para hacer el código de comprobación de argumentos más conciso:</span><span class="sxs-lookup"><span data-stu-id="7507b-121">Beginning with C# 7.0, you can use a [`throw` expression](../keywords/throw.md#the-throw-expression) as the right-hand operand of the `??` operator to make the argument-checking code more concise:</span></span>

  [!code-csharp[with throw expression](snippets/shared/NullCoalescingOperator.cs#WithThrowExpression)]

  <span data-ttu-id="7507b-122">El ejemplo anterior también muestra cómo usar [miembros con forma de expresión](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) para definir una propiedad.</span><span class="sxs-lookup"><span data-stu-id="7507b-122">The preceding example also demonstrates how to use [expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) to define a property.</span></span>

- <span data-ttu-id="7507b-123">A partir de C# 8.0, puede usar el operador `??=` para reemplazar el código del formulario</span><span class="sxs-lookup"><span data-stu-id="7507b-123">Beginning with C# 8.0, you can use the `??=` operator to replace the code of the form</span></span>

  ```csharp
  if (variable is null)
  {
      variable = expression;
  }
  ```

  <span data-ttu-id="7507b-124">por el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="7507b-124">with the following code:</span></span>

  ```csharp
  variable ??= expression;
  ```

## <a name="operator-overloadability"></a><span data-ttu-id="7507b-125">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="7507b-125">Operator overloadability</span></span>

<span data-ttu-id="7507b-126">Los operadores `??` y `??=` no se pueden sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="7507b-126">The operators `??` and `??=` cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="7507b-127">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="7507b-127">C# language specification</span></span>

<span data-ttu-id="7507b-128">Para obtener más información sobre el operador `??`, vea la sección [El operador de uso combinado de NULL](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="7507b-128">For more information about the `??` operator, see [The null coalescing operator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="7507b-129">Para más información sobre el operador `??=`, consulte la [nota de propuesta de características](~/_csharplang/proposals/csharp-8.0/null-coalescing-assignment.md).</span><span class="sxs-lookup"><span data-stu-id="7507b-129">For more information about the `??=` operator, see the [feature proposal note](~/_csharplang/proposals/csharp-8.0/null-coalescing-assignment.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7507b-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="7507b-130">See also</span></span>

- [<span data-ttu-id="7507b-131">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="7507b-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="7507b-132">Operadores y expresiones de C#</span><span class="sxs-lookup"><span data-stu-id="7507b-132">C# operators and expressions</span></span>](index.md)
- <span data-ttu-id="7507b-133">[Operadores ?. y ?[]](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="7507b-133">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="7507b-134">Operador ?:</span><span class="sxs-lookup"><span data-stu-id="7507b-134">?: operator</span></span>](conditional-operator.md)

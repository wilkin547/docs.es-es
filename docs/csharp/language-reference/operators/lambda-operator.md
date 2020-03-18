---
title: Operador => (referencia de C#)
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: 15c02e11610866f359e3e3a7e2751ded918154b7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846263"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="8689b-102">Operador => (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="8689b-102">=> operator (C# reference)</span></span>

<span data-ttu-id="8689b-103">El token `=>` se admite de dos formas: como el [operador lambda](#lambda-operator) y como un separador de un nombre de miembro y la implementación del miembro en una [definición de cuerpo de expresión](#expression-body-definition).</span><span class="sxs-lookup"><span data-stu-id="8689b-103">The `=>` token is supported in two forms: as the [lambda operator](#lambda-operator) and as a separator of a member name and the member implementation in an [expression body definition](#expression-body-definition).</span></span>

## <a name="lambda-operator"></a><span data-ttu-id="8689b-104">Operador{1}{2}lambda</span><span class="sxs-lookup"><span data-stu-id="8689b-104">Lambda operator</span></span>

<span data-ttu-id="8689b-105">En las [expresiones lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md), el operador`=>`{4}lambda {5} separa los parámetros de entrada del lado izquierdo y el cuerpo lambda del lado derecho.</span><span class="sxs-lookup"><span data-stu-id="8689b-105">In [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md), the lambda operator `=>` separates the input parameters on the left side from the lambda body on the right side.</span></span>

<span data-ttu-id="8689b-106">En el ejemplo siguiente se usa la característica [LINQ](../../programming-guide/concepts/linq/index.md) con sintaxis de método para demostrar el uso de las expresiones lambda:</span><span class="sxs-lookup"><span data-stu-id="8689b-106">The following example uses the [LINQ](../../programming-guide/concepts/linq/index.md) feature with method syntax to demonstrate the usage of lambda expressions:</span></span>

[!code-csharp-interactive[infer types of input variables](snippets/LambdaOperator.cs#InferredTypes)]

<span data-ttu-id="8689b-107">Los parámetros de entrada de una expresión lambda están fuertemente tipados en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="8689b-107">Input parameters of a lambda expression are strongly typed at compile time.</span></span> <span data-ttu-id="8689b-108">Cuando el compilador puede deducir los tipos de los parámetros de entrada, como en el ejemplo anterior, se pueden omitir las declaraciones de tipos.</span><span class="sxs-lookup"><span data-stu-id="8689b-108">When the compiler can infer the types of input parameters, like in the preceding example, you may omit type declarations.</span></span> <span data-ttu-id="8689b-109">Si tiene que especificar el tipo de los parámetros de entrada, debe hacerlo para cada uno de ellos, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8689b-109">If you need to specify the type of input parameters, you must do that for each parameter, as the following example shows:</span></span>

[!code-csharp-interactive[specify types of input variables](snippets/LambdaOperator.cs#ExplicitTypes)]

<span data-ttu-id="8689b-110">En el ejemplo siguiente se muestra cómo definir una expresión lambda sin parámetros de entrada:</span><span class="sxs-lookup"><span data-stu-id="8689b-110">The following example shows how to define a lambda expression without input parameters:</span></span>

[!code-csharp-interactive[without input variables](snippets/LambdaOperator.cs#WithoutInput)]

<span data-ttu-id="8689b-111">Para obtener más información, vea [Expresiones lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="8689b-111">For more information, see [Lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>

## <a name="expression-body-definition"></a><span data-ttu-id="8689b-112">Definición de cuerpo de expresiones</span><span class="sxs-lookup"><span data-stu-id="8689b-112">Expression body definition</span></span>

<span data-ttu-id="8689b-113">Una definición de cuerpo de expresión tiene la siguiente sintaxis general:</span><span class="sxs-lookup"><span data-stu-id="8689b-113">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="8689b-114">donde `expression` es una expresión válida.</span><span class="sxs-lookup"><span data-stu-id="8689b-114">where `expression` is a valid expression.</span></span> <span data-ttu-id="8689b-115">El tipo de valor devuelto de `expression` se debe poder convertir implícitamente al tipo de valor devuelto del miembro.</span><span class="sxs-lookup"><span data-stu-id="8689b-115">The return type of `expression` must be implicitly convertible to the member's return type.</span></span> <span data-ttu-id="8689b-116">Si el tipo de valor devuelto del miembro es `void`, o si el miembro es un constructor, un finalizador o un descriptor de acceso `set` de propiedad, `expression` debe ser una [*expresión de instrucción*](~/_csharplang/spec/statements.md#expression-statements), que puede ser de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="8689b-116">If the member's return type is `void` or if the member is a constructor, a finalizer, or a property `set` accessor, `expression` must be a [*statement expression*](~/_csharplang/spec/statements.md#expression-statements), which can be of any type.</span></span>

<span data-ttu-id="8689b-117">En el ejemplo siguiente se muestra una definición de cuerpo de expresión para un método `Person.ToString`:</span><span class="sxs-lookup"><span data-stu-id="8689b-117">The following example shows an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="8689b-118">Es una versión abreviada de la definición de método siguiente:</span><span class="sxs-lookup"><span data-stu-id="8689b-118">It's a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```

<span data-ttu-id="8689b-119">A partir de C# 6, se admiten definiciones de cuerpos de expresión para métodos, operadores y propiedades de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="8689b-119">Expression body definitions for methods, operators, and read-only properties are supported beginning with C# 6.</span></span> <span data-ttu-id="8689b-120">A partir de C# 7.0, se admiten definiciones de cuerpos de expresión para constructores, finalizadores y descriptores de acceso de propiedad e indizador.</span><span class="sxs-lookup"><span data-stu-id="8689b-120">Expression body definitions for constructors, finalizers, and property and indexer accessors are supported beginning with C# 7.0.</span></span>

<span data-ttu-id="8689b-121">Para obtener más información, vea [Miembros con forma de expresión](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="8689b-121">For more information, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="8689b-122">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="8689b-122">Operator overloadability</span></span>

<span data-ttu-id="8689b-123">El operador `=>` no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="8689b-123">The `=>` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="8689b-124">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="8689b-124">C# language specification</span></span>

<span data-ttu-id="8689b-125">Para más información sobre el operador lambda, vea la sección [Expresiones de función anónima](~/_csharplang/spec/expressions.md#anonymous-function-expressions) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="8689b-125">For more information about the lambda operator, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8689b-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="8689b-126">See also</span></span>

- [<span data-ttu-id="8689b-127">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="8689b-127">C# reference</span></span>](../index.md)
- [<span data-ttu-id="8689b-128">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="8689b-128">C# operators</span></span>](index.md)

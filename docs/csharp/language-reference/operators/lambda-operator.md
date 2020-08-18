---
title: Operador => (referencia de C#)
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: 30e1a3546f83a0a1ba5b1363238878868e94ab93
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063138"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="17573-102">Operador => (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="17573-102">=> operator (C# reference)</span></span>

<span data-ttu-id="17573-103">El token `=>` se admite de dos formas: como el [operador lambda](#lambda-operator) y como un separador de un nombre de miembro y la implementación del miembro en una [definición de cuerpo de expresión](#expression-body-definition).</span><span class="sxs-lookup"><span data-stu-id="17573-103">The `=>` token is supported in two forms: as the [lambda operator](#lambda-operator) and as a separator of a member name and the member implementation in an [expression body definition](#expression-body-definition).</span></span>

## <a name="lambda-operator"></a><span data-ttu-id="17573-104">Operador{1}{2}lambda</span><span class="sxs-lookup"><span data-stu-id="17573-104">Lambda operator</span></span>

<span data-ttu-id="17573-105">En las [expresiones lambda](lambda-expressions.md), el operador`=>`{4}lambda {5} separa los parámetros de entrada del lado izquierdo y el cuerpo lambda del lado derecho.</span><span class="sxs-lookup"><span data-stu-id="17573-105">In [lambda expressions](lambda-expressions.md), the lambda operator `=>` separates the input parameters on the left side from the lambda body on the right side.</span></span>

<span data-ttu-id="17573-106">En el ejemplo siguiente se usa la característica [LINQ](../../programming-guide/concepts/linq/index.md) con sintaxis de método para demostrar el uso de las expresiones lambda:</span><span class="sxs-lookup"><span data-stu-id="17573-106">The following example uses the [LINQ](../../programming-guide/concepts/linq/index.md) feature with method syntax to demonstrate the usage of lambda expressions:</span></span>

[!code-csharp-interactive[infer types of input variables](snippets/shared/LambdaOperator.cs#InferredTypes)]

<span data-ttu-id="17573-107">Los parámetros de entrada de una expresión lambda están fuertemente tipados en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="17573-107">Input parameters of a lambda expression are strongly typed at compile time.</span></span> <span data-ttu-id="17573-108">Cuando el compilador puede deducir los tipos de los parámetros de entrada, como en el ejemplo anterior, se pueden omitir las declaraciones de tipos.</span><span class="sxs-lookup"><span data-stu-id="17573-108">When the compiler can infer the types of input parameters, like in the preceding example, you may omit type declarations.</span></span> <span data-ttu-id="17573-109">Si tiene que especificar el tipo de los parámetros de entrada, debe hacerlo para cada uno de ellos, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="17573-109">If you need to specify the type of input parameters, you must do that for each parameter, as the following example shows:</span></span>

[!code-csharp-interactive[specify types of input variables](snippets/shared/LambdaOperator.cs#ExplicitTypes)]

<span data-ttu-id="17573-110">En el ejemplo siguiente se muestra cómo definir una expresión lambda sin parámetros de entrada:</span><span class="sxs-lookup"><span data-stu-id="17573-110">The following example shows how to define a lambda expression without input parameters:</span></span>

[!code-csharp-interactive[without input variables](snippets/shared/LambdaOperator.cs#WithoutInput)]

<span data-ttu-id="17573-111">Para obtener más información, vea [Expresiones lambda](lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="17573-111">For more information, see [Lambda expressions](lambda-expressions.md).</span></span>

## <a name="expression-body-definition"></a><span data-ttu-id="17573-112">Definición de cuerpo de expresiones</span><span class="sxs-lookup"><span data-stu-id="17573-112">Expression body definition</span></span>

<span data-ttu-id="17573-113">Una definición de cuerpo de expresión tiene la siguiente sintaxis general:</span><span class="sxs-lookup"><span data-stu-id="17573-113">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="17573-114">donde `expression` es una expresión válida.</span><span class="sxs-lookup"><span data-stu-id="17573-114">where `expression` is a valid expression.</span></span> <span data-ttu-id="17573-115">El tipo de valor devuelto de `expression` se debe poder convertir implícitamente al tipo de valor devuelto del miembro.</span><span class="sxs-lookup"><span data-stu-id="17573-115">The return type of `expression` must be implicitly convertible to the member's return type.</span></span> <span data-ttu-id="17573-116">Si el tipo de valor devuelto del miembro es `void`, o si el miembro es un constructor, un finalizador o un descriptor de acceso `set` de propiedad o indizador, `expression` debe ser una [*expresión de instrucción*](~/_csharplang/spec/statements.md#expression-statements).</span><span class="sxs-lookup"><span data-stu-id="17573-116">If the member's return type is `void` or if the member is a constructor, a finalizer, or a property or indexer `set` accessor, `expression` must be a [*statement expression*](~/_csharplang/spec/statements.md#expression-statements).</span></span> <span data-ttu-id="17573-117">Dado que el resultado de la expresión se descarta, el tipo de valor devuelto de esa expresión puede ser cualquiera.</span><span class="sxs-lookup"><span data-stu-id="17573-117">Because the expression's result is discarded, the return type of that expression can be any type.</span></span>

<span data-ttu-id="17573-118">En el ejemplo siguiente se muestra una definición de cuerpo de expresión para un método `Person.ToString`:</span><span class="sxs-lookup"><span data-stu-id="17573-118">The following example shows an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="17573-119">Es una versión abreviada de la definición de método siguiente:</span><span class="sxs-lookup"><span data-stu-id="17573-119">It's a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```

<span data-ttu-id="17573-120">A partir de C# 6, se admiten definiciones de cuerpos de expresión para métodos, operadores y propiedades de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="17573-120">Expression body definitions for methods, operators, and read-only properties are supported beginning with C# 6.</span></span> <span data-ttu-id="17573-121">A partir de C# 7.0, se admiten definiciones de cuerpos de expresión para constructores, finalizadores y descriptores de acceso de propiedad e indizador.</span><span class="sxs-lookup"><span data-stu-id="17573-121">Expression body definitions for constructors, finalizers, and property and indexer accessors are supported beginning with C# 7.0.</span></span>

<span data-ttu-id="17573-122">Para obtener más información, vea [Miembros con forma de expresión](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="17573-122">For more information, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="17573-123">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="17573-123">Operator overloadability</span></span>

<span data-ttu-id="17573-124">El operador `=>` no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="17573-124">The `=>` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="17573-125">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="17573-125">C# language specification</span></span>

<span data-ttu-id="17573-126">Para más información sobre el operador lambda, vea la sección [Expresiones de función anónima](~/_csharplang/spec/expressions.md#anonymous-function-expressions) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="17573-126">For more information about the lambda operator, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="17573-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="17573-127">See also</span></span>

- [<span data-ttu-id="17573-128">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="17573-128">C# reference</span></span>](../index.md)
- [<span data-ttu-id="17573-129">Operadores y expresiones de C#</span><span class="sxs-lookup"><span data-stu-id="17573-129">C# operators and expressions</span></span>](index.md)

---
title: Operador => (referencia de C#)
ms.custom: seodec18
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: 3b3a5c2e96e92271da66cbd8f1039a9ec97544fa
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971231"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="1ee28-102">Operador => (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="1ee28-102">=> operator (C# reference)</span></span>

<span data-ttu-id="1ee28-103">El token `=>` se admite de dos formas: como el operador lambda y como un separador de un nombre de miembro y la implementación del miembro en una definición de cuerpo de expresión.</span><span class="sxs-lookup"><span data-stu-id="1ee28-103">The `=>` token is supported in two forms: as the lambda operator and as a separator of a member name and the member implementation in an expression body definition.</span></span>

## <a name="lambda-operator"></a><span data-ttu-id="1ee28-104">Operador lambda</span><span class="sxs-lookup"><span data-stu-id="1ee28-104">Lambda operator</span></span>

<span data-ttu-id="1ee28-105">En las [expresiones lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md), el operador lambda `=>` se usa para separar las variables de entrada del lado izquierdo y el cuerpo lambda del lado derecho.</span><span class="sxs-lookup"><span data-stu-id="1ee28-105">In [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md), the lambda operator `=>` separates the input variables on the left side from the lambda body on the right side.</span></span>

<span data-ttu-id="1ee28-106">En el ejemplo siguiente se usa la característica [LINQ](../../programming-guide/concepts/linq/index.md) con sintaxis de método para demostrar el uso de las expresiones lambda:</span><span class="sxs-lookup"><span data-stu-id="1ee28-106">The following example uses the [LINQ](../../programming-guide/concepts/linq/index.md) feature with method syntax to demonstrate the usage of lambda expressions:</span></span>

[!code-csharp-interactive[infer types of input variables](~/samples/csharp/language-reference/operators/LambdaOperator.cs#InferredTypes)]

<span data-ttu-id="1ee28-107">Las variables de entrada de las expresiones lambda están fuertemente tipadas en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="1ee28-107">Input variables of lambda expressions are strongly typed at compile time.</span></span> <span data-ttu-id="1ee28-108">Cuando el compilador puede deducir los tipos de las variables de entrada, como en el ejemplo anterior, las declaraciones de tipos se pueden omitir.</span><span class="sxs-lookup"><span data-stu-id="1ee28-108">When the compiler can infer the types of input variables, like in the preceding example, you may omit type declarations.</span></span> <span data-ttu-id="1ee28-109">Si tiene que especificar el tipo de las variables de entrada, debe hacerlo para cada variable, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1ee28-109">If you need to specify the type of input variables, you must do that for each variable, as the following example shows:</span></span>

[!code-csharp-interactive[specify types of input variables](~/samples/csharp/language-reference/operators/LambdaOperator.cs#ExplicitTypes)]

<span data-ttu-id="1ee28-110">En el ejemplo siguiente se muestra cómo definir una expresión lambda sin variables de entrada:</span><span class="sxs-lookup"><span data-stu-id="1ee28-110">The following example shows how to define a lambda expression without input variables:</span></span>

[!code-csharp-interactive[without input variables](~/samples/csharp/language-reference/operators/LambdaOperator.cs#WithoutInput)]

<span data-ttu-id="1ee28-111">Para obtener más información, vea [Expresiones lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="1ee28-111">For more information, see [Lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>

## <a name="expression-body-definition"></a><span data-ttu-id="1ee28-112">Definición de cuerpo de expresiones</span><span class="sxs-lookup"><span data-stu-id="1ee28-112">Expression body definition</span></span>

<span data-ttu-id="1ee28-113">Una definición de cuerpo de expresión tiene la siguiente sintaxis general:</span><span class="sxs-lookup"><span data-stu-id="1ee28-113">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="1ee28-114">donde `expression` es una expresión válida.</span><span class="sxs-lookup"><span data-stu-id="1ee28-114">where `expression` is a valid expression.</span></span> <span data-ttu-id="1ee28-115">El tipo de valor devuelto de `expression` se debe poder convertir implícitamente al tipo de valor devuelto del miembro.</span><span class="sxs-lookup"><span data-stu-id="1ee28-115">The return type of `expression` must be implicitly convertible to the member's return type.</span></span> <span data-ttu-id="1ee28-116">Si el tipo de valor devuelto del miembro es `void`, o si el miembro es un constructor, un finalizador o un descriptor de acceso `set` de propiedad, `expression` debe ser una [*expresión de instrucción*](~/_csharplang/spec/statements.md#expression-statements); puede ser de cualquier tipo entonces.</span><span class="sxs-lookup"><span data-stu-id="1ee28-116">If the member's return type is `void` or if the member is a constructor, a finalizer, or a property `set` accessor, `expression` must be a [*statement expression*](~/_csharplang/spec/statements.md#expression-statements); it can be of any type then.</span></span>

<span data-ttu-id="1ee28-117">En el ejemplo siguiente se muestra una definición de cuerpo de expresión para un método `Person.ToString`:</span><span class="sxs-lookup"><span data-stu-id="1ee28-117">The following example shows an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="1ee28-118">Es una versión abreviada de la definición de método siguiente:</span><span class="sxs-lookup"><span data-stu-id="1ee28-118">It's a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```

<span data-ttu-id="1ee28-119">A partir de C# 6, se admiten definiciones de cuerpos de expresión para métodos y propiedades de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="1ee28-119">Expression body definitions for methods and read-only properties are supported starting with C# 6.</span></span> <span data-ttu-id="1ee28-120">A partir de C# 7.0, se admiten definiciones de cuerpos de expresión para constructores, finalizadores, descriptores de acceso de propiedad e indizadores.</span><span class="sxs-lookup"><span data-stu-id="1ee28-120">Expression body definitions for constructors, finalizers, property accessors, and indexers are supported starting with C# 7.0.</span></span>

<span data-ttu-id="1ee28-121">Para obtener más información, vea [Miembros con forma de expresión](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="1ee28-121">For more information, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="1ee28-122">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="1ee28-122">Operator overloadability</span></span>

<span data-ttu-id="1ee28-123">El operador `=>` no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="1ee28-123">The `=>` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1ee28-124">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="1ee28-124">C# language specification</span></span>

<span data-ttu-id="1ee28-125">Para obtener más información, vea la sección [Expresiones de función anónima](~/_csharplang/spec/expressions.md#anonymous-function-expressions) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="1ee28-125">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1ee28-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ee28-126">See also</span></span>

- [<span data-ttu-id="1ee28-127">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="1ee28-127">C# reference</span></span>](../index.md)
- [<span data-ttu-id="1ee28-128">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="1ee28-128">C# operators</span></span>](index.md)
- [<span data-ttu-id="1ee28-129">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="1ee28-129">Lambda expressions</span></span>](../../programming-guide/statements-expressions-operators/lambda-expressions.md)
- [<span data-ttu-id="1ee28-130">Miembros con forma de expresión</span><span class="sxs-lookup"><span data-stu-id="1ee28-130">Expression-bodied members</span></span>](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)

---
title: 'Operador =>: Referencia de C#'
ms.custom: seodec18
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: 4c075cedb3cf479f53409f3b0acf4463fc3d7a03
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758216"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="5552a-102">Operador => (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="5552a-102">=> operator (C# Reference)</span></span>

<span data-ttu-id="5552a-103">El token `=>` se admite de dos formas: como el operador lambda y como un separador de un nombre de miembro y la implementación del miembro en una definición de cuerpo de expresión.</span><span class="sxs-lookup"><span data-stu-id="5552a-103">The `=>` token is supported in two forms: as the lambda operator and as a separator of a member name and the member implementation in an expression body definition.</span></span>

## <a name="lambda-operator"></a><span data-ttu-id="5552a-104">Operador lambda</span><span class="sxs-lookup"><span data-stu-id="5552a-104">Lambda operator</span></span>

<span data-ttu-id="5552a-105">En las [expresiones lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md), el operador lambda `=>` se usa para separar las variables de entrada del lado izquierdo y el cuerpo lambda del lado derecho.</span><span class="sxs-lookup"><span data-stu-id="5552a-105">In [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md), the lambda operator `=>` separates the input variables on the left side from the lambda body on the right side.</span></span>

<span data-ttu-id="5552a-106">En el ejemplo siguiente se usa la característica [LINQ](../../programming-guide/concepts/linq/index.md) con sintaxis de método para demostrar el uso de las expresiones lambda:</span><span class="sxs-lookup"><span data-stu-id="5552a-106">The following example uses the [LINQ](../../programming-guide/concepts/linq/index.md) feature with method syntax to demonstrate the usage of lambda expressions:</span></span>

[!code-csharp-interactive[infer types of input variables](~/samples/csharp/language-reference/operators/LambdaOperator.cs#InferredTypes)]

<span data-ttu-id="5552a-107">Las variables de entrada de las expresiones lambda están fuertemente tipadas en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="5552a-107">Input variables of lambda expressions are strongly typed at compile time.</span></span> <span data-ttu-id="5552a-108">Cuando el compilador puede deducir los tipos de las variables de entrada, como en el ejemplo anterior, las declaraciones de tipos se pueden omitir.</span><span class="sxs-lookup"><span data-stu-id="5552a-108">When the compiler can infer the types of input variables, like in the preceding example, you may omit type declarations.</span></span> <span data-ttu-id="5552a-109">Si tiene que especificar el tipo de las variables de entrada, debe hacerlo para cada variable, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5552a-109">If you need to specify the type of input variables, you must do that for each variable, as the following example shows:</span></span>

[!code-csharp-interactive[specify types of input variables](~/samples/csharp/language-reference/operators/LambdaOperator.cs#ExplicitTypes)]

<span data-ttu-id="5552a-110">En el ejemplo siguiente se muestra cómo definir una expresión lambda sin variables de entrada:</span><span class="sxs-lookup"><span data-stu-id="5552a-110">The following example shows how to define a lambda expression without input variables:</span></span>

[!code-csharp-interactive[without input variables](~/samples/csharp/language-reference/operators/LambdaOperator.cs#WithoutInput)]

<span data-ttu-id="5552a-111">Para obtener más información, vea [Expresiones lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="5552a-111">For more information, see [Lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>

## <a name="expression-body-definition"></a><span data-ttu-id="5552a-112">Definición de cuerpo de expresiones</span><span class="sxs-lookup"><span data-stu-id="5552a-112">Expression body definition</span></span>

<span data-ttu-id="5552a-113">Una definición de cuerpo de expresión tiene la siguiente sintaxis general:</span><span class="sxs-lookup"><span data-stu-id="5552a-113">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="5552a-114">donde *expresión* es una expresión válida.</span><span class="sxs-lookup"><span data-stu-id="5552a-114">where *expression* is a valid expression.</span></span> <span data-ttu-id="5552a-115">Tenga en cuenta que *expresión* puede ser una *expresión de instrucción* solo si el tipo de valor devuelto del miembro es `void`, o bien si el miembro es un constructor, un finalizador o un descriptor de acceso `set` de propiedad.</span><span class="sxs-lookup"><span data-stu-id="5552a-115">Note that *expression* can be a *statement expression* only if the member's return type is `void`, or if the member is a constructor, a finalizer, or a property `set` accessor.</span></span>

<span data-ttu-id="5552a-116">En el ejemplo siguiente se muestra una definición de cuerpo de expresión para un método `Person.ToString`:</span><span class="sxs-lookup"><span data-stu-id="5552a-116">The following example shows an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="5552a-117">Es una versión abreviada de la definición de método siguiente:</span><span class="sxs-lookup"><span data-stu-id="5552a-117">It's a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```

<span data-ttu-id="5552a-118">A partir de C# 6, se admiten definiciones de cuerpos de expresión para métodos y propiedades de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="5552a-118">Expression body definitions for methods and read-only properties are supported starting with C# 6.</span></span> <span data-ttu-id="5552a-119">A partir de C# 7.0, se admiten definiciones de cuerpos de expresión para constructores, finalizadores, descriptores de acceso de propiedad e indizadores.</span><span class="sxs-lookup"><span data-stu-id="5552a-119">Expression body definitions for constructors, finalizers, property accessors, and indexers are supported starting with C# 7.0.</span></span>

<span data-ttu-id="5552a-120">Para obtener más información, vea [Miembros con forma de expresión](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="5552a-120">For more information, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="5552a-121">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="5552a-121">Operator overloadability</span></span>

<span data-ttu-id="5552a-122">El operador `=>` no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="5552a-122">The `=>` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5552a-123">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="5552a-123">C# language specification</span></span>

<span data-ttu-id="5552a-124">Para obtener más información, vea la sección [Expresiones de función anónima](~/_csharplang/spec/expressions.md#anonymous-function-expressions) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="5552a-124">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5552a-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="5552a-125">See also</span></span>

- [<span data-ttu-id="5552a-126">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="5552a-126">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5552a-127">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="5552a-127">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5552a-128">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="5552a-128">C# Operators</span></span>](index.md)
- [<span data-ttu-id="5552a-129">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="5552a-129">Lambda expressions</span></span>](../../programming-guide/statements-expressions-operators/lambda-expressions.md)
- [<span data-ttu-id="5552a-130">Miembros con forma de expresión</span><span class="sxs-lookup"><span data-stu-id="5552a-130">Expression-bodied members</span></span>](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)

---
title: 'Expresiones de valor predeterminado: referencia de C#'
description: Use las expresiones de valor predeterminado para obtener el valor predeterminado de un tipo
ms.date: 03/13/2020
f1_keywords:
- default_CSharpKeyword
- default
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: f03971efa87bf03967c79512e44d22134dd80c17
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916864"
---
# <a name="default-value-expressions-c-reference"></a><span data-ttu-id="27ee0-103">Expresiones de valor predeterminado (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="27ee0-103">default value expressions (C# reference)</span></span>

<span data-ttu-id="27ee0-104">Una expresión de valor predeterminado genera el [valor predeterminado](../builtin-types/default-values.md) de un tipo.</span><span class="sxs-lookup"><span data-stu-id="27ee0-104">A default value expression produces the [default value](../builtin-types/default-values.md) of a type.</span></span> <span data-ttu-id="27ee0-105">Hay dos tipos de expresiones de valor predeterminado: la llamada al [operador predeterminado](#default-operator) y un [literal predeterminado](#default-literal).</span><span class="sxs-lookup"><span data-stu-id="27ee0-105">There are two kinds of default value expressions: the [default operator](#default-operator) call and a [default literal](#default-literal).</span></span>

<span data-ttu-id="27ee0-106">También se usa la palabra clave `default` como etiqueta de mayúsculas y minúsculas predeterminada dentro de una [instrucción `switch`](../keywords/switch.md).</span><span class="sxs-lookup"><span data-stu-id="27ee0-106">You also use the `default` keyword as the default case label within a [`switch` statement](../keywords/switch.md).</span></span>

## <a name="default-operator"></a><span data-ttu-id="27ee0-107">operador default</span><span class="sxs-lookup"><span data-stu-id="27ee0-107">default operator</span></span>

<span data-ttu-id="27ee0-108">El argumento del operador `default` debe ser el nombre de un tipo o un parámetro de tipo, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="27ee0-108">The argument to the `default` operator must be the name of a type or a type parameter, as the following example shows:</span></span>

[!code-csharp-interactive[default of T](snippets/shared/DefaultOperator.cs#WithOperand)]

## <a name="default-literal"></a><span data-ttu-id="27ee0-109">Literal default</span><span class="sxs-lookup"><span data-stu-id="27ee0-109">default literal</span></span>

<span data-ttu-id="27ee0-110">A partir C# de 7.1, puede usar el literal `default` para generar el valor predeterminado de un tipo cuando el compilador puede deducir el tipo de expresión.</span><span class="sxs-lookup"><span data-stu-id="27ee0-110">Beginning with C# 7.1, you can use the `default` literal to produce the default value of a type when the compiler can infer the expression type.</span></span> <span data-ttu-id="27ee0-111">La expresión literal `default` genera el mismo valor que la expresión `default(T)` cuando se deduce el tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="27ee0-111">The `default` literal expression produces the same value as the `default(T)` expression where `T` is the inferred type.</span></span> <span data-ttu-id="27ee0-112">Puede usar el literal `default` en cualquiera de los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="27ee0-112">You can use the `default` literal in any of the following cases:</span></span>

- <span data-ttu-id="27ee0-113">En la asignación o inicialización de una variable.</span><span class="sxs-lookup"><span data-stu-id="27ee0-113">In the assignment or initialization of a variable.</span></span>
- <span data-ttu-id="27ee0-114">En la declaración del valor predeterminado de un [parámetro de método opcional](../../methods.md#optional-parameters-and-arguments).</span><span class="sxs-lookup"><span data-stu-id="27ee0-114">In the declaration of the default value for an [optional method parameter](../../methods.md#optional-parameters-and-arguments).</span></span>
- <span data-ttu-id="27ee0-115">En una llamada al método para proporcionar un valor de argumento.</span><span class="sxs-lookup"><span data-stu-id="27ee0-115">In a method call to provide an argument value.</span></span>
- <span data-ttu-id="27ee0-116">En una [instrucción `return`](../keywords/return.md) o como una expresión de un [miembro con cuerpo de expresión](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="27ee0-116">In a [`return` statement](../keywords/return.md) or as an expression in an [expression-bodied member](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

<span data-ttu-id="27ee0-117">En el ejemplo siguiente se muestra el uso del literal `default`:</span><span class="sxs-lookup"><span data-stu-id="27ee0-117">The following example shows the usage of the `default` literal:</span></span>

[!code-csharp-interactive[default literal](snippets/shared/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a><span data-ttu-id="27ee0-118">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="27ee0-118">C# language specification</span></span>

<span data-ttu-id="27ee0-119">Para más información, consulte la sección [Expresiones de valor predeterminado](~/_csharplang/spec/expressions.md#default-value-expressions) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="27ee0-119">For more information, see the [Default value expressions](~/_csharplang/spec/expressions.md#default-value-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="27ee0-120">Para más información sobre el literal `default`, consulte la [nota de propuesta de características](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span><span class="sxs-lookup"><span data-stu-id="27ee0-120">For more information about the `default` literal, see the [feature proposal note](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="27ee0-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="27ee0-121">See also</span></span>

- [<span data-ttu-id="27ee0-122">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="27ee0-122">C# reference</span></span>](../index.md)
- [<span data-ttu-id="27ee0-123">Operadores y expresiones de C#</span><span class="sxs-lookup"><span data-stu-id="27ee0-123">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="27ee0-124">Valores predeterminados de los tipos de C#</span><span class="sxs-lookup"><span data-stu-id="27ee0-124">Default values of C# types</span></span>](../builtin-types/default-values.md)
- [<span data-ttu-id="27ee0-125">Elementos genéricos en .NET</span><span class="sxs-lookup"><span data-stu-id="27ee0-125">Generics in .NET</span></span>](../../../standard/generics/index.md)

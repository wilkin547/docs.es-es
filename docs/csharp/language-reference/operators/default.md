---
title: Operador default (referencia de C#)
ms.custom: seodec18
description: Uso del operador default para generar el valor predeterminado de un tipo
ms.date: 08/01/2019
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: 5623cb9dc3790b5bb99635c41cb3f122f4c71d8e
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796944"
---
# <a name="default-operator-c-reference"></a><span data-ttu-id="60682-103">Operador default (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="60682-103">default operator (C# reference)</span></span>

<span data-ttu-id="60682-104">El operador `default` genera el [valor predeterminado](../keywords/default-values-table.md) de un tipo.</span><span class="sxs-lookup"><span data-stu-id="60682-104">The `default` operator produces the [default value](../keywords/default-values-table.md) of a type.</span></span> <span data-ttu-id="60682-105">El argumento del operador `default` debe ser el nombre de un tipo o un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="60682-105">The argument to the `default` operator must be the name of a type or a type parameter.</span></span>

<span data-ttu-id="60682-106">En el ejemplo siguiente se muestra el uso del operador `default`:</span><span class="sxs-lookup"><span data-stu-id="60682-106">The following example shows the usage of the `default` operator:</span></span>

[!code-csharp-interactive[default of T](~/samples/csharp/language-reference/operators/DefaultOperator.cs#WithOperand)]

<span data-ttu-id="60682-107">También se utiliza la palabra clave `default` como etiqueta de mayúsculas y minúsculas predeterminada dentro de la [instrucción `switch`](../keywords/switch.md).</span><span class="sxs-lookup"><span data-stu-id="60682-107">You also use the `default` keyword as the default case label within the [`switch` statement](../keywords/switch.md).</span></span>

## <a name="default-literal"></a><span data-ttu-id="60682-108">Literal default</span><span class="sxs-lookup"><span data-stu-id="60682-108">default literal</span></span>

<span data-ttu-id="60682-109">A partir C# de 7.1, puede usar el literal `default` para generar el valor predeterminado de un tipo cuando el compilador puede deducir el tipo de expresión.</span><span class="sxs-lookup"><span data-stu-id="60682-109">Beginning with C# 7.1, you can use the `default` literal to produce the default value of a type when the compiler can infer the expression type.</span></span> <span data-ttu-id="60682-110">La expresión literal `default` genera el mismo valor que la expresión `default(T)` cuando se deduce el tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="60682-110">The `default` literal expression produces the same value as the `default(T)` expression where `T` is the inferred type.</span></span> <span data-ttu-id="60682-111">Puede usar el literal `default` en cualquiera de los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="60682-111">You can use the `default` literal in any of the following cases:</span></span>

- <span data-ttu-id="60682-112">En la asignación o inicialización de una variable.</span><span class="sxs-lookup"><span data-stu-id="60682-112">In the assignment or initialization of a variable.</span></span>
- <span data-ttu-id="60682-113">En la declaración del valor predeterminado de un parámetro de método opcional.</span><span class="sxs-lookup"><span data-stu-id="60682-113">In the declaration of the default value for an optional method parameter.</span></span>
- <span data-ttu-id="60682-114">En una llamada al método para proporcionar un valor de argumento.</span><span class="sxs-lookup"><span data-stu-id="60682-114">In a method call to provide an argument value.</span></span>
- <span data-ttu-id="60682-115">En una instrucción `return` o como una expresión de un miembro con cuerpo de expresión.</span><span class="sxs-lookup"><span data-stu-id="60682-115">In a `return` statement or as an expression in an expression-bodied member.</span></span>

<span data-ttu-id="60682-116">En el ejemplo siguiente se muestra el uso del literal `default`:</span><span class="sxs-lookup"><span data-stu-id="60682-116">The following example shows the usage of the `default` literal:</span></span>

[!code-csharp-interactive[default literal](~/samples/csharp/language-reference/operators/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a><span data-ttu-id="60682-117">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="60682-117">C# language specification</span></span>

<span data-ttu-id="60682-118">Para más información, consulte la sección [Expresiones de valor predeterminado](~/_csharplang/spec/expressions.md#default-value-expressions) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="60682-118">For more information, see the [Default value expressions](~/_csharplang/spec/expressions.md#default-value-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="60682-119">Para más información sobre el literal `default`, consulte la [nota de propuesta de características](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span><span class="sxs-lookup"><span data-stu-id="60682-119">For more information about the `default` literal, see the [feature proposal note](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="60682-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="60682-120">See also</span></span>

- [<span data-ttu-id="60682-121">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="60682-121">C# reference</span></span>](../index.md)
- [<span data-ttu-id="60682-122">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="60682-122">C# operators</span></span>](index.md)
- [<span data-ttu-id="60682-123">Tabla de valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="60682-123">Default values table</span></span>](../keywords/default-values-table.md)

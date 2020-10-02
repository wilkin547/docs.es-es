---
description: 'Operador delegate: referencia de C#'
title: 'Operador delegate: referencia de C#'
ms.date: 09/25/2020
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: db2bf673db12e4a10741a26112820726a4b8aaee
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2020
ms.locfileid: "91247662"
---
# <a name="delegate-operator-c-reference"></a><span data-ttu-id="7d59c-103">Operador delegate (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="7d59c-103">delegate operator (C# reference)</span></span>

<span data-ttu-id="7d59c-104">El operador `delegate` crea un método anónimo que se puede convertir en un tipo delegado:</span><span class="sxs-lookup"><span data-stu-id="7d59c-104">The `delegate` operator creates an anonymous method that can be converted to a delegate type:</span></span>

[!code-csharp-interactive[anonymous method](snippets/shared/DelegateOperator.cs#AnonymousMethod)]

> [!NOTE]
> <span data-ttu-id="7d59c-105">A partir de C# 3, las expresiones lambda proporcionan una manera más concisa y expresiva de crear una función anónima.</span><span class="sxs-lookup"><span data-stu-id="7d59c-105">Beginning with C# 3, lambda expressions provide a more concise and expressive way to create an anonymous function.</span></span> <span data-ttu-id="7d59c-106">Use el [operador =>](lambda-operator.md) para construir una expresión lambda:</span><span class="sxs-lookup"><span data-stu-id="7d59c-106">Use the [=> operator](lambda-operator.md) to construct a lambda expression:</span></span>
>
> [!code-csharp-interactive[lambda expression](snippets/shared/DelegateOperator.cs#Lambda)]
>
> <span data-ttu-id="7d59c-107">Para más información sobre las características de las expresiones lambda, como capturar las variables externas, consulte [Expresiones lambda](lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="7d59c-107">For more information about features of lambda expressions, for example, capturing outer variables, see [Lambda expressions](lambda-expressions.md).</span></span>

<span data-ttu-id="7d59c-108">Al usar el operador `delegate`, puede omitir la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="7d59c-108">When you use the `delegate` operator, you might omit the parameter list.</span></span> <span data-ttu-id="7d59c-109">Si lo hace, el método anónimo creado se puede convertir en un tipo delegado con cualquier lista de parámetros, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7d59c-109">If you do that, the created anonymous method can be converted to a delegate type with any list of  parameters, as the following example shows:</span></span>

[!code-csharp-interactive[no parameter list](snippets/shared/DelegateOperator.cs#WithoutParameterList)]

<span data-ttu-id="7d59c-110">Esta es la única funcionalidad de los métodos anónimos que las expresiones lambda no admiten.</span><span class="sxs-lookup"><span data-stu-id="7d59c-110">That's the only functionality of anonymous methods that is not supported by lambda expressions.</span></span> <span data-ttu-id="7d59c-111">En todos los demás casos, una expresión lambda es una de las maneras preferidas de escribir código alineado.</span><span class="sxs-lookup"><span data-stu-id="7d59c-111">In all other cases, a lambda expression is a preferred way to write inline code.</span></span>

<span data-ttu-id="7d59c-112">A partir de C# 9.0, puede usar [descartes](../../discards.md) para especificar dos o más parámetros de entrada de un método anónimo que no usa el método:</span><span class="sxs-lookup"><span data-stu-id="7d59c-112">Beginning with C# 9.0, you can use [discards](../../discards.md) to specify two or more input parameters of an anonymous method that aren't used by the method:</span></span>

:::code language="csharp" source="snippets/shared/DelegateOperator.cs" id="SnippetDiscards" :::

<span data-ttu-id="7d59c-113">Por compatibilidad con versiones anteriores, si solo un parámetro se denomina `_`, `_` se trata como el nombre de ese parámetro dentro de un método anónimo.</span><span class="sxs-lookup"><span data-stu-id="7d59c-113">For backwards compatibility, if only a single parameter is named `_`, `_` is treated as the name of that parameter within an anonymous method.</span></span>

<span data-ttu-id="7d59c-114">También a partir de C# 9.0, puede usar el modificador `static` en la declaración de un método anónimo:</span><span class="sxs-lookup"><span data-stu-id="7d59c-114">Also beginning with C# 9.0, you can use the `static` modifier at the declaration of an anonymous method:</span></span>

:::code language="csharp" source="snippets/shared/DelegateOperator.cs" id="SnippetStatic" :::

<span data-ttu-id="7d59c-115">Un método anónimo estático no puede capturar variables locales ni el estado de la instancia desde el ámbito de inclusión.</span><span class="sxs-lookup"><span data-stu-id="7d59c-115">A static anonymous method can't capture local variables or instance state from enclosing scopes.</span></span>

<span data-ttu-id="7d59c-116">También puede usar la palabra clave `delegate` para declarar un [tipo delegado](../builtin-types/reference-types.md#the-delegate-type).</span><span class="sxs-lookup"><span data-stu-id="7d59c-116">You also use the `delegate` keyword to declare a [delegate type](../builtin-types/reference-types.md#the-delegate-type).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="7d59c-117">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="7d59c-117">C# language specification</span></span>

<span data-ttu-id="7d59c-118">Para obtener más información, vea la sección [Expresiones de función anónima](~/_csharplang/spec/expressions.md#anonymous-function-expressions) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="7d59c-118">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7d59c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d59c-119">See also</span></span>

- [<span data-ttu-id="7d59c-120">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="7d59c-120">C# reference</span></span>](../index.md)
- [<span data-ttu-id="7d59c-121">Operadores y expresiones de C#</span><span class="sxs-lookup"><span data-stu-id="7d59c-121">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="7d59c-122">Operador =></span><span class="sxs-lookup"><span data-stu-id="7d59c-122">=> operator</span></span>](lambda-operator.md)

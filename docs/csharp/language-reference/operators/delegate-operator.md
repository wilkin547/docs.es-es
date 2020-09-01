---
description: 'Operador delegate: referencia de C#'
title: 'Operador delegate: referencia de C#'
ms.date: 07/18/2019
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: 1dfaaf40c0f5a19534adef3be7e3c917bc95c4a8
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89122256"
---
# <a name="delegate-operator-c-reference"></a><span data-ttu-id="96109-103">Operador delegate (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="96109-103">delegate operator (C# reference)</span></span>

<span data-ttu-id="96109-104">El operador `delegate` crea un método anónimo que se puede convertir en un tipo delegado:</span><span class="sxs-lookup"><span data-stu-id="96109-104">The `delegate` operator creates an anonymous method that can be converted to a delegate type:</span></span>

[!code-csharp-interactive[anonymous method](snippets/shared/DelegateOperator.cs#AnonymousMethod)]

> [!NOTE]
> <span data-ttu-id="96109-105">A partir de C# 3, las expresiones lambda proporcionan una manera más concisa y expresiva de crear una función anónima.</span><span class="sxs-lookup"><span data-stu-id="96109-105">Beginning with C# 3, lambda expressions provide a more concise and expressive way to create an anonymous function.</span></span> <span data-ttu-id="96109-106">Use el [operador =>](lambda-operator.md) para construir una expresión lambda:</span><span class="sxs-lookup"><span data-stu-id="96109-106">Use the [=> operator](lambda-operator.md) to construct a lambda expression:</span></span>
>
> [!code-csharp-interactive[lambda expression](snippets/shared/DelegateOperator.cs#Lambda)]
>
> <span data-ttu-id="96109-107">Para más información sobre las características de las expresiones lambda, como capturar las variables externas, consulte [Expresiones lambda](lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="96109-107">For more information about features of lambda expressions, for example, capturing outer variables, see [Lambda expressions](lambda-expressions.md).</span></span>

<span data-ttu-id="96109-108">Al usar el operador `delegate`, puede omitir la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="96109-108">When you use the `delegate` operator, you might omit the parameter list.</span></span> <span data-ttu-id="96109-109">Si lo hace, el método anónimo creado se puede convertir en un tipo delegado con cualquier lista de parámetros, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="96109-109">If you do that, the created anonymous method can be converted to a delegate type with any list of  parameters, as the following example shows:</span></span>

[!code-csharp-interactive[no parameter list](snippets/shared/DelegateOperator.cs#WithoutParameterList)]

<span data-ttu-id="96109-110">Esta es la única funcionalidad de los métodos anónimos que las expresiones lambda no admiten.</span><span class="sxs-lookup"><span data-stu-id="96109-110">That's the only functionality of anonymous methods that is not supported by lambda expressions.</span></span> <span data-ttu-id="96109-111">En todos los demás casos, una expresión lambda es una de las maneras preferidas de escribir código alineado.</span><span class="sxs-lookup"><span data-stu-id="96109-111">In all other cases, a lambda expression is a preferred way to write inline code.</span></span>

<span data-ttu-id="96109-112">También puede usar la palabra clave `delegate` para declarar un [tipo delegado](../builtin-types/reference-types.md#the-delegate-type).</span><span class="sxs-lookup"><span data-stu-id="96109-112">You also use the `delegate` keyword to declare a [delegate type](../builtin-types/reference-types.md#the-delegate-type).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="96109-113">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="96109-113">C# language specification</span></span>

<span data-ttu-id="96109-114">Para obtener más información, vea la sección [Expresiones de función anónima](~/_csharplang/spec/expressions.md#anonymous-function-expressions) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="96109-114">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="96109-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="96109-115">See also</span></span>

- [<span data-ttu-id="96109-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="96109-116">C# reference</span></span>](../index.md)
- [<span data-ttu-id="96109-117">Operadores y expresiones de C#</span><span class="sxs-lookup"><span data-stu-id="96109-117">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="96109-118">Operador =></span><span class="sxs-lookup"><span data-stu-id="96109-118">=> operator</span></span>](lambda-operator.md)

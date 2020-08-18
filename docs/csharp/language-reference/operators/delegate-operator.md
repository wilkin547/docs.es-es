---
title: 'Operador delegate: referencia de C#'
ms.date: 07/18/2019
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: 33c438b88f1e993f4648786da9b20b91961b7ee1
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062995"
---
# <a name="delegate-operator-c-reference"></a><span data-ttu-id="2ba2a-102">Operador delegate (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="2ba2a-102">delegate operator (C# reference)</span></span>

<span data-ttu-id="2ba2a-103">El operador `delegate` crea un método anónimo que se puede convertir en un tipo delegado:</span><span class="sxs-lookup"><span data-stu-id="2ba2a-103">The `delegate` operator creates an anonymous method that can be converted to a delegate type:</span></span>

[!code-csharp-interactive[anonymous method](snippets/shared/DelegateOperator.cs#AnonymousMethod)]

> [!NOTE]
> <span data-ttu-id="2ba2a-104">A partir de C# 3, las expresiones lambda proporcionan una manera más concisa y expresiva de crear una función anónima.</span><span class="sxs-lookup"><span data-stu-id="2ba2a-104">Beginning with C# 3, lambda expressions provide a more concise and expressive way to create an anonymous function.</span></span> <span data-ttu-id="2ba2a-105">Use el [operador =>](lambda-operator.md) para construir una expresión lambda:</span><span class="sxs-lookup"><span data-stu-id="2ba2a-105">Use the [=> operator](lambda-operator.md) to construct a lambda expression:</span></span>
>
> [!code-csharp-interactive[lambda expression](snippets/shared/DelegateOperator.cs#Lambda)]
>
> <span data-ttu-id="2ba2a-106">Para más información sobre las características de las expresiones lambda, como capturar las variables externas, consulte [Expresiones lambda](lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="2ba2a-106">For more information about features of lambda expressions, for example, capturing outer variables, see [Lambda expressions](lambda-expressions.md).</span></span>

<span data-ttu-id="2ba2a-107">Al usar el operador `delegate`, puede omitir la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="2ba2a-107">When you use the `delegate` operator, you might omit the parameter list.</span></span> <span data-ttu-id="2ba2a-108">Si lo hace, el método anónimo creado se puede convertir en un tipo delegado con cualquier lista de parámetros, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2ba2a-108">If you do that, the created anonymous method can be converted to a delegate type with any list of  parameters, as the following example shows:</span></span>

[!code-csharp-interactive[no parameter list](snippets/shared/DelegateOperator.cs#WithoutParameterList)]

<span data-ttu-id="2ba2a-109">Esta es la única funcionalidad de los métodos anónimos que las expresiones lambda no admiten.</span><span class="sxs-lookup"><span data-stu-id="2ba2a-109">That's the only functionality of anonymous methods that is not supported by lambda expressions.</span></span> <span data-ttu-id="2ba2a-110">En todos los demás casos, una expresión lambda es una de las maneras preferidas de escribir código alineado.</span><span class="sxs-lookup"><span data-stu-id="2ba2a-110">In all other cases, a lambda expression is a preferred way to write inline code.</span></span>

<span data-ttu-id="2ba2a-111">También puede usar la palabra clave `delegate` para declarar un [tipo delegado](../builtin-types/reference-types.md#the-delegate-type).</span><span class="sxs-lookup"><span data-stu-id="2ba2a-111">You also use the `delegate` keyword to declare a [delegate type](../builtin-types/reference-types.md#the-delegate-type).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="2ba2a-112">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="2ba2a-112">C# language specification</span></span>

<span data-ttu-id="2ba2a-113">Para obtener más información, vea la sección [Expresiones de función anónima](~/_csharplang/spec/expressions.md#anonymous-function-expressions) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="2ba2a-113">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2ba2a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ba2a-114">See also</span></span>

- [<span data-ttu-id="2ba2a-115">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="2ba2a-115">C# reference</span></span>](../index.md)
- [<span data-ttu-id="2ba2a-116">Operadores y expresiones de C#</span><span class="sxs-lookup"><span data-stu-id="2ba2a-116">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="2ba2a-117">Operador =></span><span class="sxs-lookup"><span data-stu-id="2ba2a-117">=> operator</span></span>](lambda-operator.md)

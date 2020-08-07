---
title: 'Funciones anónimas: Guía de programación de C#'
description: Aprenda sobre las funciones anónimas. Puede usar una expresión lambda o un método anónimo para crear una función anónima.
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], as anonymous functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
ms.openlocfilehash: ae8bda3c68542637b1430587ca4a537980c028bc
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381676"
---
# <a name="anonymous-functions-c-programming-guide"></a><span data-ttu-id="e79db-104">Funciones anónimas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="e79db-104">Anonymous functions (C# Programming Guide)</span></span>

<span data-ttu-id="e79db-105">Una función anónima es una instrucción o expresión "alineada" que se puede usar siempre que se espera un tipo delegado.</span><span class="sxs-lookup"><span data-stu-id="e79db-105">An anonymous function is an "inline" statement or expression that can be used wherever a delegate type is expected.</span></span> <span data-ttu-id="e79db-106">Se puede usar para inicializar un delegado con nombre o se puede pasar como un parámetro de método en lugar de un tipo delegado con nombre.</span><span class="sxs-lookup"><span data-stu-id="e79db-106">You can use it to initialize a named delegate or pass it instead of a named delegate type as a method parameter.</span></span>

<span data-ttu-id="e79db-107">Puede usar una [expresión lambda](lambda-expressions.md) o un [método anónimo](../../language-reference/operators/delegate-operator.md) para crear una función anónima.</span><span class="sxs-lookup"><span data-stu-id="e79db-107">You can use a [lambda expression](lambda-expressions.md) or an [anonymous method](../../language-reference/operators/delegate-operator.md) to create an anonymous function.</span></span> <span data-ttu-id="e79db-108">Se recomienda usar expresiones lambda porque proporcionan una manera más concisa y expresiva para escribir código alineado.</span><span class="sxs-lookup"><span data-stu-id="e79db-108">We recommend using lambda expressions as they provide more concise and expressive way to write inline code.</span></span> <span data-ttu-id="e79db-109">A diferencia de los métodos anónimos, algunos tipos de expresiones lambda se pueden convertir en los tipos de árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="e79db-109">Unlike anonymous methods, some types of lambda expressions can be converted to the expression tree types.</span></span>

## <a name="the-evolution-of-delegates-in-c"></a><span data-ttu-id="e79db-110">La evolución de los delegados en C\#</span><span class="sxs-lookup"><span data-stu-id="e79db-110">The Evolution of Delegates in C\#</span></span>

 <span data-ttu-id="e79db-111">En C# 1.0, una instancia de un delegado se creaba al inicializarla de forma explícita con un método que se definía en otro lugar en el código.</span><span class="sxs-lookup"><span data-stu-id="e79db-111">In C# 1.0, you created an instance of a delegate by explicitly initializing it with a method that was defined elsewhere in the code.</span></span> <span data-ttu-id="e79db-112">C# 2.0 introdujo el concepto de métodos anónimos como una manera de escribir bloques de instrucciones insertados sin nombre que se podían ejecutar en la invocación de un delegado.</span><span class="sxs-lookup"><span data-stu-id="e79db-112">C# 2.0 introduced the concept of anonymous methods as a way to write unnamed inline statement blocks that can be executed in a delegate invocation.</span></span> <span data-ttu-id="e79db-113">C# 3.0 introdujo las expresiones lambda, que son similares en concepto a los métodos anónimos, pero más expresivas y concisas.</span><span class="sxs-lookup"><span data-stu-id="e79db-113">C# 3.0 introduced lambda expressions, which are similar in concept to anonymous methods but more expressive and concise.</span></span> <span data-ttu-id="e79db-114">Estas dos características se conocen colectivamente como *funciones anónimas*.</span><span class="sxs-lookup"><span data-stu-id="e79db-114">These two features are known collectively as *anonymous functions*.</span></span> <span data-ttu-id="e79db-115">Por lo general, las aplicaciones que tienen como destino .NET Framework 3.5 y versiones posteriores deberían usar expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="e79db-115">In general, applications that target .NET Framework 3.5 or later should use lambda expressions.</span></span>  
  
 <span data-ttu-id="e79db-116">En el ejemplo siguiente se muestra la evolución de la creación de delegados desde C# 1.0 a C# 3.0:</span><span class="sxs-lookup"><span data-stu-id="e79db-116">The following example demonstrates the evolution of delegate creation from C# 1.0 to C# 3.0:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#65](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#65)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="e79db-117">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="e79db-117">C# language specification</span></span>

<span data-ttu-id="e79db-118">Para obtener más información, vea la sección [Expresiones de función anónima](~/_csharplang/spec/expressions.md#anonymous-function-expressions) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="e79db-118">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e79db-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e79db-119">See also</span></span>

- [<span data-ttu-id="e79db-120">Instrucciones, expresiones y operadores</span><span class="sxs-lookup"><span data-stu-id="e79db-120">Statements, Expressions, and Operators</span></span>](./index.md)
- [<span data-ttu-id="e79db-121">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="e79db-121">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="e79db-122">Delegados</span><span class="sxs-lookup"><span data-stu-id="e79db-122">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="e79db-123">Árboles de expresión (C#)</span><span class="sxs-lookup"><span data-stu-id="e79db-123">Expression Trees (C#)</span></span>](../concepts/expression-trees/index.md)

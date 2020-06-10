---
title: 'Funciones anónimas: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], as anonymous functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
ms.openlocfilehash: c99aaf4f35d2d294a9f07de54129bb3b4fbfbfde
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241908"
---
# <a name="anonymous-functions-c-programming-guide"></a><span data-ttu-id="79670-102">Funciones anónimas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="79670-102">Anonymous functions (C# Programming Guide)</span></span>

<span data-ttu-id="79670-103">Una función anónima es una instrucción o expresión "alineada" que se puede usar siempre que se espera un tipo delegado.</span><span class="sxs-lookup"><span data-stu-id="79670-103">An anonymous function is an "inline" statement or expression that can be used wherever a delegate type is expected.</span></span> <span data-ttu-id="79670-104">Se puede usar para inicializar un delegado con nombre o se puede pasar como un parámetro de método en lugar de un tipo delegado con nombre.</span><span class="sxs-lookup"><span data-stu-id="79670-104">You can use it to initialize a named delegate or pass it instead of a named delegate type as a method parameter.</span></span>

<span data-ttu-id="79670-105">Puede usar una [expresión lambda](lambda-expressions.md) o un [método anónimo](../../language-reference/operators/delegate-operator.md) para crear una función anónima.</span><span class="sxs-lookup"><span data-stu-id="79670-105">You can use a [lambda expression](lambda-expressions.md) or an [anonymous method](../../language-reference/operators/delegate-operator.md) to create an anonymous function.</span></span> <span data-ttu-id="79670-106">Se recomienda usar expresiones lambda porque proporcionan una manera más concisa y expresiva para escribir código alineado.</span><span class="sxs-lookup"><span data-stu-id="79670-106">We recommend using lambda expressions as they provide more concise and expressive way to write inline code.</span></span> <span data-ttu-id="79670-107">A diferencia de los métodos anónimos, algunos tipos de expresiones lambda se pueden convertir en los tipos de árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="79670-107">Unlike anonymous methods, some types of lambda expressions can be converted to the expression tree types.</span></span>

## <a name="the-evolution-of-delegates-in-c"></a><span data-ttu-id="79670-108">La evolución de los delegados en C\#</span><span class="sxs-lookup"><span data-stu-id="79670-108">The Evolution of Delegates in C\#</span></span>

 <span data-ttu-id="79670-109">En C# 1.0, una instancia de un delegado se creaba al inicializarla de forma explícita con un método que se definía en otro lugar en el código.</span><span class="sxs-lookup"><span data-stu-id="79670-109">In C# 1.0, you created an instance of a delegate by explicitly initializing it with a method that was defined elsewhere in the code.</span></span> <span data-ttu-id="79670-110">C# 2.0 introdujo el concepto de métodos anónimos como una manera de escribir bloques de instrucciones insertados sin nombre que se podían ejecutar en la invocación de un delegado.</span><span class="sxs-lookup"><span data-stu-id="79670-110">C# 2.0 introduced the concept of anonymous methods as a way to write unnamed inline statement blocks that can be executed in a delegate invocation.</span></span> <span data-ttu-id="79670-111">C# 3.0 introdujo las expresiones lambda, que son similares en concepto a los métodos anónimos, pero más expresivas y concisas.</span><span class="sxs-lookup"><span data-stu-id="79670-111">C# 3.0 introduced lambda expressions, which are similar in concept to anonymous methods but more expressive and concise.</span></span> <span data-ttu-id="79670-112">Estas dos características se conocen colectivamente como *funciones anónimas*.</span><span class="sxs-lookup"><span data-stu-id="79670-112">These two features are known collectively as *anonymous functions*.</span></span> <span data-ttu-id="79670-113">Por lo general, las aplicaciones que tienen como destino .NET Framework 3.5 y versiones posteriores deberían usar expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="79670-113">In general, applications that target .NET Framework 3.5 or later should use lambda expressions.</span></span>  
  
 <span data-ttu-id="79670-114">En el ejemplo siguiente se muestra la evolución de la creación de delegados desde C# 1.0 a C# 3.0:</span><span class="sxs-lookup"><span data-stu-id="79670-114">The following example demonstrates the evolution of delegate creation from C# 1.0 to C# 3.0:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#65](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#65)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="79670-115">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="79670-115">C# language specification</span></span>

<span data-ttu-id="79670-116">Para obtener más información, vea la sección [Expresiones de función anónima](~/_csharplang/spec/expressions.md#anonymous-function-expressions) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="79670-116">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="79670-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="79670-117">See also</span></span>

- [<span data-ttu-id="79670-118">Instrucciones, expresiones y operadores</span><span class="sxs-lookup"><span data-stu-id="79670-118">Statements, Expressions, and Operators</span></span>](./index.md)
- [<span data-ttu-id="79670-119">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="79670-119">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="79670-120">Delegados</span><span class="sxs-lookup"><span data-stu-id="79670-120">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="79670-121">Árboles de expresión (C#)</span><span class="sxs-lookup"><span data-stu-id="79670-121">Expression Trees (C#)</span></span>](../concepts/expression-trees/index.md)

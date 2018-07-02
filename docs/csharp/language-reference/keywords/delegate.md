---
title: delegado (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- delegate_CSharpKeyword
- delegate
- CS0123
helpviewer_keywords:
- delegate keyword [C#]
- function pointers [C#]
ms.assetid: 0bb8cb6d-2f87-47c7-9d1f-d65c1cd01e9f
ms.openlocfilehash: ba1cfdcc56b3d2301a07ffa4af793e7002da21bb
ms.sourcegitcommit: ed7b4b9b77d35e94a35a2634e8c874f46603fb2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2018
ms.locfileid: "36948428"
---
# <a name="delegate-c-reference"></a><span data-ttu-id="92c99-102">delegado (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="92c99-102">delegate (C# Reference)</span></span>

<span data-ttu-id="92c99-103">La declaración de un tipo delegado es similar a una firma de método.</span><span class="sxs-lookup"><span data-stu-id="92c99-103">The declaration of a delegate type is similar to a method signature.</span></span> <span data-ttu-id="92c99-104">Tiene un valor devuelto y un número cualquiera de parámetros de cualquier tipo:</span><span class="sxs-lookup"><span data-stu-id="92c99-104">It has a return value and any number of parameters of any type:</span></span>

```csharp
public delegate void TestDelegate(string message);
public delegate int TestDelegate(MyType m, long num);
```

<span data-ttu-id="92c99-105">Un `delegate` es un tipo de referencia que puede usarse para encapsular un método con nombre o anónimo.</span><span class="sxs-lookup"><span data-stu-id="92c99-105">A `delegate` is a reference type that can be used to encapsulate a named or an anonymous method.</span></span> <span data-ttu-id="92c99-106">Los delegados son similares a los punteros de función en C++; pero son más seguros y proporcionan mayor seguridad de tipos.</span><span class="sxs-lookup"><span data-stu-id="92c99-106">Delegates are similar to function pointers in C++; however, delegates are type-safe and secure.</span></span> <span data-ttu-id="92c99-107">Para las aplicaciones de delegados, vea [Delegados](../../../csharp/programming-guide/delegates/index.md) y [Delegados genéricos](../../../csharp/programming-guide/generics/generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="92c99-107">For applications of delegates, see [Delegates](../../../csharp/programming-guide/delegates/index.md) and [Generic Delegates](../../../csharp/programming-guide/generics/generic-delegates.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="92c99-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="92c99-108">Remarks</span></span>

<span data-ttu-id="92c99-109">Los delegados son la base de los [eventos](../../../csharp/programming-guide/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="92c99-109">Delegates are the basis for [Events](../../../csharp/programming-guide/events/index.md).</span></span>

<span data-ttu-id="92c99-110">Se pueden crear instancias de un delegado asociándolo a un método con nombre o anónimo.</span><span class="sxs-lookup"><span data-stu-id="92c99-110">A delegate can be instantiated by associating it either with a named or anonymous method.</span></span> <span data-ttu-id="92c99-111">Para obtener más información, vea [Métodos con nombre](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) y [Métodos anónimos](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span><span class="sxs-lookup"><span data-stu-id="92c99-111">For more information, see [Named Methods](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) and [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span></span>

<span data-ttu-id="92c99-112">Para crear instancias del delegado debe usarse un método o una expresión lambda que tenga un tipo de valor devuelto y parámetros de entrada compatibles.</span><span class="sxs-lookup"><span data-stu-id="92c99-112">The delegate must be instantiated with a method or lambda expression that has a compatible return type and input parameters.</span></span> <span data-ttu-id="92c99-113">Para obtener más información sobre el grado de variación permitida en la firma de método, vea [Varianza en delegados](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="92c99-113">For more information on the degree of variance that is allowed in the method signature, see [Variance in Delegates](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span> <span data-ttu-id="92c99-114">Para el uso con métodos anónimos, el delegado y el código que se van a asociar se declaran juntos.</span><span class="sxs-lookup"><span data-stu-id="92c99-114">For use with anonymous methods, the delegate and the code to be associated with it are declared together.</span></span> <span data-ttu-id="92c99-115">En esta sección se describen las dos maneras de crear instancias de delegados.</span><span class="sxs-lookup"><span data-stu-id="92c99-115">Both ways of instantiating delegates are discussed in this section.</span></span>

## <a name="example"></a><span data-ttu-id="92c99-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="92c99-116">Example</span></span>

[!code-csharp[csrefKeywordsTypes#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#8)]

## <a name="c-language-specification"></a><span data-ttu-id="92c99-117">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="92c99-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="92c99-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="92c99-118">See also</span></span>

[<span data-ttu-id="92c99-119">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="92c99-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
[<span data-ttu-id="92c99-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="92c99-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
[<span data-ttu-id="92c99-121">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="92c99-121">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
[<span data-ttu-id="92c99-122">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="92c99-122">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
[<span data-ttu-id="92c99-123">Delegados</span><span class="sxs-lookup"><span data-stu-id="92c99-123">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
[<span data-ttu-id="92c99-124">Eventos</span><span class="sxs-lookup"><span data-stu-id="92c99-124">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
[<span data-ttu-id="92c99-125">Delegados con métodos con nombre y delegados con métodos anónimos</span><span class="sxs-lookup"><span data-stu-id="92c99-125">Delegates with Named vs. Anonymous Methods</span></span>](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)  
[<span data-ttu-id="92c99-126">Métodos anónimos</span><span class="sxs-lookup"><span data-stu-id="92c99-126">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)

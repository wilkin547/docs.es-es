---
title: "Modificador del parámetro in (referencia de C#)"
ms.date: 03/06/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- parameters [C#], in
- in parameters [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 035aac3e6b902f607e533b709713eb1d07c9774a
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2018
---
# <a name="in-parameter-modifier-c-reference"></a><span data-ttu-id="1b0ff-102">Modificador del parámetro in (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="1b0ff-102">in parameter modifier (C# Reference)</span></span>

<span data-ttu-id="1b0ff-103">La palabra clave `in` hace que los argumentos se pasen por referencia.</span><span class="sxs-lookup"><span data-stu-id="1b0ff-103">The `in` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="1b0ff-104">Es como las palabras clave [ref](ref.md) o [out](out-parameter-modifier.md), salvo que el método llamado no puede modificar los argumentos `in`. Mientras que los argumentos `ref` sí se pueden modificar, los argumentos `out` debe modificarlos el llamador, y estas modificaciones se pueden observar en el contexto de llamada.</span><span class="sxs-lookup"><span data-stu-id="1b0ff-104">It is like the [ref](ref.md) or [out](out-parameter-modifier.md) keywords, except that `in` arguments cannot be modified by the called method, whereas `ref` arguments may be modified,  `out` arguments must be modified by the caller, and those modifications are observable in the calling context.</span></span>

[!code-csharp-interactive[cs-in-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/InParameterModifier.cs#1)]  

<span data-ttu-id="1b0ff-105">En el ejemplo anterior se muestra que el modificador `in` no es necesario en el sitio de llamada,</span><span class="sxs-lookup"><span data-stu-id="1b0ff-105">The preceding example demonstrates that the `in` modifier is unnecessary at the call site.</span></span> <span data-ttu-id="1b0ff-106">sino que solo lo es en la declaración del método.</span><span class="sxs-lookup"><span data-stu-id="1b0ff-106">It is only required in the method declaration.</span></span>

> [!NOTE] 
> <span data-ttu-id="1b0ff-107">Además, la palabra clave `in` puede usarse con un parámetro de tipo genérico para especificar que el parámetro de tipo es contravariante, parte de una instrucción `foreach` o de una cláusula `join` de una consulta de LINQ.</span><span class="sxs-lookup"><span data-stu-id="1b0ff-107">The `in` keyword can also be used with a generic type parameter to specify that the type parameter is contravariant, as part of a `foreach` statement, or as part of a `join` clause in a LINQ query.</span></span> <span data-ttu-id="1b0ff-108">Para obtener más información sobre el uso de la palabra clave `in` en esos contextos, vea [in](in.md), en que se proporcionan vínculos que dirigen a todos esos usos.</span><span class="sxs-lookup"><span data-stu-id="1b0ff-108">For more information on the use of the `in` keyword in these contexts, see [in](in.md) which provides links to all those uses.</span></span>
  
 <span data-ttu-id="1b0ff-109">Las variables que se han pasado como argumentos `in` deben inicializarse antes de pasarse en una llamada de método.</span><span class="sxs-lookup"><span data-stu-id="1b0ff-109">Variables passed as `in` arguments must be initialized before being passed in a method call.</span></span> <span data-ttu-id="1b0ff-110">Sin embargo, es posible que el método llamado no asigne ningún valor o modifique el argumento.</span><span class="sxs-lookup"><span data-stu-id="1b0ff-110">However, the called method may not assign a value or modify the argument.</span></span>  
  
 <span data-ttu-id="1b0ff-111">Aunque las palabras clave `in`, `ref` y `out` causan un comportamiento diferente en tiempo de ejecución, no se consideran parte de la signatura del método en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="1b0ff-111">Although the `in`, `ref`, and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="1b0ff-112">Por lo tanto, los métodos no pueden sobrecargarse si la única diferencia es que un método toma un argumento `ref` o `in` y el otro toma un argumento `out`.</span><span class="sxs-lookup"><span data-stu-id="1b0ff-112">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="1b0ff-113">Por ejemplo, el código siguiente, no se compilará:</span><span class="sxs-lookup"><span data-stu-id="1b0ff-113">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on in, ref and out".
    public void SampleMethod(in int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="1b0ff-114">Se permiten las sobrecargas basadas en la presencia de `in`, pero ella genera una advertencia del compilador:</span><span class="sxs-lookup"><span data-stu-id="1b0ff-114">Overloading based on the presence of `in` is allowed, but generates a compiler warning:</span></span>  
  
```csharp
class InOverloads
{
    // Discouraged. Calling SampleMethod(value) is ambiguous.
    public void SampleMethod(in int i) { }
    public void SampleMethod(int i) { }
}
```

<span data-ttu-id="1b0ff-115">Se pueden pasar propiedades o constantes como parámetros `in` porque el método de llamada no modifica sus valores.</span><span class="sxs-lookup"><span data-stu-id="1b0ff-115">Properties or constants may be passed as `in` parameters, because the calling method may not modify their values.</span></span>
  
<span data-ttu-id="1b0ff-116">Las palabras clave `in`, `ref` y `out` no pueden usarse para estos tipos de métodos:</span><span class="sxs-lookup"><span data-stu-id="1b0ff-116">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="1b0ff-117">Métodos asincrónicos, que se definen mediante el uso del modificador [async](../../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="1b0ff-117">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
  
- <span data-ttu-id="1b0ff-118">Métodos de iterador, que incluyen una instrucción [yield return](../../../csharp/language-reference/keywords/yield.md) o `yield break`.</span><span class="sxs-lookup"><span data-stu-id="1b0ff-118">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

<span data-ttu-id="1b0ff-119">Normalmente, se declaran los argumentos `in` para evitar las operaciones de copia necesarias para pasar argumentos por valor.</span><span class="sxs-lookup"><span data-stu-id="1b0ff-119">You typically declare `in` arguments to avoid the copy operations necessary for passing arguments by value.</span></span> <span data-ttu-id="1b0ff-120">Ello resulta más útil cuando los argumentos son estructuras o matrices de estructuras.</span><span class="sxs-lookup"><span data-stu-id="1b0ff-120">This is most useful when arguments are structures or arrays of structures.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1b0ff-121">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="1b0ff-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1b0ff-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b0ff-122">See Also</span></span>  
 [<span data-ttu-id="1b0ff-123">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="1b0ff-123">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="1b0ff-124">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="1b0ff-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="1b0ff-125">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="1b0ff-125">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="1b0ff-126">Parámetros de métodos</span><span class="sxs-lookup"><span data-stu-id="1b0ff-126">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)

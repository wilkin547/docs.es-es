---
title: Modificador del parámetro out (Referencia de C#)
ms.date: 03/06/2018
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.openlocfilehash: 76c2c27d4575918bb2ed4209a7ff7d2b0517b6f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33288624"
---
# <a name="out-parameter-modifier-c-reference"></a><span data-ttu-id="1ae3f-102">Modificador del parámetro out (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="1ae3f-102">out parameter modifier (C# Reference)</span></span>
<span data-ttu-id="1ae3f-103">La palabra clave `out` hace que los argumentos se pasen por referencia.</span><span class="sxs-lookup"><span data-stu-id="1ae3f-103">The `out` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="1ae3f-104">Esto es como la palabra clave [ref](ref.md), salvo que `ref` requiere que se inicialice la variable antes de pasarla.</span><span class="sxs-lookup"><span data-stu-id="1ae3f-104">It is like the [ref](ref.md) keyword, except that `ref` requires that the variable be initialized before it is passed.</span></span> <span data-ttu-id="1ae3f-105">También es como la palabra clave [in](in-parameter-modifier.md), salvo que `in` no permite que el método llamado modifique el valor del argumento.</span><span class="sxs-lookup"><span data-stu-id="1ae3f-105">It is also like the [in](in-parameter-modifier.md) keyword, except that `in` does not allow the called method to modify the argument value.</span></span> <span data-ttu-id="1ae3f-106">Para usar un parámetro `out`, tanto la definición de método como el método de llamada deben utilizar explícitamente la palabra clave `out`.</span><span class="sxs-lookup"><span data-stu-id="1ae3f-106">To use an `out` parameter, both the method definition and the calling method must explicitly use the `out` keyword.</span></span> <span data-ttu-id="1ae3f-107">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1ae3f-107">For example:</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#1)]  

> [!NOTE] 
> <span data-ttu-id="1ae3f-108">La palabra clave `out` también puede usarse con un parámetro de tipo genérico para especificar que el parámetro de tipo es covariante.</span><span class="sxs-lookup"><span data-stu-id="1ae3f-108">The `out` keyword can also be used with a generic type parameter to specify that the type parameter is covariant.</span></span> <span data-ttu-id="1ae3f-109">Para obtener más información sobre el uso de la palabra clave `out` en este contexto, vea [Out (Modificador genérico)](out-generic-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="1ae3f-109">For more information on the use of the `out` keyword in this context, see [out (Generic Modifier)](out-generic-modifier.md).</span></span>
  
<span data-ttu-id="1ae3f-110">Las variables que se han pasado como argumentos `out` no tienen que inicializarse antes de pasarse en una llamada al método.</span><span class="sxs-lookup"><span data-stu-id="1ae3f-110">Variables passed as `out` arguments do not have to be initialized before being passed in a method call.</span></span> <span data-ttu-id="1ae3f-111">En cambio, se necesita el método que se ha llamado para asignar un valor antes de que el método se devuelva.</span><span class="sxs-lookup"><span data-stu-id="1ae3f-111">However, the called method is required to assign a value before the method returns.</span></span>  
  
<span data-ttu-id="1ae3f-112">Aunque las palabras clave `in`, `ref` y `out` causan un comportamiento diferente en tiempo de ejecución, no se consideran parte de la signatura del método en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="1ae3f-112">Although the `in`, `ref`, and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="1ae3f-113">Por lo tanto, los métodos no pueden sobrecargarse si la única diferencia es que un método toma un argumento `ref` o `in` y el otro toma un argumento `out`.</span><span class="sxs-lookup"><span data-stu-id="1ae3f-113">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="1ae3f-114">Por ejemplo, el código siguiente, no se compilará:</span><span class="sxs-lookup"><span data-stu-id="1ae3f-114">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="1ae3f-115">En cambio, la sobrecarga es legal si un método toma un argumento `ref`, `in` o `out` y el otro no tiene ninguno de estos modificadores, como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="1ae3f-115">Overloading is legal, however, if one method takes a `ref`, `in`, or `out` argument and the other has none of those modifiers, like this:</span></span>  
  
[!code-csharp[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#2)]  

<span data-ttu-id="1ae3f-116">El compilador elige la mejor sobrecarga haciendo coincidir los modificadores de parámetro del sitio de llamada con los usados en la llamada de método.</span><span class="sxs-lookup"><span data-stu-id="1ae3f-116">The compiler chooses the best overload by matching the parameter modifiers at the call site to the parameter modifiers used in the method call.</span></span>
 
<span data-ttu-id="1ae3f-117">Las propiedades no son variables y, por tanto, no pueden pasarse como parámetros `out`.</span><span class="sxs-lookup"><span data-stu-id="1ae3f-117">Properties are not variables and therefore cannot be passed as `out` parameters.</span></span>
  
 <span data-ttu-id="1ae3f-118">Para obtener información sobre cómo pasar matrices, vea [Pasar matrices mediante Ref y Out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span><span class="sxs-lookup"><span data-stu-id="1ae3f-118">For information about passing arrays, see [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="1ae3f-119">Las palabras clave `in`, `ref` y `out` no pueden usarse para estos tipos de métodos:</span><span class="sxs-lookup"><span data-stu-id="1ae3f-119">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
-   <span data-ttu-id="1ae3f-120">Métodos asincrónicos, que se definen mediante el uso del modificador [async](../../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="1ae3f-120">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
  
-   <span data-ttu-id="1ae3f-121">Métodos de iterador, que incluyen una instrucción [yield return](../../../csharp/language-reference/keywords/yield.md) o `yield break`.</span><span class="sxs-lookup"><span data-stu-id="1ae3f-121">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

## <a name="declaring-out-arguments"></a><span data-ttu-id="1ae3f-122">Declarar argumentos `out`</span><span class="sxs-lookup"><span data-stu-id="1ae3f-122">Declaring `out` arguments</span></span>   

 <span data-ttu-id="1ae3f-123">Declarar un método con argumentos `out` resulta útil cuando quiere que devuelva varios valores.</span><span class="sxs-lookup"><span data-stu-id="1ae3f-123">Declaring a method with `out` arguments is useful when you want a method to return multiple values.</span></span> <span data-ttu-id="1ae3f-124">En el ejemplo siguiente, se utiliza `out` para devolver tres variables con una única llamada al método.</span><span class="sxs-lookup"><span data-stu-id="1ae3f-124">The following example uses `out` to return three variables with a single method call.</span></span> <span data-ttu-id="1ae3f-125">Tenga en cuenta que el tercer argumento se asigna a null.</span><span class="sxs-lookup"><span data-stu-id="1ae3f-125">Note that the third argument is assigned to null.</span></span> <span data-ttu-id="1ae3f-126">Esto permite que los métodos devuelvan valores opcionalmente.</span><span class="sxs-lookup"><span data-stu-id="1ae3f-126">This enables methods to return values optionally.</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#3)]  

 <span data-ttu-id="1ae3f-127">El [patrón Try](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) implica la devolución de `bool` para indicar si una operación se ha realizado correcta o incorrectamente, y la devolución del valor que ha generado la operación en un argumento `out`.</span><span class="sxs-lookup"><span data-stu-id="1ae3f-127">The [Try pattern](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) involves returning a `bool` to indicate whether an operation succeeded and failed, and returning the value produced by the operation in an `out` argument.</span></span> <span data-ttu-id="1ae3f-128">Varios métodos de análisis, como el método [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)), usan este patrón.</span><span class="sxs-lookup"><span data-stu-id="1ae3f-128">A number of parsing methods, such as the [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) method, use this pattern.</span></span>
   
## <a name="calling-a-method-with-an-out-argument"></a><span data-ttu-id="1ae3f-129">Llamar a un método con un argumento `out`</span><span class="sxs-lookup"><span data-stu-id="1ae3f-129">Calling a method with an `out` argument</span></span>

<span data-ttu-id="1ae3f-130">En C# 6 y versiones anteriores, debe declarar una variable en una instrucción independiente antes de pasarla como un argumento `out`.</span><span class="sxs-lookup"><span data-stu-id="1ae3f-130">In C# 6 and earlier, you must declare a variable in a separate statement before you pass it as an `out` argument.</span></span> <span data-ttu-id="1ae3f-131">En el ejemplo siguiente se declara una variable denominada `number` antes de que se pase al método [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)), que intenta convertir una cadena en un número.</span><span class="sxs-lookup"><span data-stu-id="1ae3f-131">The following example declares a variable named `number` before it is passed to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method, which attempts to convert a string to a number.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#4)]  

<span data-ttu-id="1ae3f-132">A partir de C# 7.0, puede declarar la variable `out` en la lista de argumentos de la llamada al método, en lugar de en una declaración de variable independiente.</span><span class="sxs-lookup"><span data-stu-id="1ae3f-132">Starting with C# 7.0, you can declare the `out` variable in the argument list of the method call, rather than in a separate variable declaration.</span></span> <span data-ttu-id="1ae3f-133">Esto genera un código legible más compacto y, además, evita que asigne un valor a la variable antes de la llamada al método de manera involuntaria.</span><span class="sxs-lookup"><span data-stu-id="1ae3f-133">This produces more compact, readable code, and also prevents you from inadvertently assigning a value to the variable before the method call.</span></span> <span data-ttu-id="1ae3f-134">El ejemplo siguiente es como el ejemplo anterior, excepto que define la variable `number` en la llamada al método [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)).</span><span class="sxs-lookup"><span data-stu-id="1ae3f-134">The following example is like the previous example, except that it defines the `number` variable in the call to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#5)]  
   
<span data-ttu-id="1ae3f-135">En el ejemplo anterior, la variable `number` está fuertemente tipada como `int`.</span><span class="sxs-lookup"><span data-stu-id="1ae3f-135">In the previous example, the `number` variable is strongly typed as an `int`.</span></span> <span data-ttu-id="1ae3f-136">También puede declarar una variable local con tipo implícito como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1ae3f-136">You can also declare an implicitly typed local variable, as the following example does.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#6)]  
   
## <a name="c-language-specification"></a><span data-ttu-id="1ae3f-137">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="1ae3f-137">C# Language Specification</span></span>  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1ae3f-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ae3f-138">See Also</span></span>  
 [<span data-ttu-id="1ae3f-139">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="1ae3f-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="1ae3f-140">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="1ae3f-140">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="1ae3f-141">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="1ae3f-141">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="1ae3f-142">Parámetros de métodos</span><span class="sxs-lookup"><span data-stu-id="1ae3f-142">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)

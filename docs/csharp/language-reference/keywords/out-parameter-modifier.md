---
title: "Modificador del parámetro out (Referencia de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.assetid: 3fce0dc5-03f4-4faa-bd61-36c41bc6baf1
caps.latest.revision: "9"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 68ef554f95fe71f925cfa22cc49758cec3da237e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="out-parameter-modifier-c-reference"></a><span data-ttu-id="8a42b-102">Modificador del parámetro out (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="8a42b-102">out parameter modifier (C# Reference)</span></span>
<span data-ttu-id="8a42b-103">La palabra clave `out` hace que los argumentos se pasen por referencia.</span><span class="sxs-lookup"><span data-stu-id="8a42b-103">The `out` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="8a42b-104">Esto es como la palabra clave [ref](../../../csharp/language-reference/keywords/ref.md), salvo que `ref` requiere que se inicialice la variable antes de pasarla.</span><span class="sxs-lookup"><span data-stu-id="8a42b-104">It is like the [ref](../../../csharp/language-reference/keywords/ref.md) keyword, except that `ref` requires that the variable be initialized before it is passed.</span></span> <span data-ttu-id="8a42b-105">Para usar un parámetro `out`, tanto la definición de método como el método de llamada deben utilizar explícitamente la palabra clave `out`.</span><span class="sxs-lookup"><span data-stu-id="8a42b-105">To use an `out` parameter, both the method definition and the calling method must explicitly use the `out` keyword.</span></span> <span data-ttu-id="8a42b-106">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8a42b-106">For example:</span></span>  
  
 [!code-csharp[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/out/out-1.cs)]  

> [!NOTE] 
> <span data-ttu-id="8a42b-107">La palabra clave `out` también puede usarse con un parámetro de tipo genérico para especificar que el parámetro de tipo es covariante.</span><span class="sxs-lookup"><span data-stu-id="8a42b-107">The `out` keyword can also be used with a generic type parameter to specify that the type parameter is covariant.</span></span> <span data-ttu-id="8a42b-108">Para obtener más información sobre el uso de la palabra clave `out` en este contexto, vea [Out (Modificador genérico)](../../../csharp/language-reference/keywords/out-generic-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="8a42b-108">For more information on the use of the `out` keyword in this context, see [out (Generic Modifier)](../../../csharp/language-reference/keywords/out-generic-modifier.md).</span></span>
  
 <span data-ttu-id="8a42b-109">Las variables que se han pasado como argumentos `out` no tienen que inicializarse antes de pasarse en una llamada al método.</span><span class="sxs-lookup"><span data-stu-id="8a42b-109">Variables passed as `out` arguments do not have to be initialized before being passed in a method call.</span></span> <span data-ttu-id="8a42b-110">En cambio, se necesita el método que se ha llamado para asignar un valor antes de que el método se devuelva.</span><span class="sxs-lookup"><span data-stu-id="8a42b-110">However, the called method is required to assign a value before the method returns.</span></span>  
  
 <span data-ttu-id="8a42b-111">Aunque las palabras clave `ref` y `out` causan un comportamiento diferente en tiempo de ejecución, no se consideran parte de la signatura del método en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="8a42b-111">Although the `ref` and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="8a42b-112">Por lo tanto, los métodos no pueden sobrecargarse si la única diferencia es que un método toma un argumento `ref` y el otro toma un argumento `out`.</span><span class="sxs-lookup"><span data-stu-id="8a42b-112">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="8a42b-113">Por ejemplo, el código siguiente, no se compilará:</span><span class="sxs-lookup"><span data-stu-id="8a42b-113">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="8a42b-114">En cambio, la sobrecarga es legal si un método toma un argumento `ref` o `out` y el otro no usa ninguno, como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="8a42b-114">Overloading is legal, however, if one method takes a `ref` or `out` argument and the other uses neither, like this:</span></span>  
  
 [!code-csharp[csrefKeywordsMethodParams#3](../../../../samples/snippets/csharp/language-reference/keywords/out/out-3.cs)]  
  
 <span data-ttu-id="8a42b-115">Las propiedades no son variables y, por tanto, no pueden pasarse como parámetros `out`.</span><span class="sxs-lookup"><span data-stu-id="8a42b-115">Properties are not variables and therefore cannot be passed as `out` parameters.</span></span>  
  
 <span data-ttu-id="8a42b-116">Para obtener información sobre cómo pasar matrices, vea [Pasar matrices mediante Ref y Out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span><span class="sxs-lookup"><span data-stu-id="8a42b-116">For information about passing arrays, see [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="8a42b-117">Las palabras clave `ref` y `out` no pueden usarse para los siguientes tipos de métodos:</span><span class="sxs-lookup"><span data-stu-id="8a42b-117">You can't use the `ref` and `out` keywords for the following kinds of methods:</span></span>  
  
-   <span data-ttu-id="8a42b-118">Métodos asincrónicos, que se definen mediante el uso del modificador [async](../../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="8a42b-118">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
  
-   <span data-ttu-id="8a42b-119">Métodos de iterador, que incluyen una instrucción [yield return](../../../csharp/language-reference/keywords/yield.md) o `yield break`.</span><span class="sxs-lookup"><span data-stu-id="8a42b-119">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

## <a name="declaring-out-arguments"></a><span data-ttu-id="8a42b-120">Declarar argumentos `out`</span><span class="sxs-lookup"><span data-stu-id="8a42b-120">Declaring `out` arguments</span></span>   

 <span data-ttu-id="8a42b-121">Declarar un método con argumentos `out` resulta útil cuando quiere que devuelva varios valores.</span><span class="sxs-lookup"><span data-stu-id="8a42b-121">Declaring a method with `out` arguments is useful when you want a method to return multiple values.</span></span> <span data-ttu-id="8a42b-122">En el ejemplo siguiente, se utiliza `out` para devolver tres variables con una única llamada al método.</span><span class="sxs-lookup"><span data-stu-id="8a42b-122">The following example uses `out` to return three variables with a single method call.</span></span> <span data-ttu-id="8a42b-123">Tenga en cuenta que el tercer argumento se asigna a null.</span><span class="sxs-lookup"><span data-stu-id="8a42b-123">Note that the third argument is assigned to null.</span></span> <span data-ttu-id="8a42b-124">Esto permite que los métodos devuelvan valores opcionalmente.</span><span class="sxs-lookup"><span data-stu-id="8a42b-124">This enables methods to return values optionally.</span></span>  
  
 [!code-csharp[csrefKeywordsMethodParams#4](../../../../samples/snippets/csharp/language-reference/keywords/out/out-4.cs)]  

 <span data-ttu-id="8a42b-125">El [patrón Try](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) implica la devolución de `bool` para indicar si una operación se ha realizado correcta o incorrectamente, y la devolución del valor que ha generado la operación en un argumento `out`.</span><span class="sxs-lookup"><span data-stu-id="8a42b-125">The [Try pattern](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) involves returning a `bool` to indicate whether an operation succeeded and failed, and returning the value produced by the operation in an `out` argument.</span></span> <span data-ttu-id="8a42b-126">Varios métodos de análisis, como el método [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)), usan este patrón.</span><span class="sxs-lookup"><span data-stu-id="8a42b-126">A number of parsing methods, such as the [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) method, use this pattern.</span></span>
   
## <a name="calling-a-method-with-an-out-argument"></a><span data-ttu-id="8a42b-127">Llamar a un método con un argumento `out`</span><span class="sxs-lookup"><span data-stu-id="8a42b-127">Calling a method with an `out` argument</span></span>

<span data-ttu-id="8a42b-128">En C# 6 y versiones anteriores, debe declarar una variable en una instrucción independiente antes de pasarla como un argumento `out`.</span><span class="sxs-lookup"><span data-stu-id="8a42b-128">In C# 6 and earlier, you must declare a variable in a separate statement before you pass it as an `out` argument.</span></span> <span data-ttu-id="8a42b-129">En el ejemplo siguiente se declara una variable denominada `number` antes de que se pase al método [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)), que intenta convertir una cadena en un número.</span><span class="sxs-lookup"><span data-stu-id="8a42b-129">The following example declares a variable named `number` before it is passed to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method, which attempts to convert a string to a number.</span></span>

 [!code-csharp[csrefKeywordsMethodParams#5](../../../../samples/snippets/csharp/language-reference/keywords/out/out-5.cs)]  

<span data-ttu-id="8a42b-130">A partir de C# 7, puede declarar la variable `out` en la lista de argumentos de la llamada al método, en lugar de en una declaración de variable independiente.</span><span class="sxs-lookup"><span data-stu-id="8a42b-130">Starting with C# 7, you can declare the `out` variable in the argument list of the method call, rather than in a separate variable declaration.</span></span> <span data-ttu-id="8a42b-131">Esto genera un código legible más compacto y, además, evita que asigne un valor a la variable antes de la llamada al método de manera involuntaria.</span><span class="sxs-lookup"><span data-stu-id="8a42b-131">This produces more compact, readable code, and also prevents you from inadvertently assigning a value to the variable before the method call.</span></span> <span data-ttu-id="8a42b-132">El ejemplo siguiente es como el ejemplo anterior, excepto que define la variable `number` en la llamada al método [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)).</span><span class="sxs-lookup"><span data-stu-id="8a42b-132">The following example is like the previous example, except that it defines the `number` variable in the call to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method.</span></span>

 [!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/out/out-6.cs)]  
   
<span data-ttu-id="8a42b-133">En el ejemplo anterior, la variable `number` está fuertemente tipada como `int`.</span><span class="sxs-lookup"><span data-stu-id="8a42b-133">In the previous example, the `number` variable is strongly typed as an `int`.</span></span> <span data-ttu-id="8a42b-134">También puede declarar una variable local con tipo implícito como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8a42b-134">You can also declare an implicitly typed local variable, as the following example does.</span></span>

 [!code-csharp[csrefKeywordsMethodParams#7](../../../../samples/snippets/csharp/language-reference/keywords/out/out-7.cs)]  
   
## <a name="c-language-specification"></a><span data-ttu-id="8a42b-135">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="8a42b-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8a42b-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a42b-136">See Also</span></span>  
 [<span data-ttu-id="8a42b-137">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="8a42b-137">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8a42b-138">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="8a42b-138">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8a42b-139">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="8a42b-139">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="8a42b-140">Parámetros de métodos</span><span class="sxs-lookup"><span data-stu-id="8a42b-140">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)

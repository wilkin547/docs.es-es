---
title: "Modificador del parámetro out (Referencia de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.assetid: 3fce0dc5-03f4-4faa-bd61-36c41bc6baf1
caps.latest.revision: 9
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 59e445ac27f07c85d9e98c5f595cf5f935f75443
ms.openlocfilehash: 9a0a488c6f444608a335cd990847774fb6fe9e3f
ms.contentlocale: es-es
ms.lasthandoff: 08/31/2017

---
# <a name="out-parameter-modifier-c-reference"></a><span data-ttu-id="079ec-102">Modificador del parámetro out (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="079ec-102">out parameter modifier (C# Reference)</span></span>
<span data-ttu-id="079ec-103">La palabra clave `out` hace que los argumentos se pasen por referencia.</span><span class="sxs-lookup"><span data-stu-id="079ec-103">The `out` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="079ec-104">Esto es como la palabra clave [ref](../../../csharp/language-reference/keywords/ref.md), salvo que `ref` requiere que se inicialice la variable antes de pasarla.</span><span class="sxs-lookup"><span data-stu-id="079ec-104">It is like the [ref](../../../csharp/language-reference/keywords/ref.md) keyword, except that `ref` requires that the variable be initialized before it is passed.</span></span> <span data-ttu-id="079ec-105">Para usar un parámetro `out`, tanto la definición de método como el método de llamada deben utilizar explícitamente la palabra clave `out`.</span><span class="sxs-lookup"><span data-stu-id="079ec-105">To use an `out` parameter, both the method definition and the calling method must explicitly use the `out` keyword.</span></span> <span data-ttu-id="079ec-106">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="079ec-106">For example:</span></span>  
  
 <span data-ttu-id="079ec-107">[!code-cs[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/out/out-1.cs)]</span><span class="sxs-lookup"><span data-stu-id="079ec-107">[!code-cs[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/out/out-1.cs)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="079ec-108">La palabra clave `out` también puede usarse con un parámetro de tipo genérico para especificar que el parámetro de tipo es covariante.</span><span class="sxs-lookup"><span data-stu-id="079ec-108">The `out` keyword can also be used with a generic type parameter to specify that the type parameter is covariant.</span></span> <span data-ttu-id="079ec-109">Para obtener más información sobre el uso de la palabra clave `out` en este contexto, vea [Out (Modificador genérico)](../../../csharp/language-reference/keywords/out-generic-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="079ec-109">For more information on the use of the `out` keyword in this context, see [out (Generic Modifier)](../../../csharp/language-reference/keywords/out-generic-modifier.md).</span></span>
  
 <span data-ttu-id="079ec-110">Las variables que se han pasado como argumentos `out` no tienen que inicializarse antes de pasarse en una llamada al método.</span><span class="sxs-lookup"><span data-stu-id="079ec-110">Variables passed as `out` arguments do not have to be initialized before being passed in a method call.</span></span> <span data-ttu-id="079ec-111">En cambio, se necesita el método que se ha llamado para asignar un valor antes de que el método se devuelva.</span><span class="sxs-lookup"><span data-stu-id="079ec-111">However, the called method is required to assign a value before the method returns.</span></span>  
  
 <span data-ttu-id="079ec-112">Aunque las palabras clave `ref` y `out` causan un comportamiento diferente en tiempo de ejecución, no se consideran parte de la signatura del método en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="079ec-112">Although the `ref` and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="079ec-113">Por lo tanto, los métodos no pueden sobrecargarse si la única diferencia es que un método toma un argumento `ref` y el otro toma un argumento `out`.</span><span class="sxs-lookup"><span data-stu-id="079ec-113">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="079ec-114">Por ejemplo, el código siguiente, no se compilará:</span><span class="sxs-lookup"><span data-stu-id="079ec-114">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="079ec-115">En cambio, la sobrecarga es legal si un método toma un argumento `ref` o `out` y el otro no usa ninguno, como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="079ec-115">Overloading is legal, however, if one method takes a `ref` or `out` argument and the other uses neither, like this:</span></span>  
  
 <span data-ttu-id="079ec-116">[!code-cs[csrefKeywordsMethodParams#3](../../../../samples/snippets/csharp/language-reference/keywords/out/out-3.cs)]</span><span class="sxs-lookup"><span data-stu-id="079ec-116">[!code-cs[csrefKeywordsMethodParams#3](../../../../samples/snippets/csharp/language-reference/keywords/out/out-3.cs)]</span></span>  
  
 <span data-ttu-id="079ec-117">Las propiedades no son variables y, por tanto, no pueden pasarse como parámetros `out`.</span><span class="sxs-lookup"><span data-stu-id="079ec-117">Properties are not variables and therefore cannot be passed as `out` parameters.</span></span>  
  
 <span data-ttu-id="079ec-118">Para obtener información sobre cómo pasar matrices, vea [Pasar matrices mediante Ref y Out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span><span class="sxs-lookup"><span data-stu-id="079ec-118">For information about passing arrays, see [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="079ec-119">Las palabras clave `ref` y `out` no pueden usarse para los siguientes tipos de métodos:</span><span class="sxs-lookup"><span data-stu-id="079ec-119">You can't use the `ref` and `out` keywords for the following kinds of methods:</span></span>  
  
-   <span data-ttu-id="079ec-120">Métodos asincrónicos, que se definen mediante el uso del modificador [async](../../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="079ec-120">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
  
-   <span data-ttu-id="079ec-121">Métodos de iterador, que incluyen una instrucción [yield return](../../../csharp/language-reference/keywords/yield.md) o `yield break`.</span><span class="sxs-lookup"><span data-stu-id="079ec-121">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

## <a name="declaring-out-arguments"></a><span data-ttu-id="079ec-122">Declarar argumentos `out`</span><span class="sxs-lookup"><span data-stu-id="079ec-122">Declaring `out` arguments</span></span>   

 <span data-ttu-id="079ec-123">Declarar un método con argumentos `out` resulta útil cuando quiere que devuelva varios valores.</span><span class="sxs-lookup"><span data-stu-id="079ec-123">Declaring a method with `out` arguments is useful when you want a method to return multiple values.</span></span> <span data-ttu-id="079ec-124">En el ejemplo siguiente, se utiliza `out` para devolver tres variables con una única llamada al método.</span><span class="sxs-lookup"><span data-stu-id="079ec-124">The following example uses `out` to return three variables with a single method call.</span></span> <span data-ttu-id="079ec-125">Tenga en cuenta que el tercer argumento se asigna a null.</span><span class="sxs-lookup"><span data-stu-id="079ec-125">Note that the third argument is assigned to null.</span></span> <span data-ttu-id="079ec-126">Esto permite que los métodos devuelvan valores opcionalmente.</span><span class="sxs-lookup"><span data-stu-id="079ec-126">This enables methods to return values optionally.</span></span>  
  
 <span data-ttu-id="079ec-127">[!code-cs[csrefKeywordsMethodParams#4](../../../../samples/snippets/csharp/language-reference/keywords/out/out-4.cs)]</span><span class="sxs-lookup"><span data-stu-id="079ec-127">[!code-cs[csrefKeywordsMethodParams#4](../../../../samples/snippets/csharp/language-reference/keywords/out/out-4.cs)]</span></span>  

 <span data-ttu-id="079ec-128">El [patrón Try](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) implica la devolución de `bool` para indicar si una operación se ha realizado correcta o incorrectamente, y la devolución del valor que ha generado la operación en un argumento `out`.</span><span class="sxs-lookup"><span data-stu-id="079ec-128">The [Try pattern](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) involves returning a `bool` to indicate whether an operation succeeded and failed, and returning the value produced by the operation in an `out` argument.</span></span> <span data-ttu-id="079ec-129">Varios métodos de análisis, como el método [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)), usan este patrón.</span><span class="sxs-lookup"><span data-stu-id="079ec-129">A number of parsing methods, such as the [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) method, use this pattern.</span></span>
   
## <a name="calling-a-method-with-an-out-argument"></a><span data-ttu-id="079ec-130">Llamar a un método con un argumento `out`</span><span class="sxs-lookup"><span data-stu-id="079ec-130">Calling a method with an `out` argument</span></span>

<span data-ttu-id="079ec-131">En C# 6 y versiones anteriores, debe declarar una variable en una instrucción independiente antes de pasarla como un argumento `out`.</span><span class="sxs-lookup"><span data-stu-id="079ec-131">In C# 6 and earlier, you must declare a variable in a separate statement before you pass it as an `out` argument.</span></span> <span data-ttu-id="079ec-132">En el ejemplo siguiente se declara una variable denominada `number` antes de que se pase al método [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)), que intenta convertir una cadena en un número.</span><span class="sxs-lookup"><span data-stu-id="079ec-132">The following example declares a variable named `number` before it is passed to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method, which attempts to convert a string to a number.</span></span>

 <span data-ttu-id="079ec-133">[!code-cs[csrefKeywordsMethodParams#5](../../../../samples/snippets/csharp/language-reference/keywords/out/out-5.cs)]</span><span class="sxs-lookup"><span data-stu-id="079ec-133">[!code-cs[csrefKeywordsMethodParams#5](../../../../samples/snippets/csharp/language-reference/keywords/out/out-5.cs)]</span></span>  

<span data-ttu-id="079ec-134">A partir de C# 7, puede declarar la variable `out` en la lista de argumentos de la llamada al método, en lugar de en una declaración de variable independiente.</span><span class="sxs-lookup"><span data-stu-id="079ec-134">Starting with C# 7, you can declare the `out` variable in the argument list of the method call, rather than in a separate variable declaration.</span></span> <span data-ttu-id="079ec-135">Esto genera un código legible más compacto y, además, evita que asigne un valor a la variable antes de la llamada al método de manera involuntaria.</span><span class="sxs-lookup"><span data-stu-id="079ec-135">This produces more compact, readable code, and also prevents you from inadvertently assigning a value to the variable before the method call.</span></span> <span data-ttu-id="079ec-136">El ejemplo siguiente es como el ejemplo anterior, excepto que define la variable `number` en la llamada al método [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)).</span><span class="sxs-lookup"><span data-stu-id="079ec-136">The following example is like the previous example, except that it defines the `number` variable in the call to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method.</span></span>

 <span data-ttu-id="079ec-137">[!code-cs[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/out/out-6.cs)]</span><span class="sxs-lookup"><span data-stu-id="079ec-137">[!code-cs[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/out/out-6.cs)]</span></span>  
   
<span data-ttu-id="079ec-138">En el ejemplo anterior, la variable `number` está fuertemente tipada como `int`.</span><span class="sxs-lookup"><span data-stu-id="079ec-138">In the previous example, the `number` variable is strongly typed as an `int`.</span></span> <span data-ttu-id="079ec-139">También puede declarar una variable local con tipo implícito como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="079ec-139">You can also declare an implicitly typed local variable, as the following example does.</span></span>

 <span data-ttu-id="079ec-140">[!code-cs[csrefKeywordsMethodParams#7](../../../../samples/snippets/csharp/language-reference/keywords/out/out-7.cs)]</span><span class="sxs-lookup"><span data-stu-id="079ec-140">[!code-cs[csrefKeywordsMethodParams#7](../../../../samples/snippets/csharp/language-reference/keywords/out/out-7.cs)]</span></span>  
   
## <a name="c-language-specification"></a><span data-ttu-id="079ec-141">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="079ec-141">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="079ec-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="079ec-142">See Also</span></span>  
 <span data-ttu-id="079ec-143">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="079ec-143">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="079ec-144">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="079ec-144">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="079ec-145">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="079ec-145">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 [<span data-ttu-id="079ec-146">Parámetros de métodos</span><span class="sxs-lookup"><span data-stu-id="079ec-146">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)


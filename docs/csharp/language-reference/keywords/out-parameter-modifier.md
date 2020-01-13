---
title: 'Modificador del parámetro out: Referencia de C#'
ms.date: 03/26/2019
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.openlocfilehash: bc3814b91ed4327f4af1a4a1bfbda632b0393bb8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713270"
---
# <a name="out-parameter-modifier-c-reference"></a><span data-ttu-id="8af12-102">Modificador del parámetro out (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="8af12-102">out parameter modifier (C# Reference)</span></span>
<span data-ttu-id="8af12-103">La palabra clave `out` hace que los argumentos se pasen por referencia.</span><span class="sxs-lookup"><span data-stu-id="8af12-103">The `out` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="8af12-104">Hace que el parámetro formal sea un alias para el argumento, que debe ser una variable.</span><span class="sxs-lookup"><span data-stu-id="8af12-104">It makes the formal parameter an alias for the argument, which must be a variable.</span></span> <span data-ttu-id="8af12-105">En otras palabras, cualquier operación en el parámetro se realiza en el argumento.</span><span class="sxs-lookup"><span data-stu-id="8af12-105">In other words, any operation on the parameter is made on the argument.</span></span> <span data-ttu-id="8af12-106">Esto es como la palabra clave [ref](ref.md), salvo que `ref` requiere que se inicialice la variable antes de pasarla.</span><span class="sxs-lookup"><span data-stu-id="8af12-106">It is like the [ref](ref.md) keyword, except that `ref` requires that the variable be initialized before it is passed.</span></span> <span data-ttu-id="8af12-107">También es como la palabra clave [in](in-parameter-modifier.md), salvo que `in` no permite que el método llamado modifique el valor del argumento.</span><span class="sxs-lookup"><span data-stu-id="8af12-107">It is also like the [in](in-parameter-modifier.md) keyword, except that `in` does not allow the called method to modify the argument value.</span></span> <span data-ttu-id="8af12-108">Para usar un parámetro `out`, tanto la definición de método como el método de llamada deben utilizar explícitamente la palabra clave `out`.</span><span class="sxs-lookup"><span data-stu-id="8af12-108">To use an `out` parameter, both the method definition and the calling method must explicitly use the `out` keyword.</span></span> <span data-ttu-id="8af12-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8af12-109">For example:</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#1)]  

> [!NOTE] 
> <span data-ttu-id="8af12-110">La palabra clave `out` también puede usarse con un parámetro de tipo genérico para especificar que el parámetro de tipo es covariante.</span><span class="sxs-lookup"><span data-stu-id="8af12-110">The `out` keyword can also be used with a generic type parameter to specify that the type parameter is covariant.</span></span> <span data-ttu-id="8af12-111">Para obtener más información sobre el uso de la palabra clave `out` en este contexto, vea [Out (Modificador genérico)](out-generic-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="8af12-111">For more information on the use of the `out` keyword in this context, see [out (Generic Modifier)](out-generic-modifier.md).</span></span>
  
<span data-ttu-id="8af12-112">Las variables que se han pasado como argumentos `out` no tienen que inicializarse antes de pasarse en una llamada al método.</span><span class="sxs-lookup"><span data-stu-id="8af12-112">Variables passed as `out` arguments do not have to be initialized before being passed in a method call.</span></span> <span data-ttu-id="8af12-113">En cambio, se necesita el método que se ha llamado para asignar un valor antes de que el método se devuelva.</span><span class="sxs-lookup"><span data-stu-id="8af12-113">However, the called method is required to assign a value before the method returns.</span></span>  
  
<span data-ttu-id="8af12-114">Las palabras clave `in`, `ref` y `out` no se consideran parte de la firma del método con el fin de resolver la sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="8af12-114">The `in`, `ref`, and `out` keywords are not considered part of the method signature for the purpose of overload resolution.</span></span> <span data-ttu-id="8af12-115">Por lo tanto, los métodos no pueden sobrecargarse si la única diferencia es que un método toma un argumento `ref` o `in` y el otro toma un argumento `out`.</span><span class="sxs-lookup"><span data-stu-id="8af12-115">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="8af12-116">Por ejemplo, el código siguiente, no se compilará:</span><span class="sxs-lookup"><span data-stu-id="8af12-116">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="8af12-117">En cambio, la sobrecarga es legal si un método toma un argumento `ref`, `in` o `out` y el otro no tiene ninguno de estos modificadores, como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="8af12-117">Overloading is legal, however, if one method takes a `ref`, `in`, or `out` argument and the other has none of those modifiers, like this:</span></span>  
  
[!code-csharp[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#2)]  

<span data-ttu-id="8af12-118">El compilador elige la mejor sobrecarga haciendo coincidir los modificadores de parámetro del sitio de llamada con los usados en la llamada de método.</span><span class="sxs-lookup"><span data-stu-id="8af12-118">The compiler chooses the best overload by matching the parameter modifiers at the call site to the parameter modifiers used in the method call.</span></span>
 
<span data-ttu-id="8af12-119">Las propiedades no son variables y, por tanto, no pueden pasarse como parámetros `out`.</span><span class="sxs-lookup"><span data-stu-id="8af12-119">Properties are not variables and therefore cannot be passed as `out` parameters.</span></span>
  
<span data-ttu-id="8af12-120">Las palabras clave `in`, `ref` y `out` no pueden usarse para estos tipos de métodos:</span><span class="sxs-lookup"><span data-stu-id="8af12-120">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="8af12-121">Métodos asincrónicos, que se definen mediante el uso del modificador [async](./async.md).</span><span class="sxs-lookup"><span data-stu-id="8af12-121">Async methods, which you define by using the [async](./async.md) modifier.</span></span>  
  
- <span data-ttu-id="8af12-122">Métodos de iterador, que incluyen una instrucción [yield return](./yield.md) o `yield break`.</span><span class="sxs-lookup"><span data-stu-id="8af12-122">Iterator methods, which include a [yield return](./yield.md) or `yield break` statement.</span></span>  

## <a name="declaring-out-parameters"></a><span data-ttu-id="8af12-123">Declaración de parámetros `out`</span><span class="sxs-lookup"><span data-stu-id="8af12-123">Declaring `out` parameters</span></span>   

<span data-ttu-id="8af12-124">Declarar un método con el argumento `out` es una solución alternativa clásica para devolver varios valores.</span><span class="sxs-lookup"><span data-stu-id="8af12-124">Declaring a method with `out` arguments is a classic workaround to return multiple values.</span></span> <span data-ttu-id="8af12-125">A partir de C# 7.0, considere las [tuplas](../../tuples.md) para escenarios similares.</span><span class="sxs-lookup"><span data-stu-id="8af12-125">Beginning with C# 7.0, consider [tuples](../../tuples.md) for similar scenarios.</span></span> <span data-ttu-id="8af12-126">En el ejemplo siguiente, se utiliza `out` para devolver tres variables con una única llamada al método.</span><span class="sxs-lookup"><span data-stu-id="8af12-126">The following example uses `out` to return three variables with a single method call.</span></span> <span data-ttu-id="8af12-127">Tenga en cuenta que el tercer argumento se asigna a null.</span><span class="sxs-lookup"><span data-stu-id="8af12-127">Note that the third argument is assigned to null.</span></span> <span data-ttu-id="8af12-128">Esto permite que los métodos devuelvan valores opcionalmente.</span><span class="sxs-lookup"><span data-stu-id="8af12-128">This enables methods to return values optionally.</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#3)]  

## <a name="calling-a-method-with-an-out-argument"></a><span data-ttu-id="8af12-129">Llamar a un método con un argumento `out`</span><span class="sxs-lookup"><span data-stu-id="8af12-129">Calling a method with an `out` argument</span></span>

<span data-ttu-id="8af12-130">En C# 6 y versiones anteriores, debe declarar una variable en una instrucción independiente antes de pasarla como un argumento `out`.</span><span class="sxs-lookup"><span data-stu-id="8af12-130">In C# 6 and earlier, you must declare a variable in a separate statement before you pass it as an `out` argument.</span></span> <span data-ttu-id="8af12-131">En el ejemplo siguiente se declara una variable denominada `number` antes de que se pase al método [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)), que intenta convertir una cadena en un número.</span><span class="sxs-lookup"><span data-stu-id="8af12-131">The following example declares a variable named `number` before it is passed to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method, which attempts to convert a string to a number.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#4)]  

<span data-ttu-id="8af12-132">A partir de C# 7.0, puede declarar la variable `out` en la lista de argumentos de la llamada al método, en lugar de en una declaración de variable independiente.</span><span class="sxs-lookup"><span data-stu-id="8af12-132">Starting with C# 7.0, you can declare the `out` variable in the argument list of the method call, rather than in a separate variable declaration.</span></span> <span data-ttu-id="8af12-133">Esto genera un código legible más compacto y, además, evita que asigne un valor a la variable antes de la llamada al método de manera involuntaria.</span><span class="sxs-lookup"><span data-stu-id="8af12-133">This produces more compact, readable code, and also prevents you from inadvertently assigning a value to the variable before the method call.</span></span> <span data-ttu-id="8af12-134">El ejemplo siguiente es como el ejemplo anterior, excepto que define la variable `number` en la llamada al método [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)).</span><span class="sxs-lookup"><span data-stu-id="8af12-134">The following example is like the previous example, except that it defines the `number` variable in the call to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#5)]  
   
<span data-ttu-id="8af12-135">En el ejemplo anterior, la variable `number` está fuertemente tipada como `int`.</span><span class="sxs-lookup"><span data-stu-id="8af12-135">In the previous example, the `number` variable is strongly typed as an `int`.</span></span> <span data-ttu-id="8af12-136">También puede declarar una variable local con tipo implícito como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8af12-136">You can also declare an implicitly typed local variable, as the following example does.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#6)]  
   
## <a name="c-language-specification"></a><span data-ttu-id="8af12-137">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="8af12-137">C# Language Specification</span></span>  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8af12-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="8af12-138">See also</span></span>

- [<span data-ttu-id="8af12-139">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="8af12-139">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="8af12-140">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="8af12-140">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8af12-141">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="8af12-141">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="8af12-142">Parámetros de métodos</span><span class="sxs-lookup"><span data-stu-id="8af12-142">Method Parameters</span></span>](./method-parameters.md)

---
title: ref (Referencia de C#)
ms.date: 03/06/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ref_CSharpKeyword
- ref
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 427045317e9d7d0fe3435a486b9f761908ab5e78
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2018
---
# <a name="ref-c-reference"></a><span data-ttu-id="d9981-102">ref (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="d9981-102">ref (C# Reference)</span></span>

<span data-ttu-id="d9981-103">La palabra clave `ref` indica un valor que se ha pasado mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="d9981-103">The `ref` keyword indicates a value that is passed by reference.</span></span> <span data-ttu-id="d9981-104">Se usa en tres contextos diferentes:</span><span class="sxs-lookup"><span data-stu-id="d9981-104">It is used in three different contexts:</span></span> 

- <span data-ttu-id="d9981-105">En una firma del método y en una llamada al método, para pasar un argumento a un método mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="d9981-105">In a method signature and in a method call, to pass an argument to a method by reference.</span></span> <span data-ttu-id="d9981-106">Vea [Pasar un argumento mediante referencia](#passing-an-argument-by-reference) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d9981-106">See [Passing an argument by reference](#passing-an-argument-by-reference) for more information.</span></span>

- <span data-ttu-id="d9981-107">En una firma del método, para devolver un valor al autor de la llamada mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="d9981-107">In a method signature, to return a value to the caller by reference.</span></span> <span data-ttu-id="d9981-108">Para obtener más información, vea [Valores devueltos de referencia](#reference-return-values).</span><span class="sxs-lookup"><span data-stu-id="d9981-108">See [Reference return values](#reference-return-values) for more information.</span></span>

- <span data-ttu-id="d9981-109">En un cuerpo de miembro, para indicar que un valor devuelto de referencia se almacena localmente como una referencia que el autor de la llamada pretende modificar.</span><span class="sxs-lookup"><span data-stu-id="d9981-109">In a member body, to indicate that a reference return value is stored locally as a reference that the caller intends to modify.</span></span> <span data-ttu-id="d9981-110">Vea [Variables locales de tipo ref](#ref-locals) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d9981-110">See [Ref locals](#ref-locals) for more information.</span></span>

## <a name="passing-an-argument-by-reference"></a><span data-ttu-id="d9981-111">Pasar un argumento mediante referencia</span><span class="sxs-lookup"><span data-stu-id="d9981-111">Passing an argument by reference</span></span>

<span data-ttu-id="d9981-112">Cuando se usa en una lista de parámetros del método, la palabra clave `ref` indica que un argumento se ha pasado mediante referencia, no por valor.</span><span class="sxs-lookup"><span data-stu-id="d9981-112">When used in a method's parameter list, the `ref` keyword indicates that an argument is passed by reference, not by value.</span></span> <span data-ttu-id="d9981-113">El efecto de pasar por referencia es que cualquier cambio del argumento en el método llamado se refleja en el método de llamada.</span><span class="sxs-lookup"><span data-stu-id="d9981-113">The effect of passing by reference is that any change to the argument in the called method is reflected in the calling method.</span></span> <span data-ttu-id="d9981-114">Por ejemplo, si el autor de la llamada pasa una expresión de variable local o una expresión de acceso de elemento de matriz, y el método llamado reemplaza el objeto al que hace referencia el parámetro ref, entonces la variable local del autor de la llamada o el elemento de matriz hace ahora referencia al nuevo objeto cuando el método devuelve.</span><span class="sxs-lookup"><span data-stu-id="d9981-114">For example, if the caller passes a local variable expression or an array element access expression, and the called method replaces the object to which the ref parameter refers, then the caller’s local variable or the array element now refers to the new object when the method returns.</span></span>

> [!NOTE]
>  <span data-ttu-id="d9981-115">No confunda el concepto de pasar por referencia con el concepto de tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="d9981-115">Do not confuse the concept of passing by reference with the concept of reference types.</span></span> <span data-ttu-id="d9981-116">Estos dos conceptos no son lo mismo.</span><span class="sxs-lookup"><span data-stu-id="d9981-116">The two concepts are not the same.</span></span> <span data-ttu-id="d9981-117">Un parámetro de método puede ser modificado por `ref` independientemente de si se trata de un tipo de valor o de un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="d9981-117">A method parameter can be modified by `ref` regardless of whether it is a value type or a reference type.</span></span> <span data-ttu-id="d9981-118">No hay ninguna conversión boxing de un tipo de valor cuando se pasa por referencia.</span><span class="sxs-lookup"><span data-stu-id="d9981-118">There is no boxing of a value type when it is passed by reference.</span></span>  

<span data-ttu-id="d9981-119">Para usar un parámetro `ref`, la definición de método y el método de llamada deben utilizar explícitamente la palabra clave `ref`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d9981-119">To use a `ref` parameter, both the method definition and the calling method must explicitly use the `ref` keyword, as shown in the following example.</span></span>  

[!code-csharp-interactive[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#1)]

<span data-ttu-id="d9981-120">Un argumento que se pasa a un parámetro `ref` o `in` debe inicializarse antes de pasarlo.</span><span class="sxs-lookup"><span data-stu-id="d9981-120">An argument that is passed to a `ref` or `in` parameter must be initialized before it is passed.</span></span> <span data-ttu-id="d9981-121">En esto difiere de los parámetros [out](out-parameter-modifier.md), cuyos argumentos no tienen que inicializarse explícitamente antes de pasarlos.</span><span class="sxs-lookup"><span data-stu-id="d9981-121">This differs from [out](out-parameter-modifier.md) parameters, whose arguments do not have to be explicitly initialized before they are passed.</span></span>

<span data-ttu-id="d9981-122">Los miembros de una clase no pueden tener signaturas que se diferencien solo por `ref`, `in` o `out`.</span><span class="sxs-lookup"><span data-stu-id="d9981-122">Members of a class can't have signatures that differ only by `ref`, `in`, or `out`.</span></span> <span data-ttu-id="d9981-123">Si la única diferencia entre dos miembros de un tipo es que uno de ellos tiene un parámetro `ref` y el otro tiene un parámetro `out` o `in`, se produce un error de compilador.</span><span class="sxs-lookup"><span data-stu-id="d9981-123">A compiler error occurs if the only difference between two members of a type is that one of them has a `ref` parameter and the other has an `out`, or `in` parameter.</span></span> <span data-ttu-id="d9981-124">El código siguiente, por ejemplo, no se compila.</span><span class="sxs-lookup"><span data-stu-id="d9981-124">The following code, for example, doesn't compile.</span></span>  

```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
<span data-ttu-id="d9981-125">En cambio, los métodos pueden sobrecargarse cuando un método tiene un parámetro `ref`, `in` o `out` y el otro tiene un parámetro de valor, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d9981-125">However, methods can be overloaded when one method has a `ref`, `in`, or `out` parameter and the other has a value parameter, as shown in the following example.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#2)]
  
 <span data-ttu-id="d9981-126">En otras situaciones que requieran firma coincidente, como ocultar o reemplazar, `in`, `ref` y `out` forman parte de la signatura y no coinciden entre sí.</span><span class="sxs-lookup"><span data-stu-id="d9981-126">In other situations that require signature matching, such as hiding or overriding, `in`, `ref`, and `out` are part of the signature and don't match each other.</span></span>  
  
 <span data-ttu-id="d9981-127">Las propiedades no son variables.</span><span class="sxs-lookup"><span data-stu-id="d9981-127">Properties are not variables.</span></span> <span data-ttu-id="d9981-128">Son métodos y no se pueden pasar a parámetros `ref`.</span><span class="sxs-lookup"><span data-stu-id="d9981-128">They are methods, and cannot be passed to `ref` parameters.</span></span>  
  
 <span data-ttu-id="d9981-129">Para obtener información sobre cómo pasar matrices, vea [Pasar matrices mediante Ref y Out ](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span><span class="sxs-lookup"><span data-stu-id="d9981-129">For information about how to pass arrays, see [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="d9981-130">Las palabras clave `ref`, `in` y `out` no pueden usarse para estos tipos de métodos:</span><span class="sxs-lookup"><span data-stu-id="d9981-130">You can't use the `ref`, `in`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="d9981-131">Métodos asincrónicos, que se definen mediante el uso del modificador [async](../../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="d9981-131">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
- <span data-ttu-id="d9981-132">Métodos de iterador, que incluyen una instrucción [yield return](../../../csharp/language-reference/keywords/yield.md) o `yield break`.</span><span class="sxs-lookup"><span data-stu-id="d9981-132">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

## <a name="passing-an-argument-by-reference-an-example"></a><span data-ttu-id="d9981-133">Pasar un argumento mediante referencia: un ejemplo</span><span class="sxs-lookup"><span data-stu-id="d9981-133">Passing an argument by reference: An example</span></span>

<span data-ttu-id="d9981-134">En los ejemplos anteriores se pasan tipos de valor mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="d9981-134">The previous examples pass value types by reference.</span></span> <span data-ttu-id="d9981-135">También se puede usar la palabra clave `ref` para pasar tipos de referencia mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="d9981-135">You can also use the `ref` keyword to pass reference types by reference.</span></span> <span data-ttu-id="d9981-136">Pasar un tipo de referencia por referencia permite que el método llamado pueda reemplazar el objeto al que hace referencia el parámetro de referencia en el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d9981-136">Passing a reference type by reference enables the called method to replace the object to which the reference parameter refers in the caller.</span></span> <span data-ttu-id="d9981-137">La ubicación de almacenamiento del objeto se pasa al método como el valor del parámetro de referencia.</span><span class="sxs-lookup"><span data-stu-id="d9981-137">The storage location of the object is passed to the method as the value of the reference parameter.</span></span> <span data-ttu-id="d9981-138">Si cambia el valor de la ubicación de almacenamiento del parámetro (para que apunte a un nuevo objeto), también debe cambiar la ubicación de almacenamiento a la que se refiere el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d9981-138">If you change the value in the storage location of the parameter (to point to a new object), you also change the storage location to which the caller refers.</span></span> <span data-ttu-id="d9981-139">En el ejemplo siguiente se pasa una instancia de un tipo de referencia como un parámetro `ref`.</span><span class="sxs-lookup"><span data-stu-id="d9981-139">The following example passes an instance of a reference type as a `ref` parameter.</span></span>   
  
[!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#3)]

<span data-ttu-id="d9981-140">Para obtener más información sobre cómo pasar tipos de referencia por valor y por referencia, vea [Pasar parámetros Reference-Type ](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="d9981-140">For more information about how to pass reference types by value and by reference, see [Passing Reference-Type Parameters](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span></span>
  
## <a name="reference-return-values"></a><span data-ttu-id="d9981-141">Valores devueltos de referencia</span><span class="sxs-lookup"><span data-stu-id="d9981-141">Reference return values</span></span>

<span data-ttu-id="d9981-142">Los valores devueltos de referencia (o valores devueltos de tipo ref) son valores que devuelve un método mediante referencia al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d9981-142">Reference return values (or ref returns) are values that a method returns by reference to the caller.</span></span> <span data-ttu-id="d9981-143">Es decir, el autor de la llamada puede modificar el valor devuelto por un método, y ese cambio se refleja en el estado del objeto que contiene el método.</span><span class="sxs-lookup"><span data-stu-id="d9981-143">That is, the caller can modify the value returned by a method, and that change is reflected in the state of the object that contains the method.</span></span> 

<span data-ttu-id="d9981-144">Un valor devuelto de referencia se define mediante la palabra clave `ref`:</span><span class="sxs-lookup"><span data-stu-id="d9981-144">A reference return value is defined by using the `ref` keyword:</span></span>

- <span data-ttu-id="d9981-145">En la firma del método.</span><span class="sxs-lookup"><span data-stu-id="d9981-145">In the method signature.</span></span> <span data-ttu-id="d9981-146">Por ejemplo, la siguiente firma del método indica que el método `GetCurrentPrice` devuelve un valor <xref:System.Decimal> mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="d9981-146">For example, the following method signature inidicates that the `GetCurrentPrice` method returns a <xref:System.Decimal> value by reference.</span></span>

   ```csharp
   public ref decimal GetCurrentValue()
   ``` 
- <span data-ttu-id="d9981-147">Entre el token `return` y la variable devuelta en una instrucción `return` en el método.</span><span class="sxs-lookup"><span data-stu-id="d9981-147">Between the `return` token and the variable returned in a `return` statement in the method.</span></span> <span data-ttu-id="d9981-148">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d9981-148">For example:</span></span>
 
   ```csharp
   return ref DecimalArray[0];
   ``` 

<span data-ttu-id="d9981-149">Para que el autor de la llamada modifique el estado del objeto, el valor devuelto de referencia debe almacenarse en una variable que se defina explícitamente como una [variable local de tipo ref](#ref-locals).</span><span class="sxs-lookup"><span data-stu-id="d9981-149">In order for the caller to modify the object's state, the reference return value must be stored to a variable that is explicitly defined as a [ref local](#ref-locals).</span></span> 

<span data-ttu-id="d9981-150">Para obtener un ejemplo, vea [Un ejemplo de valores devueltos y variables locales de tipo ref](#a-ref-returns-and-ref-locals-example).</span><span class="sxs-lookup"><span data-stu-id="d9981-150">For an example, see [A ref returns and ref locals example](#a-ref-returns-and-ref-locals-example)</span></span>

## <a name="ref-locals"></a><span data-ttu-id="d9981-151">Variables locales de tipo ref</span><span class="sxs-lookup"><span data-stu-id="d9981-151">Ref locals</span></span>

<span data-ttu-id="d9981-152">Una variable local de tipo ref se usa para hacer referencia a valores devueltos con `return ref`.</span><span class="sxs-lookup"><span data-stu-id="d9981-152">A ref local variable is used to refer to values returned using `return ref`.</span></span>  <span data-ttu-id="d9981-153">Una variable local de tipo ref debe inicializarse y asignarse a un valor devuelto de tipo ref.</span><span class="sxs-lookup"><span data-stu-id="d9981-153">A ref local variable must be initialized and assigned to a ref return value.</span></span> <span data-ttu-id="d9981-154">Cualquier modificación en el valor de la variable local de tipo ref se refleja en el estado del objeto cuyo método ha devuelto el valor mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="d9981-154">Any modifications to the value of the ref local are reflected in the state of the object whose method returned the value by reference.</span></span>

<span data-ttu-id="d9981-155">Defina una variable local de tipo ref mediante la palabra clave `ref` antes de la declaración de variable, así como inmediatamente antes de la llamada al método que devuelve el valor mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="d9981-155">You define a ref local by using the `ref` keyword before the variable declaration, as well as immediately before the call to the method that returns the value by reference.</span></span> 

<span data-ttu-id="d9981-156">Por ejemplo, en la siguiente instrucción se define un valor de variable local de tipo ref que se devuelve mediante un método denominado `GetEstimatedValue`:</span><span class="sxs-lookup"><span data-stu-id="d9981-156">For example, the following statement defines a ref local value that is returned by a method named `GetEstimatedValue`:</span></span>

```csharp
ref decimal estValue = ref Building.GetEstimatedValue();
```

<span data-ttu-id="d9981-157">Tenga en cuenta que la palabra clave `ref` debe usarse en ambos lugares, o el compilador genera un error CS8172, "No se puede inicializar una variable por referencia con un valor".</span><span class="sxs-lookup"><span data-stu-id="d9981-157">Note that the `ref` keyword must be used in both places, or the compiler generates error CS8172, "Cannot initialize a by-reference variable with a value."</span></span> 
 
## <a name="a-ref-returns-and-ref-locals-example"></a><span data-ttu-id="d9981-158">Un ejemplo de valores devueltos y variables locales de tipo ref</span><span class="sxs-lookup"><span data-stu-id="d9981-158">A ref returns and ref locals example</span></span>

<span data-ttu-id="d9981-159">En el ejemplo siguiente se define una clase `Book` que tiene dos campos <xref:System.String>, `Title` y `Author`.</span><span class="sxs-lookup"><span data-stu-id="d9981-159">The following example defines a `Book` class that has two <xref:System.String> fields, `Title` and `Author`.</span></span> <span data-ttu-id="d9981-160">También define una clase `BookCollection` que incluye una matriz privada de objetos `Book`.</span><span class="sxs-lookup"><span data-stu-id="d9981-160">It also defines a `BookCollection` class that includes a private array of `Book` objects.</span></span> <span data-ttu-id="d9981-161">Los objetos book individuales se devuelven mediante referencia llamando a su método `GetBookByTitle`.</span><span class="sxs-lookup"><span data-stu-id="d9981-161">Individual book objects are returned by reference by calling its `GetBookByTitle` method.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#4)]

<span data-ttu-id="d9981-162">Cuando el autor de la llamada almacena el valor devuelto mediante el método `GetBookByTitle` como una variable local de tipo ref, los cambios que el autor de la llamada realiza en el valor devuelto se reflejan en el objeto `BookCollection`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d9981-162">When the caller stores the value returned by the `GetBookByTitle` method as a ref local, changes that the caller makes to the return value are reflected in the `BookCollection` object, as the following example shows.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="d9981-163">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="d9981-163">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d9981-164">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9981-164">See Also</span></span>  
 [<span data-ttu-id="d9981-165">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="d9981-165">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="d9981-166">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d9981-166">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d9981-167">Pasar parámetros</span><span class="sxs-lookup"><span data-stu-id="d9981-167">Passing Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)  
 [<span data-ttu-id="d9981-168">Parámetros de métodos</span><span class="sxs-lookup"><span data-stu-id="d9981-168">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)  
 [<span data-ttu-id="d9981-169">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="d9981-169">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)

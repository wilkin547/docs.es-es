---
title: ref (Referencia de C#)
ms.date: 03/06/2018
f1_keywords:
- ref_CSharpKeyword
- ref
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
ms.openlocfilehash: a72624d5702ec12bfda98d49a16474cc84205ff0
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245757"
---
# <a name="ref-c-reference"></a><span data-ttu-id="0512d-102">ref (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="0512d-102">ref (C# Reference)</span></span>

<span data-ttu-id="0512d-103">La palabra clave `ref` indica un valor que se ha pasado mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="0512d-103">The `ref` keyword indicates a value that is passed by reference.</span></span> <span data-ttu-id="0512d-104">Se usa en cuatro contextos diferentes:</span><span class="sxs-lookup"><span data-stu-id="0512d-104">It is used in four different contexts:</span></span>

- <span data-ttu-id="0512d-105">En una firma del método y en una llamada al método, para pasar un argumento a un método mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="0512d-105">In a method signature and in a method call, to pass an argument to a method by reference.</span></span> <span data-ttu-id="0512d-106">Vea [Pasar un argumento mediante referencia](#passing-an-argument-by-reference) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0512d-106">See [Passing an argument by reference](#passing-an-argument-by-reference) for more information.</span></span>
- <span data-ttu-id="0512d-107">En una firma del método, para devolver un valor al autor de la llamada mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="0512d-107">In a method signature, to return a value to the caller by reference.</span></span> <span data-ttu-id="0512d-108">Para obtener más información, vea [Valores devueltos de referencia](#reference-return-values).</span><span class="sxs-lookup"><span data-stu-id="0512d-108">See [Reference return values](#reference-return-values) for more information.</span></span>
- <span data-ttu-id="0512d-109">En un cuerpo de miembro, para indicar que un valor devuelto de referencia se almacena localmente como una referencia que el autor de la llamada pretende modificar o, en general, que una variable local accede a otro valor por referencia.</span><span class="sxs-lookup"><span data-stu-id="0512d-109">In a member body, to indicate that a reference return value is stored locally as a reference that the caller intends to modify or, in general, a local variable accesses another value by reference.</span></span> <span data-ttu-id="0512d-110">Vea [Variables locales de tipo ref](#ref-locals) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0512d-110">See [Ref locals](#ref-locals) for more information.</span></span>
- <span data-ttu-id="0512d-111">En una declaración `struct` para declarar `ref struct` o `ref readonly struct`.</span><span class="sxs-lookup"><span data-stu-id="0512d-111">In a `struct` declaration to declare a `ref struct` or a `ref readonly struct`.</span></span> <span data-ttu-id="0512d-112">Vea [Declaraciones de estructuras ref](#ref-struct-declarations) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0512d-112">See [ref struct declarations](#ref-struct-declarations) for more information.</span></span>

## <a name="passing-an-argument-by-reference"></a><span data-ttu-id="0512d-113">Pasar un argumento mediante referencia</span><span class="sxs-lookup"><span data-stu-id="0512d-113">Passing an argument by reference</span></span>

<span data-ttu-id="0512d-114">Cuando se usa en una lista de parámetros del método, la palabra clave `ref` indica que un argumento se ha pasado mediante referencia, no por valor.</span><span class="sxs-lookup"><span data-stu-id="0512d-114">When used in a method's parameter list, the `ref` keyword indicates that an argument is passed by reference, not by value.</span></span> <span data-ttu-id="0512d-115">El efecto de pasar por referencia es que cualquier cambio del argumento en el método llamado se refleja en el método de llamada.</span><span class="sxs-lookup"><span data-stu-id="0512d-115">The effect of passing by reference is that any change to the argument in the called method is reflected in the calling method.</span></span> <span data-ttu-id="0512d-116">Por ejemplo, si el autor de la llamada pasa una expresión de variable local o una expresión de acceso de elemento de matriz, y el método llamado reemplaza el objeto al que hace referencia el parámetro ref, entonces la variable local del autor de la llamada o el elemento de matriz hace ahora referencia al nuevo objeto cuando el método devuelve.</span><span class="sxs-lookup"><span data-stu-id="0512d-116">For example, if the caller passes a local variable expression or an array element access expression, and the called method replaces the object to which the ref parameter refers, then the caller’s local variable or the array element now refers to the new object when the method returns.</span></span>

> [!NOTE]
> <span data-ttu-id="0512d-117">No confunda el concepto de pasar por referencia con el concepto de tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="0512d-117">Do not confuse the concept of passing by reference with the concept of reference types.</span></span> <span data-ttu-id="0512d-118">Estos dos conceptos no son lo mismo.</span><span class="sxs-lookup"><span data-stu-id="0512d-118">The two concepts are not the same.</span></span> <span data-ttu-id="0512d-119">Un parámetro de método puede ser modificado por `ref` independientemente de si se trata de un tipo de valor o de un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="0512d-119">A method parameter can be modified by `ref` regardless of whether it is a value type or a reference type.</span></span> <span data-ttu-id="0512d-120">No hay ninguna conversión boxing de un tipo de valor cuando se pasa por referencia.</span><span class="sxs-lookup"><span data-stu-id="0512d-120">There is no boxing of a value type when it is passed by reference.</span></span>  

<span data-ttu-id="0512d-121">Para usar un parámetro `ref`, la definición de método y el método de llamada deben utilizar explícitamente la palabra clave `ref`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="0512d-121">To use a `ref` parameter, both the method definition and the calling method must explicitly use the `ref` keyword, as shown in the following example.</span></span>  

[!code-csharp-interactive[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#1)]

<span data-ttu-id="0512d-122">Un argumento que se pasa a un parámetro `ref` o `in` debe inicializarse antes de pasarlo.</span><span class="sxs-lookup"><span data-stu-id="0512d-122">An argument that is passed to a `ref` or `in` parameter must be initialized before it is passed.</span></span> <span data-ttu-id="0512d-123">En esto difiere de los parámetros [out](out-parameter-modifier.md), cuyos argumentos no tienen que inicializarse explícitamente antes de pasarlos.</span><span class="sxs-lookup"><span data-stu-id="0512d-123">This differs from [out](out-parameter-modifier.md) parameters, whose arguments do not have to be explicitly initialized before they are passed.</span></span>

<span data-ttu-id="0512d-124">Los miembros de una clase no pueden tener signaturas que se diferencien solo por `ref`, `in` o `out`.</span><span class="sxs-lookup"><span data-stu-id="0512d-124">Members of a class can't have signatures that differ only by `ref`, `in`, or `out`.</span></span> <span data-ttu-id="0512d-125">Si la única diferencia entre dos miembros de un tipo es que uno de ellos tiene un parámetro `ref` y el otro tiene un parámetro `out` o `in`, se produce un error de compilador.</span><span class="sxs-lookup"><span data-stu-id="0512d-125">A compiler error occurs if the only difference between two members of a type is that one of them has a `ref` parameter and the other has an `out`, or `in` parameter.</span></span> <span data-ttu-id="0512d-126">El código siguiente, por ejemplo, no se compila.</span><span class="sxs-lookup"><span data-stu-id="0512d-126">The following code, for example, doesn't compile.</span></span>  

```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```

<span data-ttu-id="0512d-127">En cambio, los métodos pueden sobrecargarse cuando un método tiene un parámetro `ref`, `in` o `out` y el otro tiene un parámetro de valor, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="0512d-127">However, methods can be overloaded when one method has a `ref`, `in`, or `out` parameter and the other has a value parameter, as shown in the following example.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#2)]
  
 <span data-ttu-id="0512d-128">En otras situaciones que requieran firma coincidente, como ocultar o reemplazar, `in`, `ref` y `out` forman parte de la signatura y no coinciden entre sí.</span><span class="sxs-lookup"><span data-stu-id="0512d-128">In other situations that require signature matching, such as hiding or overriding, `in`, `ref`, and `out` are part of the signature and don't match each other.</span></span>  
  
 <span data-ttu-id="0512d-129">Las propiedades no son variables.</span><span class="sxs-lookup"><span data-stu-id="0512d-129">Properties are not variables.</span></span> <span data-ttu-id="0512d-130">Son métodos y no se pueden pasar a parámetros `ref`.</span><span class="sxs-lookup"><span data-stu-id="0512d-130">They are methods, and cannot be passed to `ref` parameters.</span></span>  
  
 <span data-ttu-id="0512d-131">Para obtener información sobre cómo pasar matrices, vea [Pasar matrices mediante Ref y Out ](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span><span class="sxs-lookup"><span data-stu-id="0512d-131">For information about how to pass arrays, see [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="0512d-132">Las palabras clave `ref`, `in` y `out` no pueden usarse para estos tipos de métodos:</span><span class="sxs-lookup"><span data-stu-id="0512d-132">You can't use the `ref`, `in`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="0512d-133">Métodos asincrónicos, que se definen mediante el uso del modificador [async](../../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="0512d-133">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
- <span data-ttu-id="0512d-134">Métodos de iterador, que incluyen una instrucción [yield return](../../../csharp/language-reference/keywords/yield.md) o `yield break`.</span><span class="sxs-lookup"><span data-stu-id="0512d-134">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

## <a name="passing-an-argument-by-reference-an-example"></a><span data-ttu-id="0512d-135">Pasar un argumento mediante referencia: un ejemplo</span><span class="sxs-lookup"><span data-stu-id="0512d-135">Passing an argument by reference: An example</span></span>

<span data-ttu-id="0512d-136">En los ejemplos anteriores se pasan tipos de valor mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="0512d-136">The previous examples pass value types by reference.</span></span> <span data-ttu-id="0512d-137">También se puede usar la palabra clave `ref` para pasar tipos de referencia mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="0512d-137">You can also use the `ref` keyword to pass reference types by reference.</span></span> <span data-ttu-id="0512d-138">Pasar un tipo de referencia por referencia permite que el método llamado pueda reemplazar el objeto al que hace referencia el parámetro de referencia en el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0512d-138">Passing a reference type by reference enables the called method to replace the object to which the reference parameter refers in the caller.</span></span> <span data-ttu-id="0512d-139">La ubicación de almacenamiento del objeto se pasa al método como el valor del parámetro de referencia.</span><span class="sxs-lookup"><span data-stu-id="0512d-139">The storage location of the object is passed to the method as the value of the reference parameter.</span></span> <span data-ttu-id="0512d-140">Si cambia el valor de la ubicación de almacenamiento del parámetro (para que apunte a un nuevo objeto), también debe cambiar la ubicación de almacenamiento a la que se refiere el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0512d-140">If you change the value in the storage location of the parameter (to point to a new object), you also change the storage location to which the caller refers.</span></span> <span data-ttu-id="0512d-141">En el ejemplo siguiente se pasa una instancia de un tipo de referencia como un parámetro `ref`.</span><span class="sxs-lookup"><span data-stu-id="0512d-141">The following example passes an instance of a reference type as a `ref` parameter.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#3)]

<span data-ttu-id="0512d-142">Para obtener más información sobre cómo pasar tipos de referencia por valor y por referencia, vea [Pasar parámetros Reference-Type ](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="0512d-142">For more information about how to pass reference types by value and by reference, see [Passing Reference-Type Parameters](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span></span>
  
## <a name="reference-return-values"></a><span data-ttu-id="0512d-143">Valores devueltos de referencia</span><span class="sxs-lookup"><span data-stu-id="0512d-143">Reference return values</span></span>

<span data-ttu-id="0512d-144">Los valores devueltos de referencia (o valores devueltos de tipo ref) son valores que devuelve un método mediante referencia al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0512d-144">Reference return values (or ref returns) are values that a method returns by reference to the caller.</span></span> <span data-ttu-id="0512d-145">Es decir, el autor de la llamada puede modificar el valor devuelto por un método, y ese cambio se refleja en el estado del objeto que contiene el método.</span><span class="sxs-lookup"><span data-stu-id="0512d-145">That is, the caller can modify the value returned by a method, and that change is reflected in the state of the object that contains the method.</span></span>

<span data-ttu-id="0512d-146">Un valor devuelto de referencia se define mediante la palabra clave `ref`:</span><span class="sxs-lookup"><span data-stu-id="0512d-146">A reference return value is defined by using the `ref` keyword:</span></span>

- <span data-ttu-id="0512d-147">En la firma del método.</span><span class="sxs-lookup"><span data-stu-id="0512d-147">In the method signature.</span></span> <span data-ttu-id="0512d-148">Por ejemplo, en la firma de método siguiente se indica que el método `GetCurrentPrice` devuelve un valor <xref:System.Decimal> por referencia.</span><span class="sxs-lookup"><span data-stu-id="0512d-148">For example, the following method signature indicates that the `GetCurrentPrice` method returns a <xref:System.Decimal> value by reference.</span></span>

```csharp
public ref decimal GetCurrentValue()
```

- <span data-ttu-id="0512d-149">Entre el token `return` y la variable devuelta en una instrucción `return` en el método.</span><span class="sxs-lookup"><span data-stu-id="0512d-149">Between the `return` token and the variable returned in a `return` statement in the method.</span></span> <span data-ttu-id="0512d-150">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0512d-150">For example:</span></span>

```csharp
return ref DecimalArray[0];
```

<span data-ttu-id="0512d-151">Para que el autor de la llamada modifique el estado del objeto, el valor devuelto de referencia debe almacenarse en una variable que se defina explícitamente como una [variable local de tipo ref](#ref-locals).</span><span class="sxs-lookup"><span data-stu-id="0512d-151">In order for the caller to modify the object's state, the reference return value must be stored to a variable that is explicitly defined as a [ref local](#ref-locals).</span></span>

<span data-ttu-id="0512d-152">Para obtener un ejemplo, vea [Un ejemplo de valores devueltos y variables locales de tipo ref](#a-ref-returns-and-ref-locals-example).</span><span class="sxs-lookup"><span data-stu-id="0512d-152">For an example, see [A ref returns and ref locals example](#a-ref-returns-and-ref-locals-example)</span></span>

## <a name="ref-locals"></a><span data-ttu-id="0512d-153">Variables locales de tipo ref</span><span class="sxs-lookup"><span data-stu-id="0512d-153">Ref locals</span></span>

<span data-ttu-id="0512d-154">Una variable local de tipo ref se usa para hacer referencia a valores devueltos con `return ref`.</span><span class="sxs-lookup"><span data-stu-id="0512d-154">A ref local variable is used to refer to values returned using `return ref`.</span></span>  <span data-ttu-id="0512d-155">Una variable local de tipo ref debe inicializarse y asignarse a un valor devuelto de tipo ref.</span><span class="sxs-lookup"><span data-stu-id="0512d-155">A ref local variable must be initialized and assigned to a ref return value.</span></span> <span data-ttu-id="0512d-156">Cualquier modificación en el valor de la variable local de tipo ref se refleja en el estado del objeto cuyo método ha devuelto el valor mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="0512d-156">Any modifications to the value of the ref local are reflected in the state of the object whose method returned the value by reference.</span></span>

<span data-ttu-id="0512d-157">Defina una variable local de tipo ref mediante la palabra clave `ref` antes de la declaración de variable, así como inmediatamente antes de la llamada al método que devuelve el valor mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="0512d-157">You define a ref local by using the `ref` keyword before the variable declaration, as well as immediately before the call to the method that returns the value by reference.</span></span>

<span data-ttu-id="0512d-158">Por ejemplo, en la siguiente instrucción se define un valor de variable local de tipo ref que se devuelve mediante un método denominado `GetEstimatedValue`:</span><span class="sxs-lookup"><span data-stu-id="0512d-158">For example, the following statement defines a ref local value that is returned by a method named `GetEstimatedValue`:</span></span>

```csharp
ref decimal estValue = ref Building.GetEstimatedValue();
```

<span data-ttu-id="0512d-159">Puede acceder a un valor por referencia de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="0512d-159">You can access a value by reference in the same way.</span></span> <span data-ttu-id="0512d-160">En algunos casos, acceder a un valor por referencia aumenta el rendimiento, ya que evita una operación de copia potencialmente cara.</span><span class="sxs-lookup"><span data-stu-id="0512d-160">In some cases, accessing a value by reference increases performance by avoiding a potentially expensive copy operation.</span></span> <span data-ttu-id="0512d-161">Por ejemplo, en la instrucción siguiente se muestra cómo es posible definir un valor local de referencia que se usa para hacer referencia a un valor.</span><span class="sxs-lookup"><span data-stu-id="0512d-161">For example, the following statement shows how one can define a ref local value that is used to reference a value.</span></span>

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct;
```

<span data-ttu-id="0512d-162">Tenga en cuenta que en ambos ejemplos la palabra clave `ref` debe usarse en ambos lugares. De lo contrario, el compilador genera el error CS8172, "No se puede inicializar una variable por referencia con un valor".</span><span class="sxs-lookup"><span data-stu-id="0512d-162">Note that in both examples the `ref` keyword must be used in both places, or the compiler generates error CS8172, "Cannot initialize a by-reference variable with a value."</span></span>

## <a name="a-ref-returns-and-ref-locals-example"></a><span data-ttu-id="0512d-163">Un ejemplo de valores devueltos y variables locales de tipo ref</span><span class="sxs-lookup"><span data-stu-id="0512d-163">A ref returns and ref locals example</span></span>

<span data-ttu-id="0512d-164">En el ejemplo siguiente se define una clase `Book` que tiene dos campos <xref:System.String>, `Title` y `Author`.</span><span class="sxs-lookup"><span data-stu-id="0512d-164">The following example defines a `Book` class that has two <xref:System.String> fields, `Title` and `Author`.</span></span> <span data-ttu-id="0512d-165">También define una clase `BookCollection` que incluye una matriz privada de objetos `Book`.</span><span class="sxs-lookup"><span data-stu-id="0512d-165">It also defines a `BookCollection` class that includes a private array of `Book` objects.</span></span> <span data-ttu-id="0512d-166">Los objetos book individuales se devuelven mediante referencia llamando a su método `GetBookByTitle`.</span><span class="sxs-lookup"><span data-stu-id="0512d-166">Individual book objects are returned by reference by calling its `GetBookByTitle` method.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#4)]

<span data-ttu-id="0512d-167">Cuando el autor de la llamada almacena el valor devuelto mediante el método `GetBookByTitle` como una variable local de tipo ref, los cambios que el autor de la llamada realiza en el valor devuelto se reflejan en el objeto `BookCollection`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="0512d-167">When the caller stores the value returned by the `GetBookByTitle` method as a ref local, changes that the caller makes to the return value are reflected in the `BookCollection` object, as the following example shows.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#5)]

## <a name="ref-struct-declarations"></a><span data-ttu-id="0512d-168">Declaraciones de estructuras ref</span><span class="sxs-lookup"><span data-stu-id="0512d-168">Ref struct declarations</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0512d-169">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="0512d-169">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0512d-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="0512d-170">See also</span></span>

 [<span data-ttu-id="0512d-171">Semántica de referencia con tipos de valor</span><span class="sxs-lookup"><span data-stu-id="0512d-171">Reference semantics with value types</span></span>](../../reference-semantics-with-value-types.md)  
 [<span data-ttu-id="0512d-172">Pasar parámetros</span><span class="sxs-lookup"><span data-stu-id="0512d-172">Passing Parameters</span></span>](../../programming-guide/classes-and-structs/passing-parameters.md)  
 [<span data-ttu-id="0512d-173">Parámetros de métodos</span><span class="sxs-lookup"><span data-stu-id="0512d-173">Method Parameters</span></span>](method-parameters.md)  
 [<span data-ttu-id="0512d-174">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="0512d-174">C# Reference</span></span>](../index.md)  
 [<span data-ttu-id="0512d-175">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="0512d-175">C# Programming Guide</span></span>](../../programming-guide/index.md)  
 [<span data-ttu-id="0512d-176">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="0512d-176">C# Keywords</span></span>](index.md)

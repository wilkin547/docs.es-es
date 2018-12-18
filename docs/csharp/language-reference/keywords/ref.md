---
title: ref (palabra clave) - Referencia de C#
ms.custom: seodec18
ms.date: 10/24/2018
f1_keywords:
- ref_CSharpKeyword
- ref
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
ms.openlocfilehash: 187d2fb7399195c544bae59927d66e9853df5fa0
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236328"
---
# <a name="ref-c-reference"></a><span data-ttu-id="b5de0-102">ref (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="b5de0-102">ref (C# Reference)</span></span>

<span data-ttu-id="b5de0-103">La palabra clave `ref` indica un valor que se ha pasado mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="b5de0-103">The `ref` keyword indicates a value that is passed by reference.</span></span> <span data-ttu-id="b5de0-104">Se usa en cuatro contextos diferentes:</span><span class="sxs-lookup"><span data-stu-id="b5de0-104">It is used in four different contexts:</span></span>

- <span data-ttu-id="b5de0-105">En una firma del método y en una llamada al método, para pasar un argumento a un método mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="b5de0-105">In a method signature and in a method call, to pass an argument to a method by reference.</span></span> <span data-ttu-id="b5de0-106">Para más información, vea [Pasar un argumento mediante referencia](#passing-an-argument-by-reference).</span><span class="sxs-lookup"><span data-stu-id="b5de0-106">For more information, see [Passing an argument by reference](#passing-an-argument-by-reference).</span></span>
- <span data-ttu-id="b5de0-107">En una firma del método, para devolver un valor al autor de la llamada mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="b5de0-107">In a method signature, to return a value to the caller by reference.</span></span> <span data-ttu-id="b5de0-108">Para obtener más información, consulte [Valores devueltos de referencia](#reference-return-values).</span><span class="sxs-lookup"><span data-stu-id="b5de0-108">For more information, see [Reference return values](#reference-return-values).</span></span>
- <span data-ttu-id="b5de0-109">En un cuerpo de miembro, para indicar que un valor devuelto de referencia se almacena localmente como una referencia que el autor de la llamada pretende modificar o, en general, que una variable local accede a otro valor por referencia.</span><span class="sxs-lookup"><span data-stu-id="b5de0-109">In a member body, to indicate that a reference return value is stored locally as a reference that the caller intends to modify or, in general, a local variable accesses another value by reference.</span></span> <span data-ttu-id="b5de0-110">Para más información, vea [Variables locales de tipo ref](#ref-locals).</span><span class="sxs-lookup"><span data-stu-id="b5de0-110">For more information, see [Ref locals](#ref-locals).</span></span>
- <span data-ttu-id="b5de0-111">En una declaración `struct` para declarar `ref struct` o `ref readonly struct`.</span><span class="sxs-lookup"><span data-stu-id="b5de0-111">In a `struct` declaration to declare a `ref struct` or a `ref readonly struct`.</span></span> <span data-ttu-id="b5de0-112">Para más información, vea [Tipo de estructura de referencia](#ref-struct-types).</span><span class="sxs-lookup"><span data-stu-id="b5de0-112">For more information, see [ref struct types](#ref-struct-types).</span></span>


## <a name="passing-an-argument-by-reference"></a><span data-ttu-id="b5de0-113">Pasar un argumento mediante referencia</span><span class="sxs-lookup"><span data-stu-id="b5de0-113">Passing an argument by reference</span></span>

<span data-ttu-id="b5de0-114">Cuando se usa en una lista de parámetros del método, la palabra clave `ref` indica que un argumento se ha pasado mediante referencia, no por valor.</span><span class="sxs-lookup"><span data-stu-id="b5de0-114">When used in a method's parameter list, the `ref` keyword indicates that an argument is passed by reference, not by value.</span></span> <span data-ttu-id="b5de0-115">El efecto de pasar por referencia es que cualquier cambio del argumento en el método llamado se refleja en el método de llamada.</span><span class="sxs-lookup"><span data-stu-id="b5de0-115">The effect of passing by reference is that any change to the argument in the called method is reflected in the calling method.</span></span> <span data-ttu-id="b5de0-116">Por ejemplo, si el autor de la llamada pasa una expresión de variable local o una expresión de acceso de elemento de matriz, y el método llamado reemplaza el objeto al que hace referencia el parámetro ref, entonces la variable local del autor de la llamada o el elemento de matriz hace ahora referencia al nuevo objeto cuando el método devuelve.</span><span class="sxs-lookup"><span data-stu-id="b5de0-116">For example, if the caller passes a local variable expression or an array element access expression, and the called method replaces the object to which the ref parameter refers, then the caller’s local variable or the array element now refers to the new object when the method returns.</span></span>

> [!NOTE]
> <span data-ttu-id="b5de0-117">No confunda el concepto de pasar por referencia con el concepto de tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="b5de0-117">Do not confuse the concept of passing by reference with the concept of reference types.</span></span> <span data-ttu-id="b5de0-118">Estos dos conceptos no son lo mismo.</span><span class="sxs-lookup"><span data-stu-id="b5de0-118">The two concepts are not the same.</span></span> <span data-ttu-id="b5de0-119">Un parámetro de método puede ser modificado por `ref` independientemente de si se trata de un tipo de valor o de un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="b5de0-119">A method parameter can be modified by `ref` regardless of whether it is a value type or a reference type.</span></span> <span data-ttu-id="b5de0-120">No hay ninguna conversión boxing de un tipo de valor cuando se pasa por referencia.</span><span class="sxs-lookup"><span data-stu-id="b5de0-120">There is no boxing of a value type when it is passed by reference.</span></span>  

<span data-ttu-id="b5de0-121">Para usar un parámetro `ref`, la definición de método y el método de llamada deben utilizar explícitamente la palabra clave `ref`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b5de0-121">To use a `ref` parameter, both the method definition and the calling method must explicitly use the `ref` keyword, as shown in the following example.</span></span>  

[!code-csharp-interactive[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#1)]

<span data-ttu-id="b5de0-122">Un argumento que se pasa a un parámetro `ref` o `in` debe inicializarse antes de pasarlo.</span><span class="sxs-lookup"><span data-stu-id="b5de0-122">An argument that is passed to a `ref` or `in` parameter must be initialized before it is passed.</span></span> <span data-ttu-id="b5de0-123">En esto difiere de los parámetros [out](out-parameter-modifier.md), cuyos argumentos no tienen que inicializarse explícitamente antes de pasarlos.</span><span class="sxs-lookup"><span data-stu-id="b5de0-123">This differs from [out](out-parameter-modifier.md) parameters, whose arguments do not have to be explicitly initialized before they are passed.</span></span>

<span data-ttu-id="b5de0-124">Los miembros de una clase no pueden tener signaturas que se diferencien solo por `ref`, `in` o `out`.</span><span class="sxs-lookup"><span data-stu-id="b5de0-124">Members of a class can't have signatures that differ only by `ref`, `in`, or `out`.</span></span> <span data-ttu-id="b5de0-125">Si la única diferencia entre dos miembros de un tipo es que uno de ellos tiene un parámetro `ref` y el otro tiene un parámetro `out` o `in`, se produce un error de compilador.</span><span class="sxs-lookup"><span data-stu-id="b5de0-125">A compiler error occurs if the only difference between two members of a type is that one of them has a `ref` parameter and the other has an `out`, or `in` parameter.</span></span> <span data-ttu-id="b5de0-126">El código siguiente, por ejemplo, no se compila.</span><span class="sxs-lookup"><span data-stu-id="b5de0-126">The following code, for example, doesn't compile.</span></span>  

```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```

<span data-ttu-id="b5de0-127">En cambio, los métodos pueden sobrecargarse cuando un método tiene un parámetro `ref`, `in` o `out` y el otro tiene un parámetro de valor, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b5de0-127">However, methods can be overloaded when one method has a `ref`, `in`, or `out` parameter and the other has a value parameter, as shown in the following example.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#2)]
  
 <span data-ttu-id="b5de0-128">En otras situaciones que requieran firma coincidente, como ocultar o reemplazar, `in`, `ref` y `out` forman parte de la signatura y no coinciden entre sí.</span><span class="sxs-lookup"><span data-stu-id="b5de0-128">In other situations that require signature matching, such as hiding or overriding, `in`, `ref`, and `out` are part of the signature and don't match each other.</span></span>  
  
 <span data-ttu-id="b5de0-129">Las propiedades no son variables.</span><span class="sxs-lookup"><span data-stu-id="b5de0-129">Properties are not variables.</span></span> <span data-ttu-id="b5de0-130">Son métodos y no se pueden pasar a parámetros `ref`.</span><span class="sxs-lookup"><span data-stu-id="b5de0-130">They are methods, and cannot be passed to `ref` parameters.</span></span>  
  
 <span data-ttu-id="b5de0-131">Las palabras clave `ref`, `in` y `out` no pueden usarse para estos tipos de métodos:</span><span class="sxs-lookup"><span data-stu-id="b5de0-131">You can't use the `ref`, `in`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="b5de0-132">Métodos asincrónicos, que se definen mediante el uso del modificador [async](async.md).</span><span class="sxs-lookup"><span data-stu-id="b5de0-132">Async methods, which you define by using the [async](async.md) modifier.</span></span>  
- <span data-ttu-id="b5de0-133">Métodos de iterador, que incluyen una instrucción [yield return](yield.md) o `yield break`.</span><span class="sxs-lookup"><span data-stu-id="b5de0-133">Iterator methods, which include a [yield return](yield.md) or `yield break` statement.</span></span>  

## <a name="passing-an-argument-by-reference-an-example"></a><span data-ttu-id="b5de0-134">Paso de un argumento mediante referencia: Un ejemplo</span><span class="sxs-lookup"><span data-stu-id="b5de0-134">Passing an argument by reference: An example</span></span>

<span data-ttu-id="b5de0-135">En los ejemplos anteriores se pasan tipos de valor mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="b5de0-135">The previous examples pass value types by reference.</span></span> <span data-ttu-id="b5de0-136">También se puede usar la palabra clave `ref` para pasar tipos de referencia mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="b5de0-136">You can also use the `ref` keyword to pass reference types by reference.</span></span> <span data-ttu-id="b5de0-137">Pasar un tipo de referencia por referencia permite que el método llamado pueda reemplazar el objeto al que hace referencia el parámetro de referencia en el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b5de0-137">Passing a reference type by reference enables the called method to replace the object to which the reference parameter refers in the caller.</span></span> <span data-ttu-id="b5de0-138">La ubicación de almacenamiento del objeto se pasa al método como el valor del parámetro de referencia.</span><span class="sxs-lookup"><span data-stu-id="b5de0-138">The storage location of the object is passed to the method as the value of the reference parameter.</span></span> <span data-ttu-id="b5de0-139">Si cambia el valor de la ubicación de almacenamiento del parámetro (para que apunte a un nuevo objeto), también debe cambiar la ubicación de almacenamiento a la que se refiere el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b5de0-139">If you change the value in the storage location of the parameter (to point to a new object), you also change the storage location to which the caller refers.</span></span> <span data-ttu-id="b5de0-140">En el ejemplo siguiente se pasa una instancia de un tipo de referencia como un parámetro `ref`.</span><span class="sxs-lookup"><span data-stu-id="b5de0-140">The following example passes an instance of a reference type as a `ref` parameter.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#3)]

<span data-ttu-id="b5de0-141">Para obtener más información sobre cómo pasar tipos de referencia por valor y por referencia, vea [Pasar parámetros Reference-Type ](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="b5de0-141">For more information about how to pass reference types by value and by reference, see [Passing Reference-Type Parameters](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span></span>
  
## <a name="reference-return-values"></a><span data-ttu-id="b5de0-142">Valores devueltos de referencia</span><span class="sxs-lookup"><span data-stu-id="b5de0-142">Reference return values</span></span>

<span data-ttu-id="b5de0-143">Los valores devueltos de referencia (o valores devueltos de tipo ref) son valores que devuelve un método mediante referencia al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b5de0-143">Reference return values (or ref returns) are values that a method returns by reference to the caller.</span></span> <span data-ttu-id="b5de0-144">Es decir, el autor de la llamada puede modificar el valor devuelto por un método, y ese cambio se refleja en el estado del objeto que contiene el método.</span><span class="sxs-lookup"><span data-stu-id="b5de0-144">That is, the caller can modify the value returned by a method, and that change is reflected in the state of the object that contains the method.</span></span>

<span data-ttu-id="b5de0-145">Un valor devuelto de referencia se define mediante la palabra clave `ref`:</span><span class="sxs-lookup"><span data-stu-id="b5de0-145">A reference return value is defined by using the `ref` keyword:</span></span>

- <span data-ttu-id="b5de0-146">En la firma del método.</span><span class="sxs-lookup"><span data-stu-id="b5de0-146">In the method signature.</span></span> <span data-ttu-id="b5de0-147">Por ejemplo, en la firma de método siguiente se indica que el método `GetCurrentPrice` devuelve un valor <xref:System.Decimal> por referencia.</span><span class="sxs-lookup"><span data-stu-id="b5de0-147">For example, the following method signature indicates that the `GetCurrentPrice` method returns a <xref:System.Decimal> value by reference.</span></span>

```csharp
public ref decimal GetCurrentPrice()
```

- <span data-ttu-id="b5de0-148">Entre el token `return` y la variable devuelta en una instrucción `return` en el método.</span><span class="sxs-lookup"><span data-stu-id="b5de0-148">Between the `return` token and the variable returned in a `return` statement in the method.</span></span> <span data-ttu-id="b5de0-149">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b5de0-149">For example:</span></span>

```csharp
return ref DecimalArray[0];
```

<span data-ttu-id="b5de0-150">Para que el autor de la llamada modifique el estado del objeto, el valor devuelto de referencia debe almacenarse en una variable que se defina explícitamente como una [variable local de tipo ref](#ref-locals).</span><span class="sxs-lookup"><span data-stu-id="b5de0-150">In order for the caller to modify the object's state, the reference return value must be stored to a variable that is explicitly defined as a [ref local](#ref-locals).</span></span>

<span data-ttu-id="b5de0-151">El método llamado también puede declarar el valor devuelto como `ref readonly` para devolver el valor por referencia y exigir que el código de llamada no pueda modificar el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="b5de0-151">The called method may also declare the return value as `ref readonly` to return the value by reference, and enforce that the calling code cannot modify the returned value.</span></span> <span data-ttu-id="b5de0-152">El método de llamada puede evitar copiar el valor devuelto mediante el almacenamiento del valor en una variable de tipo [ref readonly](#ref-readonly-locals).</span><span class="sxs-lookup"><span data-stu-id="b5de0-152">The calling method can avoid copying the returned valued by storing the value in a local [ref readonly](#ref-readonly-locals) variable.</span></span>

<span data-ttu-id="b5de0-153">Para obtener un ejemplo, vea [Un ejemplo de valores devueltos y variables locales de tipo ref](#a-ref-returns-and-ref-locals-example).</span><span class="sxs-lookup"><span data-stu-id="b5de0-153">For an example, see [A ref returns and ref locals example](#a-ref-returns-and-ref-locals-example).</span></span>

## <a name="ref-locals"></a><span data-ttu-id="b5de0-154">Variables locales de tipo ref</span><span class="sxs-lookup"><span data-stu-id="b5de0-154">Ref locals</span></span>

<span data-ttu-id="b5de0-155">Una variable local de tipo ref se usa para hacer referencia a valores devueltos con `return ref`.</span><span class="sxs-lookup"><span data-stu-id="b5de0-155">A ref local variable is used to refer to values returned using `return ref`.</span></span> <span data-ttu-id="b5de0-156">Una variable local de tipo ref no se puede inicializar en un valor devuelto de tipo no ref.</span><span class="sxs-lookup"><span data-stu-id="b5de0-156">A ref local variable cannot be initialized to a non-ref return value.</span></span> <span data-ttu-id="b5de0-157">Es decir, el lado derecho de la inicialización debe ser una referencia.</span><span class="sxs-lookup"><span data-stu-id="b5de0-157">In other words, the right hand side of the initialization must be a reference.</span></span> <span data-ttu-id="b5de0-158">Cualquier modificación en el valor de la variable local de tipo ref se refleja en el estado del objeto cuyo método ha devuelto el valor mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="b5de0-158">Any modifications to the value of the ref local are reflected in the state of the object whose method returned the value by reference.</span></span>

<span data-ttu-id="b5de0-159">Defina una variable local de tipo ref mediante la palabra clave `ref` antes de la declaración de variable, así como inmediatamente antes de la llamada al método que devuelve el valor mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="b5de0-159">You define a ref local by using the `ref` keyword before the variable declaration, as well as immediately before the call to the method that returns the value by reference.</span></span>

<span data-ttu-id="b5de0-160">Por ejemplo, en la siguiente instrucción se define un valor de variable local de tipo ref que se devuelve mediante un método denominado `GetEstimatedValue`:</span><span class="sxs-lookup"><span data-stu-id="b5de0-160">For example, the following statement defines a ref local value that is returned by a method named `GetEstimatedValue`:</span></span>

```csharp
ref decimal estValue = ref Building.GetEstimatedValue();
```

<span data-ttu-id="b5de0-161">Puede acceder a un valor por referencia de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="b5de0-161">You can access a value by reference in the same way.</span></span> <span data-ttu-id="b5de0-162">En algunos casos, acceder a un valor por referencia aumenta el rendimiento, ya que evita una operación de copia potencialmente cara.</span><span class="sxs-lookup"><span data-stu-id="b5de0-162">In some cases, accessing a value by reference increases performance by avoiding a potentially expensive copy operation.</span></span> <span data-ttu-id="b5de0-163">Por ejemplo, en la instrucción siguiente se muestra cómo es posible definir un valor local de referencia que se usa para hacer referencia a un valor.</span><span class="sxs-lookup"><span data-stu-id="b5de0-163">For example, the following statement shows how one can define a ref local value that is used to reference a value.</span></span>

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct;
```

<span data-ttu-id="b5de0-164">Tenga en cuenta que en ambos ejemplos la palabra clave `ref` debe usarse en ambos lugares. De lo contrario, el compilador genera el error CS8172, "No se puede inicializar una variable por referencia con un valor".</span><span class="sxs-lookup"><span data-stu-id="b5de0-164">Note that in both examples the `ref` keyword must be used in both places, or the compiler generates error CS8172, "Cannot initialize a by-reference variable with a value."</span></span>

<span data-ttu-id="b5de0-165">A partir C# 7.3, la variable de iteración de la instrucción `foreach` puede ser una variable ref local o ref readonly local.</span><span class="sxs-lookup"><span data-stu-id="b5de0-165">Beginning with C# 7.3, the iteration variable of the `foreach` statement can be ref local or ref readonly local variable.</span></span> <span data-ttu-id="b5de0-166">Para más información, vea el artículo sobre la [instrucción foreach](foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="b5de0-166">For more information, see the [foreach statement](foreach-in.md) article.</span></span>

## <a name="ref-readonly-locals"></a><span data-ttu-id="b5de0-167">Variables locales de tipo ref readonly</span><span class="sxs-lookup"><span data-stu-id="b5de0-167">Ref readonly locals</span></span>

<span data-ttu-id="b5de0-168">Una variable local de tipo ref readonly se usa para hacer referencia a los valores devueltos por el método o la propiedad que tiene `ref readonly` en su firma y utiliza `return ref`.</span><span class="sxs-lookup"><span data-stu-id="b5de0-168">A ref readonly local is used to refer to values returned by the method or property that has `ref readonly` in its signature and uses `return ref`.</span></span> <span data-ttu-id="b5de0-169">Una variable `ref readonly` combina las propiedades de una `ref` variable local con una variable `readonly`: es un alias para el almacenamiento al que se asigna y no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="b5de0-169">A `ref readonly` variable combines the properties of a `ref` local variable with a `readonly` variable: it is an alias to the storage it's assigned to, and it cannot be modified.</span></span> 

## <a name="a-ref-returns-and-ref-locals-example"></a><span data-ttu-id="b5de0-170">Un ejemplo de valores devueltos y variables locales de tipo ref</span><span class="sxs-lookup"><span data-stu-id="b5de0-170">A ref returns and ref locals example</span></span>

<span data-ttu-id="b5de0-171">En el ejemplo siguiente se define una clase `Book` que tiene dos campos <xref:System.String>, `Title` y `Author`.</span><span class="sxs-lookup"><span data-stu-id="b5de0-171">The following example defines a `Book` class that has two <xref:System.String> fields, `Title` and `Author`.</span></span> <span data-ttu-id="b5de0-172">También define una clase `BookCollection` que incluye una matriz privada de objetos `Book`.</span><span class="sxs-lookup"><span data-stu-id="b5de0-172">It also defines a `BookCollection` class that includes a private array of `Book` objects.</span></span> <span data-ttu-id="b5de0-173">Los objetos book individuales se devuelven mediante referencia llamando a su método `GetBookByTitle`.</span><span class="sxs-lookup"><span data-stu-id="b5de0-173">Individual book objects are returned by reference by calling its `GetBookByTitle` method.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#4)]

<span data-ttu-id="b5de0-174">Cuando el autor de la llamada almacena el valor devuelto mediante el método `GetBookByTitle` como una variable local de tipo ref, los cambios que el autor de la llamada realiza en el valor devuelto se reflejan en el objeto `BookCollection`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b5de0-174">When the caller stores the value returned by the `GetBookByTitle` method as a ref local, changes that the caller makes to the return value are reflected in the `BookCollection` object, as the following example shows.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#5)]

## <a name="ref-struct-types"></a><span data-ttu-id="b5de0-175">Tipos de estructura de referencia</span><span class="sxs-lookup"><span data-stu-id="b5de0-175">Ref struct types</span></span>

<span data-ttu-id="b5de0-176">La incorporación del modificador `ref` a una declaración `struct` define que las instancias de ese tipo se deben asignar a la pila.</span><span class="sxs-lookup"><span data-stu-id="b5de0-176">Adding the `ref` modifier to a `struct` declaration defines that instances of that type must be stack allocated.</span></span> <span data-ttu-id="b5de0-177">En otras palabras, las instancias de estos tipos no se pueden crear nunca en el montón como un miembro de otra clase.</span><span class="sxs-lookup"><span data-stu-id="b5de0-177">In other words, instances of these types can never be created on the heap as a member of another class.</span></span> <span data-ttu-id="b5de0-178">La principal motivación para esta característica era <xref:System.Span%601> y las estructuras relacionadas.</span><span class="sxs-lookup"><span data-stu-id="b5de0-178">The primary motivation for this feature was <xref:System.Span%601> and related structures.</span></span>

<span data-ttu-id="b5de0-179">El objetivo de mantener un tipo `ref struct` como una variable asignada a la pila presenta varias reglas que el compilador exige para todos los tipos `ref struct`.</span><span class="sxs-lookup"><span data-stu-id="b5de0-179">The goal of keeping a `ref struct` type as a stack-allocated variable introduces several rules that the compiler enforces for all `ref struct` types.</span></span>

- <span data-ttu-id="b5de0-180">No puede encerrar un valor de `ref struct`.</span><span class="sxs-lookup"><span data-stu-id="b5de0-180">You can't box a `ref struct`.</span></span> <span data-ttu-id="b5de0-181">No puede asignar un tipo `ref struct` a una variable de tipo `object`, `dynamic` o cualquier tipo de interfaz.</span><span class="sxs-lookup"><span data-stu-id="b5de0-181">You cannot assign a `ref struct` type to a variable of type `object`, `dynamic`, or any interface type.</span></span>
- <span data-ttu-id="b5de0-182">Los tipos `ref struct` no pueden implementar interfaces.</span><span class="sxs-lookup"><span data-stu-id="b5de0-182">`ref struct` types cannot implement interfaces.</span></span>
- <span data-ttu-id="b5de0-183">No puede declarar un `ref struct` como miembro de una clase o una estructura normal.</span><span class="sxs-lookup"><span data-stu-id="b5de0-183">You can't declare a `ref struct` as a member of a class or a normal struct.</span></span>
- <span data-ttu-id="b5de0-184">No puede declarar variables locales que sean tipos `ref struct` en métodos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="b5de0-184">You cannot declare local variables that are `ref struct` types in async methods.</span></span> <span data-ttu-id="b5de0-185">Puede declararlas en los métodos sincrónicos que devuelven tipos similares a <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601> o `Task`.</span><span class="sxs-lookup"><span data-stu-id="b5de0-185">You can declare them in synchronous methods that return <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601> or `Task`-like types.</span></span>
- <span data-ttu-id="b5de0-186">No puede declarar las variables locales de `ref struct` en iteradores.</span><span class="sxs-lookup"><span data-stu-id="b5de0-186">You cannot declare `ref struct` local variables in iterators.</span></span>
- <span data-ttu-id="b5de0-187">No puede capturar variables `ref struct` en expresiones lambda o funciones locales.</span><span class="sxs-lookup"><span data-stu-id="b5de0-187">You cannot capture `ref struct` variables in lambda expressions or local functions.</span></span>

<span data-ttu-id="b5de0-188">Estas restricciones aseguran que no se usará por error un valor `ref struct` de manera que pueda promoverlo al montón administrado.</span><span class="sxs-lookup"><span data-stu-id="b5de0-188">These restrictions ensure you don't accidentally use a `ref struct` in a manner that could promote it to the managed heap.</span></span>

<span data-ttu-id="b5de0-189">Puede combinar modificadores para declarar una estructura como `readonly ref`.</span><span class="sxs-lookup"><span data-stu-id="b5de0-189">You can combine modifiers to declare a struct as `readonly ref`.</span></span> <span data-ttu-id="b5de0-190">`readonly ref struct` combina las ventajas y las restricciones de las declaraciones `ref struct` y `readonly struct`.</span><span class="sxs-lookup"><span data-stu-id="b5de0-190">A `readonly ref struct` combines the benefits and restrictions of `ref struct` and `readonly struct` declarations.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b5de0-191">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="b5de0-191">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b5de0-192">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5de0-192">See also</span></span>

- [<span data-ttu-id="b5de0-193">Escritura de código seguro y eficaz</span><span class="sxs-lookup"><span data-stu-id="b5de0-193">Write safe efficient code</span></span>](../../write-safe-efficient-code.md)  
- [<span data-ttu-id="b5de0-194">Devoluciones y variables locales ref</span><span class="sxs-lookup"><span data-stu-id="b5de0-194">Ref returns and ref locals</span></span>](../../programming-guide/classes-and-structs/ref-returns.md)
- [<span data-ttu-id="b5de0-195">Expresión condicional ref</span><span class="sxs-lookup"><span data-stu-id="b5de0-195">Conditional ref expression</span></span>](../operators/conditional-operator.md#conditional-ref-expression)
- [<span data-ttu-id="b5de0-196">Operador de asignación ref</span><span class="sxs-lookup"><span data-stu-id="b5de0-196">ref assignment operator</span></span>](../operators/assignment-operator.md#ref-assignment-operator)
- [<span data-ttu-id="b5de0-197">Pasar parámetros</span><span class="sxs-lookup"><span data-stu-id="b5de0-197">Passing Parameters</span></span>](../../programming-guide/classes-and-structs/passing-parameters.md)  
- [<span data-ttu-id="b5de0-198">Parámetros de métodos</span><span class="sxs-lookup"><span data-stu-id="b5de0-198">Method Parameters</span></span>](method-parameters.md)  
- [<span data-ttu-id="b5de0-199">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="b5de0-199">C# Reference</span></span>](../index.md)  
- [<span data-ttu-id="b5de0-200">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="b5de0-200">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="b5de0-201">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="b5de0-201">C# Keywords</span></span>](index.md)

---
title: ref (palabra clave) - Referencia de C#
ms.date: 04/21/2020
f1_keywords:
- ref_CSharpKeyword
- ref
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
ms.openlocfilehash: 07e1b49605c83908f7b9af25e0cb2599a97257c5
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102078"
---
# <a name="ref-c-reference"></a><span data-ttu-id="033f8-102">ref (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="033f8-102">ref (C# Reference)</span></span>

<span data-ttu-id="033f8-103">La palabra clave `ref` indica un valor que se ha pasado mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="033f8-103">The `ref` keyword indicates a value that is passed by reference.</span></span> <span data-ttu-id="033f8-104">Se usa en cuatro contextos diferentes:</span><span class="sxs-lookup"><span data-stu-id="033f8-104">It is used in four different contexts:</span></span>

- <span data-ttu-id="033f8-105">En una firma del método y en una llamada al método, para pasar un argumento a un método mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="033f8-105">In a method signature and in a method call, to pass an argument to a method by reference.</span></span> <span data-ttu-id="033f8-106">Para más información, vea [Pasar un argumento mediante referencia](#passing-an-argument-by-reference).</span><span class="sxs-lookup"><span data-stu-id="033f8-106">For more information, see [Passing an argument by reference](#passing-an-argument-by-reference).</span></span>
- <span data-ttu-id="033f8-107">En una firma del método, para devolver un valor al autor de la llamada mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="033f8-107">In a method signature, to return a value to the caller by reference.</span></span> <span data-ttu-id="033f8-108">Para obtener más información, consulte [Valores devueltos de referencia](#reference-return-values).</span><span class="sxs-lookup"><span data-stu-id="033f8-108">For more information, see [Reference return values](#reference-return-values).</span></span>
- <span data-ttu-id="033f8-109">En un cuerpo de miembro, para indicar que un valor devuelto de referencia se almacena localmente como una referencia que el autor de la llamada pretende modificar o, en general, que una variable local accede a otro valor por referencia.</span><span class="sxs-lookup"><span data-stu-id="033f8-109">In a member body, to indicate that a reference return value is stored locally as a reference that the caller intends to modify or, in general, a local variable accesses another value by reference.</span></span> <span data-ttu-id="033f8-110">Para más información, vea [Variables locales de tipo ref](#ref-locals).</span><span class="sxs-lookup"><span data-stu-id="033f8-110">For more information, see [Ref locals](#ref-locals).</span></span>
- <span data-ttu-id="033f8-111">En una declaración `struct` para declarar `ref struct` o `readonly ref struct`.</span><span class="sxs-lookup"><span data-stu-id="033f8-111">In a `struct` declaration to declare a `ref struct` or a `readonly ref struct`.</span></span> <span data-ttu-id="033f8-112">Para obtener más información, vea la sección [ struct `ref`](../builtin-types/struct.md#ref-struct) del artículo [tipos de estructura](../builtin-types/struct.md).</span><span class="sxs-lookup"><span data-stu-id="033f8-112">For more information, see the [`ref` struct](../builtin-types/struct.md#ref-struct) section of the [Structure types](../builtin-types/struct.md) article.</span></span>

## <a name="passing-an-argument-by-reference"></a><span data-ttu-id="033f8-113">Pasar un argumento mediante referencia</span><span class="sxs-lookup"><span data-stu-id="033f8-113">Passing an argument by reference</span></span>

<span data-ttu-id="033f8-114">Cuando se usa en una lista de parámetros del método, la palabra clave `ref` indica que un argumento se ha pasado mediante referencia, no por valor.</span><span class="sxs-lookup"><span data-stu-id="033f8-114">When used in a method's parameter list, the `ref` keyword indicates that an argument is passed by reference, not by value.</span></span> <span data-ttu-id="033f8-115">La palabra clave `ref` hace que el parámetro formal sea un alias para el argumento, que debe ser una variable.</span><span class="sxs-lookup"><span data-stu-id="033f8-115">The `ref` keyword makes the formal parameter an alias for the argument, which must be a variable.</span></span> <span data-ttu-id="033f8-116">En otras palabras, cualquier operación en el parámetro se realiza en el argumento.</span><span class="sxs-lookup"><span data-stu-id="033f8-116">In other words, any operation on the parameter is made on the argument.</span></span> <span data-ttu-id="033f8-117">Por ejemplo, si el autor de la llamada pasa una expresión de variable local o una expresión de acceso de elemento de matriz, y el método llamado reemplaza el objeto al que hace referencia el parámetro ref, entonces la variable local del autor de la llamada o el elemento de matriz hacen ahora referencia al nuevo objeto cuando el método devuelve resultados.</span><span class="sxs-lookup"><span data-stu-id="033f8-117">For example, if the caller passes a local variable expression or an array element access expression, and the called method replaces the object to which the ref parameter refers, then the caller's local variable or the array element now refers to the new object when the method returns.</span></span>

> [!NOTE]
> <span data-ttu-id="033f8-118">No confunda el concepto de pasar por referencia con el concepto de tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="033f8-118">Do not confuse the concept of passing by reference with the concept of reference types.</span></span> <span data-ttu-id="033f8-119">Estos dos conceptos no son lo mismo.</span><span class="sxs-lookup"><span data-stu-id="033f8-119">The two concepts are not the same.</span></span> <span data-ttu-id="033f8-120">Un parámetro de método puede ser modificado por `ref` independientemente de si se trata de un tipo de valor o de un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="033f8-120">A method parameter can be modified by `ref` regardless of whether it is a value type or a reference type.</span></span> <span data-ttu-id="033f8-121">No hay ninguna conversión boxing de un tipo de valor cuando se pasa por referencia.</span><span class="sxs-lookup"><span data-stu-id="033f8-121">There is no boxing of a value type when it is passed by reference.</span></span>  

<span data-ttu-id="033f8-122">Para usar un parámetro `ref`, la definición de método y el método de llamada deben utilizar explícitamente la palabra clave `ref`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="033f8-122">To use a `ref` parameter, both the method definition and the calling method must explicitly use the `ref` keyword, as shown in the following example.</span></span>  

[!code-csharp-interactive[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#1)]

<span data-ttu-id="033f8-123">Un argumento que se pasa a un parámetro `ref` o `in` debe inicializarse antes de pasarlo.</span><span class="sxs-lookup"><span data-stu-id="033f8-123">An argument that is passed to a `ref` or `in` parameter must be initialized before it is passed.</span></span> <span data-ttu-id="033f8-124">En esto difiere de los parámetros [out](out-parameter-modifier.md), cuyos argumentos no tienen que inicializarse explícitamente antes de pasarlos.</span><span class="sxs-lookup"><span data-stu-id="033f8-124">This differs from [out](out-parameter-modifier.md) parameters, whose arguments do not have to be explicitly initialized before they are passed.</span></span>

<span data-ttu-id="033f8-125">Los miembros de una clase no pueden tener signaturas que se diferencien solo por `ref`, `in` o `out`.</span><span class="sxs-lookup"><span data-stu-id="033f8-125">Members of a class can't have signatures that differ only by `ref`, `in`, or `out`.</span></span> <span data-ttu-id="033f8-126">Si la única diferencia entre dos miembros de un tipo es que uno de ellos tiene un parámetro `ref` y el otro tiene un parámetro `out` o `in`, se produce un error de compilador.</span><span class="sxs-lookup"><span data-stu-id="033f8-126">A compiler error occurs if the only difference between two members of a type is that one of them has a `ref` parameter and the other has an `out`, or `in` parameter.</span></span> <span data-ttu-id="033f8-127">El código siguiente, por ejemplo, no se compila.</span><span class="sxs-lookup"><span data-stu-id="033f8-127">The following code, for example, doesn't compile.</span></span>  

```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```

<span data-ttu-id="033f8-128">En cambio, los métodos pueden sobrecargarse cuando un método tiene un parámetro `ref`, `in` o `out` y el otro tiene un parámetro de valor, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="033f8-128">However, methods can be overloaded when one method has a `ref`, `in`, or `out` parameter and the other has a value parameter, as shown in the following example.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#2)]
  
 <span data-ttu-id="033f8-129">En otras situaciones que requieran firma coincidente, como ocultar o reemplazar, `in`, `ref` y `out` forman parte de la signatura y no coinciden entre sí.</span><span class="sxs-lookup"><span data-stu-id="033f8-129">In other situations that require signature matching, such as hiding or overriding, `in`, `ref`, and `out` are part of the signature and don't match each other.</span></span>  
  
 <span data-ttu-id="033f8-130">Las propiedades no son variables.</span><span class="sxs-lookup"><span data-stu-id="033f8-130">Properties are not variables.</span></span> <span data-ttu-id="033f8-131">Son métodos y no se pueden pasar a parámetros `ref`.</span><span class="sxs-lookup"><span data-stu-id="033f8-131">They are methods, and cannot be passed to `ref` parameters.</span></span>  
  
 <span data-ttu-id="033f8-132">Las palabras clave `ref`, `in` y `out` no pueden usarse para estos tipos de métodos:</span><span class="sxs-lookup"><span data-stu-id="033f8-132">You can't use the `ref`, `in`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="033f8-133">Métodos asincrónicos, que se definen mediante el uso del modificador [async](async.md).</span><span class="sxs-lookup"><span data-stu-id="033f8-133">Async methods, which you define by using the [async](async.md) modifier.</span></span>  
- <span data-ttu-id="033f8-134">Métodos de iterador, que incluyen una instrucción [yield return](yield.md) o `yield break`.</span><span class="sxs-lookup"><span data-stu-id="033f8-134">Iterator methods, which include a [yield return](yield.md) or `yield break` statement.</span></span>

<span data-ttu-id="033f8-135">Además, los [métodos de extensión](../../programming-guide/classes-and-structs/extension-methods.md) tienen las restricciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="033f8-135">In addition, [extension methods](../../programming-guide/classes-and-structs/extension-methods.md) have the following restrictions:</span></span>

- <span data-ttu-id="033f8-136">No se puede usar la palabra clave `out` en el primer argumento de un método de extensión.</span><span class="sxs-lookup"><span data-stu-id="033f8-136">The `out` keyword cannot be used on the first argument of an extension method.</span></span>
- <span data-ttu-id="033f8-137">No se puede usar la palabra clave `ref` en el primer argumento de un método de extensión cuando el argumento no es un struct ni un tipo genérico no restringido a ser un struct.</span><span class="sxs-lookup"><span data-stu-id="033f8-137">The `ref` keyword cannot be used on the first argument of an extension method when the argument is not a struct, or a generic type not constrained to be a struct.</span></span>
- <span data-ttu-id="033f8-138">No se puede usar la palabra clave `in` a menos que el primer argumento sea un struct.</span><span class="sxs-lookup"><span data-stu-id="033f8-138">The `in` keyword cannot be used unless the first argument is a struct.</span></span> <span data-ttu-id="033f8-139">No se puede usar la palabra clave `in` en ningún tipo genérico, incluso cuando está restringido a ser un struct.</span><span class="sxs-lookup"><span data-stu-id="033f8-139">The `in` keyword cannot be used on any generic type, even when constrained to be a struct.</span></span>

## <a name="passing-an-argument-by-reference-an-example"></a><span data-ttu-id="033f8-140">Paso de un argumento mediante referencia: Un ejemplo</span><span class="sxs-lookup"><span data-stu-id="033f8-140">Passing an argument by reference: An example</span></span>

<span data-ttu-id="033f8-141">En los ejemplos anteriores se pasan tipos de valor mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="033f8-141">The previous examples pass value types by reference.</span></span> <span data-ttu-id="033f8-142">También se puede usar la palabra clave `ref` para pasar tipos de referencia mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="033f8-142">You can also use the `ref` keyword to pass reference types by reference.</span></span> <span data-ttu-id="033f8-143">Pasar un tipo de referencia por referencia permite que el método llamado pueda reemplazar el objeto al que hace referencia el parámetro de referencia en el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="033f8-143">Passing a reference type by reference enables the called method to replace the object to which the reference parameter refers in the caller.</span></span> <span data-ttu-id="033f8-144">La ubicación de almacenamiento del objeto se pasa al método como el valor del parámetro de referencia.</span><span class="sxs-lookup"><span data-stu-id="033f8-144">The storage location of the object is passed to the method as the value of the reference parameter.</span></span> <span data-ttu-id="033f8-145">Si cambia el valor de la ubicación de almacenamiento del parámetro (para que apunte a un nuevo objeto), también debe cambiar la ubicación de almacenamiento a la que se refiere el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="033f8-145">If you change the value in the storage location of the parameter (to point to a new object), you also change the storage location to which the caller refers.</span></span> <span data-ttu-id="033f8-146">En el ejemplo siguiente se pasa una instancia de un tipo de referencia como un parámetro `ref`.</span><span class="sxs-lookup"><span data-stu-id="033f8-146">The following example passes an instance of a reference type as a `ref` parameter.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#3)]

<span data-ttu-id="033f8-147">Para obtener más información sobre cómo pasar tipos de referencia por valor y por referencia, vea [Pasar parámetros Reference-Type ](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="033f8-147">For more information about how to pass reference types by value and by reference, see [Passing Reference-Type Parameters](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span></span>
  
## <a name="reference-return-values"></a><span data-ttu-id="033f8-148">Valores devueltos de referencia</span><span class="sxs-lookup"><span data-stu-id="033f8-148">Reference return values</span></span>

<span data-ttu-id="033f8-149">Los valores devueltos de referencia (o valores devueltos de tipo ref) son valores que devuelve un método mediante referencia al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="033f8-149">Reference return values (or ref returns) are values that a method returns by reference to the caller.</span></span> <span data-ttu-id="033f8-150">Es decir, el autor de la llamada puede modificar el valor devuelto por un método, y ese cambio se refleja en el estado del objeto del método de llamada.</span><span class="sxs-lookup"><span data-stu-id="033f8-150">That is, the caller can modify the value returned by a method, and that change is reflected in the state of the object in the calling method.</span></span>

<span data-ttu-id="033f8-151">Un valor devuelto de referencia se define mediante la palabra clave `ref`:</span><span class="sxs-lookup"><span data-stu-id="033f8-151">A reference return value is defined by using the `ref` keyword:</span></span>

- <span data-ttu-id="033f8-152">En la firma del método.</span><span class="sxs-lookup"><span data-stu-id="033f8-152">In the method signature.</span></span> <span data-ttu-id="033f8-153">Por ejemplo, en la firma de método siguiente se indica que el método `GetCurrentPrice` devuelve un valor <xref:System.Decimal> por referencia.</span><span class="sxs-lookup"><span data-stu-id="033f8-153">For example, the following method signature indicates that the `GetCurrentPrice` method returns a <xref:System.Decimal> value by reference.</span></span>

```csharp
public ref decimal GetCurrentPrice()
```

- <span data-ttu-id="033f8-154">Entre el token `return` y la variable devuelta en una instrucción `return` en el método.</span><span class="sxs-lookup"><span data-stu-id="033f8-154">Between the `return` token and the variable returned in a `return` statement in the method.</span></span> <span data-ttu-id="033f8-155">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="033f8-155">For example:</span></span>

```csharp
return ref DecimalArray[0];
```

<span data-ttu-id="033f8-156">Para que el autor de la llamada modifique el estado del objeto, el valor devuelto de referencia debe almacenarse en una variable que se defina explícitamente como una [variable local de tipo ref](#ref-locals).</span><span class="sxs-lookup"><span data-stu-id="033f8-156">In order for the caller to modify the object's state, the reference return value must be stored to a variable that is explicitly defined as a [ref local](#ref-locals).</span></span>

<span data-ttu-id="033f8-157">Este es un ejemplo de valor devuelto de referencia más completo que muestra la firma y el cuerpo del método.</span><span class="sxs-lookup"><span data-stu-id="033f8-157">Here is a more complete ref return example, showing both the method signature and method body.</span></span>

[!code-csharp[FindReturningRef](~/samples/snippets/csharp/new-in-7/MatrixSearch.cs#FindReturningRef "Find returning by reference")]

<span data-ttu-id="033f8-158">El método llamado también puede declarar el valor devuelto como `ref readonly` para devolver el valor por referencia y exigir que el código de llamada no pueda modificar el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="033f8-158">The called method may also declare the return value as `ref readonly` to return the value by reference, and enforce that the calling code cannot modify the returned value.</span></span> <span data-ttu-id="033f8-159">El método de llamada puede evitar copiar el valor devuelto mediante el almacenamiento del valor en una variable de tipo [ref readonly](#ref-readonly-locals).</span><span class="sxs-lookup"><span data-stu-id="033f8-159">The calling method can avoid copying the returned valued by storing the value in a local [ref readonly](#ref-readonly-locals) variable.</span></span>

<span data-ttu-id="033f8-160">Para obtener un ejemplo, vea [Un ejemplo de valores devueltos y variables locales de tipo ref](#a-ref-returns-and-ref-locals-example).</span><span class="sxs-lookup"><span data-stu-id="033f8-160">For an example, see [A ref returns and ref locals example](#a-ref-returns-and-ref-locals-example).</span></span>

## <a name="ref-locals"></a><span data-ttu-id="033f8-161">Variables locales de tipo ref</span><span class="sxs-lookup"><span data-stu-id="033f8-161">Ref locals</span></span>

<span data-ttu-id="033f8-162">Una variable local de tipo ref se usa para hacer referencia a valores devueltos con `return ref`.</span><span class="sxs-lookup"><span data-stu-id="033f8-162">A ref local variable is used to refer to values returned using `return ref`.</span></span> <span data-ttu-id="033f8-163">Una variable local de tipo ref no se puede inicializar en un valor devuelto de tipo no ref.</span><span class="sxs-lookup"><span data-stu-id="033f8-163">A ref local variable cannot be initialized to a non-ref return value.</span></span> <span data-ttu-id="033f8-164">Es decir, el lado derecho de la inicialización debe ser una referencia.</span><span class="sxs-lookup"><span data-stu-id="033f8-164">In other words, the right-hand side of the initialization must be a reference.</span></span> <span data-ttu-id="033f8-165">Cualquier modificación en el valor de la variable local de tipo ref se refleja en el estado del objeto cuyo método ha devuelto el valor mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="033f8-165">Any modifications to the value of the ref local are reflected in the state of the object whose method returned the value by reference.</span></span>

<span data-ttu-id="033f8-166">Defina una variable local de tipo ref mediante la palabra clave `ref` antes de la declaración de variable, así como inmediatamente antes de la llamada al método que devuelve el valor mediante referencia.</span><span class="sxs-lookup"><span data-stu-id="033f8-166">You define a ref local by using the `ref` keyword before the variable declaration, as well as immediately before the call to the method that returns the value by reference.</span></span>

<span data-ttu-id="033f8-167">Por ejemplo, en la siguiente instrucción se define un valor de variable local de tipo ref que se devuelve mediante un método denominado `GetEstimatedValue`:</span><span class="sxs-lookup"><span data-stu-id="033f8-167">For example, the following statement defines a ref local value that is returned by a method named `GetEstimatedValue`:</span></span>

```csharp
ref decimal estValue = ref Building.GetEstimatedValue();
```

<span data-ttu-id="033f8-168">Puede acceder a un valor por referencia de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="033f8-168">You can access a value by reference in the same way.</span></span> <span data-ttu-id="033f8-169">En algunos casos, acceder a un valor por referencia aumenta el rendimiento, ya que evita una operación de copia potencialmente cara.</span><span class="sxs-lookup"><span data-stu-id="033f8-169">In some cases, accessing a value by reference increases performance by avoiding a potentially expensive copy operation.</span></span> <span data-ttu-id="033f8-170">Por ejemplo, en la instrucción siguiente se muestra cómo es posible definir un valor local de referencia que se usa para hacer referencia a un valor.</span><span class="sxs-lookup"><span data-stu-id="033f8-170">For example, the following statement shows how one can define a ref local value that is used to reference a value.</span></span>

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct;
```

<span data-ttu-id="033f8-171">En ambos ejemplos la palabra clave `ref` debe usarse en ambos lugares. De lo contrario, el compilador genera el error CS8172, "No se puede inicializar una variable por referencia con un valor".</span><span class="sxs-lookup"><span data-stu-id="033f8-171">In both examples the `ref` keyword must be used in both places, or the compiler generates error CS8172, "Cannot initialize a by-reference variable with a value."</span></span>

<span data-ttu-id="033f8-172">A partir C# 7.3, la variable de iteración de la instrucción `foreach` puede ser una variable ref local o ref readonly local.</span><span class="sxs-lookup"><span data-stu-id="033f8-172">Beginning with C# 7.3, the iteration variable of the `foreach` statement can be ref local or ref readonly local variable.</span></span> <span data-ttu-id="033f8-173">Para más información, vea el artículo sobre la [instrucción foreach](foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="033f8-173">For more information, see the [foreach statement](foreach-in.md) article.</span></span>

<span data-ttu-id="033f8-174">A partir C# 7.3, las variables locales de tipo ref o locales de tipo ref readonly se pueden reasignar con el [operador de asignación ref](../operators/assignment-operator.md#ref-assignment-operator).</span><span class="sxs-lookup"><span data-stu-id="033f8-174">Also beginning with C# 7.3, you can reassign a ref local or ref readonly local variable with the [ref assignment operator](../operators/assignment-operator.md#ref-assignment-operator).</span></span>

## <a name="ref-readonly-locals"></a><span data-ttu-id="033f8-175">Variables locales de tipo ref readonly</span><span class="sxs-lookup"><span data-stu-id="033f8-175">Ref readonly locals</span></span>

<span data-ttu-id="033f8-176">Una variable local de tipo ref readonly se usa para hacer referencia a los valores devueltos por el método o la propiedad que tiene `ref readonly` en su firma y utiliza `return ref`.</span><span class="sxs-lookup"><span data-stu-id="033f8-176">A ref readonly local is used to refer to values returned by the method or property that has `ref readonly` in its signature and uses `return ref`.</span></span> <span data-ttu-id="033f8-177">Una variable `ref readonly` combina las propiedades de una `ref` variable local con una variable `readonly`: es un alias para el almacenamiento al que se asigna y no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="033f8-177">A `ref readonly` variable combines the properties of a `ref` local variable with a `readonly` variable: it is an alias to the storage it's assigned to, and it cannot be modified.</span></span>

## <a name="a-ref-returns-and-ref-locals-example"></a><span data-ttu-id="033f8-178">Un ejemplo de valores devueltos y variables locales de tipo ref</span><span class="sxs-lookup"><span data-stu-id="033f8-178">A ref returns and ref locals example</span></span>

<span data-ttu-id="033f8-179">En el ejemplo siguiente se define una clase `Book` que tiene dos campos <xref:System.String>, `Title` y `Author`.</span><span class="sxs-lookup"><span data-stu-id="033f8-179">The following example defines a `Book` class that has two <xref:System.String> fields, `Title` and `Author`.</span></span> <span data-ttu-id="033f8-180">También define una clase `BookCollection` que incluye una matriz privada de objetos `Book`.</span><span class="sxs-lookup"><span data-stu-id="033f8-180">It also defines a `BookCollection` class that includes a private array of `Book` objects.</span></span> <span data-ttu-id="033f8-181">Los objetos book individuales se devuelven mediante referencia llamando a su método `GetBookByTitle`.</span><span class="sxs-lookup"><span data-stu-id="033f8-181">Individual book objects are returned by reference by calling its `GetBookByTitle` method.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#4)]

<span data-ttu-id="033f8-182">Cuando el autor de la llamada almacena el valor devuelto mediante el método `GetBookByTitle` como una variable local de tipo ref, los cambios que el autor de la llamada realiza en el valor devuelto se reflejan en el objeto `BookCollection`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="033f8-182">When the caller stores the value returned by the `GetBookByTitle` method as a ref local, changes that the caller makes to the return value are reflected in the `BookCollection` object, as the following example shows.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="033f8-183">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="033f8-183">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="033f8-184">Vea también</span><span class="sxs-lookup"><span data-stu-id="033f8-184">See also</span></span>

- [<span data-ttu-id="033f8-185">Escritura de código seguro y eficaz</span><span class="sxs-lookup"><span data-stu-id="033f8-185">Write safe efficient code</span></span>](../../write-safe-efficient-code.md)
- [<span data-ttu-id="033f8-186">Devoluciones y variables locales ref</span><span class="sxs-lookup"><span data-stu-id="033f8-186">Ref returns and ref locals</span></span>](../../programming-guide/classes-and-structs/ref-returns.md)
- [<span data-ttu-id="033f8-187">Expresión condicional ref</span><span class="sxs-lookup"><span data-stu-id="033f8-187">Conditional ref expression</span></span>](../operators/conditional-operator.md#conditional-ref-expression)
- [<span data-ttu-id="033f8-188">Pasar parámetros</span><span class="sxs-lookup"><span data-stu-id="033f8-188">Passing Parameters</span></span>](../../programming-guide/classes-and-structs/passing-parameters.md)
- [<span data-ttu-id="033f8-189">Parámetros de métodos</span><span class="sxs-lookup"><span data-stu-id="033f8-189">Method Parameters</span></span>](method-parameters.md)
- [<span data-ttu-id="033f8-190">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="033f8-190">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="033f8-191">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="033f8-191">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="033f8-192">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="033f8-192">C# Keywords</span></span>](index.md)

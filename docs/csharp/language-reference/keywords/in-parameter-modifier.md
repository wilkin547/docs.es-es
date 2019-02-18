---
title: 'Modificador del parámetro in: Referencia de C#'
ms.custom: seodec18
ms.date: 02/12/2019
helpviewer_keywords:
- parameters [C#], in
- in parameters [C#]
ms.openlocfilehash: 5a765a330e4d9efe22943538503c0822e1c9dfdb
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219560"
---
# <a name="in-parameter-modifier-c-reference"></a><span data-ttu-id="a26ec-102">Modificador del parámetro in (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="a26ec-102">in parameter modifier (C# Reference)</span></span>

<span data-ttu-id="a26ec-103">La palabra clave `in` hace que los argumentos se pasen por referencia.</span><span class="sxs-lookup"><span data-stu-id="a26ec-103">The `in` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="a26ec-104">Es como las palabras clave [ref](ref.md) o [out](out-parameter-modifier.md), salvo que el método al que se llama no puede modificar los argumentos `in`.</span><span class="sxs-lookup"><span data-stu-id="a26ec-104">It is like the [ref](ref.md) or [out](out-parameter-modifier.md) keywords, except that `in` arguments cannot be modified by the called method.</span></span> <span data-ttu-id="a26ec-105">Mientras que los argumentos `ref` se pueden modificar, el método llamado debe modificar los argumentos `out` y esas modificaciones se pueden observar en el contexto de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a26ec-105">Whereas `ref` arguments may be modified,  `out` arguments must be modified by the called method, and those modifications are observable in the calling context.</span></span>

[!code-csharp-interactive[cs-in-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/InParameterModifier.cs#1)]  

<span data-ttu-id="a26ec-106">En el ejemplo anterior se muestra que el modificador `in` no suele ser necesario en el sitio de llamada,</span><span class="sxs-lookup"><span data-stu-id="a26ec-106">The preceding example demonstrates that the `in` modifier is usually unnecessary at the call site.</span></span> <span data-ttu-id="a26ec-107">sino que solo lo es en la declaración del método.</span><span class="sxs-lookup"><span data-stu-id="a26ec-107">It is only required in the method declaration.</span></span>


> [!NOTE] 
> <span data-ttu-id="a26ec-108">Además, la palabra clave `in` puede usarse con un parámetro de tipo genérico para especificar que el parámetro de tipo es contravariante, parte de una instrucción `foreach` o de una cláusula `join` de una consulta de LINQ.</span><span class="sxs-lookup"><span data-stu-id="a26ec-108">The `in` keyword can also be used with a generic type parameter to specify that the type parameter is contravariant, as part of a `foreach` statement, or as part of a `join` clause in a LINQ query.</span></span> <span data-ttu-id="a26ec-109">Para más información sobre el uso de la palabra clave `in` en esos contextos, vea [in](in.md), que además incluye vínculos a todos estos usos.</span><span class="sxs-lookup"><span data-stu-id="a26ec-109">For more information on the use of the `in` keyword in these contexts, see [in](in.md), which provides links to all those uses.</span></span>
  
 <span data-ttu-id="a26ec-110">Las variables que se han pasado como argumentos `in` deben inicializarse antes de pasarse en una llamada de método.</span><span class="sxs-lookup"><span data-stu-id="a26ec-110">Variables passed as `in` arguments must be initialized before being passed in a method call.</span></span> <span data-ttu-id="a26ec-111">Sin embargo, es posible que el método llamado no asigne ningún valor o modifique el argumento.</span><span class="sxs-lookup"><span data-stu-id="a26ec-111">However, the called method may not assign a value or modify the argument.</span></span>  

<span data-ttu-id="a26ec-112">El modificador de parámetro `in` está disponible en C# 7.2 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="a26ec-112">The `in` parameter modifier is available in C# 7.2 and later.</span></span> <span data-ttu-id="a26ec-113">Las versiones anteriores generan el error del compilador `CS8107` ("Feature 'readonly references' is not available in C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="a26ec-113">Previous versions generate compiler error `CS8107` ("Feature 'readonly references' is not available in C# 7.0.</span></span> <span data-ttu-id="a26ec-114">Please use language version 7.2 or greater.") (La característica "readonly references" no está disponible en C# 7.0. Use la versión de lenguaje 7.2 o superior"). Para configurar la versión del lenguaje de compilador, vea [Seleccionar la versión del lenguaje C#](../configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="a26ec-114">Please use language version 7.2 or greater.") To configure the compiler language version, see [Select the C# language version](../configure-language-version.md).</span></span>

 <span data-ttu-id="a26ec-115">Aunque las palabras clave `in`, `ref` y `out` causan un comportamiento diferente en tiempo de ejecución, no se consideran parte de la signatura del método en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="a26ec-115">Although the `in`, `ref`, and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="a26ec-116">Por lo tanto, los métodos no pueden sobrecargarse si la única diferencia es que un método toma un argumento `ref` o `in` y el otro toma un argumento `out`.</span><span class="sxs-lookup"><span data-stu-id="a26ec-116">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="a26ec-117">Por ejemplo, el código siguiente, no se compilará:</span><span class="sxs-lookup"><span data-stu-id="a26ec-117">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on in, ref and out".
    public void SampleMethod(in int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="a26ec-118">Está permitida la sobrecarga en función de la presencia de `in`:</span><span class="sxs-lookup"><span data-stu-id="a26ec-118">Overloading based on the presence of `in` is allowed:</span></span>  
  
```csharp
class InOverloads
{
    public void SampleMethod(in int i) { }
    public void SampleMethod(int i) { }
}
```

## <a name="overload-resolution-rules"></a><span data-ttu-id="a26ec-119">Reglas de resolución de sobrecarga</span><span class="sxs-lookup"><span data-stu-id="a26ec-119">Overload resolution rules</span></span>

<span data-ttu-id="a26ec-120">Puede comprender las reglas de resolución de sobrecarga de métodos por valor frente a argumentos `in` mediante la comprensión de la motivación de argumentos `in`.</span><span class="sxs-lookup"><span data-stu-id="a26ec-120">You can understand the overload resolution rules for methods with by value vs. `in` arguments by understanding the motivation for `in` arguments.</span></span> <span data-ttu-id="a26ec-121">Definir métodos usando parámetros `in` es una optimización del rendimiento potencial.</span><span class="sxs-lookup"><span data-stu-id="a26ec-121">Defining methods using `in` parameters is a potential performance optimization.</span></span> <span data-ttu-id="a26ec-122">Algunos argumentos de tipo `struct` pueden tener un gran tamaño y, cuando se llama a métodos en bucles de pequeñas dimensiones o rutas de acceso de código crítico, el costo de copiar esas estructuras resulta crucial.</span><span class="sxs-lookup"><span data-stu-id="a26ec-122">Some `struct` type arguments may be large in size, and when methods are called in tight loops or critical code paths, the cost of copying those structures is critical.</span></span> <span data-ttu-id="a26ec-123">Los métodos declaran parámetros `in` para especificar qué argumentos pueden pasarse por referencia sin ningún riesgo porque el método llamado no modifica el estado de ese argumento.</span><span class="sxs-lookup"><span data-stu-id="a26ec-123">Methods declare `in` parameters to specify that arguments may be passed by reference safely because the called method does not modify the state of that argument.</span></span> <span data-ttu-id="a26ec-124">Al pasar esos argumentos por referencia se evita la copia (potencialmente) costosa.</span><span class="sxs-lookup"><span data-stu-id="a26ec-124">Passing those arguments by reference avoids the (potentially) expensive copy.</span></span> 

<span data-ttu-id="a26ec-125">Especificar `in` en argumentos en el sitio de llamada suele ser opcional.</span><span class="sxs-lookup"><span data-stu-id="a26ec-125">Specifying `in` for arguments at the call site is typically optional.</span></span> <span data-ttu-id="a26ec-126">No hay ninguna diferencia semántica entre pasar argumentos por valor y pasarlos por referencia mediante el modificador `in`.</span><span class="sxs-lookup"><span data-stu-id="a26ec-126">There is no semantic difference between passing arguments by value and passing them by reference using the `in` modifier.</span></span> <span data-ttu-id="a26ec-127">El modificador `in` en el sitio de llamada es opcional porque no es necesario indicar que podría cambiarse el valor del argumento.</span><span class="sxs-lookup"><span data-stu-id="a26ec-127">The `in` modifier at the call site is optional because you don't need to indicate that the argument's value might be changed.</span></span> <span data-ttu-id="a26ec-128">Se agrega explícitamente el modificador `in` en el sitio de llamada para garantizar que el argumento se pasa por referencia, y no por valor.</span><span class="sxs-lookup"><span data-stu-id="a26ec-128">You explicitly add the `in` modifier at the call site to ensure the argument is passed by reference, not by value.</span></span> <span data-ttu-id="a26ec-129">Usar explícitamente `in` tiene los dos efectos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a26ec-129">Explicitly using `in` has the following two effects:</span></span>

<span data-ttu-id="a26ec-130">El primero es que, al especificar `in` en el sitio de llamada, se fuerza al compilador a seleccionar un método definido con un parámetro `in` coincidente.</span><span class="sxs-lookup"><span data-stu-id="a26ec-130">First, specifying `in` at the call site forces the compiler to select a method defined with a matching `in` parameter.</span></span> <span data-ttu-id="a26ec-131">En caso contrario, cuando dos métodos se diferencian solo en presencia de `in`, la sobrecarga por valor es una coincidencia mejor.</span><span class="sxs-lookup"><span data-stu-id="a26ec-131">Otherwise, when two methods differ only in the presence of `in`, the by value overload is a better match.</span></span>

<span data-ttu-id="a26ec-132">El segundo es que, al especificar `in` declara su intención para pasar un argumento por referencia.</span><span class="sxs-lookup"><span data-stu-id="a26ec-132">Second, specifying `in` declares your intent to pass an argument by reference.</span></span> <span data-ttu-id="a26ec-133">Los argumentos usados con `in` deben representar una ubicación a la que se pueda hacer referencia directamente.</span><span class="sxs-lookup"><span data-stu-id="a26ec-133">The argument used with `in` must represent a location that can be directly referred to.</span></span> <span data-ttu-id="a26ec-134">Se aplican las mismas reglas generales para los argumentos `out` y `ref`: no se pueden usar constantes, propiedades normales u otras expresiones que produzcan valores.</span><span class="sxs-lookup"><span data-stu-id="a26ec-134">The same general rules for `out` and `ref` arguments apply: You cannot use constants, ordinary properties, or other expressions that produce values.</span></span> <span data-ttu-id="a26ec-135">En caso contrario, si se omite `in` en el sitio de llamada, se informa al compilador de que le permitirá crear una variable temporal para pasar por referencia de solo lectura para el método.</span><span class="sxs-lookup"><span data-stu-id="a26ec-135">Otherwise, omitting `in` at the call site informs the compiler that you will allow it to create a temporary variable to pass by read-only reference to the method.</span></span> <span data-ttu-id="a26ec-136">El compilador crea una variable temporal para superar varias restricciones con argumentos `in`:</span><span class="sxs-lookup"><span data-stu-id="a26ec-136">The compiler creates a temporary variable to overcome several restrictions with `in` arguments:</span></span>

- <span data-ttu-id="a26ec-137">Una variable temporal permite constantes en tiempo de compilación como parámetros `in`.</span><span class="sxs-lookup"><span data-stu-id="a26ec-137">A temporary variable allows compile-time constants as `in` parameters.</span></span>
- <span data-ttu-id="a26ec-138">Una variable temporal permite propiedades u otras expresiones para parámetros `in`.</span><span class="sxs-lookup"><span data-stu-id="a26ec-138">A temporary variable allows properties, or other expressions for `in` parameters.</span></span>
- <span data-ttu-id="a26ec-139">Una variable temporal permite argumentos en los que hay una conversión implícita desde el tipo de argumento hacia el tipo de parámetro.</span><span class="sxs-lookup"><span data-stu-id="a26ec-139">A temporary variable allows arguments where there is an implicit conversion from the argument type to the parameter type.</span></span>

<span data-ttu-id="a26ec-140">En todas las instancias anteriores, el compilador crea una variable temporal que almacena el valor de la constante, la propiedad u otra expresión.</span><span class="sxs-lookup"><span data-stu-id="a26ec-140">In all the preceding instances, the compiler creates a temporary variable that stores the value of the constant, property, or other expression.</span></span>

<span data-ttu-id="a26ec-141">Estas reglas se muestran en este código:</span><span class="sxs-lookup"><span data-stu-id="a26ec-141">The following code illustrates these rules:</span></span>

```csharp
static void Method(in int argument)
{
    // implementation removed
}

Method(5); // OK, temporary variable created.
Method(5L); // CS1503: no implicit conversion from long to int
short s = 0;
Method(s); // OK, temporary int created with the value 0
Method(in s); // CS1503: cannot convert from in short to in int
int i = 42;
Method(i); // passed by readonly reference
Method(in i); // passed by readonly reference, explicitly using `in`
```

<span data-ttu-id="a26ec-142">Supongamos ahora que hay disponible otro método que usa argumentos por valor.</span><span class="sxs-lookup"><span data-stu-id="a26ec-142">Now, suppose another method using by value arguments was available.</span></span> <span data-ttu-id="a26ec-143">Los resultados cambian como se muestra en este código:</span><span class="sxs-lookup"><span data-stu-id="a26ec-143">The results change as shown in the following code:</span></span>

```csharp
static void Method(int argument)
{
    // implementation removed
}

static void Method(in int argument)
{
    // implementation removed
}

Method(5); // Calls overload passed by value
Method(5L); // CS1503: no implicit conversion from long to int
short s = 0;
Method(s); // Calls overload passed by value.
Method(in s); // CS1503: cannot convert from in short to in int
int i = 42;
Method(i); // Calls overload passed by value
Method(in i); // passed by readonly reference, explicitly using `in`
```

<span data-ttu-id="a26ec-144">La única llamada de método donde se pasa el argumento por referencia es la última.</span><span class="sxs-lookup"><span data-stu-id="a26ec-144">The only method call where the argument is passed by reference is the final one.</span></span>

> [!NOTE]
> <span data-ttu-id="a26ec-145">El código anterior usa `int` como el tipo de argumento para simplificar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="a26ec-145">The preceding code uses `int` as the argument type for simplicity.</span></span> <span data-ttu-id="a26ec-146">Como `int` no es más grande que una referencia en la mayoría de máquinas modernas, no supone ninguna ventaja pasar un único `int` como una referencia de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="a26ec-146">Because `int` is no larger than a reference in most modern machines, there is no benefit to passing a single `int` as a readonly reference.</span></span> 

## <a name="limitations-on-in-parameters"></a><span data-ttu-id="a26ec-147">Limitaciones de los parámetros `in`</span><span class="sxs-lookup"><span data-stu-id="a26ec-147">Limitations on `in` parameters</span></span>

<span data-ttu-id="a26ec-148">Las palabras clave `in`, `ref` y `out` no pueden usarse para estos tipos de métodos:</span><span class="sxs-lookup"><span data-stu-id="a26ec-148">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="a26ec-149">Métodos asincrónicos, que se definen mediante el uso del modificador [async](async.md).</span><span class="sxs-lookup"><span data-stu-id="a26ec-149">Async methods, which you define by using the [async](async.md) modifier.</span></span>  
- <span data-ttu-id="a26ec-150">Métodos de iterador, que incluyen una instrucción [yield return](yield.md) o `yield break`.</span><span class="sxs-lookup"><span data-stu-id="a26ec-150">Iterator methods, which include a [yield return](yield.md) or `yield break` statement.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="a26ec-151">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="a26ec-151">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a26ec-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="a26ec-152">See also</span></span>

- [<span data-ttu-id="a26ec-153">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="a26ec-153">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a26ec-154">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="a26ec-154">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a26ec-155">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="a26ec-155">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a26ec-156">Parámetros de métodos</span><span class="sxs-lookup"><span data-stu-id="a26ec-156">Method Parameters</span></span>](method-parameters.md)
- [<span data-ttu-id="a26ec-157">Escritura de código seguro y eficaz</span><span class="sxs-lookup"><span data-stu-id="a26ec-157">Write safe efficient code</span></span>](../../write-safe-efficient-code.md)

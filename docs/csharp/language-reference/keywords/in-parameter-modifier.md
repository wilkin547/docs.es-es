---
description: 'Modificador del parámetro in: Referencia de C#'
title: 'Modificador del parámetro in: Referencia de C#'
ms.date: 03/19/2020
helpviewer_keywords:
- parameters [C#], in
- in parameters [C#]
ms.openlocfilehash: 171218dcc4904b797b0c9a66b56bcb970607684e
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102104853"
---
# <a name="in-parameter-modifier-c-reference"></a><span data-ttu-id="d7f04-103">Modificador del parámetro in (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="d7f04-103">in parameter modifier (C# Reference)</span></span>

<span data-ttu-id="d7f04-104">La palabra clave `in` hace que los argumentos se pasen por referencia pero garantiza que el argumento no se modifica.</span><span class="sxs-lookup"><span data-stu-id="d7f04-104">The `in` keyword causes arguments to be passed by reference but ensures the argument is not modified.</span></span> <span data-ttu-id="d7f04-105">Hace que el parámetro formal sea un alias para el argumento, que debe ser una variable.</span><span class="sxs-lookup"><span data-stu-id="d7f04-105">It makes the formal parameter an alias for the argument, which must be a variable.</span></span> <span data-ttu-id="d7f04-106">En otras palabras, cualquier operación en el parámetro se realiza en el argumento.</span><span class="sxs-lookup"><span data-stu-id="d7f04-106">In other words, any operation on the parameter is made on the argument.</span></span> <span data-ttu-id="d7f04-107">Es como las palabras clave [ref](ref.md) o [out](out-parameter-modifier.md), salvo que el método al que se llama no puede modificar los argumentos `in`.</span><span class="sxs-lookup"><span data-stu-id="d7f04-107">It is like the [ref](ref.md) or [out](out-parameter-modifier.md) keywords, except that `in` arguments cannot be modified by the called method.</span></span> <span data-ttu-id="d7f04-108">Mientras que los argumentos `ref` se pueden modificar, el método llamado debe modificar los argumentos `out` y esas modificaciones se pueden observar en el contexto de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d7f04-108">Whereas `ref` arguments may be modified, `out` arguments must be modified by the called method, and those modifications are observable in the calling context.</span></span>

[!code-csharp-interactive[cs-in-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/InParameterModifier.cs#1)]  

<span data-ttu-id="d7f04-109">En el ejemplo anterior se muestra que el modificador `in` no suele ser necesario en el sitio de llamada,</span><span class="sxs-lookup"><span data-stu-id="d7f04-109">The preceding example demonstrates that the `in` modifier is usually unnecessary at the call site.</span></span> <span data-ttu-id="d7f04-110">sino que solo lo es en la declaración del método.</span><span class="sxs-lookup"><span data-stu-id="d7f04-110">It is only required in the method declaration.</span></span>

> [!NOTE]
> <span data-ttu-id="d7f04-111">Además, la palabra clave `in` puede usarse con un parámetro de tipo genérico para especificar que el parámetro de tipo es contravariante, parte de una instrucción `foreach` o de una cláusula `join` de una consulta de LINQ.</span><span class="sxs-lookup"><span data-stu-id="d7f04-111">The `in` keyword can also be used with a generic type parameter to specify that the type parameter is contravariant, as part of a `foreach` statement, or as part of a `join` clause in a LINQ query.</span></span> <span data-ttu-id="d7f04-112">Para más información sobre el uso de la palabra clave `in` en esos contextos, vea [in](in.md), que además incluye vínculos a todos estos usos.</span><span class="sxs-lookup"><span data-stu-id="d7f04-112">For more information on the use of the `in` keyword in these contexts, see [in](in.md), which provides links to all those uses.</span></span>
  
<span data-ttu-id="d7f04-113">Las variables que se han pasado como argumentos `in` deben inicializarse antes de pasarse en una llamada de método.</span><span class="sxs-lookup"><span data-stu-id="d7f04-113">Variables passed as `in` arguments must be initialized before being passed in a method call.</span></span> <span data-ttu-id="d7f04-114">Sin embargo, es posible que el método llamado no asigne ningún valor o modifique el argumento.</span><span class="sxs-lookup"><span data-stu-id="d7f04-114">However, the called method may not assign a value or modify the argument.</span></span>  

<span data-ttu-id="d7f04-115">El modificador de parámetro `in` está disponible en C# 7.2 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="d7f04-115">The `in` parameter modifier is available in C# 7.2 and later.</span></span> <span data-ttu-id="d7f04-116">Las versiones anteriores generan el error del compilador `CS8107` ("Feature 'readonly references' is not available in C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="d7f04-116">Previous versions generate compiler error `CS8107` ("Feature 'readonly references' is not available in C# 7.0.</span></span> <span data-ttu-id="d7f04-117">Please use language version 7.2 or greater.") (La característica "readonly references" no está disponible en C# 7.0. Use la versión de lenguaje 7.2 o superior"). Para configurar la versión del lenguaje de compilador, vea [Seleccionar la versión del lenguaje C#](../configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="d7f04-117">Please use language version 7.2 or greater.") To configure the compiler language version, see [Select the C# language version](../configure-language-version.md).</span></span>

<span data-ttu-id="d7f04-118">Las palabras clave `in`, `ref` y `out` no se consideran parte de la firma del método con el fin de resolver la sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="d7f04-118">The `in`, `ref`, and `out` keywords are not considered part of the method signature for the purpose of overload resolution.</span></span> <span data-ttu-id="d7f04-119">Por lo tanto, los métodos no pueden sobrecargarse si la única diferencia es que un método toma un argumento `ref` o `in` y el otro toma un argumento `out`.</span><span class="sxs-lookup"><span data-stu-id="d7f04-119">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="d7f04-120">Por ejemplo, el código siguiente, no se compilará:</span><span class="sxs-lookup"><span data-stu-id="d7f04-120">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded
    // methods that differ only on in, ref and out".
    public void SampleMethod(in int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="d7f04-121">Está permitida la sobrecarga en función de la presencia de `in`:</span><span class="sxs-lookup"><span data-stu-id="d7f04-121">Overloading based on the presence of `in` is allowed:</span></span>  
  
```csharp
class InOverloads
{
    public void SampleMethod(in int i) { }
    public void SampleMethod(int i) { }
}
```

## <a name="overload-resolution-rules"></a><span data-ttu-id="d7f04-122">Reglas de resolución de sobrecarga</span><span class="sxs-lookup"><span data-stu-id="d7f04-122">Overload resolution rules</span></span>

<span data-ttu-id="d7f04-123">Puede comprender las reglas de resolución de sobrecarga de métodos por valor frente a argumentos `in` mediante la comprensión de la motivación de argumentos `in`.</span><span class="sxs-lookup"><span data-stu-id="d7f04-123">You can understand the overload resolution rules for methods with by value vs. `in` arguments by understanding the motivation for `in` arguments.</span></span> <span data-ttu-id="d7f04-124">Definir métodos usando parámetros `in` es una optimización del rendimiento potencial.</span><span class="sxs-lookup"><span data-stu-id="d7f04-124">Defining methods using `in` parameters is a potential performance optimization.</span></span> <span data-ttu-id="d7f04-125">Algunos argumentos de tipo `struct` pueden tener un gran tamaño y, cuando se llama a métodos en bucles de pequeñas dimensiones o rutas de acceso de código crítico, el costo de copiar esas estructuras resulta crucial.</span><span class="sxs-lookup"><span data-stu-id="d7f04-125">Some `struct` type arguments may be large in size, and when methods are called in tight loops or critical code paths, the cost of copying those structures is critical.</span></span> <span data-ttu-id="d7f04-126">Los métodos declaran parámetros `in` para especificar qué argumentos pueden pasarse por referencia sin ningún riesgo porque el método llamado no modifica el estado de ese argumento.</span><span class="sxs-lookup"><span data-stu-id="d7f04-126">Methods declare `in` parameters to specify that arguments may be passed by reference safely because the called method does not modify the state of that argument.</span></span> <span data-ttu-id="d7f04-127">Al pasar esos argumentos por referencia se evita la copia (potencialmente) costosa.</span><span class="sxs-lookup"><span data-stu-id="d7f04-127">Passing those arguments by reference avoids the (potentially) expensive copy.</span></span>

<span data-ttu-id="d7f04-128">Especificar `in` en argumentos en el sitio de llamada suele ser opcional.</span><span class="sxs-lookup"><span data-stu-id="d7f04-128">Specifying `in` for arguments at the call site is typically optional.</span></span> <span data-ttu-id="d7f04-129">No hay ninguna diferencia semántica entre pasar argumentos por valor y pasarlos por referencia mediante el modificador `in`.</span><span class="sxs-lookup"><span data-stu-id="d7f04-129">There is no semantic difference between passing arguments by value and passing them by reference using the `in` modifier.</span></span> <span data-ttu-id="d7f04-130">El modificador `in` en el sitio de llamada es opcional porque no es necesario indicar que podría cambiarse el valor del argumento.</span><span class="sxs-lookup"><span data-stu-id="d7f04-130">The `in` modifier at the call site is optional because you don't need to indicate that the argument's value might be changed.</span></span> <span data-ttu-id="d7f04-131">Se agrega explícitamente el modificador `in` en el sitio de llamada para garantizar que el argumento se pasa por referencia, y no por valor.</span><span class="sxs-lookup"><span data-stu-id="d7f04-131">You explicitly add the `in` modifier at the call site to ensure the argument is passed by reference, not by value.</span></span> <span data-ttu-id="d7f04-132">Usar explícitamente `in` tiene los dos efectos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d7f04-132">Explicitly using `in` has the following two effects:</span></span>

<span data-ttu-id="d7f04-133">El primero es que, al especificar `in` en el sitio de llamada, se fuerza al compilador a seleccionar un método definido con un parámetro `in` coincidente.</span><span class="sxs-lookup"><span data-stu-id="d7f04-133">First, specifying `in` at the call site forces the compiler to select a method defined with a matching `in` parameter.</span></span> <span data-ttu-id="d7f04-134">En caso contrario, cuando dos métodos se diferencian solo en presencia de `in`, la sobrecarga por valor es una coincidencia mejor.</span><span class="sxs-lookup"><span data-stu-id="d7f04-134">Otherwise, when two methods differ only in the presence of `in`, the by value overload is a better match.</span></span>

<span data-ttu-id="d7f04-135">El segundo es que, al especificar `in` declara su intención para pasar un argumento por referencia.</span><span class="sxs-lookup"><span data-stu-id="d7f04-135">Second, specifying `in` declares your intent to pass an argument by reference.</span></span> <span data-ttu-id="d7f04-136">Los argumentos usados con `in` deben representar una ubicación a la que se pueda hacer referencia directamente.</span><span class="sxs-lookup"><span data-stu-id="d7f04-136">The argument used with `in` must represent a location that can be directly referred to.</span></span> <span data-ttu-id="d7f04-137">Se aplican las mismas reglas generales para los argumentos `out` y `ref`: no se pueden usar constantes, propiedades normales u otras expresiones que produzcan valores.</span><span class="sxs-lookup"><span data-stu-id="d7f04-137">The same general rules for `out` and `ref` arguments apply: You cannot use constants, ordinary properties, or other expressions that produce values.</span></span> <span data-ttu-id="d7f04-138">En caso contrario, si se omite `in` en el sitio de llamada, se informa al compilador de que le permitirá crear una variable temporal para pasar por referencia de solo lectura para el método.</span><span class="sxs-lookup"><span data-stu-id="d7f04-138">Otherwise, omitting `in` at the call site informs the compiler that you will allow it to create a temporary variable to pass by read-only reference to the method.</span></span> <span data-ttu-id="d7f04-139">El compilador crea una variable temporal para superar varias restricciones con argumentos `in`:</span><span class="sxs-lookup"><span data-stu-id="d7f04-139">The compiler creates a temporary variable to overcome several restrictions with `in` arguments:</span></span>

- <span data-ttu-id="d7f04-140">Una variable temporal permite constantes en tiempo de compilación como parámetros `in`.</span><span class="sxs-lookup"><span data-stu-id="d7f04-140">A temporary variable allows compile-time constants as `in` parameters.</span></span>
- <span data-ttu-id="d7f04-141">Una variable temporal permite propiedades u otras expresiones para parámetros `in`.</span><span class="sxs-lookup"><span data-stu-id="d7f04-141">A temporary variable allows properties, or other expressions for `in` parameters.</span></span>
- <span data-ttu-id="d7f04-142">Una variable temporal permite argumentos en los que hay una conversión implícita desde el tipo de argumento hacia el tipo de parámetro.</span><span class="sxs-lookup"><span data-stu-id="d7f04-142">A temporary variable allows arguments where there is an implicit conversion from the argument type to the parameter type.</span></span>

<span data-ttu-id="d7f04-143">En todas las instancias anteriores, el compilador crea una variable temporal que almacena el valor de la constante, la propiedad u otra expresión.</span><span class="sxs-lookup"><span data-stu-id="d7f04-143">In all the preceding instances, the compiler creates a temporary variable that stores the value of the constant, property, or other expression.</span></span>

<span data-ttu-id="d7f04-144">Estas reglas se muestran en este código:</span><span class="sxs-lookup"><span data-stu-id="d7f04-144">The following code illustrates these rules:</span></span>

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

<span data-ttu-id="d7f04-145">Supongamos ahora que hay disponible otro método que usa argumentos por valor.</span><span class="sxs-lookup"><span data-stu-id="d7f04-145">Now, suppose another method using by value arguments was available.</span></span> <span data-ttu-id="d7f04-146">Los resultados cambian como se muestra en este código:</span><span class="sxs-lookup"><span data-stu-id="d7f04-146">The results change as shown in the following code:</span></span>

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

<span data-ttu-id="d7f04-147">La única llamada de método donde se pasa el argumento por referencia es la última.</span><span class="sxs-lookup"><span data-stu-id="d7f04-147">The only method call where the argument is passed by reference is the final one.</span></span>

> [!NOTE]
> <span data-ttu-id="d7f04-148">El código anterior usa `int` como el tipo de argumento para simplificar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="d7f04-148">The preceding code uses `int` as the argument type for simplicity.</span></span> <span data-ttu-id="d7f04-149">Como `int` no es más grande que una referencia en la mayoría de máquinas modernas, no supone ninguna ventaja pasar un único `int` como una referencia de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="d7f04-149">Because `int` is no larger than a reference in most modern machines, there is no benefit to passing a single `int` as a readonly reference.</span></span>

## <a name="limitations-on-in-parameters"></a><span data-ttu-id="d7f04-150">Limitaciones de los parámetros `in`</span><span class="sxs-lookup"><span data-stu-id="d7f04-150">Limitations on `in` parameters</span></span>

<span data-ttu-id="d7f04-151">Las palabras clave `in`, `ref` y `out` no pueden usarse para estos tipos de métodos:</span><span class="sxs-lookup"><span data-stu-id="d7f04-151">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="d7f04-152">Métodos asincrónicos, que se definen mediante el uso del modificador [async](async.md).</span><span class="sxs-lookup"><span data-stu-id="d7f04-152">Async methods, which you define by using the [async](async.md) modifier.</span></span>  
- <span data-ttu-id="d7f04-153">Métodos de iterador, que incluyen una instrucción [yield return](yield.md) o `yield break`.</span><span class="sxs-lookup"><span data-stu-id="d7f04-153">Iterator methods, which include a [yield return](yield.md) or `yield break` statement.</span></span>
- <span data-ttu-id="d7f04-154">El primer argumento de un método de extensión no puede tener el modificador `in` a menos que ese argumento sea una estructura.</span><span class="sxs-lookup"><span data-stu-id="d7f04-154">The first argument of an extension method cannot have the `in` modifier unless that argument is a struct.</span></span>
- <span data-ttu-id="d7f04-155">El primer argumento de un método de extensión donde el argumento es un tipo genérico (incluso si el tipo está restringido para ser una estructura).</span><span class="sxs-lookup"><span data-stu-id="d7f04-155">The first argument of an extension method where that argument is a generic type (even when that type is constrained to be a struct.)</span></span>

<span data-ttu-id="d7f04-156">Puede obtener más información sobre el modificador `in` y sobre cómo difiere de `ref` y `out` en el artículo sobre [Escritura de código eficaz y seguro](../../write-safe-efficient-code.md).</span><span class="sxs-lookup"><span data-stu-id="d7f04-156">You can learn more about the `in` modifier, how it differs from `ref` and `out` in the article on [Write safe efficient code](../../write-safe-efficient-code.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d7f04-157">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="d7f04-157">C# Language Specification</span></span>  

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  

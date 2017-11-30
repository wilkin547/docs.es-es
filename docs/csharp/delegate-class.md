---
title: System.Delegate y la palabra clave "delegate"
description: "Obtenga información sobre las clases de .NET Framework que admiten delegados y sobre cómo se asignan a la palabra clave \"delegate\"."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: f3742fda-13c2-4283-8966-9e21c2674393
ms.openlocfilehash: 09c7da7c780389d3819cf23a533cc425b43ad5ff
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2017
---
# <a name="systemdelegate-and-the-delegate-keyword"></a><span data-ttu-id="d90fe-104">System.Delegate y la palabra clave `delegate`</span><span class="sxs-lookup"><span data-stu-id="d90fe-104">System.Delegate and the `delegate` keyword</span></span>

[<span data-ttu-id="d90fe-105">Anterior</span><span class="sxs-lookup"><span data-stu-id="d90fe-105">Previous</span></span>](delegates-overview.md)

<span data-ttu-id="d90fe-106">Este artículo trata sobre las clases de .NET Framework que admiten delegados y sobre cómo se asignan a la palabra clave `delegate`.</span><span class="sxs-lookup"><span data-stu-id="d90fe-106">This article will cover the classes in the .NET framework that support delegates, and how those map to the `delegate` keyword.</span></span>

## <a name="defining-delegate-types"></a><span data-ttu-id="d90fe-107">Definir tipos de delegados</span><span class="sxs-lookup"><span data-stu-id="d90fe-107">Defining Delegate Types</span></span>

<span data-ttu-id="d90fe-108">Comencemos con la palabra clave "delegate", ya que es lo que usará principalmente al trabajar con delegados.</span><span class="sxs-lookup"><span data-stu-id="d90fe-108">Let's start with the 'delegate' keyword, because that's primarily what you will use as you work with delegates.</span></span> <span data-ttu-id="d90fe-109">El código que genere el compilador cuando se usa la palabra clave `delegate` se asignará a las llamadas de método que invocan a miembros de las clases <xref:System.Delegate> y <xref:System.MulticastDelegate>.</span><span class="sxs-lookup"><span data-stu-id="d90fe-109">The code that the compiler generates when you use the `delegate` keyword will map to method calls that invoke members of the <xref:System.Delegate> and <xref:System.MulticastDelegate> classes.</span></span> 

<span data-ttu-id="d90fe-110">Para definir un tipo de delegado, se usa una sintaxis similar a la definición de una firma de método.</span><span class="sxs-lookup"><span data-stu-id="d90fe-110">You define a delegate type using syntax that is similar to defining a method signature.</span></span> <span data-ttu-id="d90fe-111">Solo hace falta agregar la palabra clave `delegate` a la definición.</span><span class="sxs-lookup"><span data-stu-id="d90fe-111">You just add the `delegate` keyword to the definition.</span></span>

<span data-ttu-id="d90fe-112">Vamos a usar el método List.Sort() como ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d90fe-112">Let's continue to use the List.Sort() method as our example.</span></span> <span data-ttu-id="d90fe-113">El primer paso consiste en crear un tipo para el delegado de comparación:</span><span class="sxs-lookup"><span data-stu-id="d90fe-113">The first step is to create a type for the comparison delegate:</span></span>

```csharp
// From the .NET Core library

// Define the delegate type:
public delegate int Comparison<in T>(T left, T right);
```

<span data-ttu-id="d90fe-114">El compilador genera una clase derivada de `System.Delegate` que coincide con la firma usada (en este caso, un método que devuelve un entero y tiene dos argumentos).</span><span class="sxs-lookup"><span data-stu-id="d90fe-114">The compiler generates a class, derived from `System.Delegate` that matches the signature used (in this case, a method that returns an integer, and has two arguments).</span></span> <span data-ttu-id="d90fe-115">El tipo de ese delegado es `Comparison`.</span><span class="sxs-lookup"><span data-stu-id="d90fe-115">The type of that delegate is `Comparison`.</span></span> <span data-ttu-id="d90fe-116">El tipo de delegado `Comparison` es un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="d90fe-116">The `Comparison` delegate type is a generic type.</span></span> <span data-ttu-id="d90fe-117">[Aquí](generics.md) puede obtener más información sobre los genéricos.</span><span class="sxs-lookup"><span data-stu-id="d90fe-117">For details on generics see [here](generics.md).</span></span>

<span data-ttu-id="d90fe-118">Observe que puede parecer que la sintaxis declara una variable, pero en realidad declara un *tipo*.</span><span class="sxs-lookup"><span data-stu-id="d90fe-118">Notice that the syntax may appear as though it is declaring a variable, but it is actually declaring a *type*.</span></span> <span data-ttu-id="d90fe-119">Puede definir tipos de delegado dentro de clases, directamente dentro de espacios de nombres o incluso en el espacio de nombres global.</span><span class="sxs-lookup"><span data-stu-id="d90fe-119">You can define delegate types inside classes, directly inside namespaces, or even in the global namespace.</span></span>

> [!NOTE]
> <span data-ttu-id="d90fe-120">No se recomienda declarar tipos de delegado (u otros tipos) directamente en el espacio de nombres global.</span><span class="sxs-lookup"><span data-stu-id="d90fe-120">Declaring delegate types (or other types) directly in the global namespace is not recommended.</span></span> 

<span data-ttu-id="d90fe-121">El compilador también genera controladores de adición y eliminación para este nuevo tipo, de modo que los clientes de esta clase puedan agregar y quitar métodos de la lista de invocación de una instancia.</span><span class="sxs-lookup"><span data-stu-id="d90fe-121">The compiler also generates add and remove handlers for this new type so that clients of this class can add and remove methods from an instance's invocation list.</span></span> <span data-ttu-id="d90fe-122">El compilador forzará que la firma del método que se agrega o se quita coincida con la firma usada al declarar el método.</span><span class="sxs-lookup"><span data-stu-id="d90fe-122">The compiler will enforce that the signature of the method being added or removed matches the signature used when declaring the method.</span></span> 

## <a name="declaring-instances-of-delegates"></a><span data-ttu-id="d90fe-123">Declarar instancias de delegados</span><span class="sxs-lookup"><span data-stu-id="d90fe-123">Declaring instances of delegates</span></span>

<span data-ttu-id="d90fe-124">Después de definir el delegado, puede crear una instancia de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="d90fe-124">After defining the delegate, you can create an instance of that type.</span></span>
<span data-ttu-id="d90fe-125">Al igual que todas las variables en C#, no puede declarar instancias de delegados directamente en un espacio de nombres o en el espacio de nombres global.</span><span class="sxs-lookup"><span data-stu-id="d90fe-125">Like all variables in C#, you cannot declare delegate instances directly in a namespace, or in the global namespace.</span></span>

```csharp
// inside a class definition:

// Declare an instance of that type:
public Comparison<T> comparator;
```

<span data-ttu-id="d90fe-126">El tipo de la variable es `Comparison<T>`, el tipo de delegado definido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d90fe-126">The type of the variable is `Comparison<T>`, the delegate type defined earlier.</span></span> <span data-ttu-id="d90fe-127">El nombre de la variable es `comparator`.</span><span class="sxs-lookup"><span data-stu-id="d90fe-127">The name of the variable is `comparator`.</span></span>
 
 <span data-ttu-id="d90fe-128">El fragmento de código anterior declara una variable de miembro dentro de una clase.</span><span class="sxs-lookup"><span data-stu-id="d90fe-128">That code snippet above declared a member variable inside a class.</span></span> <span data-ttu-id="d90fe-129">También puede declarar variables de delegado que sean variables locales o argumentos para los métodos.</span><span class="sxs-lookup"><span data-stu-id="d90fe-129">You can also declare delegate variables that are local variables, or arguments to methods.</span></span>

## <a name="invoking-delegates"></a><span data-ttu-id="d90fe-130">Invocar delegados</span><span class="sxs-lookup"><span data-stu-id="d90fe-130">Invoking Delegates</span></span>

<span data-ttu-id="d90fe-131">Para invocar los métodos que se encuentran en la lista de invocación de un delegado, llame a dicho delegado.</span><span class="sxs-lookup"><span data-stu-id="d90fe-131">You invoke the methods that are in the invocation list of a delegate by calling that delegate.</span></span> <span data-ttu-id="d90fe-132">Dentro del método `Sort()`, el código llamará al método de comparación para determinar en qué orden colocará los objetos:</span><span class="sxs-lookup"><span data-stu-id="d90fe-132">Inside the `Sort()` method, the code will call the comparison method to determine which order to place objects:</span></span>

```csharp
int result = comparator(left, right);
```

<span data-ttu-id="d90fe-133">En la línea anterior, el código *invoca* al método asociado al delegado.</span><span class="sxs-lookup"><span data-stu-id="d90fe-133">In the line above, the code *invokes* the method attached to the delegate.</span></span>
<span data-ttu-id="d90fe-134">La variable se trata como un nombre de método y se invoca mediante la sintaxis de llamada de método normal.</span><span class="sxs-lookup"><span data-stu-id="d90fe-134">You treat the variable as a method name, and invoke it using normal method call syntax.</span></span>

<span data-ttu-id="d90fe-135">Esta línea de código realiza una suposición arriesgada, ya que no hay ninguna garantía de que se haya agregado un destino al delegado.</span><span class="sxs-lookup"><span data-stu-id="d90fe-135">That line of code makes an unsafe assumption: There's no guarantee that a target has been added to the delegate.</span></span> <span data-ttu-id="d90fe-136">Si no se ha asociado ningún destino, la línea anterior haría que se produjese una `NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="d90fe-136">If no targets have been attached, the line above would cause a `NullReferenceException` to be thrown.</span></span> <span data-ttu-id="d90fe-137">Las expresiones que se usan para resolver este problema son más complicadas que una simple comprobación de null y se tratan más adelante en esta [serie](delegates-patterns.md).</span><span class="sxs-lookup"><span data-stu-id="d90fe-137">The idioms used to address this problem are more complicated than a simple null-check, and are covered later in this [series](delegates-patterns.md).</span></span>

## <a name="assigning-adding-and-removing-invocation-targets"></a><span data-ttu-id="d90fe-138">Asignar, agregar y quitar destinos de invocación</span><span class="sxs-lookup"><span data-stu-id="d90fe-138">Assigning, Adding and removing Invocation Targets</span></span>

<span data-ttu-id="d90fe-139">Hemos visto cómo se define un tipo de delegado y cómo se declaran y se invocan las instancias de delegado.</span><span class="sxs-lookup"><span data-stu-id="d90fe-139">That's how a delegate type is defined, and how delegate instances are declared and invoked.</span></span>

<span data-ttu-id="d90fe-140">Los programadores que quieran usar el método `List.Sort()` deben definir un método cuya firma coincida con la definición del tipo de delegado y asignarlo al delegado usado por el método de ordenación.</span><span class="sxs-lookup"><span data-stu-id="d90fe-140">Developers that want to use the `List.Sort()` method need to define a method whose signature matches the delegate type definition, and assign it to the delegate used by the sort method.</span></span> <span data-ttu-id="d90fe-141">Esta asignación agrega el método a la lista de invocación de ese objeto de delegado.</span><span class="sxs-lookup"><span data-stu-id="d90fe-141">This assignment adds the method to the invocation list of that delegate object.</span></span>

<span data-ttu-id="d90fe-142">Supongamos que quiera ordenar una lista de cadenas por su duración.</span><span class="sxs-lookup"><span data-stu-id="d90fe-142">Suppose you wanted to sort a list of strings by their length.</span></span> <span data-ttu-id="d90fe-143">La función de comparación podría ser la siguiente:</span><span class="sxs-lookup"><span data-stu-id="d90fe-143">Your comparison function might be the following:</span></span>

```csharp
private static int CompareLength(string left, string right)
{
    return left.Length.CompareTo(right.Length);
}
```

<span data-ttu-id="d90fe-144">El método se ha declarado como un método privado.</span><span class="sxs-lookup"><span data-stu-id="d90fe-144">The method is declared as a private method.</span></span> <span data-ttu-id="d90fe-145">Esto es correcto,</span><span class="sxs-lookup"><span data-stu-id="d90fe-145">That's fine.</span></span> <span data-ttu-id="d90fe-146">ya que tal vez no le interese que este método forme parte de la interfaz pública.</span><span class="sxs-lookup"><span data-stu-id="d90fe-146">You may not want this method to be part of your public interface.</span></span> <span data-ttu-id="d90fe-147">Aun así, puede usarse como método de comparación cuando se asocia a un delegado.</span><span class="sxs-lookup"><span data-stu-id="d90fe-147">It can still be used as the comparison method when attached to a delegate.</span></span> <span data-ttu-id="d90fe-148">El código de llamada tendrá este método asociado a la lista de destino del objeto de delegado y puede tener acceso a él a través de ese delegado.</span><span class="sxs-lookup"><span data-stu-id="d90fe-148">The calling code will have this method attached to the target list of the delegate object, and can access it through that delegate.</span></span>

<span data-ttu-id="d90fe-149">Para crear esta relación, pase ese método al método `List.Sort()`:</span><span class="sxs-lookup"><span data-stu-id="d90fe-149">You create that relationship by passing that method to the `List.Sort()` method:</span></span>

```csharp
phrases.Sort(CompareLength);
```

<span data-ttu-id="d90fe-150">Observe que se usa el nombre del método sin paréntesis.</span><span class="sxs-lookup"><span data-stu-id="d90fe-150">Notice that the method name is used, without parentheses.</span></span> <span data-ttu-id="d90fe-151">Al usar el método como un argumento, le indica al compilador que convierta la referencia del método en una referencia que se puede usar como un destino de invocación del delegado y que asocie ese método como un destino de invocación.</span><span class="sxs-lookup"><span data-stu-id="d90fe-151">Using the method as an argument tells the compiler to convert the method reference into a reference that can be used as a delegate invocation target, and attach that method as an invocation target.</span></span>

<span data-ttu-id="d90fe-152">También podría haber declarado explícitamente una variable de tipo "Comparison<string>" y realizado una asignación:</span><span class="sxs-lookup"><span data-stu-id="d90fe-152">You could also have been explicit by declaring a variable of type 'Comparison<string>\` and doing an assignment:</span></span>

```csharp
Comparison<string> comparer = CompareLength;
phrases.Sort(comparer);
```

<span data-ttu-id="d90fe-153">En los casos en los que el método que se usa como destino del delegado es un método pequeño, es habitual usar la sintaxis de [expresión lambda](lambda-expressions.md) para realizar la asignación:</span><span class="sxs-lookup"><span data-stu-id="d90fe-153">In uses where the method being used as a delegate target is a small method, it's common to use [Lambda Expression](lambda-expressions.md) syntax to perform the assignment:</span></span>

```csharp
Comparison<string> comparer = (left, right) => left.Length.CompareTo(right.Length);
phrases.Sort(comparer);
```

<span data-ttu-id="d90fe-154">El uso de expresiones lambda para destinos de delegados se explica con más detalle en una [sección posterior](delegates-patterns.md).</span><span class="sxs-lookup"><span data-stu-id="d90fe-154">Using Lambda Expressions for delegate targets is covered more in a [later section](delegates-patterns.md).</span></span>

<span data-ttu-id="d90fe-155">En el ejemplo de Sort() se suele asociar un método de destino único al delegado,</span><span class="sxs-lookup"><span data-stu-id="d90fe-155">The Sort() example typically attaches a single target method to the delegate.</span></span> <span data-ttu-id="d90fe-156">pero los objetos delegados admiten listas de invocación que tienen varios métodos de destino asociados a un objeto delegado.</span><span class="sxs-lookup"><span data-stu-id="d90fe-156">However, delegate objects do support invocation lists that have multiple target methods attached to a delegate object.</span></span>

## <a name="delegate-and-multicastdelegate-classes"></a><span data-ttu-id="d90fe-157">Clases Delegate y MulticastDelegate</span><span class="sxs-lookup"><span data-stu-id="d90fe-157">Delegate and MulticastDelegate classes</span></span>

<span data-ttu-id="d90fe-158">La compatibilidad de lenguaje descrita anteriormente proporciona las características y la compatibilidad que normalmente necesitará para trabajar con delegados.</span><span class="sxs-lookup"><span data-stu-id="d90fe-158">The language support described above provides the features and support you'll typically need to work with delegates.</span></span> <span data-ttu-id="d90fe-159">Estas características están integradas en las dos clases en el marco de trabajo de .NET Core: <xref:System.Delegate> y <xref:System.MulticastDelegate>.</span><span class="sxs-lookup"><span data-stu-id="d90fe-159">These features are built on two classes in the .NET Core framework: <xref:System.Delegate> and <xref:System.MulticastDelegate>.</span></span>

<span data-ttu-id="d90fe-160">La clase `System.Delegate` y su única subclase directa `System.MulticastDelegate` proporcionan la compatibilidad con el marco para crear delegados, registrar métodos como destinos de delegados e invocar todos los métodos que se registran como un destino del delegado.</span><span class="sxs-lookup"><span data-stu-id="d90fe-160">The `System.Delegate` class, and its single direct sub-class, `System.MulticastDelegate`, provide the framework support for creating delegates, registering methods as delegate targets, and invoking all methods that are registered as a delegate target.</span></span> 

<span data-ttu-id="d90fe-161">Curiosamente, las clases `System.Delegate` y `System.MulticastDelegate` no son tipos de delegado,</span><span class="sxs-lookup"><span data-stu-id="d90fe-161">Interestingly, the `System.Delegate` and `System.MulticastDelegate` classes are not themselves delegate types.</span></span> <span data-ttu-id="d90fe-162">pero proporcionan la base para todos los tipos de delegado específicos.</span><span class="sxs-lookup"><span data-stu-id="d90fe-162">They do provide the basis for all specific delegate types.</span></span> <span data-ttu-id="d90fe-163">El propio proceso de diseño del lenguaje dictaba que no se puede declarar una clase que derive de `Delegate` o `MulticastDelegate`.</span><span class="sxs-lookup"><span data-stu-id="d90fe-163">That same language design process mandated that you cannot declare a class that derives from `Delegate` or `MulticastDelegate`.</span></span> <span data-ttu-id="d90fe-164">Las reglas del lenguaje C# lo prohíben.</span><span class="sxs-lookup"><span data-stu-id="d90fe-164">The C# language rules prohibit it.</span></span>
 
<span data-ttu-id="d90fe-165">En cambio, el compilador de C# crea instancias de una clase derivada de `MulticastDelegate` cuando se usa la palabra clave del lenguaje C# para declarar tipos de delegado.</span><span class="sxs-lookup"><span data-stu-id="d90fe-165">Instead, the C# compiler creates instances of a class derived from `MulticastDelegate` when you use the C# language keyword to declare delegate types.</span></span>

<span data-ttu-id="d90fe-166">Este diseño tiene sus orígenes en la primera versión de C# y. NET.</span><span class="sxs-lookup"><span data-stu-id="d90fe-166">This design has its roots in the first release of C# and .NET.</span></span> <span data-ttu-id="d90fe-167">Uno de los objetivos del equipo de diseño era asegurarse de que el lenguaje aplicaba seguridad de tipos al usar delegados.</span><span class="sxs-lookup"><span data-stu-id="d90fe-167">One goal for the design team was to ensure that the language enforced type safety when using delegates.</span></span> <span data-ttu-id="d90fe-168">Esto significaba que debían asegurarse no solo de que los delegados se invocaban con el tipo y el número adecuados de argumentos,</span><span class="sxs-lookup"><span data-stu-id="d90fe-168">That meant ensuring that delegates were invoked with the right type and number of arguments.</span></span> <span data-ttu-id="d90fe-169">sino de que todos los tipos de valor devueltos se indicaban correctamente en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="d90fe-169">And, that any return type was correctly indicated at compile time.</span></span> <span data-ttu-id="d90fe-170">Los delegados formaban parte de la versión 1.0 .NET, que apareció antes que los genéricos.</span><span class="sxs-lookup"><span data-stu-id="d90fe-170">Delegates were part of the 1.0 .NET release, which was before generics.</span></span>

<span data-ttu-id="d90fe-171">La mejor manera de aplicar la seguridad de tipos era que el compilador crease las clases de delegado concretas que representasen la firma del método que se usaba.</span><span class="sxs-lookup"><span data-stu-id="d90fe-171">The best way to enforce this type safety was for the compiler to create the concrete delegate classes that represented the method signature being used.</span></span>

<span data-ttu-id="d90fe-172">Aunque usted no puede crear clases derivadas directamente, usará los métodos definidos en estas clases.</span><span class="sxs-lookup"><span data-stu-id="d90fe-172">Even though you cannot create derived classes directly, you will use the methods defined on these classes.</span></span> <span data-ttu-id="d90fe-173">Vamos a ver los métodos más comunes que usará al trabajar con delegados.</span><span class="sxs-lookup"><span data-stu-id="d90fe-173">Let's go through the most common methods that you will use when you work with delegates.</span></span>

<span data-ttu-id="d90fe-174">Lo primero que debe recordar es que cada delegado con el que trabaje se deriva de `MulticastDelegate`.</span><span class="sxs-lookup"><span data-stu-id="d90fe-174">The first, most important fact to remember is that every delegate you work with is derived from `MulticastDelegate`.</span></span> <span data-ttu-id="d90fe-175">Un delegado multidifusión significa que se puede invocar más de un destino de método al invocar en un delegado.</span><span class="sxs-lookup"><span data-stu-id="d90fe-175">A multicast delegate means that more than one method target can be invoked when invoking through a delegate.</span></span> <span data-ttu-id="d90fe-176">El diseño original consideraba la posibilidad de establecer una distinción entre los delegados en los que solo se podía asociar e invocar un método de destino y los delegados en los que se podía asociar e invocar varios métodos de destino.</span><span class="sxs-lookup"><span data-stu-id="d90fe-176">The original design considered making a distinction between delegates where only one target method could be attached and invoked, and delegates where multiple target methods could be attached and invoked.</span></span> <span data-ttu-id="d90fe-177">Esa distinción resultó ser menos útil en la práctica de lo que se pensaba.</span><span class="sxs-lookup"><span data-stu-id="d90fe-177">That distinction proved to be less useful in practice than originally thought.</span></span> <span data-ttu-id="d90fe-178">Las dos clases ya estaban creadas y se han conservado en el marco de trabajo desde la versión pública inicial.</span><span class="sxs-lookup"><span data-stu-id="d90fe-178">The two different classes were already created, and have been in the framework since its initial public release.</span></span>

<span data-ttu-id="d90fe-179">Los métodos que usará más a menudo con los delegados son `Invoke()` y `BeginInvoke()` / `EndInvoke()`.</span><span class="sxs-lookup"><span data-stu-id="d90fe-179">The methods that you will use the most with delegates are `Invoke()` and `BeginInvoke()` / `EndInvoke()`.</span></span> <span data-ttu-id="d90fe-180">`Invoke()` invocará todos los métodos que se han asociado a una instancia de delegado en concreto.</span><span class="sxs-lookup"><span data-stu-id="d90fe-180">`Invoke()` will invoke all the methods that have been attached to a particular delegate instance.</span></span> <span data-ttu-id="d90fe-181">Como ya hemos visto anteriormente, por lo general los delegados se invocan mediante la sintaxis de llamada de método en la variable de delegado.</span><span class="sxs-lookup"><span data-stu-id="d90fe-181">As you saw above, you typically invoke delegates using the method call syntax on the delegate variable.</span></span> <span data-ttu-id="d90fe-182">Como verá [más adelante en esta serie](delegates-patterns.md), hay patrones que funcionan directamente con estos métodos.</span><span class="sxs-lookup"><span data-stu-id="d90fe-182">As you'll see [later in this series](delegates-patterns.md), there are patterns that work directly with these methods.</span></span>

<span data-ttu-id="d90fe-183">Ahora que ha visto la sintaxis del lenguaje y las clases que admiten delegados, examinemos cómo se usan, se crean y se invocan delegados fuertemente tipados.</span><span class="sxs-lookup"><span data-stu-id="d90fe-183">Now that you've seen the language syntax and the classes that support delegates, let's examine how strongly typed delegates are used, created and invoked.</span></span>

[<span data-ttu-id="d90fe-184">Siguiente</span><span class="sxs-lookup"><span data-stu-id="d90fe-184">Next</span></span>](delegates-strongly-typed.md)

---
title: Crear interfaces genéricas variantes (C#)
ms.date: 07/20/2015
ms.assetid: 30330ec4-9df2-4838-a535-6c406d0ed4df
ms.openlocfilehash: a8e3e010c0e5d5490aee35603cad4fd6c1dc29e0
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990049"
---
# <a name="creating-variant-generic-interfaces-c"></a><span data-ttu-id="5a197-102">Crear interfaces genéricas variantes (C#)</span><span class="sxs-lookup"><span data-stu-id="5a197-102">Creating Variant Generic Interfaces (C#)</span></span>

<span data-ttu-id="5a197-103">Puede declarar parámetros de tipo genérico en las interfaces como covariantes o contravariantes.</span><span class="sxs-lookup"><span data-stu-id="5a197-103">You can declare generic type parameters in interfaces as covariant or contravariant.</span></span> <span data-ttu-id="5a197-104">La *covarianza* permite que los métodos de interfaz tengan tipos de valor devuelto más derivados que los que se definen en los parámetros de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="5a197-104">*Covariance* allows interface methods to have more derived return types than that defined by the generic type parameters.</span></span> <span data-ttu-id="5a197-105">La *contravarianza* permite que los métodos de interfaz tengan tipos de argumento menos derivados que los que se especifican en los parámetros genéricos.</span><span class="sxs-lookup"><span data-stu-id="5a197-105">*Contravariance* allows interface methods to have argument types that are less derived than that specified by the generic parameters.</span></span> <span data-ttu-id="5a197-106">Las interfaces genéricas que tienen parámetros de tipo genérico covariantes o contravariantes se llaman *variantes*.</span><span class="sxs-lookup"><span data-stu-id="5a197-106">A generic interface that has covariant or contravariant generic type parameters is called *variant*.</span></span>

> [!NOTE]
> <span data-ttu-id="5a197-107">En .NET Framework 4 se ha presentado la compatibilidad con la varianza para varias interfaces genéricas existentes.</span><span class="sxs-lookup"><span data-stu-id="5a197-107">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="5a197-108">Para ver la lista de interfaces variantes de .NET, vea [Varianza en interfaces genéricas (C#)](./variance-in-generic-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="5a197-108">For the list of the variant interfaces in .NET, see [Variance in Generic Interfaces (C#)](./variance-in-generic-interfaces.md).</span></span>

## <a name="declaring-variant-generic-interfaces"></a><span data-ttu-id="5a197-109">Declarar interfaces genéricas variantes</span><span class="sxs-lookup"><span data-stu-id="5a197-109">Declaring Variant Generic Interfaces</span></span>

<span data-ttu-id="5a197-110">Puede declarar interfaces genéricas variantes mediante las palabras clave `in` y `out` para los parámetros de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="5a197-110">You can declare variant generic interfaces by using the `in` and `out` keywords for generic type parameters.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5a197-111">Los parámetros `ref`, `in` y `out` de C# no pueden ser variantes.</span><span class="sxs-lookup"><span data-stu-id="5a197-111">`ref`, `in`, and `out` parameters in C# cannot be variant.</span></span> <span data-ttu-id="5a197-112">Los tipos de valor tampoco admiten la varianza.</span><span class="sxs-lookup"><span data-stu-id="5a197-112">Value types also do not support variance.</span></span>

<span data-ttu-id="5a197-113">Puede declarar un parámetro de tipo genérico covariante mediante la palabra clave `out`.</span><span class="sxs-lookup"><span data-stu-id="5a197-113">You can declare a generic type parameter covariant by using the `out` keyword.</span></span> <span data-ttu-id="5a197-114">El tipo covariante debe cumplir las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="5a197-114">The covariant type must satisfy the following conditions:</span></span>

- <span data-ttu-id="5a197-115">El tipo se usa únicamente como tipo de valor devuelto de los métodos de interfaz, y no como tipo de los argumentos de método.</span><span class="sxs-lookup"><span data-stu-id="5a197-115">The type is used only as a return type of interface methods and not used as a type of method arguments.</span></span> <span data-ttu-id="5a197-116">Esto se muestra en el siguiente ejemplo, en el que el tipo `R` se declara como covariante.</span><span class="sxs-lookup"><span data-stu-id="5a197-116">This is illustrated in the following example, in which the type `R` is declared covariant.</span></span>

    ```csharp
    interface ICovariant<out R>
    {
        R GetSomething();
        // The following statement generates a compiler error.
        // void SetSomething(R sampleArg);

    }
    ```

    <span data-ttu-id="5a197-117">Hay una excepción para esta regla.</span><span class="sxs-lookup"><span data-stu-id="5a197-117">There is one exception to this rule.</span></span> <span data-ttu-id="5a197-118">Si tiene un delegado genérico contravariante como parámetro de método, puede usar el tipo como parámetro de tipo genérico para el delegado.</span><span class="sxs-lookup"><span data-stu-id="5a197-118">If you have a contravariant generic delegate as a method parameter, you can use the type as a generic type parameter for the delegate.</span></span> <span data-ttu-id="5a197-119">Esto se muestra en el siguiente ejemplo con el tipo `R`.</span><span class="sxs-lookup"><span data-stu-id="5a197-119">This is illustrated by the type `R` in the following example.</span></span> <span data-ttu-id="5a197-120">Para obtener más información, vea [Varianza en delegados (C#)](./variance-in-delegates.md) y [Usar la varianza para los delegados genéricos Func y Action (C#)](./using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="5a197-120">For more information, see [Variance in Delegates (C#)](./variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (C#)](./using-variance-for-func-and-action-generic-delegates.md).</span></span>

    ```csharp
    interface ICovariant<out R>
    {
        void DoSomething(Action<R> callback);
    }
    ```

- <span data-ttu-id="5a197-121">El tipo no se usa como restricción genérica para los métodos de interfaz.</span><span class="sxs-lookup"><span data-stu-id="5a197-121">The type is not used as a generic constraint for the interface methods.</span></span> <span data-ttu-id="5a197-122">Esto se muestra en el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="5a197-122">This is illustrated in the following code.</span></span>

    ```csharp
    interface ICovariant<out R>
    {
        // The following statement generates a compiler error
        // because you can use only contravariant or invariant types
        // in generic constraints.
        // void DoSomething<T>() where T : R;
    }
    ```

<span data-ttu-id="5a197-123">Puede declarar un parámetro de tipo genérico contravariante mediante la palabra clave `in`.</span><span class="sxs-lookup"><span data-stu-id="5a197-123">You can declare a generic type parameter contravariant by using the `in` keyword.</span></span> <span data-ttu-id="5a197-124">El tipo contravariante solo se puede usar como tipo de los argumentos de método, y no como tipo de valor devuelto de los métodos de interfaz.</span><span class="sxs-lookup"><span data-stu-id="5a197-124">The contravariant type can be used only as a type of method arguments and not as a return type of interface methods.</span></span> <span data-ttu-id="5a197-125">El tipo contravariante también se puede usar para las restricciones genéricas.</span><span class="sxs-lookup"><span data-stu-id="5a197-125">The contravariant type can also be used for generic constraints.</span></span> <span data-ttu-id="5a197-126">En el siguiente código se muestra cómo declarar una interfaz contravariante y cómo usar una restricción genérica para uno de sus métodos.</span><span class="sxs-lookup"><span data-stu-id="5a197-126">The following code shows how to declare a contravariant interface and use a generic constraint for one of its methods.</span></span>

```csharp
interface IContravariant<in A>
{
    void SetSomething(A sampleArg);
    void DoSomething<T>() where T : A;
    // The following statement generates a compiler error.
    // A GetSomething();
}
```

<span data-ttu-id="5a197-127">También se puede admitir la covarianza y la contravarianza en la misma interfaz, pero para distintos parámetros de tipo, como se muestra en el siguiente ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="5a197-127">It is also possible to support both covariance and contravariance in the same interface, but for different type parameters, as shown in the following code example.</span></span>

```csharp
interface IVariant<out R, in A>
{
    R GetSomething();
    void SetSomething(A sampleArg);
    R GetSetSomethings(A sampleArg);
}
```

## <a name="implementing-variant-generic-interfaces"></a><span data-ttu-id="5a197-128">Implementar interfaces genéricas variantes</span><span class="sxs-lookup"><span data-stu-id="5a197-128">Implementing Variant Generic Interfaces</span></span>

<span data-ttu-id="5a197-129">Las interfaces genéricas variantes se implementan en las clases usando la misma sintaxis que se usa para las interfaces invariables.</span><span class="sxs-lookup"><span data-stu-id="5a197-129">You implement variant generic interfaces in classes by using the same syntax that is used for invariant interfaces.</span></span> <span data-ttu-id="5a197-130">En el siguiente ejemplo de código se muestra cómo implementar una interfaz covariante en una clase genérica.</span><span class="sxs-lookup"><span data-stu-id="5a197-130">The following code example shows how to implement a covariant interface in a generic class.</span></span>

```csharp
interface ICovariant<out R>
{
    R GetSomething();
}
class SampleImplementation<R> : ICovariant<R>
{
    public R GetSomething()
    {
        // Some code.
        return default(R);
    }
}
```

<span data-ttu-id="5a197-131">Las clases que implementan interfaces variantes son invariables.</span><span class="sxs-lookup"><span data-stu-id="5a197-131">Classes that implement variant interfaces are invariant.</span></span> <span data-ttu-id="5a197-132">Por ejemplo, considere el fragmento de código siguiente:</span><span class="sxs-lookup"><span data-stu-id="5a197-132">For example, consider the following code.</span></span>

```csharp
// The interface is covariant.
ICovariant<Button> ibutton = new SampleImplementation<Button>();
ICovariant<Object> iobj = ibutton;

// The class is invariant.
SampleImplementation<Button> button = new SampleImplementation<Button>();
// The following statement generates a compiler error
// because classes are invariant.
// SampleImplementation<Object> obj = button;
```

## <a name="extending-variant-generic-interfaces"></a><span data-ttu-id="5a197-133">Extender interfaces genéricas variantes</span><span class="sxs-lookup"><span data-stu-id="5a197-133">Extending Variant Generic Interfaces</span></span>

<span data-ttu-id="5a197-134">Al extender una interfaz genérica variante, debe usar las palabras clave `in` y `out` para especificar de forma explícita si la interfaz derivada admite la varianza.</span><span class="sxs-lookup"><span data-stu-id="5a197-134">When you extend a variant generic interface, you have to use the `in` and `out` keywords to explicitly specify whether the derived interface supports variance.</span></span> <span data-ttu-id="5a197-135">El compilador no infiere la varianza de la interfaz que se va a extender.</span><span class="sxs-lookup"><span data-stu-id="5a197-135">The compiler does not infer the variance from the interface that is being extended.</span></span> <span data-ttu-id="5a197-136">Por ejemplo, observe las siguientes interfaces.</span><span class="sxs-lookup"><span data-stu-id="5a197-136">For example, consider the following interfaces.</span></span>

```csharp
interface ICovariant<out T> { }
interface IInvariant<T> : ICovariant<T> { }
interface IExtCovariant<out T> : ICovariant<T> { }
```

<span data-ttu-id="5a197-137">En la interfaz `IInvariant<T>`, el parámetro de tipo genérico `T` es invariable, mientras que en `IExtCovariant<out T>` el parámetro de tipo es covariante, si bien ambas interfaces extienden la misma interfaz.</span><span class="sxs-lookup"><span data-stu-id="5a197-137">In the `IInvariant<T>` interface, the generic type parameter `T` is invariant, whereas in `IExtCovariant<out T>` the type parameter is covariant, although both interfaces extend the same interface.</span></span> <span data-ttu-id="5a197-138">La misma regla se aplica a los parámetros de tipo genérico contravariantes.</span><span class="sxs-lookup"><span data-stu-id="5a197-138">The same rule is applied to contravariant generic type parameters.</span></span>

<span data-ttu-id="5a197-139">Puede crear una interfaz que extienda la interfaz donde el parámetro de tipo genérico `T` es covariante y la interfaz donde es contravariante si, en la interfaz que va a extender, el parámetro de tipo genérico `T` es invariable.</span><span class="sxs-lookup"><span data-stu-id="5a197-139">You can create an interface that extends both the interface where the generic type parameter `T` is covariant and the interface where it is contravariant if in the extending interface the generic type parameter `T` is invariant.</span></span> <span data-ttu-id="5a197-140">Esto se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5a197-140">This is illustrated in the following code example.</span></span>

```csharp
interface ICovariant<out T> { }
interface IContravariant<in T> { }
interface IInvariant<T> : ICovariant<T>, IContravariant<T> { }
```

<span data-ttu-id="5a197-141">Pero si un parámetro de tipo genérico `T` se declara como covariante en una interfaz, no puede declararlo como contravariante en la interfaz extensible (o viceversa).</span><span class="sxs-lookup"><span data-stu-id="5a197-141">However, if a generic type parameter `T` is declared covariant in one interface, you cannot declare it contravariant in the extending interface, or vice versa.</span></span> <span data-ttu-id="5a197-142">Esto se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5a197-142">This is illustrated in the following code example.</span></span>

```csharp
interface ICovariant<out T> { }
// The following statement generates a compiler error.
// interface ICoContraVariant<in T> : ICovariant<T> { }
```

### <a name="avoiding-ambiguity"></a><span data-ttu-id="5a197-143">Evitar la ambigüedad</span><span class="sxs-lookup"><span data-stu-id="5a197-143">Avoiding Ambiguity</span></span>

<span data-ttu-id="5a197-144">Al implementar interfaces genéricas variantes, la varianza a veces puede implicar ambigüedad.</span><span class="sxs-lookup"><span data-stu-id="5a197-144">When you implement variant generic interfaces, variance can sometimes lead to ambiguity.</span></span> <span data-ttu-id="5a197-145">Debe evitarse esta ambigüedad.</span><span class="sxs-lookup"><span data-stu-id="5a197-145">Such ambiguity should be avoided.</span></span>

<span data-ttu-id="5a197-146">Por ejemplo, si implementa explícitamente en una clase la misma interfaz genérica variante con distintos parámetros de tipo genérico, puede crear ambigüedad.</span><span class="sxs-lookup"><span data-stu-id="5a197-146">For example, if you explicitly implement the same variant generic interface with different generic type parameters in one class, it can create ambiguity.</span></span> <span data-ttu-id="5a197-147">El compilador no genera ningún error en este caso, pero no se especifica qué implementación de interfaz se va a elegir en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5a197-147">The compiler does not produce an error in this case, but it's not specified which interface implementation will be chosen at run time.</span></span> <span data-ttu-id="5a197-148">Esta ambigüedad podría provocar errores sutiles en el código.</span><span class="sxs-lookup"><span data-stu-id="5a197-148">This ambiguity could lead to subtle bugs in your code.</span></span> <span data-ttu-id="5a197-149">Observe el siguiente ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="5a197-149">Consider the following code example.</span></span>

```csharp
// Simple class hierarchy.
class Animal { }
class Cat : Animal { }
class Dog : Animal { }

// This class introduces ambiguity
// because IEnumerable<out T> is covariant.
class Pets : IEnumerable<Cat>, IEnumerable<Dog>
{
    IEnumerator<Cat> IEnumerable<Cat>.GetEnumerator()
    {
        Console.WriteLine("Cat");
        // Some code.
        return null;
    }

    IEnumerator IEnumerable.GetEnumerator()
    {
        // Some code.
        return null;
    }

    IEnumerator<Dog> IEnumerable<Dog>.GetEnumerator()
    {
        Console.WriteLine("Dog");
        // Some code.
        return null;
    }
}
class Program
{
    public static void Test()
    {
        IEnumerable<Animal> pets = new Pets();
        pets.GetEnumerator();
    }
}
```

<span data-ttu-id="5a197-150">En este ejemplo no se especifica cómo elige el método `pets.GetEnumerator` entre `Cat` y `Dog`.</span><span class="sxs-lookup"><span data-stu-id="5a197-150">In this example, it is unspecified how the `pets.GetEnumerator` method chooses between `Cat` and `Dog`.</span></span> <span data-ttu-id="5a197-151">Esto podría producir problemas en el código.</span><span class="sxs-lookup"><span data-stu-id="5a197-151">This could cause problems in your code.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a197-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a197-152">See also</span></span>

- [<span data-ttu-id="5a197-153">Varianza en interfaces genéricas (C#)</span><span class="sxs-lookup"><span data-stu-id="5a197-153">Variance in Generic Interfaces (C#)</span></span>](./variance-in-generic-interfaces.md)
- [<span data-ttu-id="5a197-154">Usar varianza para los delegados genéricos Func y Action (C#)</span><span class="sxs-lookup"><span data-stu-id="5a197-154">Using Variance for Func and Action Generic Delegates (C#)</span></span>](./using-variance-for-func-and-action-generic-delegates.md)

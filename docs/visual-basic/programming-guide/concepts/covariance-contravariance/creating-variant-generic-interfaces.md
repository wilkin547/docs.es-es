---
description: Más información sobre cómo crear interfaces genéricas variantes (Visual Basic)
title: Creación de interfaces genéricas variantes
ms.date: 07/20/2015
ms.assetid: d4037dd2-dfe9-4811-9150-93d4e8b20113
ms.openlocfilehash: 41da9040709ff053ba05cc7c44be989b7fa39c44
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100485268"
---
# <a name="creating-variant-generic-interfaces-visual-basic"></a><span data-ttu-id="5b580-103">Crear interfaces genéricas variantes (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b580-103">Creating Variant Generic Interfaces (Visual Basic)</span></span>

<span data-ttu-id="5b580-104">Puede declarar parámetros de tipo genérico en las interfaces como covariantes o contravariantes.</span><span class="sxs-lookup"><span data-stu-id="5b580-104">You can declare generic type parameters in interfaces as covariant or contravariant.</span></span> <span data-ttu-id="5b580-105">La *covarianza* permite que los métodos de interfaz tengan tipos de valor devuelto más derivados que los que se definen en los parámetros de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="5b580-105">*Covariance* allows interface methods to have more derived return types than that defined by the generic type parameters.</span></span> <span data-ttu-id="5b580-106">La *contravarianza* permite que los métodos de interfaz tengan tipos de argumento menos derivados que los que se especifican en los parámetros genéricos.</span><span class="sxs-lookup"><span data-stu-id="5b580-106">*Contravariance* allows interface methods to have argument types that are less derived than that specified by the generic parameters.</span></span> <span data-ttu-id="5b580-107">Las interfaces genéricas que tienen parámetros de tipo genérico covariantes o contravariantes se llaman *variantes*.</span><span class="sxs-lookup"><span data-stu-id="5b580-107">A generic interface that has covariant or contravariant generic type parameters is called *variant*.</span></span>

> [!NOTE]
> <span data-ttu-id="5b580-108">En .NET Framework 4 se ha presentado la compatibilidad con la varianza para varias interfaces genéricas existentes.</span><span class="sxs-lookup"><span data-stu-id="5b580-108">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="5b580-109">Para obtener la lista de las interfaces variantes en el .NET Framework, vea [varianza en interfaces genéricas (Visual Basic)](variance-in-generic-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="5b580-109">For the list of the variant interfaces in the .NET Framework, see [Variance in Generic Interfaces (Visual Basic)](variance-in-generic-interfaces.md).</span></span>

## <a name="declaring-variant-generic-interfaces"></a><span data-ttu-id="5b580-110">Declarar interfaces genéricas variantes</span><span class="sxs-lookup"><span data-stu-id="5b580-110">Declaring Variant Generic Interfaces</span></span>

<span data-ttu-id="5b580-111">Puede declarar interfaces genéricas variantes mediante las palabras clave `in` y `out` para los parámetros de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="5b580-111">You can declare variant generic interfaces by using the `in` and `out` keywords for generic type parameters.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5b580-112">`ByRef` los parámetros de Visual Basic no pueden ser variantes.</span><span class="sxs-lookup"><span data-stu-id="5b580-112">`ByRef` parameters in Visual Basic cannot be variant.</span></span> <span data-ttu-id="5b580-113">Los tipos de valor tampoco admiten la varianza.</span><span class="sxs-lookup"><span data-stu-id="5b580-113">Value types also do not support variance.</span></span>

<span data-ttu-id="5b580-114">Puede declarar un parámetro de tipo genérico covariante mediante la palabra clave `out`.</span><span class="sxs-lookup"><span data-stu-id="5b580-114">You can declare a generic type parameter covariant by using the `out` keyword.</span></span> <span data-ttu-id="5b580-115">El tipo covariante debe cumplir las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="5b580-115">The covariant type must satisfy the following conditions:</span></span>

- <span data-ttu-id="5b580-116">El tipo se usa únicamente como tipo de valor devuelto de los métodos de interfaz, y no como tipo de los argumentos de método.</span><span class="sxs-lookup"><span data-stu-id="5b580-116">The type is used only as a return type of interface methods and not used as a type of method arguments.</span></span> <span data-ttu-id="5b580-117">Esto se muestra en el siguiente ejemplo, en el que el tipo `R` se declara como covariante.</span><span class="sxs-lookup"><span data-stu-id="5b580-117">This is illustrated in the following example, in which the type `R` is declared covariant.</span></span>

    ```vb
    Interface ICovariant(Of Out R)
        Function GetSomething() As R
        ' The following statement generates a compiler error.
        ' Sub SetSomething(ByVal sampleArg As R)
    End Interface
    ```

    <span data-ttu-id="5b580-118">Hay una excepción para esta regla.</span><span class="sxs-lookup"><span data-stu-id="5b580-118">There is one exception to this rule.</span></span> <span data-ttu-id="5b580-119">Si tiene un delegado genérico contravariante como parámetro de método, puede usar el tipo como parámetro de tipo genérico para el delegado.</span><span class="sxs-lookup"><span data-stu-id="5b580-119">If you have a contravariant generic delegate as a method parameter, you can use the type as a generic type parameter for the delegate.</span></span> <span data-ttu-id="5b580-120">Esto se muestra en el siguiente ejemplo con el tipo `R`.</span><span class="sxs-lookup"><span data-stu-id="5b580-120">This is illustrated by the type `R` in the following example.</span></span> <span data-ttu-id="5b580-121">Para obtener más información, vea [varianza en delegados (Visual Basic)](variance-in-delegates.md) y [usar la varianza para los delegados genéricos FUNC y Action (Visual Basic)](using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="5b580-121">For more information, see [Variance in Delegates (Visual Basic)](variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (Visual Basic)](using-variance-for-func-and-action-generic-delegates.md).</span></span>

    ```vb
    Interface ICovariant(Of Out R)
        Sub DoSomething(ByVal callback As Action(Of R))
    End Interface
    ```

- <span data-ttu-id="5b580-122">El tipo no se usa como restricción genérica para los métodos de interfaz.</span><span class="sxs-lookup"><span data-stu-id="5b580-122">The type is not used as a generic constraint for the interface methods.</span></span> <span data-ttu-id="5b580-123">Esto se muestra en el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="5b580-123">This is illustrated in the following code.</span></span>

    ```vb
    Interface ICovariant(Of Out R)
        ' The following statement generates a compiler error
        ' because you can use only contravariant or invariant types
        ' in generic constraints.
        ' Sub DoSomething(Of T As R)()
    End Interface
    ```

<span data-ttu-id="5b580-124">Puede declarar un parámetro de tipo genérico contravariante mediante la palabra clave `in`.</span><span class="sxs-lookup"><span data-stu-id="5b580-124">You can declare a generic type parameter contravariant by using the `in` keyword.</span></span> <span data-ttu-id="5b580-125">El tipo contravariante solo se puede usar como tipo de los argumentos de método, y no como tipo de valor devuelto de los métodos de interfaz.</span><span class="sxs-lookup"><span data-stu-id="5b580-125">The contravariant type can be used only as a type of method arguments and not as a return type of interface methods.</span></span> <span data-ttu-id="5b580-126">El tipo contravariante también se puede usar para las restricciones genéricas.</span><span class="sxs-lookup"><span data-stu-id="5b580-126">The contravariant type can also be used for generic constraints.</span></span> <span data-ttu-id="5b580-127">En el siguiente código se muestra cómo declarar una interfaz contravariante y cómo usar una restricción genérica para uno de sus métodos.</span><span class="sxs-lookup"><span data-stu-id="5b580-127">The following code shows how to declare a contravariant interface and use a generic constraint for one of its methods.</span></span>

```vb
Interface IContravariant(Of In A)
    Sub SetSomething(ByVal sampleArg As A)
    Sub DoSomething(Of T As A)()
    ' The following statement generates a compiler error.
    ' Function GetSomething() As A
End Interface
```

<span data-ttu-id="5b580-128">También se puede admitir la covarianza y la contravarianza en la misma interfaz, pero para distintos parámetros de tipo, como se muestra en el siguiente ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="5b580-128">It is also possible to support both covariance and contravariance in the same interface, but for different type parameters, as shown in the following code example.</span></span>

```vb
Interface IVariant(Of Out R, In A)
    Function GetSomething() As R
    Sub SetSomething(ByVal sampleArg As A)
    Function GetSetSomething(ByVal sampleArg As A) As R
End Interface
```

<span data-ttu-id="5b580-129">En Visual Basic, no se pueden declarar eventos en interfaces variantes sin especificar el tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="5b580-129">In Visual Basic, you can't declare events in variant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="5b580-130">Además, una interfaz variante no puede tener clases, enumeraciones o estructuras anidadas, pero puede tener interfaces anidadas.</span><span class="sxs-lookup"><span data-stu-id="5b580-130">Also, a variant interface can't have nested classes, enums, or structures, but it can have nested interfaces.</span></span> <span data-ttu-id="5b580-131">Esto se muestra en el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="5b580-131">This is illustrated in the following code.</span></span>

```vb
Interface ICovariant(Of Out R)
    ' The following statement generates a compiler error.
    ' Event SampleEvent()
    ' The following statement specifies the delegate type and
    ' does not generate an error.
    Event AnotherEvent As EventHandler

    ' The following statements generate compiler errors,
    ' because a variant interface cannot have
    ' nested enums, classes, or structures.

    'Enum SampleEnum : test : End Enum
    'Class SampleClass : End Class
    'Structure SampleStructure : Dim value As Integer : End Structure

    ' Variant interfaces can have nested interfaces.
    Interface INested : End Interface
End Interface
```

## <a name="implementing-variant-generic-interfaces"></a><span data-ttu-id="5b580-132">Implementar interfaces genéricas variantes</span><span class="sxs-lookup"><span data-stu-id="5b580-132">Implementing Variant Generic Interfaces</span></span>

<span data-ttu-id="5b580-133">Las interfaces genéricas variantes se implementan en las clases usando la misma sintaxis que se usa para las interfaces invariables.</span><span class="sxs-lookup"><span data-stu-id="5b580-133">You implement variant generic interfaces in classes by using the same syntax that is used for invariant interfaces.</span></span> <span data-ttu-id="5b580-134">En el siguiente ejemplo de código se muestra cómo implementar una interfaz covariante en una clase genérica.</span><span class="sxs-lookup"><span data-stu-id="5b580-134">The following code example shows how to implement a covariant interface in a generic class.</span></span>

```vb
Interface ICovariant(Of Out R)
    Function GetSomething() As R
End Interface

Class SampleImplementation(Of R)
    Implements ICovariant(Of R)
    Public Function GetSomething() As R _
    Implements ICovariant(Of R).GetSomething
        ' Some code.
    End Function
End Class
```

<span data-ttu-id="5b580-135">Las clases que implementan interfaces variantes son invariables.</span><span class="sxs-lookup"><span data-stu-id="5b580-135">Classes that implement variant interfaces are invariant.</span></span> <span data-ttu-id="5b580-136">Por ejemplo, considere el fragmento de código siguiente:</span><span class="sxs-lookup"><span data-stu-id="5b580-136">For example, consider the following code.</span></span>

```vb
 The interface is covariant.
Dim ibutton As ICovariant(Of Button) =
    New SampleImplementation(Of Button)
Dim iobj As ICovariant(Of Object) = ibutton

' The class is invariant.
Dim button As SampleImplementation(Of Button) =
    New SampleImplementation(Of Button)
' The following statement generates a compiler error
' because classes are invariant.
' Dim obj As SampleImplementation(Of Object) = button
```

## <a name="extending-variant-generic-interfaces"></a><span data-ttu-id="5b580-137">Extender interfaces genéricas variantes</span><span class="sxs-lookup"><span data-stu-id="5b580-137">Extending Variant Generic Interfaces</span></span>

<span data-ttu-id="5b580-138">Al extender una interfaz genérica variante, debe usar las palabras clave `in` y `out` para especificar de forma explícita si la interfaz derivada admite la varianza.</span><span class="sxs-lookup"><span data-stu-id="5b580-138">When you extend a variant generic interface, you have to use the `in` and `out` keywords to explicitly specify whether the derived interface supports variance.</span></span> <span data-ttu-id="5b580-139">El compilador no infiere la varianza de la interfaz que se va a extender.</span><span class="sxs-lookup"><span data-stu-id="5b580-139">The compiler does not infer the variance from the interface that is being extended.</span></span> <span data-ttu-id="5b580-140">Por ejemplo, observe las siguientes interfaces.</span><span class="sxs-lookup"><span data-stu-id="5b580-140">For example, consider the following interfaces.</span></span>

```vb
Interface ICovariant(Of Out T)
End Interface

Interface IInvariant(Of T)
    Inherits ICovariant(Of T)
End Interface

Interface IExtCovariant(Of Out T)
    Inherits ICovariant(Of T)
End Interface
```

<span data-ttu-id="5b580-141">En la `Invariant(Of T)` interfaz, el parámetro de tipo genérico `T` es invariable, mientras que en `IExtCovariant (Of Out T)` el parámetro de tipo es covariante, aunque ambas interfaces amplían la misma interfaz.</span><span class="sxs-lookup"><span data-stu-id="5b580-141">In the `Invariant(Of T)` interface, the generic type parameter `T` is invariant, whereas in `IExtCovariant (Of Out T)`the type parameter is covariant, although both interfaces extend the same interface.</span></span> <span data-ttu-id="5b580-142">La misma regla se aplica a los parámetros de tipo genérico contravariantes.</span><span class="sxs-lookup"><span data-stu-id="5b580-142">The same rule is applied to contravariant generic type parameters.</span></span>

<span data-ttu-id="5b580-143">Puede crear una interfaz que extienda la interfaz donde el parámetro de tipo genérico `T` es covariante y la interfaz donde es contravariante si, en la interfaz que va a extender, el parámetro de tipo genérico `T` es invariable.</span><span class="sxs-lookup"><span data-stu-id="5b580-143">You can create an interface that extends both the interface where the generic type parameter `T` is covariant and the interface where it is contravariant if in the extending interface the generic type parameter `T` is invariant.</span></span> <span data-ttu-id="5b580-144">Esto se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5b580-144">This is illustrated in the following code example.</span></span>

```vb
Interface ICovariant(Of Out T)
End Interface

Interface IContravariant(Of In T)
End Interface

Interface IInvariant(Of T)
    Inherits ICovariant(Of T), IContravariant(Of T)
End Interface
```

<span data-ttu-id="5b580-145">Pero si un parámetro de tipo genérico `T` se declara como covariante en una interfaz, no puede declararlo como contravariante en la interfaz extensible (o viceversa).</span><span class="sxs-lookup"><span data-stu-id="5b580-145">However, if a generic type parameter `T` is declared covariant in one interface, you cannot declare it contravariant in the extending interface, or vice versa.</span></span> <span data-ttu-id="5b580-146">Esto se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5b580-146">This is illustrated in the following code example.</span></span>

```vb
Interface ICovariant(Of Out T)
End Interface

' The following statements generate a compiler error.
' Interface ICoContraVariant(Of In T)
'     Inherits ICovariant(Of T)
' End Interface
```

### <a name="avoiding-ambiguity"></a><span data-ttu-id="5b580-147">Evitar la ambigüedad</span><span class="sxs-lookup"><span data-stu-id="5b580-147">Avoiding Ambiguity</span></span>

<span data-ttu-id="5b580-148">Al implementar interfaces genéricas variantes, la varianza a veces puede implicar ambigüedad.</span><span class="sxs-lookup"><span data-stu-id="5b580-148">When you implement variant generic interfaces, variance can sometimes lead to ambiguity.</span></span> <span data-ttu-id="5b580-149">Éste debería evitarse.</span><span class="sxs-lookup"><span data-stu-id="5b580-149">This should be avoided.</span></span>

<span data-ttu-id="5b580-150">Por ejemplo, si implementa explícitamente en una clase la misma interfaz genérica variante con distintos parámetros de tipo genérico, puede crear ambigüedad.</span><span class="sxs-lookup"><span data-stu-id="5b580-150">For example, if you explicitly implement the same variant generic interface with different generic type parameters in one class, it can create ambiguity.</span></span> <span data-ttu-id="5b580-151">El compilador no genera ningún error en este caso, pero no se especifica la implementación de interfaz que se elegirá en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5b580-151">The compiler does not produce an error in this case, but it is not specified which interface implementation will be chosen at runtime.</span></span> <span data-ttu-id="5b580-152">Esto podría provocar errores imperceptibles en el código.</span><span class="sxs-lookup"><span data-stu-id="5b580-152">This could lead to subtle bugs in your code.</span></span> <span data-ttu-id="5b580-153">Observe el siguiente ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="5b580-153">Consider the following code example.</span></span>

> [!NOTE]
> <span data-ttu-id="5b580-154">Con `Option Strict Off` , Visual Basic genera una advertencia del compilador cuando hay una implementación de interfaz ambigua.</span><span class="sxs-lookup"><span data-stu-id="5b580-154">With `Option Strict Off`, Visual Basic generates a compiler warning when there is an ambiguous interface implementation.</span></span> <span data-ttu-id="5b580-155">Con `Option Strict On` , Visual Basic genera un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="5b580-155">With `Option Strict On`, Visual Basic generates a compiler error.</span></span>

```vb
' Simple class hierarchy.
Class Animal
End Class

Class Cat
    Inherits Animal
End Class

Class Dog
    Inherits Animal
End Class

' This class introduces ambiguity
' because IEnumerable(Of Out T) is covariant.
Class Pets
    Implements IEnumerable(Of Cat), IEnumerable(Of Dog)

    Public Function GetEnumerator() As IEnumerator(Of Cat) _
        Implements IEnumerable(Of Cat).GetEnumerator
        Console.WriteLine("Cat")
        ' Some code.
    End Function

    Public Function GetEnumerator1() As IEnumerator(Of Dog) _
        Implements IEnumerable(Of Dog).GetEnumerator
        Console.WriteLine("Dog")
        ' Some code.
    End Function

    Public Function GetEnumerator2() As IEnumerator _
        Implements IEnumerable.GetEnumerator
        ' Some code.
    End Function
End Class

Sub Main()
    Dim pets As IEnumerable(Of Animal) = New Pets()
    pets.GetEnumerator()
End Sub
```

<span data-ttu-id="5b580-156">En este ejemplo no se especifica cómo elige el método `pets.GetEnumerator` entre `Cat` y `Dog`.</span><span class="sxs-lookup"><span data-stu-id="5b580-156">In this example, it is unspecified how the `pets.GetEnumerator` method chooses between `Cat` and `Dog`.</span></span> <span data-ttu-id="5b580-157">Esto podría producir problemas en el código.</span><span class="sxs-lookup"><span data-stu-id="5b580-157">This could cause problems in your code.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b580-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b580-158">See also</span></span>

- [<span data-ttu-id="5b580-159">Varianza en interfaces genéricas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b580-159">Variance in Generic Interfaces (Visual Basic)</span></span>](variance-in-generic-interfaces.md)
- [<span data-ttu-id="5b580-160">Usar la varianza para los delegados genéricos Func y Action (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b580-160">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](using-variance-for-func-and-action-generic-delegates.md)

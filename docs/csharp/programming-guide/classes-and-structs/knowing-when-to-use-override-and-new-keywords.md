---
title: 'Saber cuándo utilizar las palabras clave Override y New: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- override keyword [C#]
- new keyword [C#]
- polymorphism [C#], using override and new [C#]
ms.assetid: 323db184-b136-46fc-8839-007886e7e8b0
ms.openlocfilehash: 493c6c5f5bf47c6b2cd140ac0f6922f91ca4252b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79170265"
---
# <a name="knowing-when-to-use-override-and-new-keywords-c-programming-guide"></a><span data-ttu-id="a5d83-102">Saber cuándo utilizar las palabras clave Override y New (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="a5d83-102">Knowing When to Use Override and New Keywords (C# Programming Guide)</span></span>

<span data-ttu-id="a5d83-103">En C#, un método de una clase derivada puede tener el mismo nombre que un método de la clase base.</span><span class="sxs-lookup"><span data-stu-id="a5d83-103">In C#, a method in a derived class can have the same name as a method in the base class.</span></span> <span data-ttu-id="a5d83-104">Se puede especificar cómo interactúan los métodos mediante las palabras clave [new](../../language-reference/keywords/new-modifier.md) y [override](../../language-reference/keywords/override.md).</span><span class="sxs-lookup"><span data-stu-id="a5d83-104">You can specify how the methods interact by using the [new](../../language-reference/keywords/new-modifier.md) and [override](../../language-reference/keywords/override.md) keywords.</span></span> <span data-ttu-id="a5d83-105">El modificador `override`*extiende* el método de clase base `virtual` y el modificador `new`*oculta* un método de clase base accesible.</span><span class="sxs-lookup"><span data-stu-id="a5d83-105">The `override` modifier *extends* the base class `virtual` method, and the `new` modifier *hides* an accessible base class method.</span></span> <span data-ttu-id="a5d83-106">En los ejemplos de este tema se ilustra la diferencia.</span><span class="sxs-lookup"><span data-stu-id="a5d83-106">The difference is illustrated in the examples in this topic.</span></span>  
  
 <span data-ttu-id="a5d83-107">En una aplicación de consola, declare las dos clases siguientes, `BaseClass` y `DerivedClass`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-107">In a console application, declare the following two classes, `BaseClass` and `DerivedClass`.</span></span> <span data-ttu-id="a5d83-108">`DerivedClass` hereda de `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-108">`DerivedClass` inherits from `BaseClass`.</span></span>  
  
```csharp  
class BaseClass  
{  
    public void Method1()  
    {  
        Console.WriteLine("Base - Method1");  
    }  
}  
  
class DerivedClass : BaseClass  
{  
    public void Method2()  
    {  
        Console.WriteLine("Derived - Method2");  
    }  
}  
```  
  
 <span data-ttu-id="a5d83-109">En el método `Main`, declare las variables `bc`, `dc` y `bcdc`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-109">In the `Main` method, declare variables `bc`, `dc`, and `bcdc`.</span></span>  
  
- <span data-ttu-id="a5d83-110">`bc` es de tipo `BaseClass`, y su valor es de tipo `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-110">`bc` is of type `BaseClass`, and its value is of type `BaseClass`.</span></span>  
  
- <span data-ttu-id="a5d83-111">`dc` es de tipo `DerivedClass`, y su valor es de tipo `DerivedClass`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-111">`dc` is of type `DerivedClass`, and its value is of type `DerivedClass`.</span></span>  
  
- <span data-ttu-id="a5d83-112">`bcdc` es de tipo `BaseClass`, y su valor es de tipo `DerivedClass`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-112">`bcdc` is of type `BaseClass`, and its value is of type `DerivedClass`.</span></span> <span data-ttu-id="a5d83-113">Esta es la variable a la que hay que prestar atención.</span><span class="sxs-lookup"><span data-stu-id="a5d83-113">This is the variable to pay attention to.</span></span>  
  
 <span data-ttu-id="a5d83-114">Dado que `bc` y `bcdc` tienen el tipo `BaseClass`, solo pueden tener acceso directo a `Method1`, a menos que se use la conversión.</span><span class="sxs-lookup"><span data-stu-id="a5d83-114">Because `bc` and `bcdc` have type `BaseClass`, they can only directly access `Method1`, unless you use casting.</span></span> <span data-ttu-id="a5d83-115">La variable `dc` puede tener acceso a `Method1` y `Method2`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-115">Variable `dc` can access both `Method1` and `Method2`.</span></span> <span data-ttu-id="a5d83-116">Estas relaciones se muestran en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="a5d83-116">These relationships are shown in the following code.</span></span>  
  
```csharp  
class Program  
{  
    static void Main(string[] args)  
    {  
        BaseClass bc = new BaseClass();  
        DerivedClass dc = new DerivedClass();  
        BaseClass bcdc = new DerivedClass();  
  
        bc.Method1();  
        dc.Method1();  
        dc.Method2();  
        bcdc.Method1();  
    }  
    // Output:  
    // Base - Method1  
    // Base - Method1  
    // Derived - Method2  
    // Base - Method1  
}  
```  
  
 <span data-ttu-id="a5d83-117">Después, agregue el método `Method2` siguiente a `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-117">Next, add the following `Method2` method to `BaseClass`.</span></span> <span data-ttu-id="a5d83-118">La firma de este método coincide con la firma del método `Method2` de `DerivedClass`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-118">The signature of this method matches the signature of the `Method2` method in `DerivedClass`.</span></span>  
  
```csharp  
public void Method2()  
{  
    Console.WriteLine("Base - Method2");  
}  
```  
  
 <span data-ttu-id="a5d83-119">Dado que `BaseClass` ahora tiene un método `Method2`, se puede agregar una segunda instrucción de llamada para las variables de `BaseClass``bc` y `bcdc`, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="a5d83-119">Because `BaseClass` now has a `Method2` method, a second calling statement can be added for `BaseClass` variables `bc` and `bcdc`, as shown in the following code.</span></span>  
  
```csharp  
bc.Method1();  
bc.Method2();  
dc.Method1();  
dc.Method2();  
bcdc.Method1();  
bcdc.Method2();  
```  
  
 <span data-ttu-id="a5d83-120">Al compilar el proyecto, verá que la adición del método `Method2` de `BaseClass` genera una advertencia.</span><span class="sxs-lookup"><span data-stu-id="a5d83-120">When you build the project, you see that the addition of the `Method2` method in `BaseClass` causes a warning.</span></span> <span data-ttu-id="a5d83-121">La advertencia indica que el método `Method2` de `DerivedClass` oculta el método `Method2` de `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-121">The warning says that the `Method2` method in `DerivedClass` hides the `Method2` method in `BaseClass`.</span></span> <span data-ttu-id="a5d83-122">Se recomienda usar la palabra clave `new` en la definición de `Method2` si se pretende provocar ese resultado.</span><span class="sxs-lookup"><span data-stu-id="a5d83-122">You are advised to use the `new` keyword in the `Method2` definition if you intend to cause that result.</span></span> <span data-ttu-id="a5d83-123">Como alternativa, se puede cambiar el nombre de uno de los métodos `Method2` para resolver la advertencia, pero eso no siempre resulta práctico.</span><span class="sxs-lookup"><span data-stu-id="a5d83-123">Alternatively, you could rename one of the `Method2` methods to resolve the warning, but that is not always practical.</span></span>  
  
 <span data-ttu-id="a5d83-124">Antes de agregar `new`, ejecute el programa para ver el resultado producido por las instrucciones adicionales que realizan la llamada.</span><span class="sxs-lookup"><span data-stu-id="a5d83-124">Before adding `new`, run the program to see the output produced by the additional calling statements.</span></span> <span data-ttu-id="a5d83-125">Se muestran los resultados siguientes.</span><span class="sxs-lookup"><span data-stu-id="a5d83-125">The following results are displayed.</span></span>  
  
```csharp  
// Output:  
// Base - Method1  
// Base - Method2  
// Base - Method1  
// Derived - Method2  
// Base - Method1  
// Base - Method2  
```  
  
 <span data-ttu-id="a5d83-126">La palabra clave `new` conserva las relaciones que generan ese resultado, pero se suprime la advertencia.</span><span class="sxs-lookup"><span data-stu-id="a5d83-126">The `new` keyword preserves the relationships that produce that output, but it suppresses the warning.</span></span> <span data-ttu-id="a5d83-127">Las variables de tipo `BaseClass` siguen teniendo acceso a los miembros de `BaseClass` y la variable de tipo `DerivedClass` sigue teniendo acceso a los miembros de `DerivedClass` en primer lugar y, después, tiene en cuenta los miembros heredados de `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-127">The variables that have type `BaseClass` continue to access the members of `BaseClass`, and the variable that has type `DerivedClass` continues to access members in `DerivedClass` first, and then to consider members inherited from `BaseClass`.</span></span>  
  
 <span data-ttu-id="a5d83-128">Para suprimir la advertencia, agregue el modificador `new` a la definición de `Method2` en `DerivedClass`, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="a5d83-128">To suppress the warning, add the `new` modifier to the definition of `Method2` in `DerivedClass`, as shown in the following code.</span></span> <span data-ttu-id="a5d83-129">Se puede agregar el modificador antes o después de `public`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-129">The modifier can be added before or after `public`.</span></span>  
  
```csharp  
public new void Method2()  
{  
    Console.WriteLine("Derived - Method2");  
}  
```  
  
 <span data-ttu-id="a5d83-130">Vuelva a ejecutar el programa para comprobar que el resultado no ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="a5d83-130">Run the program again to verify that the output has not changed.</span></span> <span data-ttu-id="a5d83-131">Compruebe también que ya no aparece la advertencia.</span><span class="sxs-lookup"><span data-stu-id="a5d83-131">Also verify that the warning no longer appears.</span></span> <span data-ttu-id="a5d83-132">Mediante el uso de `new`, afirma que es consciente de que el miembro que modifica oculta un miembro heredado de la clase base.</span><span class="sxs-lookup"><span data-stu-id="a5d83-132">By using `new`, you are asserting that you are aware that the member that it modifies hides a member that is inherited from the base class.</span></span> <span data-ttu-id="a5d83-133">Para más información sobre la ocultación de nombres a través de la herencia, vea [new (Modificador, Referencia de C#)](../../language-reference/keywords/new-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="a5d83-133">For more information about name hiding through inheritance, see [new Modifier](../../language-reference/keywords/new-modifier.md).</span></span>  
  
 <span data-ttu-id="a5d83-134">Para contrastar este comportamiento con los efectos de usar `override`, agregue el método siguiente a `DerivedClass`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-134">To contrast this behavior to the effects of using `override`, add the following method to `DerivedClass`.</span></span> <span data-ttu-id="a5d83-135">Se puede agregar el modificador `override` antes o después de `public`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-135">The `override` modifier can be added before or after `public`.</span></span>  
  
```csharp  
public override void Method1()  
{  
    Console.WriteLine("Derived - Method1");  
}  
```  
  
 <span data-ttu-id="a5d83-136">Agregue el modificador `virtual` a la definición de `Method1` en `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-136">Add the `virtual` modifier to the definition of `Method1` in `BaseClass`.</span></span> <span data-ttu-id="a5d83-137">Se puede agregar el modificador `virtual` antes o después de `public`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-137">The `virtual` modifier can be added before or after `public`.</span></span>  
  
```csharp  
public virtual void Method1()  
{  
    Console.WriteLine("Base - Method1");  
}  
```  
  
 <span data-ttu-id="a5d83-138">Vuelva a ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a5d83-138">Run the project again.</span></span> <span data-ttu-id="a5d83-139">Observe especialmente las dos últimas líneas del resultado siguiente.</span><span class="sxs-lookup"><span data-stu-id="a5d83-139">Notice especially the last two lines of the following output.</span></span>  
  
```csharp  
// Output:  
// Base - Method1  
// Base - Method2  
// Derived - Method1  
// Derived - Method2  
// Derived - Method1  
// Base - Method2  
```  
  
 <span data-ttu-id="a5d83-140">El uso del modificador `override` permite que `bcdc` tenga acceso al método `Method1` que se define en `DerivedClass`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-140">The use of the `override` modifier enables `bcdc` to access the `Method1` method that is defined in `DerivedClass`.</span></span> <span data-ttu-id="a5d83-141">Normalmente, es el comportamiento deseado en jerarquías de herencia.</span><span class="sxs-lookup"><span data-stu-id="a5d83-141">Typically, that is the desired behavior in inheritance hierarchies.</span></span> <span data-ttu-id="a5d83-142">La intención es que los objetos que tienen valores que se crean a partir de la clase derivada usen los métodos que se definen en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="a5d83-142">You want objects that have values that are created from the derived class to use the methods that are defined in the derived class.</span></span> <span data-ttu-id="a5d83-143">Ese comportamiento se consigue mediante el uso de `override` para extender el método de clase base.</span><span class="sxs-lookup"><span data-stu-id="a5d83-143">You achieve that behavior by using `override` to extend the base class method.</span></span>  
  
 <span data-ttu-id="a5d83-144">El código siguiente contiene el ejemplo completo.</span><span class="sxs-lookup"><span data-stu-id="a5d83-144">The following code contains the full example.</span></span>  
  
```csharp  
using System;  
using System.Text;  
  
namespace OverrideAndNew  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            BaseClass bc = new BaseClass();  
            DerivedClass dc = new DerivedClass();  
            BaseClass bcdc = new DerivedClass();  
  
            // The following two calls do what you would expect. They call  
            // the methods that are defined in BaseClass.  
            bc.Method1();  
            bc.Method2();  
            // Output:  
            // Base - Method1  
            // Base - Method2  
  
            // The following two calls do what you would expect. They call  
            // the methods that are defined in DerivedClass.  
            dc.Method1();  
            dc.Method2();  
            // Output:  
            // Derived - Method1  
            // Derived - Method2  
  
            // The following two calls produce different results, depending
            // on whether override (Method1) or new (Method2) is used.  
            bcdc.Method1();  
            bcdc.Method2();  
            // Output:  
            // Derived - Method1  
            // Base - Method2  
        }  
    }  
  
    class BaseClass  
    {  
        public virtual void Method1()  
        {  
            Console.WriteLine("Base - Method1");  
        }  
  
        public virtual void Method2()  
        {  
            Console.WriteLine("Base - Method2");  
        }  
    }  
  
    class DerivedClass : BaseClass  
    {  
        public override void Method1()  
        {  
            Console.WriteLine("Derived - Method1");  
        }  
  
        public new void Method2()  
        {  
            Console.WriteLine("Derived - Method2");  
        }  
    }  
}  
```  
  
 <span data-ttu-id="a5d83-145">En el ejemplo siguiente se muestra un comportamiento similar en un contexto diferente.</span><span class="sxs-lookup"><span data-stu-id="a5d83-145">The following example illustrates similar behavior in a different context.</span></span> <span data-ttu-id="a5d83-146">El ejemplo define tres clases: una clase base denominada `Car` y dos clases que se derivan de ella, `ConvertibleCar` y `Minivan`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-146">The example defines three classes: a base class named `Car` and two classes that are derived from it, `ConvertibleCar` and `Minivan`.</span></span> <span data-ttu-id="a5d83-147">La clase base contiene un método `DescribeCar`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-147">The base class contains a `DescribeCar` method.</span></span> <span data-ttu-id="a5d83-148">El método muestra una descripción básica de un automóvil y, después, llama a `ShowDetails` para proporcionar información adicional.</span><span class="sxs-lookup"><span data-stu-id="a5d83-148">The method displays a basic description of a car, and then calls `ShowDetails` to provide additional information.</span></span> <span data-ttu-id="a5d83-149">Cada una de las tres clases define un método `ShowDetails`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-149">Each of the three classes defines a `ShowDetails` method.</span></span> <span data-ttu-id="a5d83-150">El modificador `new` se usa para definir `ShowDetails` en la clase `ConvertibleCar`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-150">The `new` modifier is used to define `ShowDetails` in the `ConvertibleCar` class.</span></span> <span data-ttu-id="a5d83-151">El modificador `override` se usa para definir `ShowDetails` en la clase `Minivan`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-151">The `override` modifier is used to define `ShowDetails` in the `Minivan` class.</span></span>  
  
```csharp  
// Define the base class, Car. The class defines two methods,  
// DescribeCar and ShowDetails. DescribeCar calls ShowDetails, and each derived  
// class also defines a ShowDetails method. The example tests which version of  
// ShowDetails is selected, the base class method or the derived class method.  
class Car  
{  
    public void DescribeCar()  
    {  
        System.Console.WriteLine("Four wheels and an engine.");  
        ShowDetails();  
    }  
  
    public virtual void ShowDetails()  
    {  
        System.Console.WriteLine("Standard transportation.");  
    }  
}  
  
// Define the derived classes.  
  
// Class ConvertibleCar uses the new modifier to acknowledge that ShowDetails  
// hides the base class method.  
class ConvertibleCar : Car  
{  
    public new void ShowDetails()  
    {  
        System.Console.WriteLine("A roof that opens up.");  
    }  
}  
  
// Class Minivan uses the override modifier to specify that ShowDetails  
// extends the base class method.  
class Minivan : Car  
{  
    public override void ShowDetails()  
    {  
        System.Console.WriteLine("Carries seven people.");  
    }  
}  
```  
  
 <span data-ttu-id="a5d83-152">El ejemplo comprueba la versión de `ShowDetails` que se llama.</span><span class="sxs-lookup"><span data-stu-id="a5d83-152">The example tests which version of `ShowDetails` is called.</span></span> <span data-ttu-id="a5d83-153">El siguiente método, `TestCars1`, declara una instancia de cada clase y, después, llama a `DescribeCar` en cada instancia.</span><span class="sxs-lookup"><span data-stu-id="a5d83-153">The following method, `TestCars1`, declares an instance of each class, and then calls `DescribeCar` on each instance.</span></span>  
  
```csharp  
public static void TestCars1()  
{  
    System.Console.WriteLine("\nTestCars1");  
    System.Console.WriteLine("----------");  
  
    Car car1 = new Car();  
    car1.DescribeCar();  
    System.Console.WriteLine("----------");  
  
    // Notice the output from this test case. The new modifier is  
    // used in the definition of ShowDetails in the ConvertibleCar  
    // class.
  
    ConvertibleCar car2 = new ConvertibleCar();  
    car2.DescribeCar();  
    System.Console.WriteLine("----------");  
  
    Minivan car3 = new Minivan();  
    car3.DescribeCar();  
    System.Console.WriteLine("----------");  
}  
```  
  
 <span data-ttu-id="a5d83-154">`TestCars1` genera el siguiente resultado.</span><span class="sxs-lookup"><span data-stu-id="a5d83-154">`TestCars1` produces the following output.</span></span> <span data-ttu-id="a5d83-155">Observe especialmente los resultados de `car2`, que probablemente no son los que se esperaban.</span><span class="sxs-lookup"><span data-stu-id="a5d83-155">Notice especially the results for `car2`, which probably are not what you expected.</span></span> <span data-ttu-id="a5d83-156">El tipo de objeto es `ConvertibleCar`, pero `DescribeCar` no tiene acceso a la versión de `ShowDetails` que se define en la clase `ConvertibleCar` porque ese método se declara con el modificador `new`, no con el modificador `override`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-156">The type of the object is `ConvertibleCar`, but `DescribeCar` does not access the version of `ShowDetails` that is defined in the `ConvertibleCar` class because that method is declared with the `new` modifier, not the `override` modifier.</span></span> <span data-ttu-id="a5d83-157">Como resultado, un objeto `ConvertibleCar` muestra la misma descripción que un objeto `Car`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-157">As a result, a `ConvertibleCar` object displays the same description as a `Car` object.</span></span> <span data-ttu-id="a5d83-158">Compare los resultados de `car3`, que es un objeto `Minivan`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-158">Contrast the results for `car3`, which is a `Minivan` object.</span></span> <span data-ttu-id="a5d83-159">En este caso, el método `ShowDetails` que se declara en la clase `Minivan` invalida el método `ShowDetails` que se declara en la clase `Car`, y en la descripción que se muestra se describe una furgoneta.</span><span class="sxs-lookup"><span data-stu-id="a5d83-159">In this case, the `ShowDetails` method that is declared in the `Minivan` class overrides the `ShowDetails` method that is declared in the `Car` class, and the description that is displayed describes a minivan.</span></span>  
  
```csharp  
// TestCars1  
// ----------  
// Four wheels and an engine.  
// Standard transportation.  
// ----------  
// Four wheels and an engine.  
// Standard transportation.  
// ----------  
// Four wheels and an engine.  
// Carries seven people.  
// ----------  
```  
  
 <span data-ttu-id="a5d83-160">`TestCars2` crea una lista de objetos que tienen el tipo `Car`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-160">`TestCars2` creates a list of objects that have type `Car`.</span></span> <span data-ttu-id="a5d83-161">Se crean instancias de los valores de los objetos desde las clases `Car`, `ConvertibleCar` y `Minivan`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-161">The values of the objects are instantiated from the `Car`, `ConvertibleCar`, and `Minivan` classes.</span></span> <span data-ttu-id="a5d83-162">`DescribeCar` se llama en cada elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="a5d83-162">`DescribeCar` is called on each element of the list.</span></span> <span data-ttu-id="a5d83-163">En el código siguiente se muestra la definición de `TestCars2`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-163">The following code shows the definition of `TestCars2`.</span></span>  
  
```csharp  
public static void TestCars2()  
{  
    System.Console.WriteLine("\nTestCars2");  
    System.Console.WriteLine("----------");  
  
    var cars = new List<Car> { new Car(), new ConvertibleCar(),
        new Minivan() };  
  
    foreach (var car in cars)  
    {  
        car.DescribeCar();  
        System.Console.WriteLine("----------");  
    }  
}  
```  
  
 <span data-ttu-id="a5d83-164">Se muestra el siguiente resultado.</span><span class="sxs-lookup"><span data-stu-id="a5d83-164">The following output is displayed.</span></span> <span data-ttu-id="a5d83-165">Observe que es el mismo resultado mostrado por `TestCars1`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-165">Notice that it is the same as the output that is displayed by `TestCars1`.</span></span> <span data-ttu-id="a5d83-166">El método `ShowDetails` de la clase `ConvertibleCar` no se llama, independientemente de si el tipo de objeto es `ConvertibleCar`, como en `TestCars1`, o `Car` como en `TestCars2`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-166">The `ShowDetails` method of the `ConvertibleCar` class is not called, regardless of whether the type of the object is `ConvertibleCar`, as in `TestCars1`, or `Car`, as in `TestCars2`.</span></span> <span data-ttu-id="a5d83-167">Por el contrario, `car3` llama al método `ShowDetails` desde la clase `Minivan` en ambos casos, independientemente de que tenga el tipo `Minivan` o `Car`.</span><span class="sxs-lookup"><span data-stu-id="a5d83-167">Conversely, `car3` calls the `ShowDetails` method from the `Minivan` class in both cases, whether it has type `Minivan` or type `Car`.</span></span>  
  
```csharp  
// TestCars2  
// ----------  
// Four wheels and an engine.  
// Standard transportation.  
// ----------  
// Four wheels and an engine.  
// Standard transportation.  
// ----------  
// Four wheels and an engine.  
// Carries seven people.  
// ----------  
```  
  
 <span data-ttu-id="a5d83-168">Los métodos `TestCars3` y `TestCars4` completan el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a5d83-168">Methods `TestCars3` and `TestCars4` complete the example.</span></span> <span data-ttu-id="a5d83-169">Estos métodos llaman directamente a `ShowDetails`, primero desde los objetos declarados con el tipo `ConvertibleCar` y `Minivan` (`TestCars3`), y después desde los objetos declarados con el tipo `Car` (`TestCars4`).</span><span class="sxs-lookup"><span data-stu-id="a5d83-169">These methods call `ShowDetails` directly, first from objects declared to have type `ConvertibleCar` and `Minivan` (`TestCars3`), then from objects declared to have type `Car` (`TestCars4`).</span></span> <span data-ttu-id="a5d83-170">En el código siguiente se definen estos dos métodos.</span><span class="sxs-lookup"><span data-stu-id="a5d83-170">The following code defines these two methods.</span></span>  
  
```csharp  
public static void TestCars3()  
{  
    System.Console.WriteLine("\nTestCars3");  
    System.Console.WriteLine("----------");  
    ConvertibleCar car2 = new ConvertibleCar();  
    Minivan car3 = new Minivan();  
    car2.ShowDetails();  
    car3.ShowDetails();  
}  
  
public static void TestCars4()  
{  
    System.Console.WriteLine("\nTestCars4");  
    System.Console.WriteLine("----------");  
    Car car2 = new ConvertibleCar();  
    Car car3 = new Minivan();  
    car2.ShowDetails();  
    car3.ShowDetails();  
}  
```  
  
 <span data-ttu-id="a5d83-171">Los métodos generan el siguiente resultado, que se corresponde a los resultados del primer ejemplo de este tema.</span><span class="sxs-lookup"><span data-stu-id="a5d83-171">The methods produce the following output, which corresponds to the results from the first example in this topic.</span></span>  
  
```csharp  
// TestCars3  
// ----------  
// A roof that opens up.  
// Carries seven people.  
  
// TestCars4  
// ----------  
// Standard transportation.  
// Carries seven people.  
```  
  
 <span data-ttu-id="a5d83-172">En el código siguiente se muestra el proyecto completo y sus resultados.</span><span class="sxs-lookup"><span data-stu-id="a5d83-172">The following code shows the complete project and its output.</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
  
namespace OverrideAndNew2  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Declare objects of the derived classes and test which version  
            // of ShowDetails is run, base or derived.  
            TestCars1();  
  
            // Declare objects of the base class, instantiated with the  
            // derived classes, and repeat the tests.  
            TestCars2();  
  
            // Declare objects of the derived classes and call ShowDetails  
            // directly.  
            TestCars3();  
  
            // Declare objects of the base class, instantiated with the  
            // derived classes, and repeat the tests.  
            TestCars4();  
        }  
  
        public static void TestCars1()  
        {  
            System.Console.WriteLine("\nTestCars1");  
            System.Console.WriteLine("----------");  
  
            Car car1 = new Car();  
            car1.DescribeCar();  
            System.Console.WriteLine("----------");  
  
            // Notice the output from this test case. The new modifier is  
            // used in the definition of ShowDetails in the ConvertibleCar  
            // class.
            ConvertibleCar car2 = new ConvertibleCar();  
            car2.DescribeCar();  
            System.Console.WriteLine("----------");  
  
            Minivan car3 = new Minivan();  
            car3.DescribeCar();  
            System.Console.WriteLine("----------");  
        }  
        // Output:  
        // TestCars1  
        // ----------  
        // Four wheels and an engine.  
        // Standard transportation.  
        // ----------  
        // Four wheels and an engine.  
        // Standard transportation.  
        // ----------  
        // Four wheels and an engine.  
        // Carries seven people.  
        // ----------  
  
        public static void TestCars2()  
        {  
            System.Console.WriteLine("\nTestCars2");  
            System.Console.WriteLine("----------");  
  
            var cars = new List<Car> { new Car(), new ConvertibleCar(),
                new Minivan() };  
  
            foreach (var car in cars)  
            {  
                car.DescribeCar();  
                System.Console.WriteLine("----------");  
            }  
        }  
        // Output:  
        // TestCars2  
        // ----------  
        // Four wheels and an engine.  
        // Standard transportation.  
        // ----------  
        // Four wheels and an engine.  
        // Standard transportation.  
        // ----------  
        // Four wheels and an engine.  
        // Carries seven people.  
        // ----------  
  
        public static void TestCars3()  
        {  
            System.Console.WriteLine("\nTestCars3");  
            System.Console.WriteLine("----------");  
            ConvertibleCar car2 = new ConvertibleCar();  
            Minivan car3 = new Minivan();  
            car2.ShowDetails();  
            car3.ShowDetails();  
        }  
        // Output:  
        // TestCars3  
        // ----------  
        // A roof that opens up.  
        // Carries seven people.  
  
        public static void TestCars4()  
        {  
            System.Console.WriteLine("\nTestCars4");  
            System.Console.WriteLine("----------");  
            Car car2 = new ConvertibleCar();  
            Car car3 = new Minivan();  
            car2.ShowDetails();  
            car3.ShowDetails();  
        }  
        // Output:  
        // TestCars4  
        // ----------  
        // Standard transportation.  
        // Carries seven people.  
    }  
  
    // Define the base class, Car. The class defines two virtual methods,  
    // DescribeCar and ShowDetails. DescribeCar calls ShowDetails, and each derived  
    // class also defines a ShowDetails method. The example tests which version of  
    // ShowDetails is used, the base class method or the derived class method.  
    class Car  
    {  
        public virtual void DescribeCar()  
        {  
            System.Console.WriteLine("Four wheels and an engine.");  
            ShowDetails();  
        }  
  
        public virtual void ShowDetails()  
        {  
            System.Console.WriteLine("Standard transportation.");  
        }  
    }  
  
    // Define the derived classes.  
  
    // Class ConvertibleCar uses the new modifier to acknowledge that ShowDetails  
    // hides the base class method.  
    class ConvertibleCar : Car  
    {  
        public new void ShowDetails()  
        {  
            System.Console.WriteLine("A roof that opens up.");  
        }  
    }  
  
    // Class Minivan uses the override modifier to specify that ShowDetails  
    // extends the base class method.  
    class Minivan : Car  
    {  
        public override void ShowDetails()  
        {  
            System.Console.WriteLine("Carries seven people.");  
        }  
    }  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a5d83-173">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5d83-173">See also</span></span>

- [<span data-ttu-id="a5d83-174">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="a5d83-174">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a5d83-175">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="a5d83-175">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="a5d83-176">Control de versiones con las palabras clave Override y New</span><span class="sxs-lookup"><span data-stu-id="a5d83-176">Versioning with the Override and New Keywords</span></span>](./versioning-with-the-override-and-new-keywords.md)
- [<span data-ttu-id="a5d83-177">base</span><span class="sxs-lookup"><span data-stu-id="a5d83-177">base</span></span>](../../language-reference/keywords/base.md)
- [<span data-ttu-id="a5d83-178">abstract</span><span class="sxs-lookup"><span data-stu-id="a5d83-178">abstract</span></span>](../../language-reference/keywords/abstract.md)

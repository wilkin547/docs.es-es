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
# <a name="knowing-when-to-use-override-and-new-keywords-c-programming-guide"></a>Saber cuándo utilizar las palabras clave Override y New (Guía de programación de C#)

En C#, un método de una clase derivada puede tener el mismo nombre que un método de la clase base. Se puede especificar cómo interactúan los métodos mediante las palabras clave [new](../../language-reference/keywords/new-modifier.md) y [override](../../language-reference/keywords/override.md). El modificador `override`*extiende* el método de clase base `virtual` y el modificador `new`*oculta* un método de clase base accesible. En los ejemplos de este tema se ilustra la diferencia.  
  
 En una aplicación de consola, declare las dos clases siguientes, `BaseClass` y `DerivedClass`. `DerivedClass` hereda de `BaseClass`.  
  
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
  
 En el método `Main`, declare las variables `bc`, `dc` y `bcdc`.  
  
- `bc` es de tipo `BaseClass`, y su valor es de tipo `BaseClass`.  
  
- `dc` es de tipo `DerivedClass`, y su valor es de tipo `DerivedClass`.  
  
- `bcdc` es de tipo `BaseClass`, y su valor es de tipo `DerivedClass`. Esta es la variable a la que hay que prestar atención.  
  
 Dado que `bc` y `bcdc` tienen el tipo `BaseClass`, solo pueden tener acceso directo a `Method1`, a menos que se use la conversión. La variable `dc` puede tener acceso a `Method1` y `Method2`. Estas relaciones se muestran en el código siguiente.  
  
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
  
 Después, agregue el método `Method2` siguiente a `BaseClass`. La firma de este método coincide con la firma del método `Method2` de `DerivedClass`.  
  
```csharp  
public void Method2()  
{  
    Console.WriteLine("Base - Method2");  
}  
```  
  
 Dado que `BaseClass` ahora tiene un método `Method2`, se puede agregar una segunda instrucción de llamada para las variables de `BaseClass``bc` y `bcdc`, como se muestra en el código siguiente.  
  
```csharp  
bc.Method1();  
bc.Method2();  
dc.Method1();  
dc.Method2();  
bcdc.Method1();  
bcdc.Method2();  
```  
  
 Al compilar el proyecto, verá que la adición del método `Method2` de `BaseClass` genera una advertencia. La advertencia indica que el método `Method2` de `DerivedClass` oculta el método `Method2` de `BaseClass`. Se recomienda usar la palabra clave `new` en la definición de `Method2` si se pretende provocar ese resultado. Como alternativa, se puede cambiar el nombre de uno de los métodos `Method2` para resolver la advertencia, pero eso no siempre resulta práctico.  
  
 Antes de agregar `new`, ejecute el programa para ver el resultado producido por las instrucciones adicionales que realizan la llamada. Se muestran los resultados siguientes.  
  
```csharp  
// Output:  
// Base - Method1  
// Base - Method2  
// Base - Method1  
// Derived - Method2  
// Base - Method1  
// Base - Method2  
```  
  
 La palabra clave `new` conserva las relaciones que generan ese resultado, pero se suprime la advertencia. Las variables de tipo `BaseClass` siguen teniendo acceso a los miembros de `BaseClass` y la variable de tipo `DerivedClass` sigue teniendo acceso a los miembros de `DerivedClass` en primer lugar y, después, tiene en cuenta los miembros heredados de `BaseClass`.  
  
 Para suprimir la advertencia, agregue el modificador `new` a la definición de `Method2` en `DerivedClass`, como se muestra en el código siguiente. Se puede agregar el modificador antes o después de `public`.  
  
```csharp  
public new void Method2()  
{  
    Console.WriteLine("Derived - Method2");  
}  
```  
  
 Vuelva a ejecutar el programa para comprobar que el resultado no ha cambiado. Compruebe también que ya no aparece la advertencia. Mediante el uso de `new`, afirma que es consciente de que el miembro que modifica oculta un miembro heredado de la clase base. Para más información sobre la ocultación de nombres a través de la herencia, vea [new (Modificador, Referencia de C#)](../../language-reference/keywords/new-modifier.md).  
  
 Para contrastar este comportamiento con los efectos de usar `override`, agregue el método siguiente a `DerivedClass`. Se puede agregar el modificador `override` antes o después de `public`.  
  
```csharp  
public override void Method1()  
{  
    Console.WriteLine("Derived - Method1");  
}  
```  
  
 Agregue el modificador `virtual` a la definición de `Method1` en `BaseClass`. Se puede agregar el modificador `virtual` antes o después de `public`.  
  
```csharp  
public virtual void Method1()  
{  
    Console.WriteLine("Base - Method1");  
}  
```  
  
 Vuelva a ejecutar el proyecto. Observe especialmente las dos últimas líneas del resultado siguiente.  
  
```csharp  
// Output:  
// Base - Method1  
// Base - Method2  
// Derived - Method1  
// Derived - Method2  
// Derived - Method1  
// Base - Method2  
```  
  
 El uso del modificador `override` permite que `bcdc` tenga acceso al método `Method1` que se define en `DerivedClass`. Normalmente, es el comportamiento deseado en jerarquías de herencia. La intención es que los objetos que tienen valores que se crean a partir de la clase derivada usen los métodos que se definen en la clase derivada. Ese comportamiento se consigue mediante el uso de `override` para extender el método de clase base.  
  
 El código siguiente contiene el ejemplo completo.  
  
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
  
 En el ejemplo siguiente se muestra un comportamiento similar en un contexto diferente. El ejemplo define tres clases: una clase base denominada `Car` y dos clases que se derivan de ella, `ConvertibleCar` y `Minivan`. La clase base contiene un método `DescribeCar`. El método muestra una descripción básica de un automóvil y, después, llama a `ShowDetails` para proporcionar información adicional. Cada una de las tres clases define un método `ShowDetails`. El modificador `new` se usa para definir `ShowDetails` en la clase `ConvertibleCar`. El modificador `override` se usa para definir `ShowDetails` en la clase `Minivan`.  
  
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
  
 El ejemplo comprueba la versión de `ShowDetails` que se llama. El siguiente método, `TestCars1`, declara una instancia de cada clase y, después, llama a `DescribeCar` en cada instancia.  
  
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
  
 `TestCars1` genera el siguiente resultado. Observe especialmente los resultados de `car2`, que probablemente no son los que se esperaban. El tipo de objeto es `ConvertibleCar`, pero `DescribeCar` no tiene acceso a la versión de `ShowDetails` que se define en la clase `ConvertibleCar` porque ese método se declara con el modificador `new`, no con el modificador `override`. Como resultado, un objeto `ConvertibleCar` muestra la misma descripción que un objeto `Car`. Compare los resultados de `car3`, que es un objeto `Minivan`. En este caso, el método `ShowDetails` que se declara en la clase `Minivan` invalida el método `ShowDetails` que se declara en la clase `Car`, y en la descripción que se muestra se describe una furgoneta.  
  
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
  
 `TestCars2` crea una lista de objetos que tienen el tipo `Car`. Se crean instancias de los valores de los objetos desde las clases `Car`, `ConvertibleCar` y `Minivan`. `DescribeCar` se llama en cada elemento de la lista. En el código siguiente se muestra la definición de `TestCars2`.  
  
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
  
 Se muestra el siguiente resultado. Observe que es el mismo resultado mostrado por `TestCars1`. El método `ShowDetails` de la clase `ConvertibleCar` no se llama, independientemente de si el tipo de objeto es `ConvertibleCar`, como en `TestCars1`, o `Car` como en `TestCars2`. Por el contrario, `car3` llama al método `ShowDetails` desde la clase `Minivan` en ambos casos, independientemente de que tenga el tipo `Minivan` o `Car`.  
  
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
  
 Los métodos `TestCars3` y `TestCars4` completan el ejemplo. Estos métodos llaman directamente a `ShowDetails`, primero desde los objetos declarados con el tipo `ConvertibleCar` y `Minivan` (`TestCars3`), y después desde los objetos declarados con el tipo `Car` (`TestCars4`). En el código siguiente se definen estos dos métodos.  
  
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
  
 Los métodos generan el siguiente resultado, que se corresponde a los resultados del primer ejemplo de este tema.  
  
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
  
 En el código siguiente se muestra el proyecto completo y sus resultados.  
  
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
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Clases y structs](./index.md)
- [Control de versiones con las palabras clave Override y New](./versioning-with-the-override-and-new-keywords.md)
- [base](../../language-reference/keywords/base.md)
- [abstract](../../language-reference/keywords/abstract.md)

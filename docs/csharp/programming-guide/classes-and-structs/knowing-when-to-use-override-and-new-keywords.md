---
title: "Saber cu&#225;ndo utilizar las palabras clave Override y New (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "new (palabra clave) [C#]"
  - "override (palabra clave) [C#]"
  - "polimorfismo [C#], utilizar override y new [C#]"
ms.assetid: 323db184-b136-46fc-8839-007886e7e8b0
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Saber cu&#225;ndo utilizar las palabras clave Override y New (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

En C\#, un método de una clase derivada puede tener el mismo nombre que un método de la clase base.  Puede especificar cómo interactúan los métodos mediante las palabras clave [new](../../../csharp/language-reference/keywords/new.md) y [override](../../../csharp/language-reference/keywords/override.md).  El modificador `override` *extiende* el método de la clase base y el modificador `new` lo *oculta*.  La diferencia se muestra en los ejemplos de este tema.  
  
 Declare las dos clases siguientes, `BaseClass` y `DerivedClass` en una aplicación de consola.  `DerivedClass` hereda de `BaseClass`.  
  
```c#  
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
  
-   `bc` es de tipo `BaseClass`, y su valor es de tipo `BaseClass`.  
  
-   `dc` es de tipo `DerivedClass`, y su valor es de tipo `DerivedClass`.  
  
-   `bcdc` es de tipo `BaseClass`, y su valor es de tipo `DerivedClass`.  Esta es la variable a la que hay que prestar atención.  
  
 Dado que `bc` y `bcdc` tienen el tipo `BaseClass`, solo pueden tener acceso directamente a `Method1`, a menos que se utilice la conversión.  La variable `dc` puede tener acceso tanto a `Method1` como a `Method2`.  Estas relaciones se muestran en el código siguiente.  
  
```c#  
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
  
 A continuación, agregue el siguiente método `Method2` a `BaseClass`.  La firma de este método coincide con la del método `Method2` en `DerivedClass`.  
  
```c#  
public void Method2()  
{  
    Console.WriteLine("Base - Method2");  
}  
  
```  
  
 Dado que ahora `BaseClass` tiene un método `Method2`, se puede agregar una segunda instrucción de llamada para las `BaseClass` variables `bc` y `bcdc`, como se muestra en el código siguiente.  
  
```c#  
bc.Method1();  
bc.Method2();  
dc.Method1();  
dc.Method2();  
bcdc.Method1();  
bcdc.Method2();  
  
```  
  
 Al compilar el proyecto, verá que al agregarse el método `Method2` en `BaseClass` produce una advertencia.  La advertencia indica que el método `Method2` de `DerivedClass` oculta el método `Method2` de `BaseClass`.  Se aconseja que use la palabra clave `new` en la definición de `Method2` si desea producir dicho resultado.  Como alternativa, puede cambiar el nombre de uno de los métodos `Method2` para resolver la advertencia, pero que no siempre es práctica.  
  
 Antes de agregar `new`, ejecute el programa para ver el resultado generado por las instrucciones de llamada adicionales.  Se muestran los siguientes resultados:  
  
```c#  
// Output:  
// Base - Method1  
// Base - Method2  
// Base - Method1  
// Derived - Method2  
// Base - Method1  
// Base - Method2  
  
```  
  
 La palabra clave `new` conserva las relaciones que generan dichos resultados, pero suprime la advertencia.  Las variables con el tipo `BaseClass` continúan obteniendo acceso a los miembros de `BaseClass`, y la variable con el tipo `DerivedClass` continúa obteniendo acceso a los miembros en `DerivedClass` en primer lugar y, a continuación, considera los miembros heredados de `BaseClass`.  
  
 Para quitar la advertencia, agregue el modificador `new` a la definición de `Method2` en `DerivedClass`, como se muestra en el código siguiente.  El modificador puede agregarse antes o después de `public`.  
  
```c#  
public new void Method2()  
{  
    Console.WriteLine("Derived - Method2");  
}  
  
```  
  
 Ejecute el programa de nuevo para comprobar que el resultado no ha cambiado.  Compruebe también que ya no aparece la advertencia.  Mediante `new`, afirma que está al tanto de que el miembro que modifica oculta un miembro que se hereda de la clase base.  Para obtener más información sobre la ocultación de nombres por herencia, vea [new \(Modificador\)](../../../csharp/language-reference/keywords/new-modifier.md).  
  
 Para contrastar este comportamiento con los efectos de usar `override`, agregue el método siguiente a `DerivedClass`.  El modificador `override` puede agregarse antes o después de `public`.  
  
```c#  
public override void Method1()  
{  
    Console.WriteLine("Derived - Method1");  
}  
  
```  
  
 Agregue el modificador `virtual` a la definición de `Method1` en `BaseClass`.  El modificador `virtual` puede agregarse antes o después de `public`.  
  
```c#  
public virtual void Method1()  
{  
    Console.WriteLine("Base - Method1");  
}  
  
```  
  
 Ejecute de nuevo el proyecto.  Observe especialmente las últimas dos líneas del resultado siguiente.  
  
```c#  
// Output:  
// Base - Method1  
// Base - Method2  
// Derived - Method1  
// Derived - Method2  
// Derived - Method1  
// Base - Method2  
  
```  
  
 El uso del modificador `override` permite a `bcdc` tener acceso al método `Method1` que se define en `DerivedClass`.  Normalmente, ese es el comportamiento deseado en las jerarquías de herencia.  Desea que los objetos con valores creados a partir de la clase derivada usen los métodos definidos en la clase derivada.  Para conseguir este comportamiento, use `override` para extender el método la de clase base.  
  
 El código siguiente contiene el ejemplo completo.  
  
```c#  
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
  
 En el ejemplo siguiente se muestra un comportamiento similar en un contexto distinto.  En el ejemplo se definen tres clases: una clase base denominada `Car` y dos clases derivadas de ella, `ConvertibleCar` y `Minivan`.  La clase base contiene un método `DescribeCar`.  El método muestra la descripción básica de un coche y, a continuación, llama a `ShowDetails` para proporcionar información adicional.  Cada una de las tres clases define un método `ShowDetails`.  El modificador `new` se usa para definir `ShowDetails` en la clase `ConvertibleCar`.  El modificador `override` se usa para definir `ShowDetails` en la clase `Minivan`.  
  
```c#  
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
  
 El ejemplo prueba a qué versión de `ShowDetails` se llama.  El método siguiente, `TestCars1`, declara una instancia de cada clase y, a continuación, llama a `DescribeCar` en cada instancia.  
  
```c#  
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
  
 `TestCars1` genera el siguiente resultado.  Observe especialmente los resultados de `car2`, que probablemente no son lo que esperaba.  El tipo del objeto es `ConvertibleCar`, pero `DescribeCar` no tiene acceso a la versión de `ShowDetails` definida en la clase `ConvertibleCar` porque dicho método se declara con el modificador `new`, no con el modificador `override`.  Como resultado, un objeto `ConvertibleCar` muestra la misma descripción que un objeto `Car`.  Contrasta los resultados de `car3`, que es un objeto `Minivan`.  En este caso, el método `ShowDetails` declarado en la clase `Minivan` invalida el método `ShowDetails` declarado en la clase `Car`, y la descripción que se muestra describe un minivan.  
  
```c#  
  
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
  
 `TestCars2` crea una lista de objetos de tipo `Car`.  Se crean instancias de los valores de los objetos de las clases `Car`, `ConvertibleCar`, y `Minivan`.  Se llama a `DescribeCar` en cada elemento de la lista.  En el código siguiente se muestra la definición de `TestCars2`.  
  
```c#  
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
  
 Se muestra el siguiente resultado.  Observe que coincide con el resultado que muestra `TestCars1`.  No se llama al método `ShowDetails` de la clase `ConvertibleCar`, independientemente de que el tipo de objeto sea `ConvertibleCar`, como en `TestCars1`, o `Car`, como en `TestCars2`.  A la inversa, `car3` llama al método `ShowDetails` desde la clase `Minivan` en ambos casos, independientemente de que tenga el tipo `Minivan` o `Car`.  
  
```c#  
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
  
 Los métodos `TestCars3` y `TestCars4` completan el ejemplo.  Estos métodos llaman a `ShowDetails` directamente, primero desde los objetos declarados de tipo `ConvertibleCar` y `Minivan` \(`TestCars3`\) y, a continuación, desde los objetos declarados de tipo `Car` \(`TestCars4`\).  El código siguiente define estos dos métodos.  
  
```c#  
  
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
  
 Los métodos generan el siguiente resultado, que se corresponde con los resultados del primer ejemplo de este tema.  
  
```c#  
// TestCars3  
// ----------  
// A roof that opens up.  
// Carries seven people.  
  
// TestCars4  
// ----------  
// Standard transportation.  
// Carries seven people.  
  
```  
  
 El código siguiente muestra el proyecto completo y sus resultados.  
  
```c#  
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
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Control de versiones con las palabras clave Override y New](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)   
 [base](../../../csharp/language-reference/keywords/base.md)   
 [abstractas](../../../csharp/language-reference/keywords/abstract.md)
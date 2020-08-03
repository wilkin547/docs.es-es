---
title: Usar la varianza en interfaces para las colecciones genéricas (C#)
description: Aprenda a usar las interfaces covariantes y contravariantes para las colecciones genéricas. Vea ejemplos de conversión y comparación de colecciones genéricas.
ms.date: 07/20/2015
ms.assetid: a44f0708-10fa-4c76-82cd-daa6e6b31e8e
ms.openlocfilehash: c2ce849e32520cb91422ff36173e418a010476bd
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105674"
---
# <a name="using-variance-in-interfaces-for-generic-collections-c"></a>Usar la varianza en interfaces para las colecciones genéricas (C#)
Una interfaz covariante permite que sus métodos devuelvan tipos más derivados que los especificados en la interfaz. Una interfaz contravariante permite que sus métodos acepten parámetros de tipos menos derivados que los especificados en la interfaz.  
  
 Varias interfaces existentes en .NET Framework 4 pasaron a ser covariantes y contravariantes. Por ejemplo, <xref:System.Collections.Generic.IEnumerable%601> y <xref:System.IComparable%601>. Esto permite volver a usar métodos que funcionan con colecciones genéricas de tipos base para colecciones de tipos derivados.  
  
 Para ver una lista de interfaces variantes de .NET, vea [Varianza en interfaces genéricas (C#)](./variance-in-generic-interfaces.md).  
  
## <a name="converting-generic-collections"></a>Convertir colecciones genéricas  
 En el ejemplo siguiente se muestran las ventajas de la compatibilidad con la covarianza en la interfaz <xref:System.Collections.Generic.IEnumerable%601>. El método `PrintFullName` acepta una colección del tipo `IEnumerable<Person>` como parámetro. Pero se puede volver a usar para una colección del tipo `IEnumerable<Employee>` porque `Employee` hereda `Person`.  
  
```csharp  
// Simple hierarchy of classes.  
public class Person  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
}  
  
public class Employee : Person { }  
  
class Program  
{  
    // The method has a parameter of the IEnumerable<Person> type.  
    public static void PrintFullName(IEnumerable<Person> persons)  
    {  
        foreach (Person person in persons)  
        {  
            Console.WriteLine("Name: {0} {1}",  
            person.FirstName, person.LastName);  
        }  
    }  
  
    public static void Test()  
    {  
        IEnumerable<Employee> employees = new List<Employee>();  
  
        // You can pass IEnumerable<Employee>,
        // although the method expects IEnumerable<Person>.  
  
        PrintFullName(employees);  
  
    }  
}  
```  
  
## <a name="comparing-generic-collections"></a>Comparar colecciones genéricas  
 En el ejemplo siguiente se muestran las ventajas de la compatibilidad con la contravarianza en la interfaz <xref:System.Collections.Generic.IComparer%601>. La clase `PersonComparer` implementa la interfaz `IComparer<Person>`. Pero se puede volver a usar esta clase para comparar una secuencia de objetos del tipo `Employee` porque `Employee` hereda `Person`.  
  
```csharp  
// Simple hierarchy of classes.  
public class Person  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
}  
  
public class Employee : Person { }  
  
// The custom comparer for the Person type  
// with standard implementations of Equals()  
// and GetHashCode() methods.  
class PersonComparer : IEqualityComparer<Person>  
{  
    public bool Equals(Person x, Person y)  
    {
        if (Object.ReferenceEquals(x, y)) return true;  
        if (Object.ReferenceEquals(x, null) ||  
            Object.ReferenceEquals(y, null))  
            return false;
        return x.FirstName == y.FirstName && x.LastName == y.LastName;  
    }  
    public int GetHashCode(Person person)  
    {  
        if (Object.ReferenceEquals(person, null)) return 0;  
        int hashFirstName = person.FirstName == null  
            ? 0 : person.FirstName.GetHashCode();  
        int hashLastName = person.LastName.GetHashCode();  
        return hashFirstName ^ hashLastName;  
    }  
}  
  
class Program  
{  
  
    public static void Test()  
    {  
        List<Employee> employees = new List<Employee> {  
               new Employee() {FirstName = "Michael", LastName = "Alexander"},  
               new Employee() {FirstName = "Jeff", LastName = "Price"}  
            };  
  
        // You can pass PersonComparer,
        // which implements IEqualityComparer<Person>,  
        // although the method expects IEqualityComparer<Employee>.  
  
        IEnumerable<Employee> noduplicates =  
            employees.Distinct<Employee>(new PersonComparer());  
  
        foreach (var employee in noduplicates)  
            Console.WriteLine(employee.FirstName + " " + employee.LastName);  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también

- [Varianza en interfaces genéricas (C#)](./variance-in-generic-interfaces.md)

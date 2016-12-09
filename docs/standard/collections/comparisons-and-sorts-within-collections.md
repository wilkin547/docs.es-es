---
title: Comparaciones y ordenaciones en colecciones
description: Comparaciones y ordenaciones en colecciones
keywords: .NET, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: c7b7c005-628d-427a-91ad-af0c3958c00e
translationtype: Human Translation
ms.sourcegitcommit: e07788926a995b41571be276379ad9285747951d
ms.openlocfilehash: bad7fd4e9cda1976a31f287d7c95d81d113a30fa

---

# <a name="comparisons-and-sorts-within-collections"></a>Comparaciones y ordenaciones en colecciones

Las clases [System.Collections](https://docs.microsoft.com/dotnet/core/api/System.Collections) realizan comparaciones en casi todos los procesos implicados en la administración de colecciones, ya sea al buscar el elemento que se va a quitar, o al devolver el valor de un par de clave y valor.

Normalmente, las colecciones usan un comparador de igualdad o un comparador de orden. En las comparaciones se usan dos constructores. 

## <a name="checking-for-equality"></a>Comprobar la igualdad

Los métodos como `Contains`, `IndexOf`, `LastIndexOf` y `Remove` utilizan un comparador de igualdad para los elementos de la colección. Si la colección es genérica, se compara la igualdad de los elementos según las siguientes directrices:

*   Si el tipo T implementa la interfaz genérica [IEquatable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.IEquatable-1), el comparador de igualdad es el método `Equals` de dicha interfaz.

*   Si el tipo T no implementa `IEquatable<T>`, se utiliza `Object.Equals`.

Además, algunas sobrecargas de constructores para colecciones de diccionario aceptan una implementación de [IEqualityComparer&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IEqualityComparer-1), que se usa para comparar la igualdad de claves.

## <a name="determining-sort-order"></a>Determinar el criterio de ordenación

Los métodos como `BinarySearch` y `Sort` utilizan un comparador de orden para los elementos de la colección. Las comparaciones pueden ser entre elementos de la colección o entre un elemento y un valor especificado. Para comparar objetos, existe el concepto de un comparador predeterminado y un comparador explícito. 

El comparador predeterminado se basa en al menos uno de los objetos que se comparan para implementar la interfaz `IComparable`. Una práctica recomendada es implementar `IComparable` en todas las clases que se usan como valores en una colección de lista o como claves en una colección de diccionarios. Para una colección genérica, la comparación de igualdad se determina según lo siguiente:

*   Si el tipo T implementa la interfaz genérica [System.IComparable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.IComparable-1), el comparador predeterminado es el método `CompareTo(T)` de dicha interfaz.

*   Si el tipo T implementa la interfaz no genérica [System.IComparable](https://docs.microsoft.com/dotnet/core/api/System.IComparable), el comparador predeterminado es el método `CompareTo`(Object) de dicha interfaz.

*   Si el tipo T no implementa ninguna de estas interfaces, no hay ningún comparador predeterminado y debe proporcionarse explícitamente un delegado de comparación o comparador.

Para proporcionar comparaciones explícitas, algunos métodos aceptan una implementación de `IComparer` como parámetro. Por ejemplo, el método `List<T>.Sort` acepta una implementación de [System.Collections.Generic.IComparer&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IComparer-1). 

## <a name="equality-and-sort-example"></a>Ejemplo de igualdad y ordenación

El código siguiente muestra una implementación de [IEquatable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.IEquatable-1) y [IComparable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.IComparable-1) en un objeto comercial simple. Además, cuando el objeto se almacena en una lista y se ordena, la llamada al método `Sort()` implica el uso del comparador predeterminado para el tipo "Part" y el método `Sort(Comparison<T>)` implementado mediante el uso de un método anónimo.

C#

```csharp
using System;
using System.Collections.Generic;
// Simple business object. A PartId is used to identify the type of part 
// but the part name can change. 
public class Part : IEquatable<Part> , IComparable<Part>
{
    public string PartName { get; set; }

    public int PartId { get; set; }

    public override string ToString()
    {
        return "ID: " + PartId + "   Name: " + PartName;
    }
    public override bool Equals(object obj)
    {
        if (obj == null) return false;
        Part objAsPart = obj as Part;
        if (objAsPart == null) return false;
        else return Equals(objAsPart);
    }
    public int SortByNameAscending(string name1, string name2)
    {

        return name1.CompareTo(name2);
    }

    // Default comparer for Part type.
    public int CompareTo(Part comparePart)
    {
          // A null value means that this object is greater.
        if (comparePart == null)
            return 1;

        else
            return this.PartId.CompareTo(comparePart.PartId);
    }
    public override int GetHashCode()
    {
        return PartId;
    }
    public bool Equals(Part other)
    {
        if (other == null) return false;
        return (this.PartId.Equals(other.PartId));
    }
    // Should also override == and != operators.

}
public class Example
{
    public static void Main()
    {
        // Create a list of parts.
        List<Part> parts = new List<Part>();

        // Add parts to the list.
        parts.Add(new Part() { PartName = "regular seat", PartId = 1434 });
        parts.Add(new Part() { PartName= "crank arm", PartId = 1234 });
        parts.Add(new Part() { PartName = "shift lever", PartId = 1634 }); ;
        // Name intentionally left null.
        parts.Add(new Part() {  PartId = 1334 });
        parts.Add(new Part() { PartName = "banana seat", PartId = 1444 });
        parts.Add(new Part() { PartName = "cassette", PartId = 1534 });


        // Write out the parts in the list. This will call the overridden 
        // ToString method in the Part class.
        Console.WriteLine("\nBefore sort:");
        foreach (Part aPart in parts)
        {
            Console.WriteLine(aPart);
        }


        // Call Sort on the list. This will use the 
        // default comparer, which is the Compare method 
        // implemented on Part.
        parts.Sort();


        Console.WriteLine("\nAfter sort by part number:");
        foreach (Part aPart in parts)
        {
            Console.WriteLine(aPart);
        }

        // This shows calling the Sort(Comparison(T) overload using 
        // an anonymous method for the Comparison delegate. 
        // This method treats null as the lesser of two values.
        parts.Sort(delegate(Part x, Part y)
        {
            if (x.PartName == null && y.PartName == null) return 0;
            else if (x.PartName == null) return -1;
            else if (y.PartName == null) return 1;
            else return x.PartName.CompareTo(y.PartName);
        });

        Console.WriteLine("\nAfter sort by name:");
        foreach (Part aPart in parts)
        {
            Console.WriteLine(aPart);
        }

        /*

            Before sort:
        ID: 1434   Name: regular seat
        ID: 1234   Name: crank arm
        ID: 1634   Name: shift lever
        ID: 1334   Name:
        ID: 1444   Name: banana seat
        ID: 1534   Name: cassette

        After sort by part number:
        ID: 1234   Name: crank arm
        ID: 1334   Name:
        ID: 1434   Name: regular seat
        ID: 1444   Name: banana seat
        ID: 1534   Name: cassette
        ID: 1634   Name: shift lever

        After sort by name:
        ID: 1334   Name:
        ID: 1444   Name: banana seat
        ID: 1534   Name: cassette
        ID: 1234   Name: crank arm
        ID: 1434   Name: regular seat
        ID: 1634   Name: shift lever

         */

    }
}
```

## <a name="see-also"></a>Vea también

[IComparer](https://docs.microsoft.com/dotnet/core/api/System.Collections.IComparer)

[IEquatable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.IEquatable-1)

[IComparer&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IComparer-1)

[IComparable](https://docs.microsoft.com/dotnet/core/api/System.IComparable)

[IComparable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.IComparable-1)



<!--HONumber=Nov16_HO3-->



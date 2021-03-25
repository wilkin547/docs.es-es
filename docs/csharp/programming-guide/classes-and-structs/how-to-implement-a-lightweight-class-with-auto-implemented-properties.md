---
title: Procedimiento para implementar una clase ligera con propiedades autoimplementadas - Guía de programación de C#
description: Aprenda a crear una clase ligera inmutable en C# que encapsule propiedades implementadas automáticamente. Hay dos enfoques de implementación.
ms.date: 07/20/2015
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: 1dc5a8ad-a4f7-4f32-8506-3fc6d8c8bfed
ms.openlocfilehash: 1d80cb2391a94c21360117c8217ecc4514fd666e
ms.sourcegitcommit: e3cf8227573e13b8e1f4e3dc007404881cdafe47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2021
ms.locfileid: "103190273"
---
# <a name="how-to-implement-a-lightweight-class-with-auto-implemented-properties-c-programming-guide"></a>Procedimiento para implementar una clase ligera con propiedades autoimplementadas (Guía de programación de C#)

En este ejemplo se muestra cómo crear una clase ligera inmutable que solo sirve para encapsular un conjunto de propiedades autoimplementadas. Use este tipo de construcción en lugar de un struct cuando deba utilizar una semántica de tipo de referencia.

Puede hacer que una propiedad sea inmutable de estas maneras:

- Declare solo el descriptor de acceso [get](../../language-reference/keywords/get.md), que hace que la propiedad sea inmutable en cualquier lugar excepto en el constructor del tipo.

- Declare un descriptor de acceso [init](../../language-reference/keywords/init.md) en lugar de `set`, que hace que la propiedad se pueda establecer solo en el constructor o mediante un [inicializador de objeto](object-and-collection-initializers.md).

- Declare el descriptor de acceso [set](../../language-reference/keywords/set.md) como [private](../../language-reference/keywords/private.md).  La propiedad solo se puede establecer dentro del tipo, pero es inmutable para los consumidores.

  Cuando se declara un descriptor de acceso `set` privado, no se puede usar un inicializador de objeto para inicializar la propiedad. Se debe utilizar un constructor o un método factory.

En el ejemplo siguiente se muestra cómo una propiedad con solo el descriptor de acceso get es distinta de una con get y un conjunto privado.

```csharp
class Contact
{
    public string Name { get; }
    public string Address { get; private set; }

    public Contact(string contactName, string contactAddress)
    {
        // Both properties are accessible in the constructor.
        Name = contactName;
        Address = contactAddress;
    }

    // Name isn't assignable here. This will generate a compile error.
    //public void ChangeName(string newName) => Name = newName;

    // Address is assignable here.
    public void ChangeAddress(string newAddress) => Address = newAddress
}
```

## <a name="example"></a>Ejemplo

En el siguiente ejemplo se muestran dos maneras de implementar una clase inmutable que tenga propiedades autoimplementadas. Cada forma declara una de las propiedades con un `set` privado y una de las propiedades solamente con un `get`.  La primera clase usa un constructor solo para inicializar las propiedades y la segunda clase utiliza un método factory estático que llama a un constructor.

```csharp
// This class is immutable. After an object is created,
// it cannot be modified from outside the class. It uses a
// constructor to initialize its properties.
class Contact
{
    // Read-only property.
    public string Name { get; }

    // Read-write property with a private set accessor.
    public string Address { get; private set; }

    // Public constructor.
    public Contact(string contactName, string contactAddress)
    {
        Name = contactName;
        Address = contactAddress;
    }
}

// This class is immutable. After an object is created,
// it cannot be modified from outside the class. It uses a
// static method and private constructor to initialize its properties.
public class Contact2
{
    // Read-write property with a private set accessor.
    public string Name { get; private set; }

    // Read-only property.
    public string Address { get; }

    // Private constructor.
    private Contact2(string contactName, string contactAddress)
    {
        Name = contactName;
        Address = contactAddress;
    }

    // Public factory method.
    public static Contact2 CreateContact(string name, string address)
    {
        return new Contact2(name, address);
    }
}

public class Program
{
    static void Main()
    {
        // Some simple data sources.
        string[] names = {"Terry Adams","Fadi Fakhouri", "Hanying Feng",
                            "Cesar Garcia", "Debra Garcia"};
        string[] addresses = {"123 Main St.", "345 Cypress Ave.", "678 1st Ave",
                                "12 108th St.", "89 E. 42nd St."};

        // Simple query to demonstrate object creation in select clause.
        // Create Contact objects by using a constructor.
        var query1 = from i in Enumerable.Range(0, 5)
                    select new Contact(names[i], addresses[i]);

        // List elements cannot be modified by client code.
        var list = query1.ToList();
        foreach (var contact in list)
        {
            Console.WriteLine("{0}, {1}", contact.Name, contact.Address);
        }

        // Create Contact2 objects by using a static factory method.
        var query2 = from i in Enumerable.Range(0, 5)
                        select Contact2.CreateContact(names[i], addresses[i]);

        // Console output is identical to query1.
        var list2 = query2.ToList();

        // List elements cannot be modified by client code.
        // CS0272:
        // list2[0].Name = "Eugene Zabokritski";

        // Keep the console open in debug mode.
        Console.WriteLine("Press any key to exit.");
        Console.ReadKey();
    }
}

/* Output:
    Terry Adams, 123 Main St.
    Fadi Fakhouri, 345 Cypress Ave.
    Hanying Feng, 678 1st Ave
    Cesar Garcia, 12 108th St.
    Debra Garcia, 89 E. 42nd St.
*/
```

El compilador crea campos de respaldo para cada propiedad autoimplementada. No se puede acceder a los campos directamente desde el código fuente.

## <a name="see-also"></a>Consulte también

- [Propiedades](./properties.md)
- [struct](../../language-reference/builtin-types/struct.md)
- [Inicializadores de objeto y colección](./object-and-collection-initializers.md)

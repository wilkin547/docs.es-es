---
title: Procedimiento para implementar una clase ligera con propiedades autoimplementadas - Guía de programación de C#
ms.date: 07/20/2015
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: 1dc5a8ad-a4f7-4f32-8506-3fc6d8c8bfed
ms.openlocfilehash: 170a36e2a10896d9e4d29af602694700fa122e69
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714911"
---
# <a name="how-to-implement-a-lightweight-class-with-auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="a2713-102">Procedimiento para implementar una clase ligera con propiedades autoimplementadas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="a2713-102">How to implement a lightweight class with auto-implemented properties (C# Programming Guide)</span></span>

<span data-ttu-id="a2713-103">En este ejemplo se muestra cómo crear una clase ligera inmutable que solo sirve para encapsular un conjunto de propiedades autoimplementadas.</span><span class="sxs-lookup"><span data-stu-id="a2713-103">This example shows how to create an immutable lightweight class that serves only to encapsulate a set of auto-implemented properties.</span></span> <span data-ttu-id="a2713-104">Use este tipo de construcción en lugar de un struct cuando deba utilizar una semántica de tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="a2713-104">Use this kind of construct instead of a struct when you must use reference type semantics.</span></span>

<span data-ttu-id="a2713-105">Puede crear una propiedad inmutable de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="a2713-105">You can make an immutable property in two ways:</span></span>

- <span data-ttu-id="a2713-106">Puede declarar el descriptor de acceso [set](../../language-reference/keywords/set.md) como [private](../../language-reference/keywords/private.md).</span><span class="sxs-lookup"><span data-stu-id="a2713-106">You can declare the [set](../../language-reference/keywords/set.md) accessor to be [private](../../language-reference/keywords/private.md).</span></span>  <span data-ttu-id="a2713-107">La propiedad solo se puede establecer dentro del tipo, pero es inmutable a los consumidores.</span><span class="sxs-lookup"><span data-stu-id="a2713-107">The property is only settable within the type, but it is immutable to consumers.</span></span>

  <span data-ttu-id="a2713-108">Cuando se declara un descriptor de acceso `set` privado, no se puede usar un inicializador de objeto para inicializar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a2713-108">When you declare a private `set` accessor, you cannot use an object initializer to initialize the property.</span></span> <span data-ttu-id="a2713-109">Se debe utilizar un constructor o un método factory.</span><span class="sxs-lookup"><span data-stu-id="a2713-109">You must use a constructor or a factory method.</span></span>
- <span data-ttu-id="a2713-110">Puede declarar solo el descriptor de acceso [get](../../language-reference/keywords/get.md), que hace que la propiedad sea inmutable en cualquier lugar excepto en el constructor del tipo.</span><span class="sxs-lookup"><span data-stu-id="a2713-110">You can declare only the [get](../../language-reference/keywords/get.md) accessor, which makes the property immutable everywhere except in the type’s constructor.</span></span>

## <a name="example"></a><span data-ttu-id="a2713-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a2713-111">Example</span></span>

<span data-ttu-id="a2713-112">En el siguiente ejemplo se muestran dos maneras de implementar una clase inmutable que tenga propiedades autoimplementadas.</span><span class="sxs-lookup"><span data-stu-id="a2713-112">The following example shows two ways to implement an immutable class that has auto-implemented properties.</span></span> <span data-ttu-id="a2713-113">Cada forma declara una de las propiedades con un `set` privado y una de las propiedades solamente con un `get`.</span><span class="sxs-lookup"><span data-stu-id="a2713-113">Each way declares one of the properties with a private `set` and one of the properties with a `get` only.</span></span>  <span data-ttu-id="a2713-114">La primera clase usa un constructor solo para inicializar las propiedades y la segunda clase utiliza un método factory estático que llama a un constructor.</span><span class="sxs-lookup"><span data-stu-id="a2713-114">The first class uses a constructor only to initialize the properties, and the second class uses a static factory method that calls a constructor.</span></span>

```csharp
// This class is immutable. After an object is created,
// it cannot be modified from outside the class. It uses a
// constructor to initialize its properties.
class Contact
{
    // Read-only properties.
    public string Name { get; }
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
    // Read-only properties.
    public string Name { get; private set; }
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

<span data-ttu-id="a2713-115">El compilador crea campos de respaldo para cada propiedad autoimplementada.</span><span class="sxs-lookup"><span data-stu-id="a2713-115">The compiler creates backing fields for each auto-implemented property.</span></span> <span data-ttu-id="a2713-116">No se puede acceder a los campos directamente desde el código fuente.</span><span class="sxs-lookup"><span data-stu-id="a2713-116">The fields are not accessible directly from source code.</span></span>

## <a name="see-also"></a><span data-ttu-id="a2713-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2713-117">See also</span></span>

- [<span data-ttu-id="a2713-118">Propiedades</span><span class="sxs-lookup"><span data-stu-id="a2713-118">Properties</span></span>](./properties.md)
- [<span data-ttu-id="a2713-119">struct</span><span class="sxs-lookup"><span data-stu-id="a2713-119">struct</span></span>](../../language-reference/keywords/struct.md)
- [<span data-ttu-id="a2713-120">Inicializadores de objeto y colección</span><span class="sxs-lookup"><span data-stu-id="a2713-120">Object and Collection Initializers</span></span>](./object-and-collection-initializers.md)

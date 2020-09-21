---
title: Información general de tipos genéricos (genéricos)
description: Obtenga información sobre cómo los genéricos actúan como plantillas de código que le permiten definir estructuras de datos con seguridad de tipos sin confirmar un tipo de datos real.
author: kuhlenh
ms.author: wiwagn
ms.date: 10/09/2018
ms.openlocfilehash: 5f6e84e23b5bcdcb3dcd742823d83728fb43d195
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557949"
---
# <a name="generic-types-overview"></a><span data-ttu-id="abc42-103">Información general de tipos genéricos</span><span class="sxs-lookup"><span data-stu-id="abc42-103">Generic types overview</span></span>

<span data-ttu-id="abc42-104">Los desarrolladores utilizan genéricos en todo momento en .NET, ya sea implícita o explícitamente.</span><span class="sxs-lookup"><span data-stu-id="abc42-104">Developers use generics all the time in .NET, whether implicitly or explicitly.</span></span> <span data-ttu-id="abc42-105">Al usar LINQ en .NET, ¿alguna vez observó que estaba trabajando con <xref:System.Collections.Generic.IEnumerable%601>?</span><span class="sxs-lookup"><span data-stu-id="abc42-105">When you use LINQ in .NET, did you ever notice that you're working with <xref:System.Collections.Generic.IEnumerable%601>?</span></span> <span data-ttu-id="abc42-106">O, si alguna vez ha visto un ejemplo en línea de un "repositorio genérico" para comunicarse con bases de datos mediante Entity Framework, ha observado que la mayoría de los métodos devuelven `IQueryable<T>`?</span><span class="sxs-lookup"><span data-stu-id="abc42-106">Or if you ever saw an online sample of a "generic repository" for talking to databases using Entity Framework, did you see that most methods return `IQueryable<T>`?</span></span> <span data-ttu-id="abc42-107">Probablemente se pregunte qué significa la **T** en estos ejemplos y por qué aparece.</span><span class="sxs-lookup"><span data-stu-id="abc42-107">You may have wondered what the **T** is in these examples and why it's in there.</span></span>

<span data-ttu-id="abc42-108">Introducidos por primera vez en .NET Framework 2.0, los genéricos son esencialmente una "plantilla de código" que permite a los desarrolladores definir estructuras de datos [con seguridad de tipos](/previous-versions/dotnet/netframework-4.0/hbzz1a9a(v=vs.100)) sin confirmar un tipo de datos real.</span><span class="sxs-lookup"><span data-stu-id="abc42-108">First introduced in the .NET Framework 2.0, generics are essentially a "code template" that allows developers to define [type-safe](/previous-versions/dotnet/netframework-4.0/hbzz1a9a(v=vs.100)) data structures without committing to an actual data type.</span></span> <span data-ttu-id="abc42-109">Por ejemplo, <xref:System.Collections.Generic.List%601> es una [colección genérica](xref:System.Collections.Generic) que se puede declarar y usar con cualquier tipo, como `List<int>`, `List<string>` o `List<Person>`.</span><span class="sxs-lookup"><span data-stu-id="abc42-109">For example, <xref:System.Collections.Generic.List%601> is a [generic collection](xref:System.Collections.Generic) that can be declared and used with any type, such as `List<int>`, `List<string>`, or `List<Person>`.</span></span>

<span data-ttu-id="abc42-110">Para entender por qué los genéricos son útiles, vamos a echar un vistazo a una clase específica antes y después de agregar genéricos: <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="abc42-110">To understand why generics are useful, let's take a look at a specific class before and after adding generics: <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="abc42-111">En .NET Framework 1.0, los elementos `ArrayList` eran de tipo <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="abc42-111">In .NET Framework 1.0, the `ArrayList` elements were of type <xref:System.Object>.</span></span> <span data-ttu-id="abc42-112">Cualquier elemento agregado a la colección se convertía desapercibidamente en un elemento `Object`.</span><span class="sxs-lookup"><span data-stu-id="abc42-112">Any element added to the collection was silently converted into an `Object`.</span></span> <span data-ttu-id="abc42-113">Lo mismo podría suceder al leer elementos de la lista.</span><span class="sxs-lookup"><span data-stu-id="abc42-113">The same would happen when reading elements from the list.</span></span> <span data-ttu-id="abc42-114">Este proceso se conoce como [conversión boxing y unboxing](../csharp/programming-guide/types/boxing-and-unboxing.md), y afecta al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="abc42-114">This process is known as [boxing and unboxing](../csharp/programming-guide/types/boxing-and-unboxing.md), and it impacts performance.</span></span> <span data-ttu-id="abc42-115">Sin embargo, además del rendimiento, no hay ninguna manera de determinar el tipo de datos de la lista en tiempo de compilación, lo que hace que algunos códigos sean frágiles.</span><span class="sxs-lookup"><span data-stu-id="abc42-115">Aside from performance, however, there's no way to determine the type of data in the list at compile time, which makes for some fragile code.</span></span> <span data-ttu-id="abc42-116">Los genéricos solucionan este problema definiendo el tipo de datos que va a contener cada instancia de la lista.</span><span class="sxs-lookup"><span data-stu-id="abc42-116">Generics solve this problem by defining the type of data each instance of list will contain.</span></span> <span data-ttu-id="abc42-117">Por ejemplo, solo puede agregar enteros a `List<int>` y solo puede agregar personas a `List<Person>`.</span><span class="sxs-lookup"><span data-stu-id="abc42-117">For example, you can only add integers to `List<int>` and only add Persons to `List<Person>`.</span></span>

<span data-ttu-id="abc42-118">Los genéricos también están disponibles en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="abc42-118">Generics are also available at run time.</span></span> <span data-ttu-id="abc42-119">El tiempo de ejecución conoce qué tipo de estructura de datos está usando y puede almacenarla en memoria de forma más eficaz.</span><span class="sxs-lookup"><span data-stu-id="abc42-119">The runtime knows what type of data structure you're using and can store it in memory more efficiently.</span></span>

<span data-ttu-id="abc42-120">El ejemplo siguiente es un pequeño programa que muestra la eficacia que supone conocer el tipo de estructura de datos en tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="abc42-120">The following example is a small program that illustrates the efficiency of knowing the data structure type at run time:</span></span>

```csharp
  using System;
  using System.Collections;
  using System.Collections.Generic;
  using System.Diagnostics;

  namespace GenericsExample {
    class Program {
      static void Main(string[] args) {
        //generic list
        List<int> ListGeneric = new List<int> { 5, 9, 1, 4 };
        //non-generic list
        ArrayList ListNonGeneric = new ArrayList { 5, 9, 1, 4 };
        // timer for generic list sort
        Stopwatch s = Stopwatch.StartNew();
        ListGeneric.Sort();
        s.Stop();
        Console.WriteLine($"Generic Sort: {ListGeneric}  \n Time taken: {s.Elapsed.TotalMilliseconds}ms");

        //timer for non-generic list sort
        Stopwatch s2 = Stopwatch.StartNew();
        ListNonGeneric.Sort();
        s2.Stop();
        Console.WriteLine($"Non-Generic Sort: {ListNonGeneric}  \n Time taken: {s2.Elapsed.TotalMilliseconds}ms");
        Console.ReadLine();
      }
    }
  }
```

<span data-ttu-id="abc42-121">Este programa genera un resultado similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="abc42-121">This program produces output similar to the following:</span></span>

```console
Generic Sort: System.Collections.Generic.List`1[System.Int32]
 Time taken: 0.0034ms
Non-Generic Sort: System.Collections.ArrayList
 Time taken: 0.2592ms
```

<span data-ttu-id="abc42-122">Lo primero que verá aquí es que la ordenación de la lista genérica es significativamente más rápida que la de la lista no genérica.</span><span class="sxs-lookup"><span data-stu-id="abc42-122">The first thing you can notice here is that sorting the generic list is significantly faster than sorting the non-generic list.</span></span> <span data-ttu-id="abc42-123">También puede observar que el tipo de la lista genérica es distinto ([System.Int32]), mientras que el tipo de la lista no genérica es generalizado.</span><span class="sxs-lookup"><span data-stu-id="abc42-123">You might also notice that the type for the generic list is distinct ([System.Int32]), whereas the type for the non-generic list is generalized.</span></span> <span data-ttu-id="abc42-124">Dado que el tiempo de ejecución sabe que el genérico `List<int>` es de tipo <xref:System.Int32>, puede almacenar los elementos de la lista en una matriz de enteros subyacente en memoria, mientras el no genérico `ArrayList` tiene que convertir cada elemento de la lista en un objeto.</span><span class="sxs-lookup"><span data-stu-id="abc42-124">Because the runtime knows the generic `List<int>` is of type <xref:System.Int32>, it can store the list elements in an underlying integer array in memory, while the non-generic `ArrayList` has to cast each list element to an object.</span></span> <span data-ttu-id="abc42-125">Como se muestra en este ejemplo, las conversiones adicionales consumen tiempo y ralentizan la ordenación de la lista.</span><span class="sxs-lookup"><span data-stu-id="abc42-125">As this example shows, the extra casts take up time and slow down the list sort.</span></span>

<span data-ttu-id="abc42-126">Otra ventaja adicional de que el tiempo de ejecución conozca el tipo de la clase genérica es una mejor experiencia de depuración.</span><span class="sxs-lookup"><span data-stu-id="abc42-126">An additional advantage of the runtime knowing the type of your generic is a better debugging experience.</span></span> <span data-ttu-id="abc42-127">Cuando se depura un genérico en C#, sabe qué tipo de cada elemento se encuentra en la estructura de datos.</span><span class="sxs-lookup"><span data-stu-id="abc42-127">When you're debugging a generic in C#, you know what type each element is in your data structure.</span></span> <span data-ttu-id="abc42-128">Sin genéricos, no sabría qué tipo de cada elemento estaba presente.</span><span class="sxs-lookup"><span data-stu-id="abc42-128">Without generics, you would have no idea what type each element was.</span></span>

## <a name="see-also"></a><span data-ttu-id="abc42-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="abc42-129">See also</span></span>

- [<span data-ttu-id="abc42-130">Guía de programación de C#: genéricos</span><span class="sxs-lookup"><span data-stu-id="abc42-130">C# Programming Guide - Generics</span></span>](../csharp/programming-guide/generics/index.md)

---
title: Información general (genéricos) de tipos genéricos
description: Obtenga información sobre cómo los genéricos actúan como plantillas de código que le permiten definir estructuras de datos con seguridad de tipos sin confirmar un tipo de datos real.
author: kuhlenh
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: a315b111-8e48-446c-ab19-acb6405894a7
ms.openlocfilehash: ad6216998dff70ca7e36b52b374c5ffb9fd0cd45
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33575484"
---
# <a name="generic-types-generics-overview"></a><span data-ttu-id="c5b9c-103">Información general (genéricos) de tipos genéricos</span><span class="sxs-lookup"><span data-stu-id="c5b9c-103">Generic Types (Generics) Overview</span></span>

<span data-ttu-id="c5b9c-104">Usamos genéricos en todo momento en C#, ya sea implícita o explícitamente.</span><span class="sxs-lookup"><span data-stu-id="c5b9c-104">We use generics all the time in C#, whether implicitly or explicitly.</span></span> <span data-ttu-id="c5b9c-105">Al usar LINQ en C#, ¿alguna vez observó que estaba trabajando con IEnumerable<T>?</span><span class="sxs-lookup"><span data-stu-id="c5b9c-105">When you use LINQ in C#, did you ever notice that you are working with IEnumerable<T>?</span></span> <span data-ttu-id="c5b9c-106">O si alguna vez ha visto un ejemplo en línea de un "repositorio genérico" para comunicarse con bases de datos mediante Entity Framework, ¿observó que la mayoría de los métodos devuelven IQueryable<T>?</span><span class="sxs-lookup"><span data-stu-id="c5b9c-106">Or if you ever saw an online sample of a "generic repository" for talking to databases using Entity Framework, did you see that most methods return IQueryable<T>?</span></span> <span data-ttu-id="c5b9c-107">¿Probablemente se pregunte qué significa la **T** en estos ejemplos y por qué aparece?</span><span class="sxs-lookup"><span data-stu-id="c5b9c-107">You may have wondered what the **T** is in these examples and why is it in there?</span></span>

<span data-ttu-id="c5b9c-108">Los genéricos, introducidos en primer lugar en .NET Framework 2.0, implican cambios en el lenguaje de C# y en Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="c5b9c-108">First introduced to the .NET Framework 2.0, generics involved changes to both the C# language and the Common Language Runtime (CLR).</span></span> <span data-ttu-id="c5b9c-109">Los **genéricos** son esencialmente una "plantilla de código" que permite a los desarrolladores definir estructuras de datos [con seguridad de tipos](https://msdn.microsoft.com/library/hbzz1a9a.aspx) sin confirmar un tipo de datos real.</span><span class="sxs-lookup"><span data-stu-id="c5b9c-109">**Generics** are essentially a "code template" that allows developers to define [type-safe](https://msdn.microsoft.com/library/hbzz1a9a.aspx) data structures without committing to an actual data type.</span></span> <span data-ttu-id="c5b9c-110">Por ejemplo, `List<T>` es un [colección genérica](xref:System.Collections.Generic) que se puede declarar y usar con cualquier tipo: `List<int>`, `List<string>`, `List<Person>`, etc.</span><span class="sxs-lookup"><span data-stu-id="c5b9c-110">For example, `List<T>` is a [Generic Collection](xref:System.Collections.Generic) that can be declared and used with any type: `List<int>`, `List<string>`, `List<Person>`, etc.</span></span>

<span data-ttu-id="c5b9c-111">Así que, ¿para qué sirven?</span><span class="sxs-lookup"><span data-stu-id="c5b9c-111">So, what’s the point?</span></span> <span data-ttu-id="c5b9c-112">¿Por qué son útiles los genéricos?</span><span class="sxs-lookup"><span data-stu-id="c5b9c-112">Why are generics useful?</span></span> <span data-ttu-id="c5b9c-113">Para poder entenderlo, necesitamos echar un vistazo a una clase específica antes y después de agregar genéricos.</span><span class="sxs-lookup"><span data-stu-id="c5b9c-113">In order to understand this, we need to take a look at a specific class before and after adding generics.</span></span> <span data-ttu-id="c5b9c-114">Examinemos `ArrayList`.</span><span class="sxs-lookup"><span data-stu-id="c5b9c-114">Let’s look at the `ArrayList`.</span></span> <span data-ttu-id="c5b9c-115">En C# 1.0, los elementos de `ArrayList` eran de tipo `object`.</span><span class="sxs-lookup"><span data-stu-id="c5b9c-115">In C# 1.0, the `ArrayList` elements were of type `object`.</span></span> <span data-ttu-id="c5b9c-116">Esto significaba que cualquier elemento que se hubiese agregado se convertía desapercibidamente en `object`; lo mismo sucede al leer los elementos de la lista (este proceso se conoce como [conversión boxing](../../docs/csharp/programming-guide/types/boxing-and-unboxing.md) y conversión unboxing respectivamente).</span><span class="sxs-lookup"><span data-stu-id="c5b9c-116">This meant that any element that was added was silently converted into an `object`; same thing happens on reading the elements from the list (this process is known as [boxing](../../docs/csharp/programming-guide/types/boxing-and-unboxing.md) and unboxing respectively).</span></span> <span data-ttu-id="c5b9c-117">La conversión boxing y la conversión unboxing repercuten en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c5b9c-117">Boxing and unboxing have an impact of performance.</span></span> <span data-ttu-id="c5b9c-118">Pero sobre todo, no hay ninguna manera de saber en tiempo de compilación cuál es el tipo real de los datos de la lista.</span><span class="sxs-lookup"><span data-stu-id="c5b9c-118">More than that, however, there is no way to tell at compile time what is the actual type of the data in the list.</span></span> <span data-ttu-id="c5b9c-119">Por ello, algunos códigos son frágiles.</span><span class="sxs-lookup"><span data-stu-id="c5b9c-119">This makes for some fragile code.</span></span> <span data-ttu-id="c5b9c-120">Los genéricos solucionan este problema proporcionando información adicional sobre el tipo de datos que va a contener cada instancia de la lista.</span><span class="sxs-lookup"><span data-stu-id="c5b9c-120">Generics solve this problem by providing additional information the type of data each instance of list will contain.</span></span> <span data-ttu-id="c5b9c-121">En pocas palabras, solo puede agregar enteros a `List<int>` y solo puede agregar personas a `List<Person>`, etc.</span><span class="sxs-lookup"><span data-stu-id="c5b9c-121">Put simply, you can only add integers to `List<int>` and only add Persons to `List<Person>`, etc.</span></span>

<span data-ttu-id="c5b9c-122">Los genéricos también están disponibles en el runtime o **reificados**.</span><span class="sxs-lookup"><span data-stu-id="c5b9c-122">Generics are also available at runtime, or **reified**.</span></span> <span data-ttu-id="c5b9c-123">Esto significa que el runtime conoce qué tipo de estructura de datos está usando y puede almacenarla en memoria de modo más eficaz.</span><span class="sxs-lookup"><span data-stu-id="c5b9c-123">This means the runtime knows what type of data structure you are using and can store it in memory more efficiently.</span></span>

<span data-ttu-id="c5b9c-124">Este es un pequeño programa que muestra la eficacia que supone conocer el tipo de estructura de datos en el runtime:</span><span class="sxs-lookup"><span data-stu-id="c5b9c-124">Here is a small program that illustrates the efficiency of knowing the data structure type at runtime:</span></span>

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

<span data-ttu-id="c5b9c-125">Este programa produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="c5b9c-125">This program yields the following output:</span></span>

```console
Generic Sort: System.Collections.Generic.List\`1[System.Int32] Time taken: 0.0789ms
Non-Generic Sort: System.Collections.ArrayList Time taken: 2.4324ms
```

<span data-ttu-id="c5b9c-126">Lo primero que verá aquí es que la ordenación de la lista genérica es significativamente más rápida que la de la lista no genérica.</span><span class="sxs-lookup"><span data-stu-id="c5b9c-126">The first thing you notice here is that sorting the generic list is significantly faster than for the non-generic list.</span></span> <span data-ttu-id="c5b9c-127">También puede observar que el tipo de la lista genérica es distinto ([System.Int32]), mientras que el tipo de la lista no genérica es generalizado.</span><span class="sxs-lookup"><span data-stu-id="c5b9c-127">You might also notice that the type for the generic list is distinct ([System.Int32]) whereas the type for the non-generic list is generalized.</span></span> <span data-ttu-id="c5b9c-128">Dado que el runtime sabe que el genérico `List<int>` es de tipo int, puede almacenar los elementos de la lista en una matriz de enteros subyacente en memoria, mientras el no genérico `ArrayList` tiene que convertir cada elemento de la lista como un objeto a medida que se almacena en una matriz de objetos en memoria.</span><span class="sxs-lookup"><span data-stu-id="c5b9c-128">Because the runtime knows the generic `List<int>` is of type int, it can store the list elements in an underlying integer array in memory while the non-generic `ArrayList` has to cast each list element as an object as stored in an object array in memory.</span></span> <span data-ttu-id="c5b9c-129">Como se muestra en este ejemplo, las conversiones adicionales consumen tiempo y ralentizan la ordenación de la lista.</span><span class="sxs-lookup"><span data-stu-id="c5b9c-129">As shown through this example, the extra castings take up time and slow down the list sort.</span></span>

<span data-ttu-id="c5b9c-130">El último dato útil sobre el runtime es que conocer el tipo de la clase genérica supone una mejor experiencia de depuración.</span><span class="sxs-lookup"><span data-stu-id="c5b9c-130">The last useful thing about the runtime knowing the type of your generic is a better debugging experience.</span></span> <span data-ttu-id="c5b9c-131">Cuando se depura un genérico en C#, sabe qué tipo de cada elemento se encuentra en la estructura de datos.</span><span class="sxs-lookup"><span data-stu-id="c5b9c-131">When you are debugging a generic in C#, you know what type each element is in your data structure.</span></span> <span data-ttu-id="c5b9c-132">Sin genéricos, no sabría qué tipo de cada elemento estaba presente.</span><span class="sxs-lookup"><span data-stu-id="c5b9c-132">Without generics, you would have no idea what type each element was.</span></span>

## <a name="further-reading-and-resources"></a><span data-ttu-id="c5b9c-133">Más información y recursos</span><span class="sxs-lookup"><span data-stu-id="c5b9c-133">Further reading and resources</span></span>

*   [<span data-ttu-id="c5b9c-134">Introducción a los genéricos C#</span><span class="sxs-lookup"><span data-stu-id="c5b9c-134">An Introduction to C# Generics</span></span>](https://msdn.microsoft.com/library/ms379564.aspx)
*   [<span data-ttu-id="c5b9c-135">Guía de programación de C#: genéricos</span><span class="sxs-lookup"><span data-stu-id="c5b9c-135">C# Programming Guide - Generics</span></span>](../../docs/csharp/programming-guide/generics/index.md)

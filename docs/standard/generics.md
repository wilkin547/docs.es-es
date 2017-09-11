---
title: "Información general (genéricos) de tipos genéricos"
description: "Obtenga información sobre cómo los genéricos actúan como plantillas de código que le permiten definir estructuras de datos con seguridad de tipos sin confirmar un tipo de datos real."
keywords: .NET, .NET Core
author: kuhlenh
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: a315b111-8e48-446c-ab19-acb6405894a7
ms.translationtype: HT
ms.sourcegitcommit: 934373d61407c8cc19b7d6424898a582880f9c21
ms.openlocfilehash: 08b8de2fe17a0032a1c1180667f39b1d6ce0feb6
ms.contentlocale: es-es
ms.lasthandoff: 08/21/2017

---

# <a name="generic-types-generics-overview"></a><span data-ttu-id="b681e-104">Información general (genéricos) de tipos genéricos</span><span class="sxs-lookup"><span data-stu-id="b681e-104">Generic Types (Generics) Overview</span></span>

<span data-ttu-id="b681e-105">Usamos genéricos en todo momento en C#, ya sea implícita o explícitamente.</span><span class="sxs-lookup"><span data-stu-id="b681e-105">We use generics all the time in C#, whether implicitly or explicitly.</span></span> <span data-ttu-id="b681e-106">Al usar LINQ en C#, ¿alguna vez observó que estaba trabajando con IEnumerable<T>?</span><span class="sxs-lookup"><span data-stu-id="b681e-106">When you use LINQ in C#, did you ever notice that you are working with IEnumerable<T>?</span></span> <span data-ttu-id="b681e-107">O si alguna vez ha visto un ejemplo en línea de un "repositorio genérico" para comunicarse con bases de datos mediante Entity Framework, ¿observó que la mayoría de los métodos devuelven IQueryable<T>?</span><span class="sxs-lookup"><span data-stu-id="b681e-107">Or if you ever saw an online sample of a "generic repository" for talking to databases using Entity Framework, did you see that most methods return IQueryable<T>?</span></span> <span data-ttu-id="b681e-108">¿Probablemente se pregunte qué significa la **T** en estos ejemplos y por qué aparece?</span><span class="sxs-lookup"><span data-stu-id="b681e-108">You may have wondered what the **T** is in these examples and why is it in there?</span></span>

<span data-ttu-id="b681e-109">Los genéricos, introducidos en primer lugar en .NET Framework 2.0, implican cambios en el lenguaje de C# y en Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="b681e-109">First introduced to the .NET Framework 2.0, generics involved changes to both the C# language and the Common Language Runtime (CLR).</span></span> <span data-ttu-id="b681e-110">Los **genéricos** son esencialmente una "plantilla de código" que permite a los desarrolladores definir estructuras de datos [con seguridad de tipos](https://msdn.microsoft.com/library/hbzz1a9a.aspx) sin confirmar un tipo de datos real.</span><span class="sxs-lookup"><span data-stu-id="b681e-110">**Generics** are essentially a "code template" that allows developers to define [type-safe](https://msdn.microsoft.com/library/hbzz1a9a.aspx) data structures without committing to an actual data type.</span></span> <span data-ttu-id="b681e-111">Por ejemplo, `List<T>` es un [colección genérica](xref:System.Collections.Generic) que se puede declarar y usar con cualquier tipo: `List<int>`, `List<string>`, `List<Person>`, etc.</span><span class="sxs-lookup"><span data-stu-id="b681e-111">For example, `List<T>` is a [Generic Collection](xref:System.Collections.Generic) that can be declared and used with any type: `List<int>`, `List<string>`, `List<Person>`, etc.</span></span>

<span data-ttu-id="b681e-112">Así que, ¿para qué sirven?</span><span class="sxs-lookup"><span data-stu-id="b681e-112">So, what’s the point?</span></span> <span data-ttu-id="b681e-113">¿Por qué son útiles los genéricos?</span><span class="sxs-lookup"><span data-stu-id="b681e-113">Why are generics useful?</span></span> <span data-ttu-id="b681e-114">Para poder entenderlo, necesitamos echar un vistazo a una clase específica antes y después de agregar genéricos.</span><span class="sxs-lookup"><span data-stu-id="b681e-114">In order to understand this, we need to take a look at a specific class before and after adding generics.</span></span> <span data-ttu-id="b681e-115">Examinemos `ArrayList`.</span><span class="sxs-lookup"><span data-stu-id="b681e-115">Let’s look at the `ArrayList`.</span></span> <span data-ttu-id="b681e-116">En C# 1.0, los elementos de `ArrayList` eran de tipo `object`.</span><span class="sxs-lookup"><span data-stu-id="b681e-116">In C# 1.0, the `ArrayList` elements were of type `object`.</span></span> <span data-ttu-id="b681e-117">Esto significaba que cualquier elemento que se hubiese agregado se convertía desapercibidamente en `object`; lo mismo sucede al leer los elementos de la lista (este proceso se conoce como [conversión boxing](https://msdn.microsoft.com/library/yz2be5wk.aspx) y conversión unboxing respectivamente).</span><span class="sxs-lookup"><span data-stu-id="b681e-117">This meant that any element that was added was silently converted into an `object`; same thing happens on reading the elements from the list (this process is known as [boxing](https://msdn.microsoft.com/library/yz2be5wk.aspx) and unboxing respectively).</span></span> <span data-ttu-id="b681e-118">La conversión boxing y la conversión unboxing repercuten en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="b681e-118">Boxing and unboxing have an impact of performance.</span></span> <span data-ttu-id="b681e-119">Pero sobre todo, no hay ninguna manera de saber en tiempo de compilación cuál es el tipo real de los datos de la lista.</span><span class="sxs-lookup"><span data-stu-id="b681e-119">More than that, however, there is no way to tell at compile time what is the actual type of the data in the list.</span></span> <span data-ttu-id="b681e-120">Por ello, algunos códigos son frágiles.</span><span class="sxs-lookup"><span data-stu-id="b681e-120">This makes for some fragile code.</span></span> <span data-ttu-id="b681e-121">Los genéricos solucionan este problema proporcionando información adicional sobre el tipo de datos que va a contener cada instancia de la lista.</span><span class="sxs-lookup"><span data-stu-id="b681e-121">Generics solve this problem by providing additional information the type of data each instance of list will contain.</span></span> <span data-ttu-id="b681e-122">En pocas palabras, solo puede agregar enteros a `List<int>` y solo puede agregar personas a `List<Person>`, etc.</span><span class="sxs-lookup"><span data-stu-id="b681e-122">Put simply, you can only add integers to `List<int>` and only add Persons to `List<Person>`, etc.</span></span>

<span data-ttu-id="b681e-123">Los genéricos también están disponibles en el runtime o **reificados**.</span><span class="sxs-lookup"><span data-stu-id="b681e-123">Generics are also available at runtime, or **reified**.</span></span> <span data-ttu-id="b681e-124">Esto significa que el runtime conoce qué tipo de estructura de datos está usando y puede almacenarla en memoria de modo más eficaz.</span><span class="sxs-lookup"><span data-stu-id="b681e-124">This means the runtime knows what type of data structure you are using and can store it in memory more efficiently.</span></span>

<span data-ttu-id="b681e-125">Este es un pequeño programa que muestra la eficacia que supone conocer el tipo de estructura de datos en el runtime:</span><span class="sxs-lookup"><span data-stu-id="b681e-125">Here is a small program that illustrates the efficiency of knowing the data structure type at runtime:</span></span>

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

<span data-ttu-id="b681e-126">Este programa produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="b681e-126">This program yields the following output:</span></span>

```console
Generic Sort: System.Collections.Generic.List\`1[System.Int32] Time taken: 0.0789ms
Non-Generic Sort: System.Collections.ArrayList Time taken: 2.4324ms
```

<span data-ttu-id="b681e-127">Lo primero que verá aquí es que la ordenación de la lista genérica es significativamente más rápida que la de la lista no genérica.</span><span class="sxs-lookup"><span data-stu-id="b681e-127">The first thing you notice here is that sorting the generic list is significantly faster than for the non-generic list.</span></span> <span data-ttu-id="b681e-128">También puede observar que el tipo de la lista genérica es distinto ([System.Int32]), mientras que el tipo de la lista no genérica es generalizado.</span><span class="sxs-lookup"><span data-stu-id="b681e-128">You might also notice that the type for the generic list is distinct ([System.Int32]) whereas the type for the non-generic list is generalized.</span></span> <span data-ttu-id="b681e-129">Dado que el runtime sabe que el genérico `List<int>` es de tipo int, puede almacenar los elementos de la lista en una matriz de enteros subyacente en memoria, mientras el no genérico `ArrayList` tiene que convertir cada elemento de la lista como un objeto a medida que se almacena en una matriz de objetos en memoria.</span><span class="sxs-lookup"><span data-stu-id="b681e-129">Because the runtime knows the generic `List<int>` is of type int, it can store the list elements in an underlying integer array in memory while the non-generic `ArrayList` has to cast each list element as an object as stored in an object array in memory.</span></span> <span data-ttu-id="b681e-130">Como se muestra en este ejemplo, las conversiones adicionales consumen tiempo y ralentizan la ordenación de la lista.</span><span class="sxs-lookup"><span data-stu-id="b681e-130">As shown through this example, the extra castings take up time and slow down the list sort.</span></span>

<span data-ttu-id="b681e-131">El último dato útil sobre el runtime es que conocer el tipo de la clase genérica supone una mejor experiencia de depuración.</span><span class="sxs-lookup"><span data-stu-id="b681e-131">The last useful thing about the runtime knowing the type of your generic is a better debugging experience.</span></span> <span data-ttu-id="b681e-132">Cuando se depura un genérico en C#, sabe qué tipo de cada elemento se encuentra en la estructura de datos.</span><span class="sxs-lookup"><span data-stu-id="b681e-132">When you are debugging a generic in C#, you know what type each element is in your data structure.</span></span> <span data-ttu-id="b681e-133">Sin genéricos, no sabría qué tipo de cada elemento estaba presente.</span><span class="sxs-lookup"><span data-stu-id="b681e-133">Without generics, you would have no idea what type each element was.</span></span>

## <a name="further-reading-and-resources"></a><span data-ttu-id="b681e-134">Más información y recursos</span><span class="sxs-lookup"><span data-stu-id="b681e-134">Further reading and resources</span></span>

*   [<span data-ttu-id="b681e-135">Introducción a los genéricos C#</span><span class="sxs-lookup"><span data-stu-id="b681e-135">An Introduction to C# Generics</span></span>](https://msdn.microsoft.com/library/ms379564.aspx)
*   [<span data-ttu-id="b681e-136">Guía de programación de C#: genéricos</span><span class="sxs-lookup"><span data-stu-id="b681e-136">C# Programming Guide - Generics</span></span>](https://msdn.microsoft.com/library/512aeb7t.aspx)


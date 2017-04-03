---
title: "Información general (genéricos) de tipos genéricos"
description: "Información general (genéricos) de tipos genéricos"
keywords: .NET, .NET Core
author: kuhlenh
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: a315b111-8e48-446c-ab19-acb6405894a7
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 9827f9f37ce198b23bfd4e5fbca41cd86d5885a4
ms.lasthandoff: 03/02/2017

---

# <a name="generic-types-generics-overview"></a>Información general (genéricos) de tipos genéricos

Usamos genéricos en todo momento en C#, ya sea implícita o explícitamente. Al usar LINQ en C#, ¿alguna vez observó que estaba trabajando con IEnumerable<T>? O si alguna vez ha visto un ejemplo en línea de un "repositorio genérico" para comunicarse con bases de datos mediante Entity Framework, ¿observó que la mayoría de los métodos devuelven IQueryable<T>? ¿Probablemente se pregunte qué significa la **T** en estos ejemplos y por qué aparece?

Los genéricos, introducidos en primer lugar en .NET Framework 2.0, implican cambios en el lenguaje de C# y en Common Language Runtime (CLR). Los **genéricos** son esencialmente una "plantilla de código" que permite a los desarrolladores definir estructuras de datos [con seguridad de tipos](https://msdn.microsoft.com/library/hbzz1a9a.aspx) sin confirmar un tipo de datos real. Por ejemplo, `List<T>` es un [colección genérica](https://msdn.microsoft.com/library/System.Collections.Generic.aspx) que se puede declarar y usar con cualquier tipo: `List<int>`, `List<string>`, `List<Person>`, etc..

Así que, ¿para qué sirven? ¿Por qué son útiles los genéricos? Para poder entenderlo, necesitamos echar un vistazo a una clase específica antes y después de agregar genéricos. Examinemos `ArrayList`. En C# 1.0, los elementos de `ArrayList` eran de tipo `object`. Esto significaba que cualquier elemento que se hubiese agregado se convertía desapercibidamente en `object`; lo mismo sucede al leer los elementos de la lista (este proceso se conoce como [conversión boxing](https://msdn.microsoft.com/library/yz2be5wk.aspx) y conversión unboxing respectivamente). La conversión boxing y la conversión unboxing repercuten en el rendimiento. Pero sobre todo, no hay ninguna manera de saber en tiempo de compilación cuál es el tipo real de los datos de la lista. Por ello, algunos códigos son frágiles. Los genéricos solucionan este problema proporcionando información adicional sobre el tipo de datos que va a contener cada instancia de la lista. En pocas palabras, solo puede agregar enteros a `List<int>` y solo puede agregar personas a `List<Person>`, etc..

Los genéricos también están disponibles en el runtime o **reificados**. Esto significa que el runtime conoce qué tipo de estructura de datos está usando y puede almacenarla en memoria de modo más eficaz.

Este es un pequeño programa que muestra la eficacia que supone conocer el tipo de estructura de datos en el runtime:

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

Este programa produce el siguiente resultado:

```console
Generic Sort: System.Collections.Generic.List\`1[System.Int32] Time taken: 0.0789ms
Non-Generic Sort: System.Collections.ArrayList Time taken: 2.4324ms

```

Lo primero que verá aquí es que la ordenación de la lista genérica es significativamente más rápida que la de la lista no genérica. También puede observar que el tipo de la lista genérica es distinto ([System.Int32]), mientras que el tipo de la lista no genérica es generalizado. Dado que el runtime sabe que el genérico `List<int>` es de tipo int, puede almacenar los elementos de la lista en una matriz de enteros subyacente en memoria, mientras el no genérico `ArrayList` tiene que convertir cada elemento de la lista como un objeto a medida que se almacena en una matriz de objetos en memoria. Como se muestra en este ejemplo, las conversiones adicionales consumen tiempo y ralentizan la ordenación de la lista.

El último dato útil sobre el runtime es que conocer el tipo de la clase genérica supone una mejor experiencia de depuración. Cuando se depura un genérico en C#, sabe qué tipo de cada elemento se encuentra en la estructura de datos. Sin genéricos, no sabría qué tipo de cada elemento estaba presente.

## <a name="further-reading-and-resources"></a>Más información y recursos

*   [Introducción a los genéricos C#](https://msdn.microsoft.com/library/ms379564.aspx)
*   [Guía de programación de C#: genéricos](https://msdn.microsoft.com/library/512aeb7t.aspx)


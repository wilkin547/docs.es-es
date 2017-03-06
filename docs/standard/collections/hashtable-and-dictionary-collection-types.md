---
title: Tipos de las colecciones Hashtable y Dictionary
description: Tipos de las colecciones Hashtable y Dictionary
keywords: .NET, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 0f18fac7-fd0d-4f25-a046-1d3d51de062e
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 58c87f9e86b5b97feb654e92a56f81940c201a6a
ms.lasthandoff: 03/02/2017

---

# <a name="hashtable-and-dictionary-collection-types"></a>Tipos de las colecciones Hashtable y Dictionary

La clase [System.Collections.Hashtable](https://docs.microsoft.com/dotnet/core/api/System.Collections.Hashtable) y las clases genéricas [System.Collections.Generic.Dictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2) y [System.Collections.Concurrent.ConcurrentDictionary<T>](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentDictionary-2) implementan la interfaz [System.Collections.IDictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.IDictionary). La clase genérica `Dictionary<T>` también implementa la interfaz genérica [IDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IDictionary-2). Por lo tanto, cada elemento de esta colección es un par de clave y valor.

Un objeto `Hashtable` consta de depósitos que contienen los elementos de la colección. Un depósito es un subgrupo virtual de elementos dentro de la colección `Hashtable`, lo que permite buscar y recuperar más fácil y rápidamente que en la mayoría de las colecciones. Cada depósito está asociado con un código hash, que se genera usando una función hash y se basa en la clave del elemento.

La clase genérica [HashSet&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.HashSet-1) es una colección no ordenada de elementos únicos. 

Una función hash es un algoritmo que devuelve un código hash numérico basado en una clave. La clave es el valor de alguna propiedad del objeto que se almacena. Una función hash siempre debe devolver el mismo código hash para la misma clave. Una función hash puede generar el mismo código hash para dos claves diferentes, pero las funciones hash que generan un código hash único para cada clave única tienen un rendimiento mejor al recuperar los elementos de la tabla hash.

Cada objeto que se usa como un elemento en una colección `Hashtable` debe ser capaz de generar un código hash para sí mismo usando una implementación del método `GetHashCode`. 

Cuando se agrega un objeto a una colección `Hashtable`, se almacena en el depósito que está asociado con el código hash que coincide con el código hash del objeto. Cuando se busca un valor en la colección `Hashtable`, se genera el código hash para ese valor y se busca el depósito asociado con ese código hash.

Por ejemplo, una función hash para una cadena podría tomar los códigos ASCII de cada carácter de la cadena y sumarlos todos para generar un código hash. La cadena "picnic" tendría un código hash que es diferente del código hash de la cadena "cesta"; por lo tanto, las cadenas "picnic" y "cesta" estarían en depósitos distintos. En cambio, "bolsa" y "lobas" tendrían el mismo código hash y estarían en el mismo cubo.

Las clases `Dictionary<T>` y `ConcurrentDictionary<T>` tienen la misma funcionalidad que la clase `Hashtable`. Una clase `Dictionary<T>` de un tipo específico (distinto de `Object`) proporciona un rendimiento mejor que una clase `Hashtable` para tipos de valor. Esto se debe a que los elementos de `Hashtable` son del tipo `Object` y, por lo tanto, las conversiones boxing y unboxing se suelen producir al almacenar o recuperar un tipo de valor. La clase `ConcurrentDictionary<T>` debe usarse cuando varios subprocesos puedan tener acceso a la colección simultáneamente.

## <a name="see-also"></a>Vea también

[Hashtable](https://docs.microsoft.com/dotnet/core/api/System.Collections.Hashtable)

[IDictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.IDictionary)

[Dictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2)

[System.Collections.Generic.IDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IDictionary-2)

[System.Collections.Concurrent.ConcurrentDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentDictionary-2)

[Tipos de colección utilizados normalmente](commonly-used-collection-types.md)



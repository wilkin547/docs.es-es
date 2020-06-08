---
title: Tipos de las colecciones Hashtable y Dictionary
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Hashtable class, grouping data in collections
- Hashtable collection type
- hash tables
- grouping data in collections, Hashtable collection type
- hash function
- collections [.NET Framework], Hashtable collection type
ms.assetid: bfc20837-3d02-4fc7-8a8f-c5215b6b7913
ms.openlocfilehash: b228f5db16ba01969b77d601becfb94ac0506d1e
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287970"
---
# <a name="hashtable-and-dictionary-collection-types"></a>Tipos de las colecciones Hashtable y Dictionary
La clase <xref:System.Collections.Hashtable?displayProperty=nameWithType> y las clases genéricas <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> y <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=nameWithType> implementan la interfaz <xref:System.Collections.IDictionary?displayProperty=nameWithType>. La clase genérica <xref:System.Collections.Generic.Dictionary%602> también implementa la interfaz genérica <xref:System.Collections.Generic.IDictionary%602>. Por lo tanto, cada elemento de esta colección es un par de clave y valor.  
  
 Un objeto <xref:System.Collections.Hashtable> consta de depósitos que contienen los elementos de la colección. Un depósito es un subgrupo virtual de elementos dentro de la colección <xref:System.Collections.Hashtable>, lo que permite buscar y recuperar más fácil y rápidamente que en la mayoría de las colecciones. Cada depósito está asociado con un código hash, que se genera usando una función hash y se basa en la clave del elemento.  
  
 La clase genérica <xref:System.Collections.Generic.HashSet%601> es una colección no ordenada de elementos únicos.  
  
 Una función hash es un algoritmo que devuelve un código hash numérico basado en una clave. La clave es el valor de alguna propiedad del objeto que se almacena. Una función hash siempre debe devolver el mismo código hash para la misma clave. Una función hash puede generar el mismo código hash para dos claves diferentes, pero las funciones hash que generan un código hash único para cada clave única tienen un rendimiento mejor al recuperar los elementos de la tabla hash.  
  
 Cada objeto que se usa como un elemento en una colección <xref:System.Collections.Hashtable> debe ser capaz de generar un código hash para sí mismo usando una implementación del método <xref:System.Object.GetHashCode%2A>. Sin embargo, también puede especificar una función hash para todos los elementos de una colección <xref:System.Collections.Hashtable> usando un constructor <xref:System.Collections.Hashtable> que acepta una implementación de <xref:System.Collections.IHashCodeProvider> como uno de sus parámetros.  
  
 Cuando se agrega un objeto a una colección <xref:System.Collections.Hashtable>, se almacena en el depósito que está asociado con el código hash que coincide con el código hash del objeto. Cuando se busca un valor en la colección <xref:System.Collections.Hashtable>, se genera el código hash para ese valor y se busca el depósito asociado con ese código hash.  
  
 Por ejemplo, una función hash para una cadena podría tomar los códigos ASCII de cada carácter de la cadena y sumarlos todos para generar un código hash. La cadena "picnic" tendría un código hash que es diferente del código hash de la cadena "cesta"; por lo tanto, las cadenas "picnic" y "cesta" estarían en depósitos distintos. En cambio, "bolsa" y "lobas" tendrían el mismo código hash y estarían en el mismo cubo.  
  
 Las clases <xref:System.Collections.Generic.Dictionary%602> y <xref:System.Collections.Concurrent.ConcurrentDictionary%602> tienen la misma funcionalidad que la clase <xref:System.Collections.Hashtable>. Una clase <xref:System.Collections.Generic.Dictionary%602> de un tipo específico (distinto de <xref:System.Object>) proporciona un rendimiento mejor que una clase <xref:System.Collections.Hashtable> para tipos de valor. Esto se debe a que los elementos de <xref:System.Collections.Hashtable> son del tipo <xref:System.Object> y, por lo tanto, las conversiones boxing y unboxing se suelen producir al almacenar o recuperar un tipo de valor. La clase <xref:System.Collections.Concurrent.ConcurrentDictionary%602> debe usarse cuando varios subprocesos puedan tener acceso a la colección simultáneamente.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Collections.Hashtable>
- <xref:System.Collections.IDictionary>
- <xref:System.Collections.IHashCodeProvider>
- <xref:System.Collections.Generic.Dictionary%602>
- <xref:System.Collections.Generic.IDictionary%602?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=nameWithType>
- [Tipos de colección utilizados normalmente](commonly-used-collection-types.md)

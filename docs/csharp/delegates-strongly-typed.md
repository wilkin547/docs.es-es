---
title: Delegados fuertemente tipados
description: "Obtenga información sobre cómo usar tipos de delegado genéricos para declarar tipos personalizados al crear una característica que necesita delegados."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 564a683d-352b-4e57-8bac-b466529daf6b
ms.openlocfilehash: 467ba18f8e032b9b3b8f480d4b10c92d0d7ba3b9
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2017
---
# <a name="strongly-typed-delegates"></a>Delegados fuertemente tipados

[Anterior](delegate-class.md)

En el artículo anterior pudo ver que con la palabra clave `delegate` se crean tipos de delegados concretos. 

La clase abstracta Delegate proporciona la infraestructura para el acoplamiento débil y la invocación. Los tipos de delegado concretos se hacen mucho más útiles al adoptar y aplicar la seguridad de tipos para los métodos agregados a la lista de invocación de un objeto de delegado. Cuando se usa palabra clave `delegate` y se define un tipo de delegado concreto, el compilador genera esos métodos.

En la práctica, esto daría lugar a la creación de nuevos tipos de delegado siempre que necesitara otra firma de método. Este trabajo podría resultar tedioso pasado un tiempo. Cada nueva característica exige nuevos tipos de delegado.

Afortunadamente, esto no es necesario. .NET Core Framework contiene varios tipos que puede volver a usar siempre que necesite tipos de delegado. Son definiciones [genéricas](programming-guide/generics/index.md), por lo que puede declarar personalizaciones cuando necesite nuevas declaraciones de método. 

El primero de estos tipos es el tipo <xref:System.Action> y distintas variaciones:

```csharp
public delegate void Action();
public delegate void Action<in T>(T arg);
public delegate void Action<in T1, in T2>(T1 arg1, T2 arg2);
// Other variations removed for brevity.
```

El modificador `in` del argumento de tipo genérico se trata en el artículo sobre la covarianza.

Hay variaciones de la `Action` delegado que contienen hasta 16 argumentos como <xref:System.Action%6016>.
Es importante que estas definiciones usen argumentos genéricos distintos para cada uno de los argumentos del delegado: eso proporciona la máxima flexibilidad. Los argumentos de método no tienen que ser, aunque pueden ser, del mismo tipo.

Use uno de los tipos `Action` para cualquier tipo de delegado que tenga un tipo de valor devuelto void.

.NET Framework también incluye varios tipos de delegado genéricos que se pueden usar para los tipos de delegado que devuelven valores:

```csharp
public delegate TResult Func<out TResult>();
public delegate TResult Func<in T1, out TResult>(T1 arg);
public delegate TResult Func<in T1, in T2, out TResult>(T1 arg1, T2 arg2);
// Other variations removed for brevity
```

El modificador `out` del argumento de tipo genérico result se trata en el artículo sobre la covarianza.

Hay variaciones de la `Func` delegar con hasta 16 argumentos de entrada como <xref:System.Func%6017>.
Por convención, el tipo del resultado siempre es el último parámetro de tipo de todas las declaraciones `Func`.

Use uno de los tipos `Func` para cualquier tipo de delegado que devuelva un valor.

Hay también un especializada <xref:System.Predicate%601> para un delegado que devuelve una prueba en un valor único:

```csharp
public delegate bool Predicate<in T>(T obj);
```

Es posible que observe que para cualquier tipo `Predicate` existe un tipo `Func` estructuralmente equivalente, por ejemplo:

```csharp
Func<string, bool> TestForString;
Predicate<string> AnotherTestForString;
```

Podría llegar a pensar que estos dos tipos son equivalentes, pero no lo son.
Estas dos variables no se pueden usar indistintamente. A una variable de un tipo no se le puede asignar el otro tipo. El sistema de tipos de C# usa los nombres de los tipos definidos, no la estructura.

Todas estas definiciones de tipos de delegado de la biblioteca de .NET Core deberían significar que no es necesario definir ningún tipo de delegado nuevo para cualquier característica nueva creada que exija delegados. Estas definiciones genéricas deberían proporcionar todos los tipos de delegado necesarios para la mayoría de las situaciones. Puede simplemente crear instancias de uno de estos tipos con los parámetros de tipo necesarios. En el caso de los algoritmos que se pueden convertir en genéricos, estos delegados se pueden usar como tipos genéricos. 

Esto debería ahorrar tiempo y minimizar el número de nuevos tipos que es necesario crear para poder trabajar con delegados.

En el siguiente artículo se verán varios patrones comunes para trabajar con delegados en la práctica.

[Siguiente](delegates-patterns.md)

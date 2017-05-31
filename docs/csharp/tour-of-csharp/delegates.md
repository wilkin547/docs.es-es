---
title: Delegados de C# | Un paseo por el lenguaje C#
description: "Conozca los enlaces más recientes con delegados en C#."
keywords: ". NET, csharp, delegado, lambda, enlace más reciente"
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 3cc27357-3ac2-43a1-aad0-86a77b88f884
ms.translationtype: Human Translation
ms.sourcegitcommit: 19006cc5f24ffc66b92e53e8174c6bd33c249679
ms.openlocfilehash: 9cfefa5f781944b41828ebb61004f960e6cf3d59
ms.contentlocale: es-es
ms.lasthandoff: 04/14/2017

---

# <a name="delegates"></a>Delegados

Un ***tipo de delegado*** representa las referencias a métodos con una lista de parámetros determinada y un tipo de valor devuelto. Los delegados permiten tratar métodos como entidades que se puedan asignar a variables y se puedan pasar como parámetros. Los delegados son similares al concepto de punteros de función en otros lenguajes, pero a diferencia de los punteros de función, los delegados están orientados a objetos y presentan seguridad de tipos.

En el siguiente ejemplo se declara y usa un tipo de delegado denominado `Function`.

[!code-csharp[DelegateExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L3-L37)]

Una instancia del tipo de delegado `Function` puede hacer referencia a cualquier método que tome un argumento `double` y devuelva un valor `double`. El método `Apply` aplica una función dada a los elementos de un argumento `double[]`, y devuelve un valor `double[]` con los resultados. En el método `Main`, `Apply` se usa para aplicar tres funciones diferentes a un valor `double[]`.

Un delegado puede hacer referencia a un método estático (como `Square` o `Math.Sin` en el ejemplo anterior) o un método de instancia (como `m.Multiply` en el ejemplo anterior). Un delegado que hace referencia a un método de instancia también hace referencia a un objeto determinado y, cuando se invoca el método de instancia a través del delegado, ese objeto se convierte en `this` en la invocación.

Los delegados también pueden crearse mediante funciones anónimas, que son "métodos insertados" que se crean sobre la marcha. Las funciones anónimas pueden ver las variables locales de los métodos adyacentes. Por lo tanto, el ejemplo de multiplicador anterior puede escribirse más fácilmente sin utilizarse una clase de Multiplier:

[!code-csharp[LambdaExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L44-L44)]

Una propiedad interesante y útil de un delegado es que no sabe ni necesita conocer la clase del método al que hace referencia; lo único que importa es que el método al que se hace referencia tenga los mismos parámetros y el tipo de valor devuelto que el delegado.

>[!div class="step-by-step"]
[Anterior](enums.md)
[Siguiente](attributes.md)


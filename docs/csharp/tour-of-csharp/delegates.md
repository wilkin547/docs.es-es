---
title: 'Delegados de C#: un paseo por el lenguaje C#'
description: Conozca los enlaces más recientes con delegados en C#.
ms.date: 02/27/2020
ms.assetid: 3cc27357-3ac2-43a1-aad0-86a77b88f884
ms.openlocfilehash: b1740ddc65dcb0ee8775f4cbaa8356293ea55fae
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159174"
---
# <a name="delegates"></a>Delegados

Un ***tipo de delegado*** representa las referencias a métodos con una lista de parámetros determinada y un tipo de valor devuelto. Los delegados permiten tratar métodos como entidades que se puedan asignar a variables y se puedan pasar como parámetros. Los delegados son similares al concepto de punteros de función de otros lenguajes. A diferencia de los punteros de función, los delegados están orientados a objetos y tienen seguridad de tipos.

En el siguiente ejemplo se declara y usa un tipo de delegado denominado `Function`.

[!code-csharp[DelegateExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L3-L37)]

Una instancia del tipo de delegado `Function` puede hacer referencia a cualquier método que tome un argumento `double` y devuelva un valor `double`. El método `Apply` aplica una función dada a los elementos de un argumento `double[]`, y devuelve un valor `double[]` con los resultados. En el método `Main`, `Apply` se usa para aplicar tres funciones diferentes a un valor `double[]`.

Un delegado puede hacer referencia a un método estático (como `Square` o `Math.Sin` en el ejemplo anterior) o un método de instancia (como `m.Multiply` en el ejemplo anterior). Un delegado que hace referencia a un método de instancia también hace referencia a un objeto determinado y, cuando se invoca el método de instancia a través del delegado, ese objeto se convierte en `this` en la invocación.

Los delegados también se pueden crear mediante funciones anónimas, que son "métodos insertados" que se crean al declararlos. Las funciones anónimas pueden ver las variables locales de los métodos adyacentes. En el ejemplo siguiente no se crea una clase:

[!code-csharp[LambdaExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L44-L44)]

Un delegado no sabe ni necesita conocer la clase del método al que hace referencia; lo único que importa es que el método al que se hace referencia tenga los mismos parámetros y el tipo de valor devuelto que el delegado.

>[!div class="step-by-step"]
>[Anterior](interfaces.md)
>[Siguiente](attributes.md)

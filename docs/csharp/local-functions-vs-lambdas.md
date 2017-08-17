---
title: Funciones locales frente a expresiones lambda
description: "Por qué las funciones locales pueden ser una opción mejor que las expresiones lambda"
keywords: "C#, .NET, .NET Core, Características más recientes, Novedades, funciones locales, expresiones lambda"
author: BillWagner
ms.author: wiwagn
ms.date: 06/27/2016
ms.topic: article
ms.prod: visual-studio-dev-15
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 368d1752-3659-489a-97b4-f15d87e49ae3
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 315d4c5ee1f16c4fe59599c3a37437b112b784f6
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---

### <a name="local-functions-compared-to-lambda-expressions"></a>Funciones locales frente a expresiones lambda

A primera vista, las [funciones locales](programming-guide/classes-and/structs/local-functions.md) y las [expresiones lambda](lambda-expressions.md) son muy similares.
Dependiendo de sus necesidades, las funciones locales pueden ser una solución mucho mejor y más sencilla.

Vamos a examinar las diferencias entre las implementaciones de la función local y la expresión lambda del algoritmo factorial. Primero la versión que usa una función local:

[!code-csharp[LocalFunctionFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Factorial recursivo con función local")]

Compare esa implementación con una versión que use expresiones lambda:

[!code-csharp[26_LambdaFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Factorial recursivo con expresiones lambda")]

Primero, las expresiones lambda se implementan mediante la creación de instancias de un delegado y la invocación de este. Las funciones locales se implementan como llamadas a métodos.
La creación de instancias necesaria para las expresiones lambda significa asignaciones de memoria adicionales, lo que puede ser un factor de rendimiento en rutas de acceso de código crítico en el tiempo.
Las funciones locales no suponen esta sobrecarga. En el ejemplo anterior, la versión de las funciones locales tiene 2 asignaciones menos que la versión de la expresión lambda.

Este método recursivo es lo suficientemente sencillo para que la función local se implemente como un método privado con el nombre generado por el compilador. Su única diferencia de otros métodos privados es que semánticamente tiene su ámbito dentro de la función externa.

En segundo lugar, es posible llamar a las funciones locales antes de que se definan. Las expresiones lambda se deben declarar antes de definirse. Esto significa que las funciones locales son más fáciles de usar en algoritmos recursivos, como se ha mostrado anteriormente.

Observe que la versión con la expresión lambda debe declarar e inicializar la expresión lambda, `nthFactorial`, antes de definirla. De no hacerlo, se produce un error en tiempo de compilación por hacer referencia a `nthFactorial` antes de asignarlo.
Los algoritmos recursivos son más fáciles de crear con funciones locales.

En tercer lugar, en las expresiones lambda, el compilador siempre debe crear una clase anónima y una instancia de esa clase para almacenar cualquier variable capturada por la clausura. Considere este ejemplo asincrónico:

[!code-csharp[TaskLambdaExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Tarea que devuelve un método con una expresión lambda")]

La clausura de esta expresión lambda contiene las variables `address`, `index` y `name`. En el caso de las funciones locales, el objeto que implementa el cierre puede ser un tipo `struct`. Se guardaría en una asignación.

> [!NOTE]
> La función local equivalente de este método también usa una clase para el cierre. Si el cierre de una función local se implementa como `class` o `struct` es un detalle de implementación. Una función local puede usar `struct` mientras una expresión lambda siempre usará `class`.

[!code-csharp[TaskLocalFunctionExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#29_TaskExample "Método de devolución de tarea con función local")]

Una ventaja final que no se muestra en este ejemplo es que las funciones locales pueden implementarse como iteradores, con la sintaxis `yield return` para producir una secuencia de valores.

Aunque las funciones locales pueden parecer redundantes con respecto a las expresiones lambda, en realidad tienen finalidades y usos diferentes.
Las funciones locales son más eficaces si se quiere escribir una función a la que solo se llame desde el contexto de otro método.


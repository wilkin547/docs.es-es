---
title: Funciones locales frente a expresiones lambda
description: "Por qué las funciones locales pueden ser una opción mejor que las expresiones lambda"
keywords: "C#, .NET, .NET Core, Características más recientes, Novedades, funciones locales, expresiones lambda"
author: BillWagner
ms.author: wiwagn
ms.date: 10/27/2016
ms.topic: article
ms.prod: visual-studio-dev-15
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 368d1752-3659-489a-97b4-f15d87e49ae3
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: bba2a8d183f928e298c452f6ec132f3eb9dffbd3
ms.lasthandoff: 03/13/2017

---

### <a name="local-functions-compared-to-lambda-expressions"></a>Funciones locales frente a expresiones lambda

En algunos casos de uso podría crear una expresión lambda y usarla sin necesidad de crear una función local. Este es método asincrónico de ejemplo que hace justamente eso:

[!code-csharp[TaskLambdaExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Tarea que devuelve un método con una expresión lambda")]

Pero hay varias razones para preferir el uso de funciones locales en lugar de definir expresiones lambda y llamarlas.

En primer lugar, en las expresiones lambda, el compilador debe crear una clase anónima y una instancia de esa clase para almacenar cualquier variable capturada por la clausura. La clausura de esta expresión lambda contiene las variables `address`, `index` y `name`. 

En segundo lugar, las expresiones lambda se implementan mediante la creación de instancias de un delegado y la invocación de este. Las funciones locales se implementan como llamadas a métodos.
La creación de instancias necesaria para las expresiones lambda significa asignaciones de memoria adicionales, lo que puede ser un factor de rendimiento en rutas de acceso de código crítico en el tiempo.
Las funciones locales no suponen esta sobrecarga.

En tercer lugar, es posible llamar a las funciones locales antes de que se definan. Las expresiones lambda se deben declarar antes de definirse. Esto significa que las funciones locales son más fáciles de usar en algoritmos recursivos:

[!code-csharp[LocalFunctionFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Factorial recursivo con función local")]

Compare esa implementación con una versión que use expresiones lambda:

[!code-csharp[26_LambdaFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Factorial recursivo con expresiones lambda")]

Observe que la versión con la expresión lambda debe declarar e inicializar la expresión lambda, `nthFactorial`, antes de definirla. De no hacerlo, se produce un error en tiempo de compilación por hacer referencia a `nthFactorial` antes de asignarlo.
Los algoritmos recursivos son más fáciles de crear con funciones locales. 

Aunque las funciones locales pueden parecer redundantes con respecto a las expresiones lambda, en realidad tienen finalidades y usos diferentes.
Las funciones locales son más eficaces si se quiere escribir una función a la que solo se llame desde el contexto de otro método.



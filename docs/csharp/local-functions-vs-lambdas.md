---
title: Funciones locales frente a expresiones lambda
description: "Obtenga información sobre por qué las funciones locales pueden ser una opción mejor que las expresiones lambda."
keywords: "C#, .NET, .NET Core, Características más recientes, Novedades, funciones locales, expresiones lambda"
author: BillWagner
ms.author: wiwagn
ms.date: 06/27/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 368d1752-3659-489a-97b4-f15d87e49ae3
ms.openlocfilehash: 20312b58a24dc991791edad4bb92d3a8ca6d501a
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2017
---
# <a name="local-functions-compared-to-lambda-expressions"></a>Funciones locales en comparación con las expresiones lambda

A primera vista, las [funciones locales](programming-guide/classes-and-structs/local-functions.md) y las [expresiones lambda](lambda-expressions.md) son muy similares. En muchos casos, la elección entre usar expresiones lambda y funciones locales es una cuestión de estilo y preferencias personales. Sin embargo, hay diferencias reales en donde puede usar uno de los dos que debe tener en cuenta.

Vamos a examinar las diferencias entre las implementaciones de la función local y la expresión lambda del algoritmo factorial. Primero la versión que usa una función local:

[!code-csharp[LocalFunctionFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Recursive factorial using local function")]

Compare esa implementación con una versión que use expresiones lambda:

[!code-csharp[26_LambdaFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Recursive factorial using lambda expressions")]

Las funciones locales tienen nombres. Las expresiones lambda son métodos anónimos que se asignan a variables que están `Func` o `Action` tipos. Cuando se declara una función local, los tipos de argumento y el tipo de valor devuelto forman parte de la declaración de función. En lugar de formar parte del cuerpo de la expresión lambda expresión, los tipos de argumento y el tipo de valor devuelto forman parte de la declaración de tipo de variable de la expresión lambda. Esas dos diferencias pueden generar código más claro.

Funciones locales tienen reglas diferentes para la asignación definitiva que las expresiones lambda. Puede hacer referencia a una declaración de función local desde cualquier lugar del código donde esté dentro del ámbito. Una expresión lambda debe asignarse a una variable de delegado antes de pueda obtener acceso a (o llamar a través de la delgate que hacen referencia a la expresión lambda.) Observe que la versión con la expresión lambda debe declarar e inicializar la expresión lambda, `nthFactorial`, antes de definirla. De no hacerlo, se produce un error en tiempo de compilación por hacer referencia a `nthFactorial` antes de asignarlo.
Estas diferencias significan que son más fáciles de crear mediante funciones locales algoritmos recursivos. Puede declarar y definir una función local que llama a sí mismo. Expresiones lambda deben declaradas y se asigna un valor predeterminado antes de que se pueden volver a asignarse a un cuerpo que hace referencia a la misma expresión lambda.

Reglas de asignación definitiva también afecta a las variables que se capturan por la epression de función o expresión lamdba local. Funciones locales y reglas de la expresión lambda exigen que las variables capturadas definitivamente se asignan en el momento cuando la expresión de función o expresión lambda local se convierte en un delegado. La diferencia es que las expresiones lambda se convierten en delegados cuando se declaran. Funciones locales se convierten en delegados solo cuando se usa como un delegado. Si se declara una función local y solo hacer referencia a él llamando al igual que un método, no se convertirán a un delegado. Esta regla permite declarar una función local en cualquier ubicación adecuada en su ámbito de inclusión. Es común para declarar funciones locales al final del método principal, después de las instrucciones return.

En tercer lugar, el compilador puede realizar un análisis estático que permite funciones locales asignar definitivamente variables capturadas en el ámbito de inclusión. Considere este ejemplo:

```csharp
bool M()
{
    int y;
    Local();
    return y;

    void Local() => y = 0;
}
```

El compilador puede determinar que `Local` definitivamente asigna `y` cuando se llama. Dado que `Local` se llama antes de la `return` instrucción, `y` se asigna definitiely en el `return` instrucción.

El análisis que permite que el análisis permite la diferencia cuarta.
Dependiendo de su uso, funciones locales pueden evitar las asignaciones del montón que siempre son necesarias para las expresiones lambda. Si una función local nunca se convierte en un delegado, y ninguna de las variables capturadas por la función local se captura por otras expresiones lambda o funciones locales que se convierten en delegados, el compilador puede evitar las asignaciones del montón. 

Considere este ejemplo asincrónico:

[!code-csharp[TaskLambdaExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Task returning method with lambda expression")]

La clausura de esta expresión lambda contiene las variables `address`, `index` y `name`. En el caso de las funciones locales, el objeto que implementa el cierre puede ser un tipo `struct`. Luego se pasarían ese tipo de estructura por referencia a la función local. Esta diferencia de implementación se guarde en una asignación.

La creación de instancias es necesario para las expresiones lambda significa asignaciones de memoria adicional, lo que pueden ser un factor de rendimiento en las rutas de acceso del código crítico en el tiempo.
Las funciones locales no suponen esta sobrecarga. En el ejemplo anterior, la versión de las funciones locales tiene 2 asignaciones menos que la versión de la expresión lambda.

> [!NOTE]
> La función local equivalente de este método también usa una clase para el cierre. Si el cierre de una función local se implementa como `class` o `struct` es un detalle de implementación. Una función local puede usar `struct` mientras una expresión lambda siempre usará `class`.

[!code-csharp[TaskLocalFunctionExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#29_TaskExample "Task returning method with local function")]

Una ventaja final que no se muestra en este ejemplo es que las funciones locales pueden implementarse como iteradores, con la sintaxis `yield return` para producir una secuencia de valores. El `yield return` instrucción no se permite en expresiones lambda.

Aunque las funciones locales pueden parecer redundantes con respecto a las expresiones lambda, en realidad tienen finalidades y usos diferentes.
Las funciones locales son más eficaces si se quiere escribir una función a la que solo se llame desde el contexto de otro método.

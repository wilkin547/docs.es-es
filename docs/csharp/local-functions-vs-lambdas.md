---
title: Funciones locales frente a expresiones lambda
description: Obtenga información sobre por qué las funciones locales pueden ser una opción mejor que las expresiones lambda.
ms.date: 06/27/2016
ms.technology: csharp-advanced-concepts
ms.assetid: 368d1752-3659-489a-97b4-f15d87e49ae3
ms.openlocfilehash: 13cc3fe47bbcd6a465347a6c991b2006586c78fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173346"
---
# <a name="local-functions-compared-to-lambda-expressions"></a>Funciones locales frente a expresiones lambda

A primera vista, las [funciones locales](programming-guide/classes-and-structs/local-functions.md) y las [expresiones lambda](./programming-guide/statements-expressions-operators/lambda-expressions.md) son muy similares. En muchos casos, la elección entre usar expresiones lambda y funciones locales es una cuestión de estilo y de preferencia personal, aunque hay diferencias que debe tener en cuenta acerca de dónde puede usar una u otra.

Vamos a examinar las diferencias entre las implementaciones de la función local y la expresión lambda del algoritmo factorial. Primero la versión que usa una función local:

[!code-csharp[LocalFunctionFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Recursive factorial using local function")]

Compare esa implementación con una versión que use expresiones lambda:

[!code-csharp[26_LambdaFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Recursive factorial using lambda expressions")]

Las funciones locales tienen nombres, mientras que las expresiones lambda son métodos anónimos que se asignan a variables que son tipos `Func` o `Action`. Cuando se declara una función local, los tipos de argumento y el tipo de valor devuelto forman parte de la declaración de función. En lugar de formar parte del cuerpo de la expresión lambda, los tipos de argumento y el tipo de valor devuelto forman parte de la declaración de tipo de variable de la expresión lambda. Estas dos diferencias pueden hacer que el código sea más claro.

Las funciones locales tienen reglas diferentes de las expresiones lambda para la asignación definitiva. Se puede hacer referencia a una declaración de función local desde cualquier ubicación del código que esté dentro del ámbito. Las expresiones lambda se deben asignar a una variable de delegado antes de poder acceder a ellas (o para poder llamarlas mediante el delegado que hace referencia a la expresión lambda). Observe que la versión con la expresión lambda debe declarar e inicializar la expresión lambda, `nthFactorial`, antes de definirla. De no hacerlo, se produce un error en tiempo de compilación por hacer referencia a `nthFactorial` antes de asignarlo.
Estas diferencias implican que los algoritmos recursivos son más fáciles de crear usando funciones locales. Puede declarar y definir una función local que se llama a sí misma. Las expresiones lambda se deben declarar y se les debe asignar un valor predeterminado para que se les pueda volver a asignar un cuerpo que haga referencia a la misma expresión lambda.

Las reglas de asignación definitiva también afectan a las variables que se capturan con la función local o la expresión lambda. Tanto las funciones locales como las reglas de expresiones lambda exigen que las variables capturadas se asignen definitivamente en el momento en que la función local o la expresión lambda se convierta en un delegado. La diferencia está en que las expresiones lambda se convierten en delegados en el momento en que se declaran, mientras que las funciones locales se convierten en delegados solo cuando se usan como delegados. Si se declara una función local y solo se hace referencia a ella llamándola como un método, no se convertirá en un delegado. Esta regla le permite declarar una función local en cualquier ubicación adecuada de su ámbito de inclusión. Es habitual declarar funciones locales al final del método principal, después de cualquier instrucción "return".

En tercer lugar, el compilador puede efectuar un análisis estático que permita que las funciones locales asignen definitivamente variables capturadas en el ámbito de inclusión. Considere este ejemplo:

```csharp
int M()
{
    int y;
    LocalFunction();
    return y;

    void LocalFunction() => y = 0;
}
```

El compilador puede determinar que `LocalFunction` asigna `y` definitivamente cuando se le llama. Como se llama a `LocalFunction` antes de la instrucción `return`, `y` se asigna definitivamente en la instrucción `return`.

El análisis que proporciona el análisis de ejemplo posibilita la cuarta diferencia.
Dependiendo de su uso, las funciones locales pueden evitar las asignaciones de montón que siempre son necesarias para las expresiones lambda. Si una función local no se convierte nunca en un delegado y ninguna de las variables capturadas con la función local se captura con otras expresiones lambda o funciones locales que se han convertido en delegados, el compilador puede evitar las asignaciones de montón.

Considere este ejemplo asincrónico:

[!code-csharp[TaskLambdaExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Task returning method with lambda expression")]

La clausura de esta expresión lambda contiene las variables `address`, `index` y `name`. En el caso de las funciones locales, el objeto que implementa el cierre puede ser un tipo `struct`. Luego, ese tipo de estructura se pasaría por referencia a la función local. Esta diferencia de implementación supondría un ahorro en una asignación.

La creación de instancias necesaria para las expresiones lambda significa asignaciones de memoria adicionales, lo que puede ser un factor de rendimiento en rutas de acceso de código crítico en el tiempo.
Las funciones locales no suponen esta sobrecarga. En el ejemplo anterior, la versión de las funciones locales tiene 2 asignaciones menos que la versión de la expresión lambda.

> [!NOTE]
> La función local equivalente de este método también usa una clase para el cierre. Si el cierre de una función local se implementa como `class` o `struct` es un detalle de implementación. Una función local puede usar `struct` mientras una expresión lambda siempre usará `class`.

[!code-csharp[TaskLocalFunctionExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#TaskExample "Task returning method with local function")]

Una ventaja final que no se muestra en este ejemplo es que las funciones locales pueden implementarse como iteradores, con la sintaxis `yield return` para producir una secuencia de valores. La instrucción `yield return` no está permitida en las expresiones lambda.

Aunque las funciones locales pueden parecer redundantes con respecto a las expresiones lambda, en realidad tienen finalidades y usos diferentes.
Las funciones locales son más eficaces si se quiere escribir una función a la que solo se llame desde el contexto de otro método.

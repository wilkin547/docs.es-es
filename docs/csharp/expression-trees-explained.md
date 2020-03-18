---
title: Árboles de expresiones en detalle
description: Obtenga información sobre los árboles de expresión y cómo son útiles en la traducción de algoritmos para la ejecución externa y la inspección de código antes de ejecutarlo.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: bbcdd339-86eb-4ae5-9911-4c214a39a92d
ms.openlocfilehash: 12093e9c9246c87cc5ea3aedaca6ba34acacce4d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "73036990"
---
# <a name="expression-trees-explained"></a>Árboles de expresiones en detalle

[Anterior: Información general](expression-trees.md)

Los árboles de expresiones son estructuras de datos que definen código. Se basan en las mismas estructuras que usa un compilador para analizar el código y generar el resultado compilado. A medida que vaya leyendo este tutorial, observará cierta similitud entre los árboles de expresiones y los tipos usados en las API de Roslyn para compilar [analizadores y correcciones de código](https://github.com/dotnet/roslyn-analyzers).
(Los analizadores y las correcciones de código son paquetes de NuGet que realizan un análisis estático en código y pueden sugerir posibles correcciones para un desarrollador). Los conceptos son similares y el resultado final es una estructura de datos que permite examinar el código fuente de forma significativa. En cambio, los árboles de expresiones se basan en un conjunto de clases y API totalmente diferente a las API de Roslyn.

Veamos un ejemplo sencillo.
Aquí tiene una línea de código:

```csharp
var sum = 1 + 2;
```

Si fuera a analizarlo como un árbol de expresión, el árbol contiene varios nodos.
El nodo más externo es una instrucción de declaración de variable con asignación (`var sum = 1 + 2;`). Ese nodo exterior contiene varios nodos secundarios: una declaración de variable, un operador de asignación y una expresión que representa el lado derecho del signo igual. Esa expresión se subdivide aún más en expresiones que representan la operación de suma, y los operandos izquierdo y derecho de la suma.

Vamos a profundizar un poco más en las expresiones que constituyen el lado derecho del signo igual.
La expresión es `1 + 2`. Se trata de una expresión binaria. Concretamente, es una expresión binaria de suma. Una expresión binaria de suma tiene dos elementos secundarios, que representan los nodos izquierdo y derecho de la expresión de suma. Aquí, ambos nodos son expresiones constantes: El operador izquierdo es el valor `1` y el operador derecho, el valor `2`.

Visualmente, toda la instrucción es un árbol: puede empezar en el nodo raíz y desplazarse a cada uno de los nodos del árbol para ver el código que compone la instrucción:

- Instrucción de declaración de variable con asignación (`var sum = 1 + 2;`)
  - Declaración de tipo de variable implícita (`var sum`)
    - Palabra clave var implícita (`var`)
    - Declaración de nombre de variable (`sum`)
  - Operador de asignación (`=`)
  - Expresión binaria de suma (`1 + 2`)
    - Operando izquierdo (`1`)
    - Operador de suma (`+`)
    - Operando derecho (`2`)

Esto puede parecer complicado, pero resulta muy eficaz. Siguiendo el mismo proceso, puede descomponer expresiones mucho más complicadas. Tomemos esta expresión como ejemplo:

```csharp
var finalAnswer = this.SecretSauceFunction(
    currentState.createInterimResult(), currentState.createSecondValue(1, 2),
    decisionServer.considerFinalOptions("hello")) +
    MoreSecretSauce('A', DateTime.Now, true);
```

La expresión anterior también es una declaración de variable con una asignación.
En este caso, el lado derecho de la asignación es un árbol mucho más complicado.
No voy a descomponer esta expresión, pero tenga en cuenta lo que podrían ser los distintos nodos. Hay llamadas de método que usan el objeto actual como un receptor, una que tiene un receptor `this` explícito y otra que no. Hay llamadas de método que usan otros objetos de receptor, así como argumentos constantes de tipos diferentes. Y, por último, hay un operador binario de suma. Según el tipo de valor devuelto de `SecretSauceFunction()` o `MoreSecretSauce()`, ese operador binario de suma puede ser una llamada de método a un operador de suma invalidado, que se resuelva en una llamada de método estático al operador binario de suma definido para una clase.

A pesar de esta aparente complejidad, la expresión anterior crea una estructura de árbol por la que se puede navegar con tanta facilidad como en el primer ejemplo. Puede seguir recorriendo los nodos secundarios para buscar nodos hoja en la expresión. Los nodos primarios tendrán referencias a sus elementos secundarios, y cada nodo tiene una propiedad que describe de qué tipo es.

La estructura de los árboles de expresiones es muy coherente. Una vez que conozca los aspectos básicos, podrá entender incluso el código más complejo cuando esté representado como un árbol de expresión. La elegancia de la estructura de datos explica cómo el compilador de C# puede analizar los programas de C# más complejos y crear resultados correctos a partir de código fuente complicado.

Una vez que esté familiarizado con la estructura de los árboles de expresiones, verá que los conocimientos que ha adquirido le permiten trabajar rápidamente con muchos escenarios más avanzados. Los árboles de expresiones ofrecen posibilidades increíbles.

Además de traducir algoritmos para ejecutarlos en otros entornos, se pueden usar árboles de expresiones para que resulte más fácil escribir algoritmos que inspeccionen el código antes de ejecutarlo. Puede escribir un método cuyos argumentos sean expresiones y, luego, examinar esas expresiones antes de ejecutar el código. El árbol de expresión es una representación completa del código: puede ver los valores de cualquier subexpresión.
Puede ver los nombres de propiedad y método. Puede ver el valor de las expresiones constantes.
También puede convertir un árbol de expresión en un delegado ejecutable y ejecutar el código.

Las API de los árboles de expresiones permiten crear árboles que representan casi cualquier construcción de código válida. En cambio, para que todo resulte lo más sencillo posible, algunas expresiones de C# no se pueden crear en un árbol de expresión. Un ejemplo son las expresiones asincrónicas (mediante las palabras clave `async` y `await`). Si necesita algoritmos asincrónicos, tendría que manipular los objetos `Task` directamente, en lugar de confiar en la compatibilidad del compilador. Otro ejemplo es en la creación de bucles. Normalmente, puede crearlos usando bucles `for`, `foreach`, `while` o `do`. Como verá [más adelante en esta serie](expression-trees-building.md), las API de los árboles de expresiones admiten una expresión de bucle individual, con expresiones `break` y `continue` que controlan la repetición del bucle.

Lo único lo que no se puede hacer es modificar un árbol de expresión.  Los árboles de expresiones son estructuras de datos inmutables. Si quiere mutar (cambiar) un árbol de expresión, debe crear un nuevo árbol que sea una copia del original, pero con los cambios que quiera.

[Siguiente: Tipos de marco que admiten árboles de expresión](expression-classes.md)

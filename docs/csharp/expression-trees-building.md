---
title: Crear árboles de expresión
description: Obtenga información sobre técnicas para crear árboles de expresión.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: 542754a9-7f40-4293-b299-b9f80241902c
ms.openlocfilehash: c93eb16ebf2ff66dc0162afb6841f2cadfce174e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146052"
---
# <a name="building-expression-trees"></a>Crear árboles de expresión

[Anterior: Interpretación de expresiones](expression-trees-interpreting.md)

Hasta ahora, todos los árboles de expresión que ha visto se han creado con el compilador de C#. Todo lo que tenía que hacer era crear una expresión lambda que se asignaba a una variable de tipo `Expression<Func<T>>` o de algún tipo similar. Esa no es la única manera de crear un árbol de expresión. En muchos escenarios, puede que necesite crear una expresión en memoria en tiempo de ejecución.

Crear árboles de expresión es complicado por el hecho de que esos árboles de expresión son inmutables. Inmutable significa que debe crear el árbol desde las hojas hasta la raíz. Las API que usará para crear los árboles de expresión reflejan este hecho: los métodos que usará para crear un nodo toman todos sus elementos secundarios como argumentos. Veamos algunos ejemplos para mostrarle las técnicas.

## <a name="creating-nodes"></a>Crear nodos

Comencemos por algo relativamente sencillo de nuevo. Usaremos la expresión de adición con la que he estado trabajando en estas secciones:

```csharp
Expression<Func<int>> sum = () => 1 + 2;
```

Para crear ese árbol de expresión, debe crear los nodos de hoja.
Los nodos de hoja son constantes, por lo que puede usar el método `Expression.Constant` para crear los nodos:

```csharp
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
```

Después, creará la expresión de adición:

```csharp
var addition = Expression.Add(one, two);
```

Una vez que tenga la expresión de adición, puede crear la expresión lambda:

```csharp
var lambda = Expression.Lambda(addition);
```

Esta es una expresión lambda muy sencilla porque no contiene argumentos.
Posteriormente en esta sección, verá cómo asignar argumentos a parámetros y crear expresiones más complicadas.

Para las expresiones que son tan simples como esta, puede combinar todas las llamadas en una sola instrucción:

```csharp
var lambda = Expression.Lambda(
    Expression.Add(
        Expression.Constant(1, typeof(int)),
        Expression.Constant(2, typeof(int))
    )
);
```

## <a name="building-a-tree"></a>Crear un árbol

Estos son los aspectos básicos para crear un árbol de expresión en la memoria. Los árboles más complejos implican normalmente más tipos de nodo y más nodos en el árbol. Vamos a analizar un ejemplo más y a mostrar dos tipos de nodo que creará normalmente al crear árboles de expresión: los nodos de argumentos y los nodos de llamada al método.

Vamos a crear un árbol de expresión para crear esta expresión:

```csharp
Expression<Func<double, double, double>> distanceCalc =
    (x, y) => Math.Sqrt(x * x + y * y);
```

Comenzará creando expresiones de parámetro para `x` y `y`:

```csharp
var xParameter = Expression.Parameter(typeof(double), "x");
var yParameter = Expression.Parameter(typeof(double), "y");
```

La creación de expresiones de adición y multiplicación sigue el patrón que ya ha visto:

```csharp
var xSquared = Expression.Multiply(xParameter, xParameter);
var ySquared = Expression.Multiply(yParameter, yParameter);
var sum = Expression.Add(xSquared, ySquared);
```

Después, necesita crear una expresión de llamada al método para la llamada a `Math.Sqrt`.

```csharp
var sqrtMethod = typeof(Math).GetMethod("Sqrt", new[] { typeof(double) });
var distance = Expression.Call(sqrtMethod, sum);
```

Y, por último, coloque la llamada al método en una expresión lambda y asegúrese de definir los argumentos en dicha expresión:

```csharp
var distanceLambda = Expression.Lambda(
    distance,
    xParameter,
    yParameter);
```

En este ejemplo más complejo, verá un par de técnicas más que necesitará a menudo para crear árboles de expresión.

Primero, necesita crear los objetos que representan parámetros o variables locales antes de usarlos. Una vez que haya creado esos objetos, puede usarlos en su árbol de expresión siempre que los necesite.

Después, necesita usar un subconjunto de las API de reflexión para crear un objeto `MethodInfo`, de manera que pueda crear un árbol de expresión para tener acceso a ese método. Debe limitarse al subconjunto de las API de reflexión que están disponibles en la plataforma de .NET Core. De nuevo, estas técnicas se extenderán a otros árboles de expresión.

## <a name="building-code-in-depth"></a>Crear código en profundidad

No está limitado en lo que puede crear con estas API. En cambio, cuánto más complicado sea el árbol de expresión que quiera crear, más difícil será la administración y la lectura del código.

Vamos a crear un árbol de expresión que sea equivalente a este código:

```csharp
Func<int, int> factorialFunc = (n) =>
{
    var res = 1;
    while (n > 1)
    {
        res = res * n;
        n--;
    }
    return res;
};
```

Observe anteriormente que no he creado el árbol de expresión, sino simplemente el delegado. Con la clase `Expression` no puede crear expresiones lambda de instrucción. Aquí se muestra el código necesario para crear la misma función. Es complicado por el hecho de que no existe una API para crear un bucle `while`, en su lugar necesita crear un bucle que contenga una prueba condicional y un destino de la etiqueta para salir del bucle.

```csharp
var nArgument = Expression.Parameter(typeof(int), "n");
var result = Expression.Variable(typeof(int), "result");

// Creating a label that represents the return value
LabelTarget label = Expression.Label(typeof(int));

var initializeResult = Expression.Assign(result, Expression.Constant(1));

// This is the inner block that performs the multiplication,
// and decrements the value of 'n'
var block = Expression.Block(
    Expression.Assign(result,
        Expression.Multiply(result, nArgument)),
    Expression.PostDecrementAssign(nArgument)
);

// Creating a method body.
BlockExpression body = Expression.Block(
    new[] { result },
    initializeResult,
    Expression.Loop(
        Expression.IfThenElse(
            Expression.GreaterThan(nArgument, Expression.Constant(1)),
            block,
            Expression.Break(label, result)
        ),
        label
    )
);
```

El código para crear el árbol de expresión para la función factorial es bastante más largo, más complicado y está lleno de etiquetas, instrucciones Break y otros elementos que nos gustaría evitar en nuestras tareas de codificación diarias.

En esta sección, también he actualizado el código del visitante para visitar cada nodo de este árbol de expresión y escribir información sobre los nodos que se crean en este ejemplo. Puede [ver o descargar el código de ejemplo](https://github.com/dotnet/samples/tree/master/csharp/expression-trees) en el repositorio dotnet/docs de GitHub. Pruébelo compilando y ejecutando los ejemplos. Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="examining-the-apis"></a>Examinar las API

Las API del árbol de expresión son algunas de las más difíciles para navegar en .NET Core, pero no pasa nada. Su finalidad es una tarea más compleja: escribir código que genere código en tiempo de ejecución. Son inevitablemente complicadas a la hora de proporcionar un equilibrio entre la compatibilidad con todas las estructuras de control disponibles en el lenguaje de C# y mantener el área expuesta de las API tan pequeña como sea razonable. Este equilibrio significa que muchas estructuras de control se representan no por sus construcciones de C#, sino por construcciones que representan la lógica subyacente que genera el compilador desde estas construcciones de nivel superior.

Además, en este momento, existen expresiones de C# que no pueden crearse directamente con métodos de clase `Expression`. En general, estos serán las expresiones y los operadores más recientes que se han agregado a C# 5 y C# 6. (Por ejemplo, las expresiones `async` no pueden crearse y el operador `?.` nuevo no puede crearse directamente).

[Siguiente: Traducción de árboles de expresión](expression-trees-translating.md)

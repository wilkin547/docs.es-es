---
title: Tipos de marco que admiten árboles de expresión
description: Obtenga información sobre los tipos de marco que admiten árboles de expresión, la creación de árboles de expresión y las técnicas para trabajar con las API de árboles de expresión.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: e9c85021-0d36-48af-91b7-aaaa66f22654
ms.openlocfilehash: 548f5ba6a2de00d9556621791515555b6f6a325c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180444"
---
# <a name="framework-types-supporting-expression-trees"></a>Tipos de marco que admiten árboles de expresión

[Anterior: Árboles de expresiones en detalle](expression-trees-explained.md)

Hay una amplia lista de clases en .NET Core Framework que funcionan con árboles de expresiones.
En <xref:System.Linq.Expressions> puede ver la lista completa.
En lugar de analizarla al completo, vamos a explicar cómo se han diseñado las clases del marco.

En el diseño del lenguaje, una expresión es un cuerpo de código que se evalúa y devuelve un valor. Las expresiones pueden ser muy sencillas: la expresión constante `1` devuelve el valor constante de 1. También pueden ser más complicadas: la expresión `(-B + Math.Sqrt(B*B - 4 * A * C)) / (2 * A)` devuelve una raíz de una ecuación cuadrática (en el caso en el que la ecuación tenga una solución).  

## <a name="it-all-starts-with-systemlinqexpression"></a>Todo empieza con System.Linq.Expression

Una de las complejidades de trabajar con árboles de expresiones es que muchos tipos de expresiones distintos son válidos en muchos lugares de los programas. Piense en una expresión de asignación. El lado derecho de una asignación podría ser un valor constante, una variable, una expresión de llamada de método u otros elementos. Esa flexibilidad del lenguaje significa que puede encontrarse con muchos tipos de expresiones diferentes en cualquier parte de los nodos de un árbol al atravesar un árbol de expresión. Por lo tanto, lo más sencillo consiste en trabajar con el tipo de expresión base, siempre que sea posible. En cambio, en ocasiones necesitará saber más.
La clase de expresión base contiene una propiedad `NodeType` para ello.
Esta devuelve un elemento `ExpressionType`, que es una enumeración de tipos de expresiones posibles.
Una vez que sepa el tipo del nodo, puede convertirlo en ese tipo y realizar acciones específicas sabiendo el tipo del nodo de expresión. Puede buscar determinados tipos de nodo y, luego, trabajar con las propiedades específicas de ese tipo de expresión.

Por ejemplo, este código imprimirá el nombre de una variable para una expresión de acceso a la variable. He seguido el procedimiento que consiste en comprobar el tipo de nodo, convertirlo en una expresión de acceso a la variable y después comprobar las propiedades del tipo de expresión específico:

```csharp
Expression<Func<int, int>> addFive = (num) => num + 5;

if (addFive.NodeType == ExpressionType.Lambda)
{
    var lambdaExp = (LambdaExpression)addFive;

    var parameter = lambdaExp.Parameters.First();

    Console.WriteLine(parameter.Name);
    Console.WriteLine(parameter.Type);
}
```

## <a name="creating-expression-trees"></a>Crear árboles de expresiones

La clase `System.Linq.Expression` también contiene muchos métodos estáticos para crear expresiones. Estos métodos crean un nodo de expresión al usar los argumentos proporcionados para sus elementos secundarios. De esta manera, se crea una expresión a partir de sus nodos hoja. Por ejemplo, este código genera una expresión de agregar:

```csharp
// Addition is an add expression for "1 + 2"
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
var addition = Expression.Add(one, two);
```

En este sencillo ejemplo puede ver que hay muchos tipos implicados a la hora de crear árboles de expresiones y trabajar con ellos. Esta complejidad resulta necesaria para proporcionar las capacidades del vocabulario variado que ofrece el lenguaje C#.

## <a name="navigating-the-apis"></a>Navegar por las API

Hay tipos de nodos de expresión que se asignan a casi todos los elementos de sintaxis del lenguaje C#. Cada tipo tiene métodos específicos para ese tipo de elemento del lenguaje. Es mucha información como para recordarla toda. En lugar de intentar memorizar todo, estas son las técnicas que uso para trabajar con árboles de expresiones:

1. Fíjese en los miembros de la enumeración `ExpressionType` para determinar los posibles nodos que debe examinar. Esto resulta muy útil cuando quiere atravesar y comprender un árbol de expresión.
2. Fíjese en los miembros estáticos de la clase `Expression` para crear una expresión. Esos métodos pueden crear cualquier tipo de expresión a partir de un conjunto de sus nodos secundarios.
3. Fíjese en la clase `ExpressionVisitor` para crear un árbol de expresión modificado.

Encontrará más información a medida que observe cada una de esas tres áreas. Siempre encontrará lo que necesita empezando con uno de esos tres pasos.

 [Siguiente: Ejecutar árboles de expresión](expression-trees-execution.md)

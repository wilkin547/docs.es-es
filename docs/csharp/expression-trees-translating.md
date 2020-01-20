---
title: Traducción de árboles de expresión
description: Obtenga información sobre cómo visitar cada nodo en un árbol de expresión, mientras se crea una copia modificada de ese árbol de expresión.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: b453c591-acc6-4e08-8175-97e5bc65958e
ms.openlocfilehash: f60c447d5c89aa83f85073e642e621608131ed8d
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2020
ms.locfileid: "76115777"
---
# <a name="translate-expression-trees"></a>Traslado de árboles de expresión

[Anterior: Generación de expresiones](expression-trees-building.md)

En esta última sección, obtendrá información sobre cómo visitar cada nodo en un árbol de expresión, mientras se crea una copia modificada de ese árbol de expresión. Se trata de las técnicas que se van a usar en dos escenarios importantes. La primera consiste en comprender los algoritmos que se expresan mediante un árbol de expresión para poder trasladarlo a otro entorno. La segunda es cuando se quiere cambiar el algoritmo que se creó. Esto podría ser para agregar el registro, interceptar las llamadas de método y realizar un seguimiento de ellas, o con otros fines.

## <a name="translating-is-visiting"></a>Trasladar es visitar

El código que se compila para trasladar un árbol de expresión es una extensión de lo que ya se vio para visitar todos los nodos de un árbol. Al trasladar un árbol de expresión, se visitan todos los nodos y mientras se visitan, se crea el árbol nuevo. El nuevo árbol puede contener referencias a los nodos originales o a nodos nuevos que se colocaron en el árbol.

Vamos a verlo en acción mediante la visita a un árbol de expresión y la creación de un árbol nuevo con varios nodos de reemplazo. En este ejemplo, se van a sustituir todas las constantes con una constante que es diez veces mayor.
De lo contrario, el árbol de expresión se mantendrá intacto. En lugar de leer el valor de la constante y reemplazarlo con una constante nueva, este cambio se hará reemplazando el nodo constante con un nuevo nodo que realiza la multiplicación.

Aquí, una vez que se encuentre un nodo constante, se crea un nuevo nodo de multiplicación cuyos elementos secundarios son la constante original y la constante `10`:

```csharp
private static Expression ReplaceNodes(Expression original)
{
    if (original.NodeType == ExpressionType.Constant)
    {
        return Expression.Multiply(original, Expression.Constant(10));
    }
    else if (original.NodeType == ExpressionType.Add)
    {
        var binaryExpression = (BinaryExpression)original;
        return Expression.Add(
            ReplaceNodes(binaryExpression.Left),
            ReplaceNodes(binaryExpression.Right));
    }
    return original;
}
```

Al reemplazar el nodo original con el sustituto, se crea un árbol nuevo que contiene las modificaciones. Se puede comprobar mediante la compilación y ejecución del árbol reemplazado.

```csharp
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
var addition = Expression.Add(one, two);
var sum = ReplaceNodes(addition);
var executableFunc = Expression.Lambda(sum);

var func = (Func<int>)executableFunc.Compile();
var answer = func();
Console.WriteLine(answer);
```

La creación de un árbol nuevo es una combinación de visitar los nodos del árbol existente y crear nodos nuevos e insertarlos en el árbol.

En este ejemplo se muestra la importancia de la inmutabilidad de los árboles de expresión. Observe que el nuevo árbol creado anteriormente contiene una mezcla de los nodos recién creados y los nodos del árbol existente. Es seguro, ya que no se pueden modificar los nodos en el árbol existente. Esto puede producir eficiencias de memoria significativas.
Los mismos nodos se pueden usar en un árbol o en varios árboles de expresión. Dado que los nodos no se pueden modificar, se puede volver a usar el mismo nodo siempre que sea necesario.

## <a name="traversing-and-executing-an-addition"></a>Recorrer y ejecutar una adición

Vamos a comprobarlo mediante la creación de un segundo visitante que recorre el árbol de nodos de adición y calcula el resultado. Para ello, se pueden realizar algunas modificaciones en el visitante visto hasta el momento. En esta nueva versión, el visitante devolverá la suma parcial de la operación de adición hasta este punto. Para una expresión constante, es simplemente el valor de la expresión constante. Para una expresión de adición, el resultado es la suma de los operandos izquierdo y derecho, una vez que se recorren esos árboles.

```csharp
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
var three= Expression.Constant(3, typeof(int));
var four = Expression.Constant(4, typeof(int));
var addition = Expression.Add(one, two);
var add2 = Expression.Add(three, four);
var sum = Expression.Add(addition, add2);

// Declare the delegate, so we can call it
// from itself recursively:
Func<Expression, int> aggregate = null;
// Aggregate, return constants, or the sum of the left and right operand.
// Major simplification: Assume every binary expression is an addition.
aggregate = (exp) =>
    exp.NodeType == ExpressionType.Constant ?
    (int)((ConstantExpression)exp).Value :
    aggregate(((BinaryExpression)exp).Left) + aggregate(((BinaryExpression)exp).Right);

var theSum = aggregate(sum);
Console.WriteLine(theSum);
```

Aquí hay gran cantidad de código, pero los conceptos son muy accesibles.
Este código visita los elementos secundarios en una primera búsqueda de profundidad. Cuando encuentra un nodo constante, el visitante devuelve el valor de la constante. Tras la visita a los dos elementos secundarios por parte del visitante, ambos elementos habrán obtenido la suma calculada para ese subárbol. El nodo de adición ahora puede calcular la suma.
Una vez que se visiten todos los nodos en el árbol de expresión, se habrá calculado la suma. Se puede hacer el seguimiento de la ejecución ejecutando el ejemplo en el depurador y realizando el seguimiento de la ejecución.

Vamos a facilitar el seguimiento de cómo se analizan los nodos y cómo se calcula la suma mediante el recorrido del árbol. Esta es una versión actualizada del método agregado que incluye gran cantidad de información de seguimiento:

```csharp
private static int Aggregate(Expression exp)
{
    if (exp.NodeType == ExpressionType.Constant)
    {
        var constantExp = (ConstantExpression)exp;
        Console.Error.WriteLine($"Found Constant: {constantExp.Value}");
        return (int)constantExp.Value;
    }
    else if (exp.NodeType == ExpressionType.Add)
    {
        var addExp = (BinaryExpression)exp;
        Console.Error.WriteLine("Found Addition Expression");
        Console.Error.WriteLine("Computing Left node");
        var leftOperand = Aggregate(addExp.Left);
        Console.Error.WriteLine($"Left is: {leftOperand}");
        Console.Error.WriteLine("Computing Right node");
        var rightOperand = Aggregate(addExp.Right);
        Console.Error.WriteLine($"Right is: {rightOperand}");
        var sum = leftOperand + rightOperand;
        Console.Error.WriteLine($"Computed sum: {sum}");
        return sum;
    }
    else throw new NotSupportedException("Haven't written this yet");
}
```

Al ejecutarla en la misma expresión, produce el siguiente resultado:

```output
10
Found Addition Expression
Computing Left node
Found Addition Expression
Computing Left node
Found Constant: 1
Left is: 1
Computing Right node
Found Constant: 2
Right is: 2
Computed sum: 3
Left is: 3
Computing Right node
Found Addition Expression
Computing Left node
Found Constant: 3
Left is: 3
Computing Right node
Found Constant: 4
Right is: 4
Computed sum: 7
Right is: 7
Computed sum: 10
10
```

Realice el seguimiento del resultado y siga el código anterior. Debería poder averiguar cómo el código visita cada nodo y calcula la suma mientras recorre el árbol y busca la suma.

Ahora, veremos una ejecución diferente, con la expresión proporcionada por `sum1`:

```csharp
Expression<Func<int> sum1 = () => 1 + (2 + (3 + 4));
```

Este es el resultado de examinar esta expresión:

```output
Found Addition Expression
Computing Left node
Found Constant: 1
Left is: 1
Computing Right node
Found Addition Expression
Computing Left node
Found Constant: 2
Left is: 2
Computing Right node
Found Addition Expression
Computing Left node
Found Constant: 3
Left is: 3
Computing Right node
Found Constant: 4
Right is: 4
Computed sum: 7
Right is: 7
Computed sum: 9
Right is: 9
Computed sum: 10
10
```

Aunque la respuesta final es la misma, el recorrido del árbol es completamente diferente. Los nodos se recorren en un orden diferente, porque el árbol se construyó con diferentes operaciones que se producen en primer lugar.

## <a name="learning-more"></a>Obtener más información

En este ejemplo se muestra un pequeño subconjunto del código que se compilaría para recorrer e interpretar los algoritmos representados por un árbol de expresión. Para obtener una descripción completa de todo el trabajo necesario para compilar una biblioteca de propósito general que traduce árboles de expresión a otro lenguaje, lea [esta serie](https://docs.microsoft.com/archive/blogs/mattwar/linq-building-an-iqueryable-provider-series) de Matt Warren. Describe en detalle cómo traducir cualquier código que es posible encontrar en un árbol de expresión.

Espero que haya visto la verdadera eficacia de los árboles de expresión.
Puede examinar un conjunto de código, realizar los cambios que quiera en ese código y ejecutar la versión modificada. Como los árboles de expresión son inmutables, se pueden crear árboles nuevos mediante el uso de los componentes de árboles existentes. Esto minimiza la cantidad de memoria necesaria para crear árboles de expresión modificados.

[Siguiente: Resumen](expression-trees-summary.md)

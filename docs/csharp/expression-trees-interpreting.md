---
title: Interpretación de expresiones
description: Obtenga información sobre cómo escribir código para examinar la estructura de un árbol de expresión.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: adf73dde-1e52-4df3-9929-2e0670e28e16
ms.openlocfilehash: 1283d7d957c72558652b96cb428efd0f071f0184
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146013"
---
# <a name="interpreting-expressions"></a>Interpretación de expresiones

[Anterior: Ejecución de expresiones](expression-trees-execution.md)

Ahora, vamos a escribir código para examinar la estructura de un *árbol de expresión*. Cada nodo de un árbol de expresión será un objeto de una clase derivada de `Expression`.

Ese diseño hace que la visita de todos los nodos de un árbol de expresión sea una operación recursiva relativamente sencilla. La estrategia general es comenzar en el nodo raíz y determinar qué tipo de nodo es.

Si el tipo de nodo tiene elementos secundarios, visítelos recursivamente. En cada nodo secundario, repita el proceso que ha usado en el nodo raíz: determine el tipo, y si el tipo tiene elementos secundarios, visite cada uno de ellos.

## <a name="examining-an-expression-with-no-children"></a>Examinar una expresión sin elementos secundarios
Comencemos visitando cada nodo en un árbol de expresión muy sencillo.
Aquí se muestra el código que crea una expresión constante y, después, examina sus propiedades:

```csharp
var constant = Expression.Constant(24, typeof(int));

Console.WriteLine($"This is a/an {constant.NodeType} expression type");
Console.WriteLine($"The type of the constant value is {constant.Type}");
Console.WriteLine($"The value of the constant value is {constant.Value}");
```

Esto imprimirá lo siguiente:

```output
This is an Constant expression type
The type of the constant value is System.Int32
The value of the constant value is 24
```

Ahora, vamos a escribir el código que examinará esta expresión y también algunas propiedades importantes sobre este. Aquí se muestra el código:

## <a name="examining-a-simple-addition-expression"></a>Examinar una expresión de adición sencilla

Comencemos con el ejemplo de adición de la instrucción de esta sección.

```csharp
Expression<Func<int>> sum = () => 1 + 2;
```

> No estoy usando `var` para declarar este árbol de expresión, y no es posible porque el lado derecho de la asignación tiene un tipo implícito. Para comprender esto mejor, lea [aquí](implicitly-typed-lambda-expressions.md).

El nodo raíz es `LambdaExpression`. Para obtener el código interesante en el lado derecho del operador `=>`, necesita buscar uno de los elementos secundarios de `LambdaExpression`. Haremos esto con todas las expresiones de esta sección. El nodo primario nos ayuda a encontrar el tipo de valor devuelto de `LambdaExpression`.

Para examinar cada nodo de esta expresión, necesitaremos visitar recursivamente varios nodos. Aquí se muestra una primera implementación sencilla:

```csharp
Expression<Func<int, int, int>> addition = (a, b) => a + b;

Console.WriteLine($"This expression is a {addition.NodeType} expression type");
Console.WriteLine($"The name of the lambda is {((addition.Name == null) ? "<null>" : addition.Name)}");
Console.WriteLine($"The return type is {addition.ReturnType.ToString()}");
Console.WriteLine($"The expression has {addition.Parameters.Count} arguments. They are:");
foreach(var argumentExpression in addition.Parameters)
{
    Console.WriteLine($"\tParameter Type: {argumentExpression.Type.ToString()}, Name: {argumentExpression.Name}");
}

var additionBody = (BinaryExpression)addition.Body;
Console.WriteLine($"The body is a {additionBody.NodeType} expression");
Console.WriteLine($"The left side is a {additionBody.Left.NodeType} expression");
var left = (ParameterExpression)additionBody.Left;
Console.WriteLine($"\tParameter Type: {left.Type.ToString()}, Name: {left.Name}");
Console.WriteLine($"The right side is a {additionBody.Right.NodeType} expression");
var right= (ParameterExpression)additionBody.Right;
Console.WriteLine($"\tParameter Type: {right.Type.ToString()}, Name: {right.Name}");
```

Este ejemplo imprime el siguiente resultado:

```output
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 2 arguments. They are:
        Parameter Type: System.Int32, Name: a
        Parameter Type: System.Int32, Name: b
The body is a/an Add expression
The left side is a Parameter expression
        Parameter Type: System.Int32, Name: a
The right side is a Parameter expression
        Parameter Type: System.Int32, Name: b
```

Observará muchas repeticiones en el ejemplo de código anterior.
Vamos a limpiarlo y a crear un visitante del nodo de expresión con una finalidad más general. Para ello vamos a necesitar escribir un algoritmo recursivo. Cualquier nodo puede ser de un tipo que pueda tener elementos secundarios.
Cualquier nodo que tenga elementos secundarios necesita que los visitemos y determinemos cuál es ese nodo. Aquí se muestra una versión limpia que usa la recursividad para visitar las operaciones de adición:

```csharp
// Base Visitor class:
public abstract class Visitor
{
    private readonly Expression node;

    protected Visitor(Expression node)
    {
        this.node = node;
    }

    public abstract void Visit(string prefix);

    public ExpressionType NodeType => this.node.NodeType;
    public static Visitor CreateFromExpression(Expression node)
    {
        switch(node.NodeType)
        {
            case ExpressionType.Constant:
                return new ConstantVisitor((ConstantExpression)node);
            case ExpressionType.Lambda:
                return new LambdaVisitor((LambdaExpression)node);
            case ExpressionType.Parameter:
                return new ParameterVisitor((ParameterExpression)node);
            case ExpressionType.Add:
                return new BinaryVisitor((BinaryExpression)node);
            default:
                Console.Error.WriteLine($"Node not processed yet: {node.NodeType}");
                return default(Visitor);
        }
    }
}

// Lambda Visitor
public class LambdaVisitor : Visitor
{
    private readonly LambdaExpression node;
    public LambdaVisitor(LambdaExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This expression is a {NodeType} expression type");
        Console.WriteLine($"{prefix}The name of the lambda is {((node.Name == null) ? "<null>" : node.Name)}");
        Console.WriteLine($"{prefix}The return type is {node.ReturnType.ToString()}");
        Console.WriteLine($"{prefix}The expression has {node.Parameters.Count} argument(s). They are:");
        // Visit each parameter:
        foreach (var argumentExpression in node.Parameters)
        {
            var argumentVisitor = Visitor.CreateFromExpression(argumentExpression);
            argumentVisitor.Visit(prefix + "\t");
        }
        Console.WriteLine($"{prefix}The expression body is:");
        // Visit the body:
        var bodyVisitor = Visitor.CreateFromExpression(node.Body);
        bodyVisitor.Visit(prefix + "\t");
    }
}

// Binary Expression Visitor:
public class BinaryVisitor : Visitor
{
    private readonly BinaryExpression node;
    public BinaryVisitor(BinaryExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This binary expression is a {NodeType} expression");
        var left = Visitor.CreateFromExpression(node.Left);
        Console.WriteLine($"{prefix}The Left argument is:");
        left.Visit(prefix + "\t");
        var right = Visitor.CreateFromExpression(node.Right);
        Console.WriteLine($"{prefix}The Right argument is:");
        right.Visit(prefix + "\t");
    }
}

// Parameter visitor:
public class ParameterVisitor : Visitor
{
    private readonly ParameterExpression node;
    public ParameterVisitor(ParameterExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This is an {NodeType} expression type");
        Console.WriteLine($"{prefix}Type: {node.Type.ToString()}, Name: {node.Name}, ByRef: {node.IsByRef}");
    }
}

// Constant visitor:
public class ConstantVisitor : Visitor
{
    private readonly ConstantExpression node;
    public ConstantVisitor(ConstantExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This is an {NodeType} expression type");
        Console.WriteLine($"{prefix}The type of the constant value is {node.Type}");
        Console.WriteLine($"{prefix}The value of the constant value is {node.Value}");
    }
}
```

Este algoritmo es la base de un algoritmo que puede visitar cualquier `LambdaExpression` arbitrario. Existen muchas vulnerabilidades, concretamente que el código que he creado solo busca una muestra muy pequeña de los posibles conjuntos de nodos de árbol de expresión que puede encontrar. En cambio, todavía puede aprender bastante de lo que genera. (El caso predeterminado en el método `Visitor.CreateFromExpression` imprime un mensaje a la consola de error cuando se detecta un nuevo tipo de nodo. De esta manera, sabe que se va a agregar un nuevo tipo de expresión).

Cuando ejecuta este visitante en la expresión de adición que se muestra arriba, obtiene el siguiente resultado:

```output
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 2 argument(s). They are:
        This is an Parameter expression type
        Type: System.Int32, Name: a, ByRef: False
        This is an Parameter expression type
        Type: System.Int32, Name: b, ByRef: False
The expression body is:
        This binary expression is a Add expression
        The Left argument is:
                This is an Parameter expression type
                Type: System.Int32, Name: a, ByRef: False
        The Right argument is:
                This is an Parameter expression type
                Type: System.Int32, Name: b, ByRef: False
```

Ahora que ha creado una implementación de visitante más general, puede visitar y procesar muchos más tipos de expresiones diferentes.

## <a name="examining-an-addition-expression-with-many-levels"></a>Examinar una expresión de adición con muchos niveles

Vamos a probar un ejemplo más complicado, todavía limitando los tipos de nodo solo a los de adición:

```csharp
Expression<Func<int>> sum = () => 1 + 2 + 3 + 4;
```

Antes de que ejecute esto en el algoritmo de visitante, haga un ejercicio de reflexión para calcular cuál podría ser el resultado. Recuerde que el operador `+` es un *operador binario*: debe tener dos elementos secundarios, que representen los operandos izquierdo y derecho. Existen varias maneras posibles de construir un árbol que pueda ser correcto:

```csharp
Expression<Func<int>> sum1 = () => 1 + (2 + (3 + 4));
Expression<Func<int>> sum2 = () => ((1 + 2) + 3) + 4;

Expression<Func<int>> sum3 = () => (1 + 2) + (3 + 4);
Expression<Func<int>> sum4 = () => 1 + ((2 + 3) + 4);
Expression<Func<int>> sum5 = () => (1 + (2 + 3)) + 4;
```

Puede ver la separación en dos respuestas posibles para resaltar la más prometedora. La primera representa las expresiones *asociativas por la derecha*. La segunda representa las expresiones *asociativas por la izquierda*.
La ventaja de los dos formatos es que el formato escala a cualquier número arbitrario de expresiones de adición.

Si ejecuta esta expresión a través del visitante, verá este resultado y comprobará que la expresión de adición simple es *asociativa por la izquierda*.

Para ejecutar este ejemplo, y ver el árbol de expresión completo, tuve que realizar un cambio en el árbol de expresión de origen. Cuando el árbol de expresión contiene todas las constantes, el árbol resultante simplemente contiene el valor constante de `10`. El compilador realiza toda la adición y reduce la expresión a su forma más simple. Simplemente con agregar una variable a la expresión es suficiente para ver el árbol original:

```csharp
Expression<Func<int, int>> sum = (a) => 1 + a + 3 + 4;
```

Cree un visitante para esta suma y ejecute el visitante para ver este resultado:

```output
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 1 argument(s). They are:
        This is an Parameter expression type
        Type: System.Int32, Name: a, ByRef: False
The expression body is:
        This binary expression is a Add expression
        The Left argument is:
                This binary expression is a Add expression
                The Left argument is:
                        This binary expression is a Add expression
                        The Left argument is:
                                This is an Constant expression type
                                The type of the constant value is System.Int32
                                The value of the constant value is 1
                        The Right argument is:
                                This is an Parameter expression type
                                Type: System.Int32, Name: a, ByRef: False
                The Right argument is:
                        This is an Constant expression type
                        The type of the constant value is System.Int32
                        The value of the constant value is 3
        The Right argument is:
                This is an Constant expression type
                The type of the constant value is System.Int32
                The value of the constant value is 4
```

También puede ejecutar cualquiera de los otros ejemplos a través del código de visitante y ver qué árbol representa. Aquí se muestra un ejemplo de la expresión `sum3` anterior (con un parámetro adicional para evitar que el compilador calcule la constante):

```csharp
Expression<Func<int, int, int>> sum3 = (a, b) => (1 + a) + (3 + b);
```

Aquí se muestra el resultado del visitante:

```output
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 2 argument(s). They are:
        This is an Parameter expression type
        Type: System.Int32, Name: a, ByRef: False
        This is an Parameter expression type
        Type: System.Int32, Name: b, ByRef: False
The expression body is:
        This binary expression is a Add expression
        The Left argument is:
                This binary expression is a Add expression
                The Left argument is:
                        This is an Constant expression type
                        The type of the constant value is System.Int32
                        The value of the constant value is 1
                The Right argument is:
                        This is an Parameter expression type
                        Type: System.Int32, Name: a, ByRef: False
        The Right argument is:
                This binary expression is a Add expression
                The Left argument is:
                        This is an Constant expression type
                        The type of the constant value is System.Int32
                        The value of the constant value is 3
                The Right argument is:
                        This is an Parameter expression type
                        Type: System.Int32, Name: b, ByRef: False
```

Tenga en cuenta que los paréntesis no forman parte del resultado. No existen nodos en el árbol de expresión que representen los paréntesis en la expresión de entrada. La estructura del árbol de expresión contiene toda la información necesaria para comunicar la precedencia.

## <a name="extending-from-this-sample"></a>Ampliar a partir de este ejemplo

El ejemplo trata solo los árboles de expresión más básicos. El código que ha visto en esta sección solo controla enteros constantes y el operador binario `+`. Como último ejemplo, vamos a actualizar el visitante para que controle una expresión más complicada. Hagamos que funcione para esto:

```csharp
Expression<Func<int, int>> factorial = (n) =>
    n == 0 ?
    1 :
    Enumerable.Range(1, n).Aggregate((product, factor) => product * factor);
```

Este código representa una posible implementación para la función *factorial* matemática. La manera en que he escrito este código resalta dos limitaciones en la creación de árboles de expresión asignando expresiones lambda a las expresiones. En primer lugar, las expresiones lambda de instrucción no están permitidas. Eso significa que no puedo usar bucles, bloques, instrucciones IF/ELSE ni otras estructuras de control comunes en C#. Estoy limitado al uso de expresiones. En segundo lugar, no puedo llamar recursivamente a la misma expresión.
Podría si ya fuera un delegado, pero no puedo llamarla en su forma de árbol de expresión. En la sección de [Crear árboles de expresión](expression-trees-building.md), obtendrá las técnicas para superar estas limitaciones.

En esta expresión, encontrará nodos de todos estos tipos:

1. Equal (expresión binaria)
2. Multiply (expresión binaria)
3. Conditional (la expresión ? :)
4. Expresión de llamada a método (con la llamada a `Range()` y `Aggregate()`)

Una manera de modificar el algoritmo de visitante es seguir ejecutándolo y escribir el tipo de nodo cada vez que llegue a su cláusula `default`. Después de varias iteraciones, habrá visto cada uno de los nodos potenciales. Después, tiene todo lo que necesita. El resultado será similar al siguiente:

```csharp
public static Visitor CreateFromExpression(Expression node)
{
    switch(node.NodeType)
    {
        case ExpressionType.Constant:
            return new ConstantVisitor((ConstantExpression)node);
        case ExpressionType.Lambda:
            return new LambdaVisitor((LambdaExpression)node);
        case ExpressionType.Parameter:
            return new ParameterVisitor((ParameterExpression)node);
        case ExpressionType.Add:
        case ExpressionType.Equal:
        case ExpressionType.Multiply:
            return new BinaryVisitor((BinaryExpression)node);
        case ExpressionType.Conditional:
            return new ConditionalVisitor((ConditionalExpression)node);
        case ExpressionType.Call:
            return new MethodCallVisitor((MethodCallExpression)node);
        default:
            Console.Error.WriteLine($"Node not processed yet: {node.NodeType}");
            return default(Visitor);
    }
}
```

ConditionalVisitor y MethodCallVisitor procesan esos dos nodos:

```csharp
public class ConditionalVisitor : Visitor
{
    private readonly ConditionalExpression node;
    public ConditionalVisitor(ConditionalExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This expression is a {NodeType} expression");
        var testVisitor = Visitor.CreateFromExpression(node.Test);
        Console.WriteLine($"{prefix}The Test for this expression is:");
        testVisitor.Visit(prefix + "\t");
        var trueVisitor = Visitor.CreateFromExpression(node.IfTrue);
        Console.WriteLine($"{prefix}The True clause for this expression is:");
        trueVisitor.Visit(prefix + "\t");
        var falseVisitor = Visitor.CreateFromExpression(node.IfFalse);
        Console.WriteLine($"{prefix}The False clause for this expression is:");
        falseVisitor.Visit(prefix + "\t");
    }
}

public class MethodCallVisitor : Visitor
{
    private readonly MethodCallExpression node;
    public MethodCallVisitor(MethodCallExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This expression is a {NodeType} expression");
        if (node.Object == null)
            Console.WriteLine($"{prefix}This is a static method call");
        else
        {
            Console.WriteLine($"{prefix}The receiver (this) is:");
            var receiverVisitor = Visitor.CreateFromExpression(node.Object);
            receiverVisitor.Visit(prefix + "\t");
        }

        var methodInfo = node.Method;
        Console.WriteLine($"{prefix}The method name is {methodInfo.DeclaringType}.{methodInfo.Name}");
        // There is more here, like generic arguments, and so on.
        Console.WriteLine($"{prefix}The Arguments are:");
        foreach(var arg in node.Arguments)
        {
            var argVisitor = Visitor.CreateFromExpression(arg);
            argVisitor.Visit(prefix + "\t");
        }
    }
}
```

Y el resultado del árbol de expresión será:

```output
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 1 argument(s). They are:
        This is an Parameter expression type
        Type: System.Int32, Name: n, ByRef: False
The expression body is:
        This expression is a Conditional expression
        The Test for this expression is:
                This binary expression is a Equal expression
                The Left argument is:
                        This is an Parameter expression type
                        Type: System.Int32, Name: n, ByRef: False
                The Right argument is:
                        This is an Constant expression type
                        The type of the constant value is System.Int32
                        The value of the constant value is 0
        The True clause for this expression is:
                This is an Constant expression type
                The type of the constant value is System.Int32
                The value of the constant value is 1
        The False clause for this expression is:
                This expression is a Call expression
                This is a static method call
                The method name is System.Linq.Enumerable.Aggregate
                The Arguments are:
                        This expression is a Call expression
                        This is a static method call
                        The method name is System.Linq.Enumerable.Range
                        The Arguments are:
                                This is an Constant expression type
                                The type of the constant value is System.Int32
                                The value of the constant value is 1
                                This is an Parameter expression type
                                Type: System.Int32, Name: n, ByRef: False
                        This expression is a Lambda expression type
                        The name of the lambda is <null>
                        The return type is System.Int32
                        The expression has 2 arguments. They are:
                                This is an Parameter expression type
                                Type: System.Int32, Name: product, ByRef: False
                                This is an Parameter expression type
                                Type: System.Int32, Name: factor, ByRef: False
                        The expression body is:
                                This binary expression is a Multiply expression
                                The Left argument is:
                                        This is an Parameter expression type
                                        Type: System.Int32, Name: product, ByRef: False
                                The Right argument is:
                                        This is an Parameter expression type
                                        Type: System.Int32, Name: factor, ByRef: False
```

## <a name="extending-the-sample-library"></a>Ampliar la biblioteca de ejemplo

Los ejemplos de esta sección muestran las técnicas principales para visitar y examinar nodos de un árbol de expresión. He pasado por alto muchas acciones que puede necesitar para concentrarme en las tareas principales a la hora de visitar y acceder a los nodos de un árbol de expresión.

En primer lugar, los visitantes solo controlan constantes que son enteros. Los valores constantes pueden ser cualquier otro tipo numérico, y el lenguaje de C# admite conversiones y promociones entre esos tipos. Una versión más sólida de este código reflejará todas esas capacidades.

Incluso en el último ejemplo se reconoce un subconjunto de los tipos de nodo posibles.
Todavía puede proporcionarle muchas expresiones que provocarán que se produzca un error.
En .NET Standard se incluye una implementación completa con el nombre <xref:System.Linq.Expressions.ExpressionVisitor> que puede controlar todos los tipos de nodo posibles.

Por último, la biblioteca que he usado en este artículo se ha creado con fines de demostración y aprendizaje. No está optimizada. La he escrito para dejar claro las estructuras que he usado y para resaltar las técnicas usadas para visitar los nodos y analizar lo que hay ahí. Una implementación de producción prestaría más atención al rendimiento.

Incluso con esas limitaciones, se encuentra en el camino correcto para escribir algoritmos que lean y comprendan árboles de expresión.

[Siguiente: Crear árboles de expresión](expression-trees-building.md)

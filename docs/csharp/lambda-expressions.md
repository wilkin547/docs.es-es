---
title: Expresiones lambda
description: Aprenda a usar expresiones lambda, término con el que se denomina a los bloques de código ejecutable que se pueden pasar como argumentos.
ms.author: ronpet
author: rpetrusha
ms.date: 11/22/2016
ms.assetid: b6a0539a-8ce5-4da7-adcf-44be345a2714
ms.openlocfilehash: e37f0e72ee02915d16509fb2ff48bd114e8ad466
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33217979"
---
# <a name="lambda-expressions"></a>Expresiones lambda #

Una *expresión lambda* es un bloque de código (una expresión o un bloque de instrucciones) que se trata como un objeto. Se puede pasar como argumento a los métodos y también la pueden devolver las llamadas al método. Las expresiones lambda se usan mayoritariamente para:

- Pasar el código que se debe ejecutar a métodos asincrónicos, como <xref:System.Threading.Tasks.Task.Run(System.Action)>.

- Escribir [expresiones de consulta LINQ](linq/index.md).

- Crear [árboles de expresión](expression-trees-building.md).

Las expresiones lambda son un código que se puede representar como un delegado o como un árbol de expresión que se compila en un delegado. El tipo de delegado específico de una expresión lambda depende de sus parámetros y del valor devuelto. Las expresiones lambda que no devuelven ningún valor corresponden a un delegado `Action` específico, según el número de parámetros. Las expresiones lambda que devuelven un valor corresponden a un delegado `Func` específico, según el número de parámetros. Por ejemplo, una expresión lambda que tiene dos parámetros pero que no devuelve ningún valor corresponde a un delegado <xref:System.Action%602>. Una expresión lambda que tiene un parámetro y devuelve un valor corresponde a un delegado <xref:System.Func%602>.

Una expresión lambda usa `=>`, el [operador de declaración lambda](language-reference/operators/lambda-operator.md), para separar del código ejecutable la lista de parámetros de la lambda. Para crear una expresión lambda, especifique los parámetros de entrada (si existen) a la izquierda del operador lambda y coloque el bloque de expresiones o de instrucciones en el otro lado. Por ejemplo, la expresión lambda de una sola línea `x => x * x` especifica un parámetro denominado `x` y devuelve el valor de `x` al cuadrado. Puede asignar esta expresión a un tipo delegado, como se muestra en el ejemplo siguiente:

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/lambda1.cs#1)]

También puede pasarla directamente como un argumento de método:

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/lambda2.cs#2)]

## <a name="expression-lambdas"></a>Lambdas de expresión ##

 Una expresión lambda con una expresión en el lado derecho del operador => se denomina *lambda de expresión*. Las lambdas de expresión se usan ampliamente en la construcción de [árboles de expresión](expression-trees.md). Una expresión lambda devuelve el resultado de evaluar la condición y tiene la siguiente forma:

```csharp
(input parameters) => expression
```

Los paréntesis solo son opcionales si la lambda tiene un parámetro de entrada; de lo contrario, son obligatorios. Para especificar cero parámetros de entrada, utilice paréntesis vacíos:

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/expression3.cs#1)]

Dos o más parámetros de entrada se separan por comas y se encierran entre paréntesis:

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/expression3.cs#2)]

Normalmente, el compilador usa la inferencia de tipos para determinar los tipos de parámetro, aunque a veces resulta difícil o imposible para el compilador deducir los tipos de entrada. Cuando ocurre esto, los tipos se pueden especificar explícitamente, como en el ejemplo siguiente:

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/expression3.cs#3)]

Observe en el ejemplo anterior que el cuerpo de una lambda de expresión puede estar compuesto de una llamada a método. Pero, si va a crear árboles de expresión que se evaluarán fuera de .NET Framework, como en SQL Server o en Entity Framework (EF), debe evitar usar llamadas a métodos en las expresiones lambda, puesto que los métodos podrían no tener ningún significado fuera del contexto de la implementación de .NET. Si opta por usar las llamadas a métodos en este caso, asegúrese de probarlas exhaustivamente para garantizar que las llamadas a métodos se pueden resolver correctamente.

## <a name="statement-lambdas"></a>Lambdas de instrucción ##

Una lambda de instrucción es similar a un lambda de expresión, salvo que las instrucciones se encierran entre llaves:

```csharp
(input parameters) => { statement; }
```

El cuerpo de una lambda de instrucción puede estar compuesto de cualquier número de instrucciones; sin embargo, en la práctica, generalmente no hay más de dos o tres.

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/statement1.cs#1)]

Las lambdas de instrucción, como los métodos anónimos, no se pueden utilizar para crear árboles de expresión.

## <a name="async-lambdas"></a>Lambdas asincrónicas ##

Puede crear fácilmente expresiones e instrucciones lambda que incorporen el procesamiento asincrónico mediante las palabras clave [async](language-reference/keywords/async.md) y [await](language-reference/keywords/await.md). Por ejemplo, en el ejemplo se llama a un método `ShowSquares` que se ejecuta de forma asincrónica.

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/async1.cs#1)]

Para obtener más información sobre cómo crear y usar métodos asincrónicos, vea [Programación asincrónica con async y await](programming-guide/concepts/async/index.md).

## <a name="lambda-expressions-and-tuples"></a>Expresiones lambda y tuplas ##

A partir de C# 7.0, el lenguaje C# proporciona compatibilidad integrada para las tuplas. Puede proporcionar una tupla como argumento a una expresión lambda, mientras que la expresión lambda también puede devolver una tupla. En algunos casos, el compilador de C# usa la inferencia de tipos para determinar los tipos de componentes de la tupla. 

Para definir una tupla, incluya entre paréntesis una lista delimitada por comas de los componentes. En el ejemplo siguiente se usa la tupla con 5 componentes para pasar una secuencia de números a una expresión lambda, que duplica cada valor y devuelve una tupla con 5 componentes que contiene el resultado de las multiplicaciones.

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/tuples1.cs#1)]

Normalmente, los campos de una tupla se denominan `Item1`, `Item2`, etc., aunque puede definir una tupla con componentes con nombre, como en el ejemplo siguiente.

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/tuples2.cs#1)]

Para obtener más información sobre la compatibilidad de las tuplas en C#, vea [C# Tuple types](tuples.md) (Tipos de tupla de C#).

## <a name="lambdas-with-the-standard-query-operators"></a>Lambdas con los operadores de consulta estándar ##

LINQ to Objects, entre otras implementaciones, tiene un parámetro de entrada cuyo tipo es uno de la familia <xref:System.Func%601> de delegados genéricos. Estos delegados usan parámetros de tipo para definir el número y el tipo de los parámetros de entrada, así como el tipo de valor devuelto del delegado. Los delegados `Func` son muy útiles para encapsular expresiones definidas por el usuario que se aplican a cada elemento en un conjunto de datos de origen. Por ejemplo, imagínese que tiene el delegado <xref:System.Func%601>, cuya sintaxis es esta:

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/query1.cs#1)]

Se pueden crear instancias del delegado con un código similar al siguiente:

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/query1.cs#2)]

donde `int` es un parámetro de entrada y `bool` es el valor devuelto. El valor devuelto siempre se especifica en el último parámetro de tipo. Al invocarse el siguiente delegado `Func`, devuelve true o false para indicar si el parámetro de entrada es igual a 5:

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/query1.cs#3)]

También puede proporcionar una expresión lambda cuando el tipo de argumento es <xref:System.Linq.Expressions.Expression%601>, (por ejemplo, en los operadores de consulta estándar que se definen en el tipo <xref:System.Linq.Queryable>). Al especificar un argumento <xref:System.Linq.Expressions.Expression%601>, la lambda se compila en un árbol de expresión. En el ejemplo siguiente se usa el operador de consulta estándar [System.Linq.Enumerable.Count](xref:System.Linq.Enumerable.Count%60%601(System.Collections.Generic.IEnumerable{%60%600})).

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/query1.cs#4)]

El compilador puede deducir el tipo del parámetro de entrada o también se puede especificar explícitamente. Esta expresión lambda en concreto cuenta aquellos enteros (`n`) que, divididos por dos, dan como resto 1.

El siguiente ejemplo genera una secuencia que contiene todos los elementos de la matriz `numbers` que preceden al 9, ya que ese es el primer número de la secuencia que no cumple la condición.

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/query1.cs#5)]

En el siguiente ejemplo se especifican varios parámetros de entrada encerrándolos entre paréntesis. El método devuelve todos los elementos de la matriz de números hasta que encuentra un número cuyo valor es menor que la posición ordinal en la matriz.

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/query1.cs#6)]

## <a name="type-inference-in-lambda-expressions"></a>Inferencia de tipos en expresiones lambda ##

Al escribir lambdas, no tiene por qué especificar un tipo para los parámetros de entrada, ya que el compilador puede deducir el tipo según el cuerpo de lambda, los tipos de parámetros y otros factores, tal como se describe en la especificación del lenguaje C#. Para la mayoría de los operadores de consulta estándar, la primera entrada es el tipo de los elementos en la secuencia de origen. Si está realizando una consulta sobre `IEnumerable<Customer>`, se deducirá que la variable de entrada será un objeto `Customer`, lo cual significa que se podrá tener acceso a sus métodos y propiedades:

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/infer1.cs#1)]

Las reglas generales para la inferencia de tipos de las lambdas son las siguientes:

- La lambda debe contener el mismo número de parámetros que el tipo delegado.

- Cada argumento de entrada de la lambda debe poder convertirse implícitamente a su parámetro de delegado correspondiente.

- El valor devuelto de la lambda (si existe) debe poder convertirse implícitamente al tipo de valor devuelto del delegado.

Observe que las expresiones lambda, en sí mismas, no tienen tipo, ya que el sistema de tipos comunes no tiene ningún concepto intrínseco de "expresión lambda". Sin embargo, a veces resulta práctico hablar coloquialmente del "tipo" de una expresión lambda. En estos casos, el tipo hace referencia al tipo del delegado o el tipo de <xref:System.Linq.Expressions.Expression> en el que se convierte la expresión lambda.

## <a name="variable-scope-in-lambda-expressions"></a>Ámbito de las variables en las expresiones lambda ##

Las lambdas pueden hacer referencia a las *variables externas* (vea [Métodos anónimos](programming-guide/statements-expressions-operators/anonymous-methods.md)) que están en el ámbito del método que define la función lambda o en el ámbito del tipo que contiene la expresión lambda. Las variables que se capturan de esta manera se almacenan para su uso en la expresión lambda, cuando de otro modo quedarían fuera de ámbito y serían eliminadas por la recolección de elementos no utilizados. Para poder utilizar una variable externa en una expresión lambda, debe estar previamente asignada. En el ejemplo siguiente se muestran estas reglas.

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/scope.cs#1)]

 Las reglas siguientes se aplican al ámbito de las variables en las expresiones lambda:

- Una variable capturada no se recolectará como elemento no utilizado hasta que el delegado que hace referencia a ella sea elegible para la recolección de elementos no utilizados.

- Las variables introducidas en una expresión lambda no son visibles en el método externo.

- Una expresión lambda no puede capturar directamente un parámetro `in`, `ref` o `out` desde un método que la englobe.

- Una instrucción return en una expresión lambda no hace que el método que la engloba devuelva un valor.

- Una expresión lambda no puede contener una instrucción `goto` , `break` o `continue` que esté dentro de la función lambda si el destino de la instrucción de salto está fuera del bloque. También es un error utilizar una instrucción de salto fuera del bloque de la función lambda si el destino está dentro del bloque.

## <a name="see-also"></a>Vea también ##

[LINQ (Language-Integrated Query)](../standard/using-linq.md)  (Language Integrated Query [LINQ])  
[Métodos anónimos](programming-guide/statements-expressions-operators/anonymous-methods.md)   
[Árboles de expresión](expression-trees.md)

---
title: 'Expresiones lambda: Guía de programación de C#'
ms.date: 07/29/2019
helpviewer_keywords:
- lambda expressions [C#]
- outer variables [C#]
- statement lambda [C#]
- expression lambda [C#]
- expressions [C#], lambda
ms.assetid: 57e3ba27-9a82-4067-aca7-5ca446b7bf93
ms.openlocfilehash: c549b9fcc91401aed846afd39e656b60e16afb74
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937599"
---
# <a name="lambda-expressions-c-programming-guide"></a>Expresiones lambda (Guía de programación de C#)

Una *expresión lambda* es una expresión que tiene cualquiera de estas dos formas:

- Una [lambda de expresión](#expression-lambdas) que tiene una expresión como cuerpo:

  ```csharp
  (input-parameters) => expression
  ```

- Una [lambda de instrucción](#statement-lambdas) que tiene un bloque de instrucciones como cuerpo:

  ```csharp  
  (input-parameters) => { <sequence-of-statements> }
  ```

Use el [operador de declaración lambda `=>`](../../language-reference/operators/lambda-operator.md) para separar la lista de parámetros de la lamba de su cuerpo. Para crear una expresión lambda, especifique los parámetros de entrada (si existen) a la izquierda del operador lambda y una expresión o bloque de instrucciones en el otro lado.

Toda expresión lambda se puede convertir en un tipo [delegado](../../language-reference/builtin-types/reference-types.md#the-delegate-type). El tipo delegado al que se puede convertir una expresión lambda se define según los tipos de sus parámetros y el valor devuelto. Si una expresión lambda no devuelve un valor, se puede convertir en uno de los tipos delegados `Action`; de lo contrario, se puede convertir en uno de los tipos delegados `Func`. Por ejemplo, una expresión lambda que tiene dos parámetros y no devuelve ningún valor corresponde a un delegado <xref:System.Action%602>. Una expresión lambda que tiene un parámetro y devuelve un valor se puede convertir en un delegado <xref:System.Func%602>. En el ejemplo siguiente, la expresión lambda `x => x * x`, que especifica un parámetro denominado `x` y devuelve el valor de `x` al cuadrado, se asigna a una variable de un tipo delegado:

[!code-csharp-interactive[lambda is delegate](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#Delegate)]

Las expresiones lambda también se pueden convertir en los tipos de [árbol de expresión](../concepts/expression-trees/index.md), como se muestra en los ejemplos siguientes:

[!code-csharp-interactive[lambda is expression tree](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#ExpressionTree)]

Puede usar expresiones lambda en cualquier código que requiera instancias de tipos delegados o de árboles de expresión, por ejemplo, como un argumento del método <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType> para pasar el código que se debe ejecutar en segundo plano. También puede usar expresiones lambda al escribir [LINQ en C#](../../linq/index.md), como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[lambda is argument in LINQ](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#Argument)]

Cuando se usa la sintaxis de método para llamar al método <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType> en la clase <xref:System.Linq.Enumerable?displayProperty=nameWithType>, por ejemplo en LINQ to Objects y en LINQ to XML, el parámetro es un tipo delegado <xref:System.Func%602?displayProperty=nameWithType>. Cuando se llama al método <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType> en la clase <xref:System.Linq.Queryable?displayProperty=nameWithType>, por ejemplo en LINQ to SQL, el tipo de parámetro es un tipo de árbol de expresión [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>). En ambos casos, se puede usar la misma expresión lambda para especificar el valor del parámetro. Esto hace que las dos llamadas `Select` tengan un aspecto similar aunque, de hecho, el tipo de objetos creados a partir las lambdas es distinto.
  
## <a name="expression-lambdas"></a>Lambdas de expresión

Una expresión lambda con una expresión en el lado derecho del operador `=>` se denomina *lambda de expresión*. Las lambdas de expresión se usan ampliamente en la construcción de [árboles de expresión](../concepts/expression-trees/index.md). Una expresión lambda devuelve el resultado de evaluar la condición y tiene la siguiente forma:

```csharp
(input-parameters) => expression
```

Los paréntesis solo son opcionales si la lambda tiene un parámetro de entrada; de lo contrario, son obligatorios.

Para especificar cero parámetros de entrada, utilice paréntesis vacíos:  

[!code-csharp[zero parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#ZeroParameters)]

Dos o más parámetros de entrada se separan por comas y se encierran entre paréntesis:

[!code-csharp[two parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#TwoParameters)]

A veces resulta imposible que el compilador deduzca los tipos de entrada. Puede especificar los tipos de manera explícita, tal como se muestra en el ejemplo siguiente:

[!code-csharp[explicitly typed parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#ExplicitlyTypedParameters)]

Los tipos de parámetro de entrada deben ser todos explícitos o todos implícitos; de lo contrario, se produce un error del compilador [CS0748](../../misc/cs0748.md).

El cuerpo de una expresión lambda puede constar de una llamada al método. Sin embargo, si crea árboles de expresión que se evalúan fuera del contexto de Common Language Runtime de .NET, como en SQL Server, no debe utilizar llamadas a métodos en expresiones lambda. Los métodos no tendrán ningún significado fuera del contexto de .NET Common Language Runtime.

## <a name="statement-lambdas"></a>Lambdas de instrucción

Una lambda de instrucción es similar a un lambda de expresión, salvo que las instrucciones se encierran entre llaves:

```csharp  
(input-parameters) => { <sequence-of-statements> }
```

El cuerpo de una lambda de instrucción puede estar compuesto de cualquier número de instrucciones; sin embargo, en la práctica, generalmente no hay más de dos o tres.

[!code-csharp-interactive[statement lambda](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#StatementLambda)]

Las expresiones lambdas no se pueden usar para crear árboles de expresión.
  
## <a name="async-lambdas"></a>Lambdas asincrónicas

Puede crear fácilmente expresiones e instrucciones lambda que incorporen el procesamiento asincrónico mediante las palabras clave [async](../../language-reference/keywords/async.md) y [await](../../language-reference/operators/await.md) . Por ejemplo, en el siguiente ejemplo de formularios Windows Forms se incluye un controlador de eventos que llama y espera un método asincrónico, `ExampleMethodAsync`.

```csharp
public partial class Form1 : Form
{
    public Form1()
    {
        InitializeComponent();
        button1.Click += button1_Click;
    }

    private async void button1_Click(object sender, EventArgs e)
    {
        await ExampleMethodAsync();
        textBox1.Text += "\r\nControl returned to Click event handler.\n";
    }

    private async Task ExampleMethodAsync()
    {
        // The following line simulates a task-returning asynchronous process.
        await Task.Delay(1000);
    }
}
```

Puede agregar el mismo controlador de eventos utilizando una lambda asincrónica. Para agregar este controlador, agregue un modificador `async` antes de la lista de parámetros lambda, como se muestra en el ejemplo siguiente:

```csharp
public partial class Form1 : Form
{
    public Form1()
    {
        InitializeComponent();
        button1.Click += async (sender, e) =>
        {
            await ExampleMethodAsync();
            textBox1.Text += "\r\nControl returned to Click event handler.\n";
        };
    }

    private async Task ExampleMethodAsync()
    {
        // The following line simulates a task-returning asynchronous process.
        await Task.Delay(1000);
    }
}
```

Para obtener más información sobre cómo crear y usar métodos asincrónicos, vea [Programación asincrónica con async y await](../concepts/async/index.md).

## <a name="lambda-expressions-and-tuples"></a>Expresiones lambda y tuplas

A partir de C# 7.0, el lenguaje C# proporciona compatibilidad integrada para las [tuplas](../../tuples.md). Puede proporcionar una tupla como argumento a una expresión lambda, mientras que la expresión lambda también puede devolver una tupla. En algunos casos, el compilador de C# usa la inferencia de tipos para determinar los tipos de componentes de la tupla.

Para definir una tupla, incluya entre paréntesis una lista delimitada por comas de los componentes. En el ejemplo siguiente se usa la tupla con tres componentes para pasar una secuencia de números a una expresión lambda, que duplica cada valor y devuelve una tupla con tres componentes que contiene el resultado de las multiplicaciones.

[!code-csharp-interactive[lambda and tuples](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasAndTuples.cs#WithoutComponentName)]

Normalmente, los campos de una tupla se denominan `Item1`, `Item2`, etc., aunque puede definir una tupla con componentes con nombre, como en el ejemplo siguiente.

[!code-csharp-interactive[lambda and named tuples](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasAndTuples.cs#WithComponentName)]

Para más información sobre las tuplas de C#, consulte el artículo sobre los [tipos de tuplas de C#](../../tuples.md).

## <a name="lambdas-with-the-standard-query-operators"></a>Lambdas con los operadores de consulta estándar

LINQ to Objects, entre otras implementaciones, tiene un parámetro de entrada cuyo tipo es uno de la familia <xref:System.Func%601> de delegados genéricos. Estos delegados usan parámetros de tipo para definir el número y el tipo de los parámetros de entrada, así como el tipo de valor devuelto del delegado. Los delegados`Func` son muy útiles para encapsular expresiones definidas por el usuario que se aplican a cada elemento en un conjunto de datos de origen. Por ejemplo, considere el tipo delegado <xref:System.Func%602>:  

```csharp
public delegate TResult Func<in T, out TResult>(T arg)
```

Se pueden crear instancias del delegado como una instancia `Func<int, bool>`, donde `int` es un parámetro de entrada y `bool` es el valor devuelto. El valor devuelto siempre se especifica en el último parámetro de tipo. Por ejemplo, `Func<int, string, bool>` define un delegado con dos parámetros de entrada, `int` y `string`, y un tipo de valor devuelto de `bool`. El delegado `Func` siguiente, cuando se invoca, devuelve un valor booleano que indica si el parámetro de entrada es igual a cinco:

[!code-csharp-interactive[Func example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#Func)]

También puede proporcionar una expresión lambda cuando el tipo de argumento es <xref:System.Linq.Expressions.Expression%601>, (por ejemplo, en los operadores de consulta estándar que se definen en el tipo <xref:System.Linq.Queryable>). Al especificar un argumento <xref:System.Linq.Expressions.Expression%601>, la lambda se compila en un árbol de expresión.
  
En el ejemplo siguiente se usa el operador de consulta estándar <xref:System.Linq.Enumerable.Count%2A>:

[!code-csharp-interactive[Count example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#Count)]

El compilador puede deducir el tipo del parámetro de entrada o también se puede especificar explícitamente. Esta expresión lambda particular cuenta aquellos enteros (`n`) que divididos por dos dan como resto 1.

El siguiente ejemplo genera una secuencia que contiene todos los elementos de la matriz `numbers` que preceden al 9, ya que ese es el primer número de la secuencia que no cumple la condición:

[!code-csharp-interactive[TakeWhile example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhile)]

En el siguiente ejemplo se especifican varios parámetros de entrada encerrándolos entre paréntesis. El método devuelve todos los elementos de la matriz `numbers` hasta que encuentra un número cuyo valor es menor que la posición ordinal en la matriz:

[!code-csharp-interactive[TakeWhile example 2](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhileWithIndex)]

## <a name="type-inference-in-lambda-expressions"></a>Inferencia de tipos en expresiones lambda

Al escribir lambdas, no tiene por qué especificar un tipo para los parámetros de entrada, ya que el compilador puede deducir el tipo según el cuerpo de lambda, los tipos de parámetros y otros factores, tal como se describe en la especificación del lenguaje C#. Para la mayoría de los operadores de consulta estándar, la primera entrada es el tipo de los elementos en la secuencia de origen. Si está realizando una consulta sobre `IEnumerable<Customer>`, se deducirá que la variable de entrada será un objeto `Customer`, lo cual significa que se podrá tener acceso a sus métodos y propiedades:  

```csharp
customers.Where(c => c.City == "London");
```

Las reglas generales para la inferencia de tipos de las lambdas son las siguientes:

- La lambda debe contener el mismo número de parámetros que el tipo delegado.

- Cada parámetro de entrada de la lambda debe poder convertirse implícitamente a su parámetro de delegado correspondiente.

- El valor devuelto de la lambda (si existe) debe poder convertirse implícitamente al tipo de valor devuelto del delegado.
  
Observe que las expresiones lambda, en sí mismas, no tienen tipo, ya que el sistema de tipos comunes no tiene ningún concepto intrínseco de "expresión lambda". Sin embargo, a veces resulta práctico hablar coloquialmente del "tipo" de una expresión lambda. En estos casos, el tipo hace referencia al tipo del delegado o el tipo de <xref:System.Linq.Expressions.Expression> en el que se convierte la expresión lambda.

## <a name="capture-of-outer-variables-and-variable-scope-in-lambda-expressions"></a>Captura de variables externas y el ámbito de las variables en las expresiones lambda

Las operaciones lambda pueden hacer referencia a *variables externas*. Estas son las variables que están en el ámbito del método que define la expresión lambda o en el ámbito del tipo que contiene la expresión lambda. Las variables que se capturan de esta manera se almacenan para su uso en la expresión lambda, cuando de otro modo quedarían fuera de ámbito y serían eliminadas por la recolección de elementos no utilizados. Para poder utilizar una variable externa en una expresión lambda, debe estar previamente asignada. En el ejemplo siguiente se muestran estas reglas:

[!code-csharp[variable scope](~/samples/snippets/csharp/programming-guide/lambda-expressions/VariableScopeWithLambdas.cs#VariableScope)]

Las reglas siguientes se aplican al ámbito de las variables en las expresiones lambda:  

- Una variable capturada no se recolectará como elemento no utilizado hasta que el delegado que hace referencia a ella sea elegible para la recolección de elementos no utilizados.

- Las variables introducidas en una expresión lambda no son visibles en el método envolvente.

- Una expresión lambda no puede capturar directamente un parámetro [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md) ni [out](../../language-reference/keywords/out-parameter-modifier.md) desde el método envolvente.

- Una instrucción [return](../../language-reference/keywords/return.md) en una expresión lambda no hace que el método envolvente devuelva un valor.

- Una expresión lambda no puede contener una instrucción [goto](../../language-reference/keywords/goto.md), [break](../../language-reference/keywords/break.md) ni [continue](../../language-reference/keywords/continue.md) si el destino de esa instrucción de salto está fuera del bloque de la expresión lambda. También es un error utilizar una instrucción de salto fuera del bloque de la expresión lambda si el destino está dentro del bloque.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [Expresiones de función anónima](~/_csharplang/spec/expressions.md#anonymous-function-expressions) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="featured-book-chapter"></a>Capítulo destacado del libro

[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) (Delegados, eventos y expresiones lambda) en [C# 3.0 Cookbook, Tercera edición: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29) (Más de 250 soluciones para programadores de C# 3.0)  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [LINQ (Language Integrated Query)](../concepts/linq/index.md)
- [Árboles de expresión](../concepts/expression-trees/index.md)
- [Funciones locales frente a expresiones lambda](../../local-functions-vs-lambdas.md)
- [Expresiones lambda con tipo implícito](../../implicitly-typed-lambda-expressions.md)
- [Ejemplos de C# de Visual Studio 2008 (vea los archivos de ejemplos de consultas LINQ y el programa XQuery)](https://code.msdn.microsoft.com/Visual-Studio-2008-C-d295cdba)
- [Expresiones lambda recursivas](https://docs.microsoft.com/archive/blogs/madst/recursive-lambda-expressions)

---
title: "Expresiones lambda (Guía de programación de C#) | Microsoft Docs"
ms.date: 2017-03-03
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- lambda expressions [C#]
- outer variables [C#]
- statement lambda [C#]
- expression lambda [C#]
- expressions [C#], lambda
ms.assetid: 57e3ba27-9a82-4067-aca7-5ca446b7bf93
caps.latest.revision: 64
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6083af22fe8743a3d952138e04be90536cbd75d3
ms.lasthandoff: 03/13/2017

---
# <a name="lambda-expressions-c-programming-guide"></a>Expresiones lambda (Guía de programación de C#)
Una expresión lambda es una [función anónima](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) que se puede usar para crear tipos de [delegados](../../../csharp/programming-guide/delegates/using-delegates.md) o tipos de [árboles de expresión](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b). Al utilizar expresiones lambda, puede escribir funciones locales que se pueden pasar como argumentos o devolverse como valor de llamadas de función. Las expresiones lambda son especialmente útiles para escribir expresiones de consulta LINQ.  
  
 Para crear una expresión lambda, se especifican los parámetros de entrada (si existen) a la izquierda del operador lambda [=>](../../../csharp/language-reference/operators/lambda-operator.md) y se coloca el bloque de expresiones o de instrucciones en el otro lado. Por ejemplo, la expresión lambda `x => x * x` especifica un parámetro denominado `x` y devuelve el valor de `x` cuadrado. Puede asignar esta expresión a un tipo delegado, como se muestra en el ejemplo siguiente:  
  
```csharp  
delegate int del(int i);  
static void Main(string[] args)  
{  
    del myDelegate = x => x * x;  
    int j = myDelegate(5); //j = 25  
}  
```  
  
 Para crear un tipo de árbol de expresión:  
  
```csharp  
using System.Linq.Expressions;  
  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Expression<del> myET = x => x * x;  
        }  
    }  
}  
```  
  
 El operador `=>` tiene la misma prioridad que la asignación (`=`) y es [asociativa a la derecha](../../../csharp/programming-guide/statements-expressions-operators/operators.md) (vea la sección “Asociatividad” del artículo Operadores).  
  
 Las lambdas se usan en consultas [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)] basadas en métodos como argumentos de los métodos de operador de consulta estándar, tales como <xref:System.Linq.Enumerable.Where%2A>.  
  
 Si usa la sintaxis basada en métodos para llamar al método <xref:System.Linq.Enumerable.Where%2A> en la clase <xref:System.Linq.Enumerable> (como hace en [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)] to Objects y en [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]), el parámetro es un tipo de delegado <xref:System.Func%602?displayProperty=fullName>. Una expresión lambda constituye la manera más práctica de crear ese delegado. Cuando se llama al mismo método, por ejemplo, en la clase <xref:System.Linq.Queryable?displayProperty=fullName> (como se hace en [!INCLUDE[vbtecdlinq](../../../csharp/includes/vbtecdlinq_md.md)]), el tipo de parámetro es <xref:System.Linq.Expressions.Expression?displayProperty=fullName><Func\>, donde Func es cualquiera de los delegados de Func con hasta dieciséis parámetros de entrada. De nuevo, una expresión lambda constituye una manera muy concisa de construir ese árbol de expresión. Las lambdas permiten que las llamadas a `Where` tengan un aspecto similar, aunque, de hecho, el tipo de objeto creado a partir de la lambda sea diferente.  
  
 En el ejemplo anterior, observe que la signatura de delegado tiene un parámetro de entrada con tipo implícito `int`y devuelve un `int`. La expresión lambda se puede convertir en un delegado de ese tipo porque también tiene un parámetro de entrada (`x`) y un valor devuelto que el compilador puede convertir implícitamente al tipo `int`. (La inferencia de tipos se analiza con más detalle en las secciones siguientes). Cuando el delegado se invoca mediante un parámetro de entrada de 5, devuelve un resultado de 25.  
  
 Las lambdas no se permiten en el lado izquierdo del operador [is](../../../csharp/language-reference/keywords/is.md) o [as](../../../csharp/language-reference/keywords/as.md).  
  
 Todas las restricciones que se aplican a los métodos anónimos también se aplican a las expresiones lambda. Para obtener más información, vea [Métodos anónimos](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).  
  
## <a name="expression-lambdas"></a>Lambdas de expresión  
 Una expresión lambda con una expresión en el lado derecho del operador => se denomina *lambda de expresión*. Las lambdas de expresión se usan ampliamente en la construcción de [árboles de expresión](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b). Una expresión lambda devuelve el resultado de evaluar la condición y tiene la siguiente forma:  
  
```csharp
(input-parameters) => expression
```

 Los paréntesis solo son opcionales si la lambda tiene un parámetro de entrada; de lo contrario, son obligatorios. Dos o más parámetros de entrada se separan por comas y se encierran entre paréntesis:  
  
```csharp
(x, y) => x == y
```

 A veces, es difícil o imposible que el compilador deduzca los tipos de entrada. Cuando ocurre esto, los tipos se pueden especificar explícitamente como se muestra en el ejemplo siguiente:  
  
```csharp
(int x, string s) => s.Length > x
```

 Para especificar cero parámetros de entrada, utilice paréntesis vacíos:  
  
```csharp
() => SomeMethod()
```

 Observe en el ejemplo anterior que el cuerpo de una lambda de expresión puede estar compuesto de una llamada a método. Sin embargo, si crea árboles de expresiones que se evalúan fuera de .NET Framework, por ejemplo en SQL Server, no debe utilizar llamadas a métodos en expresiones lambda. Los métodos no tendrán ningún significado fuera del contexto de .NET Common Language Runtime.  
  
## <a name="statement-lambdas"></a>Lambdas de instrucción  
 Una lambda de instrucción es similar a un lambda de expresión, salvo que las instrucciones se encierran entre llaves:  
  
(parámetros de entrada) => { instrucción; }

 El cuerpo de una lambda de instrucción puede estar compuesto de cualquier número de instrucciones; sin embargo, en la práctica, generalmente no hay más de dos o tres.  
  
 [StatementLamba#1](../../../../samples\snippets\csharp\programming-guide\lambda-expressions/statements.cs#1)]

 [StatementLamba#2](../../../../samples\snippets\csharp\programming-guide\lambda-expressions/statements.cs#2)]

 Las lambdas de instrucción, como los métodos anónimos, no se pueden utilizar para crear árboles de expresión.  
  
## <a name="async-lambdas"></a>Lambdas asincrónicas  
 Puede crear fácilmente expresiones e instrucciones lambda que incorporen el procesamiento asincrónico mediante las palabras clave [async](../../../csharp/language-reference/keywords/async.md) y [await](../../../csharp/language-reference/keywords/await.md). Por ejemplo, en el siguiente ejemplo de formularios Windows Forms se incluye un controlador de eventos que llama y espera un método asincrónico, `ExampleMethodAsync`.  
  
```csharp
public partial class Form1 : Form  
{  
    public Form1()  
    {  
        InitializeComponent();  
    }  
  
    private async void button1_Click(object sender, EventArgs e)  
    {  
        // ExampleMethodAsync returns a Task.  
        await ExampleMethodAsync();  
        textBox1.Text += "\r\nControl returned to Click event handler.\n";  
    }  
  
    async Task ExampleMethodAsync()  
    {  
        // The following line simulates a task-returning asynchronous process.  
        await Task.Delay(1000);  
    }  
}  
```

 Puede agregar el mismo controlador de eventos utilizando una lambda asincrónica. Para agregar este controlador, agregue un modificador `async` antes de la lista de parámetros lambda, como se muestra en el ejemplo siguiente.  
  
```csharp  
public partial class Form1 : Form  
{  
    public Form1()  
    {  
        InitializeComponent();  
        button1.Click += async (sender, e) =>  
        {  
            // ExampleMethodAsync returns a Task.  
            await ExampleMethodAsync();  
            textBox1.Text += "\nControl returned to Click event handler.\n";  
        };  
    }  
  
    async Task ExampleMethodAsync()  
    {  
        // The following line simulates a task-returning asynchronous process.  
        await Task.Delay(1000);  
    }  
}  
```  

 Para obtener más información sobre cómo crear y usar métodos asincrónicos, vea [Programación asincrónica con async y await](../../../csharp/programming-guide/concepts/async/index.md).  
  
## <a name="lambdas-with-the-standard-query-operators"></a>Lambdas con los operadores de consulta estándar  
 Muchos operadores de consulta estándar tienen un parámetro de entrada cuyo tipo es uno de la familia <xref:System.Func%602> de delegados genéricos. Estos delegados usan parámetros de tipo para definir el número y los tipos de los parámetros de entrada y el tipo de valor devuelto del delegado. Los delegados `Func` son muy útiles para encapsular expresiones definidas por el usuario que se aplican a cada elemento en un conjunto de datos de origen. Por ejemplo, considere el siguiente tipo delegado:  
  
```csharp  
public delegate TResult Func<TArg0, TResult>(TArg0 arg0)  
```  
  
 Se pueden crear instancias del delegado como `Func<int,bool> myFunc` , donde `int` es un parámetro de entrada y `bool` es el valor devuelto. El valor devuelto siempre se especifica en el último parámetro de tipo. `Func<int, string, bool>` define un delegado con dos parámetros de entrada, `int` y `string`, y un tipo de valor devuelto de `bool`. El siguiente delegado `Func`, cuando se invoca, devolverá true o false para indicar si el parámetro de entrada es igual a 5:  
  
```csharp  
Func<int, bool> myFunc = x => x == 5;  
bool result = myFunc(4); // returns false of course  
```  
  
 También puede proporcionar una expresión lambda cuando el tipo de argumento es `Expression<Func>`, por ejemplo, en los operadores de consulta estándar que se definen en System.Linq.Queryable. Al especificar un argumento `Expression<Func>` , la lambda se compilará en un árbol de expresión.  
  
 Aquí se muestra un operador de consulta estándar, el método <xref:System.Linq.Enumerable.Count%2A>:  
  
```csharp  
int[] numbers = { 5, 4, 1, 3, 9, 8, 6, 7, 2, 0 };  
int oddNumbers = numbers.Count(n => n % 2 == 1);  
```  
  
 El compilador puede deducir el tipo del parámetro de entrada o también se puede especificar explícitamente. Esta expresión lambda particular cuenta aquellos enteros (`n`) que divididos por dos dan como resto 1.  
  
 La siguiente línea de código produce una secuencia que contiene todos los elementos de la matriz `numbers` que aparecen a la izquierda del 9, ya que ese es el primer número de la secuencia que no cumple la condición:  
  
```csharp  
var firstNumbersLessThan6 = numbers.TakeWhile(n => n < 6);  
```  
  
 En este ejemplo se muestra cómo especificar varios parámetros de entrada encerrándolos entre paréntesis. El método devuelve todos los elementos de la matriz de números hasta encontrar un número cuyo valor sea menor que su posición. No confunda el operador lambda (`=>`) con el operador mayor o igual que (`>=`).  
  
```csharp  
var firstSmallNumbers = numbers.TakeWhile((n, index) => n >= index);  
```  
  
## <a name="type-inference-in-lambdas"></a>Inferencia de tipos en las lambdas  
 Al escribir lambdas, no tiene por qué especificar un tipo para los parámetros de entrada, ya que el compilador puede deducir el tipo según el cuerpo de lambda, el tipo de delegado del parámetro y otros factores que se describen en la especificación del lenguaje C#. Para la mayoría de los operadores de consulta estándar, la primera entrada es el tipo de los elementos en la secuencia de origen. Por consiguiente, si está realizando una consulta sobre un `IEnumerable<Customer>`, se deducirá que la variable de entrada será un objeto `Customer` , lo cual significa que se podrá tener acceso a sus métodos y propiedades:  
  
```csharp  
customers.Where(c => c.City == "London");  
```  
  
 Las reglas generales para las lambdas son las siguientes:  
  
-   La lambda debe contener el mismo número de parámetros que el tipo delegado.  
  
-   Cada parámetro de entrada de la lambda debe poder convertirse implícitamente a su parámetro de delegado correspondiente.  
  
-   El valor devuelto de la lambda (si existe) debe poder convertirse implícitamente al tipo de valor devuelto del delegado.  
  
 Observe que las expresiones lambda, en sí mismas, no tienen tipo, ya que el sistema de tipos comunes no tiene ningún concepto intrínseco de "expresión lambda". Sin embargo, a veces resulta práctico hablar coloquialmente del "tipo" de una expresión lambda. En estos casos, el tipo hace referencia al tipo del delegado o el tipo de <xref:System.Linq.Expressions.Expression> en el que se convierte la expresión lambda.  
  
## <a name="variable-scope-in-lambda-expressions"></a>Ámbito de las variables en las expresiones lambda  
 Las lambdas pueden hacer referencia a las *variables externas* (vea [Métodos anónimos](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)) que están en el ámbito del método que define la función lambda o en el ámbito del tipo que contiene la expresión lambda. Las variables que se capturan de esta manera se almacenan para su uso en la expresión lambda, cuando de otro modo quedarían fuera de ámbito y serían eliminadas por la recolección de elementos no utilizados. Para poder utilizar una variable externa en una expresión lambda, debe estar previamente asignada. En el ejemplo siguiente se muestran estas reglas:  
  
```csharp  
delegate bool D();  
delegate bool D2(int i);  
  
class Test  
{  
    D del;  
    D2 del2;  
    public void TestMethod(int input)  
    {  
        int j = 0;  
        // Initialize the delegates with lambda expressions.  
        // Note access to 2 outer variables.  
        // del will be invoked within this method.  
        del = () => { j = 10;  return j > input; };  
  
        // del2 will be invoked after TestMethod goes out of scope.  
        del2 = (x) => {return x == j; };  
  
        // Demonstrate value of j:  
        // Output: j = 0   
        // The delegate has not been invoked yet.  
        Console.WriteLine("j = {0}", j);        // Invoke the delegate.  
        bool boolResult = del();  
  
        // Output: j = 10 b = True  
        Console.WriteLine("j = {0}. b = {1}", j, boolResult);  
    }  
  
    static void Main()  
    {  
        Test test = new Test();  
        test.TestMethod(5);  
  
        // Prove that del2 still has a copy of  
        // local variable j from TestMethod.  
        bool result = test.del2(10);  
  
        // Output: True  
        Console.WriteLine(result);  
  
        Console.ReadKey();  
    }  
}  
  
```  
  
 Las reglas siguientes se aplican al ámbito de las variables en las expresiones lambda:  
  
-   Una variable capturada no se recolectará como elemento no utilizado hasta que el delegado que hace referencia a ella sea elegible para la recolección de elementos no utilizados.  
  
-   Las variables introducidas en una expresión lambda no son visibles en el método externo.  
  
-   Una expresión lambda no puede capturar directamente un parámetro `ref` o `out` desde un método que la englobe.  
  
-   Una instrucción return en una expresión lambda no hace que el método que la engloba devuelva un valor.  
  
-   Una expresión lambda no puede contener una instrucción `goto` , `break` o `continue` que esté dentro de la función lambda si el destino de la instrucción de salto está fuera del bloque. También es un error utilizar una instrucción de salto fuera del bloque de la función lambda si el destino está dentro del bloque.  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="featured-book-chapter"></a>Capítulo destacado del libro  
 [Delegates, Events, and Lambda Expressions](http://go.microsoft.com/fwlink/?LinkId=195395) (Delegados, eventos y expresiones lambda) en [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](http://go.microsoft.com/fwlink/?LinkId=195369)  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)   
 [Métodos anónimos](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)   
 [is](../../../csharp/language-reference/keywords/is.md)   
 [Árboles de expresión](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b)   
 [Ejemplos de C# de Visual Studio 2008 (vea los archivos de ejemplos de consultas LINQ y el programa XQuery)](http://code.msdn.microsoft.com/Visual-Studio-2008-C-d295cdba)   
 [Expresiones lambda recursivas](http://go.microsoft.com/fwlink/?LinkId=112395)

---
title: "M&#233;todos (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lenguaje C#, métodos"
  - "métodos [C#]"
ms.assetid: cc738f07-e8cd-4683-9585-9f40c0667c37
caps.latest.revision: 41
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 41
---
# M&#233;todos (Gu&#237;a de programaci&#243;n de C#)
Un método es un bloque de código que contiene una serie de instrucciones. Un programa hace que se ejecuten las instrucciones al llamar al método y especificando los argumentos de método necesarios. En C\#, todas las instrucciones ejecutadas se realizan en el contexto de un método. El método Main es el punto de entrada para cada aplicación de C\# y se llama mediante Common Language Runtime \(CLR\) cuando se inicia el programa.  
  
> [!NOTE]
>  En este tema se analizan los métodos denominados. Para obtener información sobre funciones anónimas, vea [Funciones anónimas](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).  
  
## Firmas de método  
 Los métodos se declaran en una [clase](../../../csharp/language-reference/keywords/class.md) o [struct](../../../csharp/language-reference/keywords/struct.md) especificando el nivel de acceso, como `public` o `private`, modificadores opcionales como  `abstract` o `sealed`, el valor de retorno, el nombre del método y cualquier parámetro de método. Todas estas partes forman la firma del método.  
  
> [!NOTE]
>  Un tipo de valor devuelto de un método no forma parte de la firma del método con el objetivo de sobrecargar el método. Sin embargo, forma parte de la firma del método al determinar la compatibilidad entre un delegado y el método que señala.  
  
 Los parámetros de método se encierran entre paréntesis y se separan por comas. Los paréntesis vacíos indican que el método no requiere parámetros. Esta clase contiene tres métodos:  
  
 [!code-cs[csProgGuideObjects#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/methods_1.cs)]  
  
## Acceso a métodos  
 Llamar a un método en un objeto es como acceder a un campo. Después del nombre del objeto, agregue un punto, el nombre del método y paréntesis. Los argumentos se enumeran entre paréntesis y están separados por comas. Los métodos de la clase `Motorcycle` se pueden llamar como en el ejemplo siguiente:  
  
 [!code-cs[csProgGuideObjects#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/methods_2.cs)]  
  
## Parámetros de métodos frente a Argumentos  
 La definición del método especifica los nombres y tipos de todos los parámetros necesarios. Si el código de llamada llama al métodos, proporciona valores concretos denominados argumentos para cada parámetro. Los argumentos deben ser compatibles con el tipo de parámetro, pero el nombre del argumento \(si existe\) utilizado en el código de llamada no tiene que ser el mismo que el parámetro con nombre definido en el método. Por ejemplo:  
  
 [!code-cs[csProgGuideObjects#74](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/methods_3.cs)]  
  
## Pasar por referencia frente a Pasar por valor  
 De forma predeterminada, cuando un tipo de valor se pasa a un método, se pasa una copia en lugar del propio objeto. Por lo tanto, los cambios realizados en el argumento no tienen ningún efecto en la copia original del método de llamada. Puede pasar un tipo de valor por referencia mediante la palabra clave ref. Para obtener más información, consulta [Pasar parámetros de tipo de valor](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md). Para obtener una lista de tipos de valor integrados, vea [Tabla de tipos de valor](../../../csharp/language-reference/keywords/value-types-table.md).  
  
 Cuando se pasa un objeto de un tipo de referencia a un método, se pasa una referencia al objeto. Es decir, el método no recibe el objeto concreto, recibe un argumento que indica la ubicación del objeto. Si cambia un miembro del objeto mediante esta referencia, el cambio se refleja en el argumento del método de llamada, incluso si pasa el objeto por valor.  
  
 Crea un tipo de referencia mediante la palabra clave `class`, como se muestra en el siguiente ejemplo.  
  
 [!code-cs[csProgGuideObjects#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/methods_4.cs)]  
  
 Ahora, si se pasa un objeto basado en este tipo a un método, también se pasa una referencia al objeto. En el ejemplo siguiente se pasa un objeto de tipo `SampleRefType` al método `ModifyObject`.  
  
 [!code-cs[csProgGuideObjects#75](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/methods_5.cs)]  
  
 Fundamentalmente, el ejemplo hace lo mismo que el ejemplo anterior en el que se pasa un argumento por valor a un método. Pero, debido a que se utiliza un tipo de referencia, el resultado es diferente. La modificación que se lleva a cabo en `ModifyObject` al campo `value` del parámetro, `obj`, también cambia el campo `value` del argumento, `rt`, en el método `TestRefType`. El método `TestRefType` muestra 33 como salida.  
  
 Para más información sobre cómo pasar tipos de referencia por referencia y por valor, vea [Pasar parámetros Reference\-Type](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md) y [Tipos de referencia](../../../csharp/language-reference/keywords/reference-types.md).  
  
## Valores devueltos  
 Los métodos pueden devolver un valor al autor de llamada. Si el tipo de valor devuelto, el tipo enumerado antes del nombre de método, no es `void`, el método puede devolver el valor mediante la utilización de la palabra clave `return`. Una instrucción con la palabra clave `return` seguida de un valor que coincide con el tipo de valor devuelto devolverá este valor al autor de llamada del método. La palabra clave `return` también detiene la ejecución del método. Si el tipo de valor devuelto es `void`, una instrucción `return` sin un valor también es útil para detener la ejecución del método. Sin la palabra clave `return`, el método dejará de ejecutarse cuando alcance el final del bloque de código. Los métodos con un tipo de valor devuelto no nulo son necesarios para usar la palabra clave `return` para devolver un valor. Por ejemplo, estos dos métodos utilizan la palabra clave `return` para devolver enteros:  
  
 [!code-cs[csProgGuideObjects#44](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/methods_6.cs)]  
  
 Para utilizar un valor devuelto de un método, el método de llamada puede usar la llamada de método en cualquier lugar; un valor del mismo tipo sería suficiente. También puede asignar el valor devuelto a una variable. Por ejemplo, los dos siguientes ejemplos de código logran el mismo objetivo:  
  
 [!code-cs[csProgGuideObjects#45](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/methods_7.cs)]  
  
 [!code-cs[csProgGuideObjects#46](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/methods_8.cs)]  
  
 Usar una variable local, en este caso, `result`, para almacenar un valor es opcional. La legibilidad del código puede ser útil, o puede ser necesaria si debe almacenar el valor original del argumento para todo el ámbito del método.  
  
 La devolución de una matriz multidimensional de un método, M, que modifique el contenido de la matriz no es necesaria si la función que realiza la llamada pasa la matriz a M. Puede devolver la matriz resultante de M para lograr un buen estilo o un flujo funcional de valores, pero no es necesario.  El motivo por el que no es necesario devolver la matriz modificada es que C\# pasa todos los tipos de referencia por valor, y el valor de una referencia a la matriz es el puntero a la matriz. En el método M, los cambios en el contenido de la matriz los puede observar cualquier código que tenga una referencia a la matriz, como se muestra en el ejemplo siguiente.  
  
```c#  
static void Main(string[] args) { int[,] matrix = new int[2, 2]; FillMatrix(matrix); // matrix is now full of -1 } public static void FillMatrix(int[,] matrix) { for (int i = 0; i < matrix.GetLength(0); i++) { for (int j = 0; j < matrix.GetLength(1); j++) { matrix[i, j] = -1; } } }  
  
```  
  
 Para obtener más información, consulta [return](../../../csharp/language-reference/keywords/return.md).  
  
## Métodos asincrónicos  
 Mediante la característica asincrónica, puede invocar métodos asincrónicos sin usar definiciones de llamada explícitas ni dividir manualmente el código en varios métodos o expresiones lambda. La característica asincrónica se presentó por primera vez en [!INCLUDE[vs_dev11_long](../../../csharp/includes/vs-dev11-long-md.md)].  
  
 Si marca un método con el modificador [async](../../../csharp/language-reference/keywords/async.md), puede usar el operador [await](../../../csharp/language-reference/keywords/await.md) en el método. Cuando el control alcanza una expresión await en el método asincrónico, el control se devuelve al autor de llamada y se progreso del método se suspende hasta que se completa la tarea esperada. Cuando se completa la tarea, la ejecución puede reanudarse en el método.  
  
> [!NOTE]
>  Un método asincrónico vuelve al autor de llamada cuando encuentra el primer objeto esperado que aún no se ha completado o cuando llega al final del método asincrónico, lo que ocurra primero.  
  
 Un método asincrónico puede tener un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>, o nulo. El tipo de valor devuelto nulo se utiliza principalmente para definir controladores de eventos, donde se requiere un tipo de valor devuelto nulo. No se puede esperar un método asincrónico que devuelve nulo, y el autor de llamada de un método con tipo de devolución nulo no puede capturar ninguna excepción producida por este.  
  
 En el ejemplo siguiente, `DelayAsync` es un método asincrónico con un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601>.`DelayAsync` tiene una instrucción `return` que devuelve un entero. Por lo tanto, la declaración del método de `DelayAsync` debe tener un tipo de valor devuelto de `Task<int>`. Dado que el tipo de valor devuelto es `Task<int>`, la evaluación de la expresión `await` en `DoSomethingAsync` genera un entero, como se demuestra en la siguiente instrucción: `int result = await delayTask`.  
  
 El método `startButton_Click` es un ejemplo de un método asincrónico con un tipo de valor devuelto nulo. Dado que `DoSomethingAsync` es un método asincrónico, la tarea de la llamada a `DoSomethingAsync` debe esperar, como se muestra en la siguiente instrucción: `await DoSomethingAsync();`. El método `startButton_Click` debe definirse con el modificador `async` porque el método tiene una expresión `await`.  
  
 [!code-cs[csAsyncMethod#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/asyncmethodcs/mainwindow.xaml.cs#2)]  
  
 Un método aisncrónico no puede declarar ningún parámetro [ref](../../../csharp/language-reference/keywords/ref.md) u [out](../../../csharp/language-reference/keywords/out.md), pero puede llamar a los métodos que tienen estos parámetros.  
  
 Para más información sobre estos métodos asincrónicos, vea [Programación asincrónica con Async y Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md), [Flujo de control en programas Async](../Topic/Control%20Flow%20in%20Async%20Programs%20\(C%23%20and%20Visual%20Basic\).md) y [Tipos de valor devueltos de Async](../Topic/Async%20Return%20Types%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Definiciones de cuerpos de expresión  
 Es habitual tener definiciones de método que simplemente hacen las devoluciones de forma inmediata con el resultado de una expresión, o que tienen una sola instrucción como cuerpo del método.  Hay un acceso directo de sintaxis para definir este método mediante `=>`:  
  
```c#  
public Point Move(int dx, int dy) => new Point(x + dx, y + dy); public void Print() => Console.WriteLine(First + " " + Last); // Works with operators, properties, and indexers too. public static Complex operator +(Complex a, Complex b) => a.Add(b); public string Name => First + " " + Last; public Customer this[long id] => store.LookupCustomer(id);  
```  
  
 Si el método devuelve `void` o si es un método asincrónico, el cuerpo del método debe ser una expresión de instrucción \(igual que con las expresiones lambda\).  Para las propiedades y los indizadores, solo deben leerse, y no se utiliza la palabra clave de descriptor de acceso `get`.  
  
## Iteradores  
 Un iterador realiza una iteración personalizada en una colección, como una lista o matriz. Un iterador utiliza la instrucción [yield return](../../../csharp/language-reference/keywords/yield.md) para devolver cada elemento de uno en uno. Cuando se alcanza la instrucción [yield return](../../../csharp/language-reference/keywords/yield.md), se recuerda la ubicación actual en el código. La ejecución se reinicia desde esa ubicación la próxima vez que se llama el iterador.  
  
 Llame a un iterador a partir del código de cliente mediante una instrucción [foreach](../../../csharp/language-reference/keywords/foreach-in.md).  
  
 El tipo de valor devuelto de un iterador puede ser <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.  
  
 Para obtener más información, consulta [Iteradores](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)   
 [Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md)   
 [Clases y miembros de clase abstractos y sellados](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)   
 [params](../../../csharp/language-reference/keywords/params.md)   
 [return](../../../csharp/language-reference/keywords/return.md)   
 [out](../../../csharp/language-reference/keywords/out.md)   
 [ref](../../../csharp/language-reference/keywords/ref.md)   
 [Pasar parámetros](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)
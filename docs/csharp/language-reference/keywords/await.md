---
title: await - Referencia de C#
ms.custom: seodec18
ms.date: 05/22/2017
f1_keywords:
- await_CSharpKeyword
helpviewer_keywords:
- await keyword [C#]
- await [C#]
ms.assetid: 50725c24-ac76-4ca7-bca1-dd57642ffedb
ms.openlocfilehash: 1afd763d41ac3ffd42409ff8d1b8823979ab0c08
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713055"
---
# <a name="await-c-reference"></a>await (Referencia de C#)
El operador `await` se aplica a una tarea de un método asincrónico para insertar un punto de suspensión en la ejecución del método hasta que la tarea en espera se complete. La tarea representa el trabajo en curso.  
  
`await` solo puede usarse en un método asincrónico que se ha modificado mediante la palabra clave [async](../../../csharp/language-reference/keywords/async.md). Este tipo de método, que se define mediante el modificador `async` y que generalmente contiene una o más expresiones `await`, se denomina *método asincrónico*.  
  
> [!NOTE]
> Las palabras clave `async` y `await` se han incluido en C# 5. Para obtener una introducción a la programación asincrónica, vea [Programación asincrónica con async y await](../../../csharp/programming-guide/concepts/async/index.md).  
  
La tarea a la que se aplica el operador `await` se devuelve normalmente mediante una llamada a un método que implementa el [patrón asincrónico basado en tareas](../../../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md). Incluyen métodos que devuelven objetos <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.ValueTask> y <xref:System.Threading.Tasks.ValueTask%601>.  

En el siguiente ejemplo, el método <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A?displayProperty=nameWithType> devuelve un `Task<byte[]>`. La tarea garantiza que la matriz de bytes real se generará cuando finalice la tarea. El operador `await` suspende la ejecución hasta que el trabajo del método <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> se completa. Mientras tanto, el control vuelve al llamador de `GetPageSizeAsync`. Cuando la tarea finaliza la ejecución, la expresión `await` se evalúa como una matriz de bytes.  

[!code-csharp[await-example](../../../../samples/snippets/csharp/language-reference/keywords/await/await1.cs)]  

> [!IMPORTANT]
> Para obtener el ejemplo completo, consulte [Tutorial: Acceso a web usando Async y Await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md). Puede descargar el ejemplo desde [Ejemplos de código para desarrolladores](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) en el sitio web de Microsoft. El ejemplo está en el proyecto AsyncWalkthrough_HttpClient.  
  
Tal y como se muestra en el ejemplo anterior, si `await` se aplica al resultado de una llamada al método que devuelve `Task<TResult>`, el tipo de la expresión `await` es `TResult`. Si `await` se aplica al resultado de una llamada al método que devuelve `Task`, el tipo de la expresión `await` es `void`. En el siguiente ejemplo se ilustra la diferencia.  
  
```csharp  
// await keyword used with a method that returns a Task<TResult>.  
TResult result = await AsyncMethodThatReturnsTaskTResult();  
  
// await keyword used with a method that returns a Task.  
await AsyncMethodThatReturnsTask();  

// await keyword used with a method that returns a ValueTask<TResult>.
TResult result = await AsyncMethodThatReturnsValueTaskTResult();
```  
  
Una expresión `await` no bloquea el subproceso en el que se ejecuta. En su lugar, hace que el compilador suscriba el resto del método asincrónico como una continuación de la tarea esperada. A continuación, el control vuelve al llamador del método asincrónico. Cuando la tarea se completa, invoca su continuación y la ejecución del método asincrónico se reanuda donde se quedó.  
  
Una expresión `await` solo puede aparecer en el cuerpo de su método envolvente, en una expresión lambda o en un método anónimo que debe marcarse con un modificador `async`. El término *await* solo sirve como palabra clave en ese contexto. En cualquier otra parte, se interpretará como identificador. Dentro del método, expresión lambda o método anónimo, una expresión `await` no se puede producir en el cuerpo de una función sincrónica, en una expresión de consulta, en el bloque de una [instrucción lock](../../../csharp/language-reference/keywords/lock-statement.md), ni en un contexto [unsafe](../../../csharp/language-reference/keywords/unsafe.md).  
  
## <a name="exceptions"></a>Excepciones  
La mayoría de los métodos asincrónicos devuelven un objeto <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>. Las propiedades de la tarea devuelta llevan información acerca de su estado e historial, por ejemplo, si la tarea se ha completado, si el método asincrónico produjo una excepción o si se ha cancelado y cuál es el resultado final. El operador `await` tiene acceso a esas propiedades llamando a métodos en el objeto devuelto mediante el método `GetAwaiter`.  
  
Si espera un método asincrónico que devuelve una tarea y causa una excepción, el operador `await` volverá a generar la excepción.  
  
Si espera un método asincrónico que devuelve una tarea y se cancela, el operador `await` volverá a generar <xref:System.OperationCanceledException>.  
  
Una única tarea en estado de error puede reflejar varias excepciones. Por ejemplo, la tarea podría ser el resultado de una llamada a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>. Cuando espera dicha tarea, la operación await vuelve a generar únicamente una de las excepciones. Sin embargo, no se puede predecir cuál de las excepciones se vuelve a generar.  
  
Para obtener ejemplos de control de errores en métodos asincrónicos, vea [try-catch](../../../csharp/language-reference/keywords/try-catch.md).  
  
## <a name="example"></a>Ejemplo  
En el ejemplo siguiente se devuelve el número total de caracteres en las páginas cuyas direcciones URL se pasan como argumentos de línea de comandos. En el ejemplo se llama al método `GetPageLengthsAsync`, que se marca con la palabra clave `async`. El método `GetPageLengthsAsync` a su vez usa la palabra clave `await` para esperar llamadas del método <xref:System.Net.Http.HttpClient.GetStringAsync%2A?displayProperty=nameWithType>.  

[!code-csharp[await-example](../../../../samples/snippets/csharp/language-reference/keywords/await/await2.cs)]  

El ejemplo anterior utiliza C# 7.1, que admite el método [`async` `Main`](../../programming-guide/main-and-command-args/index.md). Dado que las versiones anteriores de C# no admiten los puntos de entrada de aplicación que devuelven <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>, no se puede aplicar el modificador `async` al método `Main` y esperar la llamada al método `GetPageLengthsAsync`. En ese caso, podemos garantizar que el método `Main` espera a que se complete la operación asincrónica recuperando el valor de la propiedad <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType>. Para las tareas que no devuelven un valor, puede llamar al método <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>. Para información sobre cómo seleccionar la versión de idioma, consulte [Seleccionar la versión del lenguaje C#](../configure-language-version.md).

## <a name="see-also"></a>Vea también
- [Programación asincrónica con Async y Await](../../../csharp/programming-guide/concepts/async/index.md)
- [Tutorial: Acceso a web usando Async y Await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
- [async](../../../csharp/language-reference/keywords/async.md)

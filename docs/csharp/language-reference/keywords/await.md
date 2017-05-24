---
title: await (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- await_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- await keyword [C#]
- await [C#]
ms.assetid: 50725c24-ac76-4ca7-bca1-dd57642ffedb
caps.latest.revision: 36
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 400dfda51d978f35c3995f90840643aaff1b9c13
ms.openlocfilehash: 3656141c32a04e3a32a2992185f4c418c6915482
ms.contentlocale: es-es
ms.lasthandoff: 03/24/2017

---
# <a name="await-c-reference"></a>await (Referencia de C#)
El operador `await` se aplica a una tarea de un método asincrónico para suspender la ejecución del método hasta que la tarea en espera se complete. La tarea representa el trabajo en curso.  
  
 El método asincrónico en el que se usa `await` se debe modificar con la palabra clave [async](../../../csharp/language-reference/keywords/async.md). Este tipo de método, que se define mediante el modificador `async` y que generalmente contiene una o más expresiones `await`, se denomina *método asincrónico*.  
  
> [!NOTE]
>  Las palabras clave `async` y `await` se incluyeron en Visual Studio 2012. Para obtener una introducción a la programación asincrónica, vea [Programación asincrónica con async y await](../../../csharp/programming-guide/concepts/async/index.md).  
  
 La tarea a la que se aplica el operador `await` suele ser el valor devuelto de una llamada a un método que implementa el [patrón asincrónico basado en tareas](http://go.microsoft.com/fwlink/?LinkId=204847). Algunos ejemplos son valores de tipo <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>.  
  
 En el código siguiente, el método <xref:System.Net.Http.HttpClient> <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> devuelve un `Task\<byte[]>`, `getContentsTask`. La tarea garantiza que la matriz de bytes real se generará cuando finalice la tarea. El operador `await` se aplica a `getContentsTask` para suspender la ejecución en `SumPageSizesAsync` hasta que se complete `getContentsTask`. Mientras tanto, el control vuelve al llamador de `SumPageSizesAsync`. Cuando `getContentsTask` haya finalizado, la expresión `await` se evalúa como una matriz de bytes.  
  
```csharp  
private async Task SumPageSizesAsync()  
{  
    // To use the HttpClient type in desktop apps, you must include a using directive and add a   
    // reference for the System.Net.Http namespace.  
    HttpClient client = new HttpClient();  
    // . . .  
    Task<byte[]> getContentsTask = client.GetByteArrayAsync(url);  
    byte[] urlContents = await getContentsTask;  
  
    // Equivalently, now that you see how it works, you can write the same thing in a single line.  
    //byte[] urlContents = await client.GetByteArrayAsync(url);  
    // . . .  
}  
```  
  
> [!IMPORTANT]
>  Para obtener el ejemplo completo, vea [Walkthrough: Accessing the Web by Using Async and Await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) (Tutorial: Acceso a la web usando Async y Await). Puede descargar el ejemplo desde [Ejemplos de código para desarrolladores](http://go.microsoft.com/fwlink/?LinkID=255191&clcid=0x409) en el sitio web de Microsoft. El ejemplo está en el proyecto AsyncWalkthrough_HttpClient.  
  
 Tal y como se muestra en el ejemplo anterior, si `await` se aplica al resultado de una llamada al método que devuelve `Task<TResult>`, el tipo de la expresión `await` será TResult. Si `await` se aplica al resultado de una llamada al método que devuelve `Task`, el tipo de la expresión `await` es nulo. En el siguiente ejemplo se ilustra la diferencia.  
  
```csharp  
// Keyword await used with a method that returns a Task<TResult>.  
TResult result = await AsyncMethodThatReturnsTaskTResult();  
  
// Keyword await used with a method that returns a Task.  
await AsyncMethodThatReturnsTask();  
```  
  
 Una expresión `await` no bloquea el subproceso en el que se ejecuta. En su lugar, hace que el compilador suscriba el resto del método asincrónico como una continuación de la tarea esperada. A continuación, el control vuelve al llamador del método asincrónico. Cuando la tarea se completa, invoca su continuación y la ejecución del método asincrónico se reanuda donde se quedó.  
  
 Una expresión `await` solo puede aparecer en el cuerpo de un método envolvente inmediato, una expresión lambda o un método anónimo marcados con el modificador `async`. El término *await* solo sirve como palabra clave en ese contexto. En cualquier otra parte, se interpretará como identificador. Dentro del método, expresión lambda o método anónimo, una expresión `await` no se puede producir en el cuerpo de una función sincrónica, en una expresión de consulta, en el bloque de una [instrucción lock](../../../csharp/language-reference/keywords/lock-statement.md), ni en un contexto [unsafe](../../../csharp/language-reference/keywords/unsafe.md).  
  
## <a name="exceptions"></a>Excepciones  
 La mayoría de los métodos asincrónicos devuelven una <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>. Las propiedades de la tarea devuelta llevan información acerca de su estado e historial, por ejemplo, si la tarea se ha completado, si el método asincrónico produjo una excepción o si se ha cancelado y cuál es el resultado final. El operador `await` tiene acceso a esas propiedades.  
  
 Si espera un método asincrónico que devuelve una tarea y causa una excepción, el operador `await` volverá a generar la excepción.  
  
 Si espera un método asincrónico que devuelve una tarea y se cancela, el operador `await` volverá a generar una excepción <xref:System.OperationCanceledException>.  
  
 Una única tarea en estado de error puede reflejar varias excepciones. Por ejemplo, la tarea podría ser el resultado de una llamada a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>. Cuando espera dicha tarea, la operación await vuelve a generar únicamente una de las excepciones. Sin embargo, no se puede predecir cuál de las excepciones se vuelve a generar.  
  
 Para obtener ejemplos de control de errores en métodos asincrónicos, vea [try-catch](../../../csharp/language-reference/keywords/try-catch.md).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente de Windows Forms muestra el uso de `await` en un método asincrónico, `WaitAsynchronouslyAsync`. Compare el comportamiento de dicho método con el de `WaitSynchronously`. Sin un operador `await` aplicado a una tarea, `WaitSynchronously` se ejecuta de forma sincrónica a pesar del uso del modificador `async` en su definición y una llamada a <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName> en el cuerpo.  
  
```csharp  
private async void button1_Click(object sender, EventArgs e)  
{  
    // Call the method that runs asynchronously.  
    string result = await WaitAsynchronouslyAsync();  
  
    // Call the method that runs synchronously.  
    //string result = await WaitSynchronously ();  
  
    // Display the result.  
    textBox1.Text += result;  
}  
  
// The following method runs asynchronously. The UI thread is not  
// blocked during the delay. You can move or resize the Form1 window   
// while Task.Delay is running.  
public async Task<string> WaitAsynchronouslyAsync()  
{  
    await Task.Delay(10000);  
    return "Finished";  
}  
  
// The following method runs synchronously, despite the use of async.  
// You cannot move or resize the Form1 window while Thread.Sleep  
// is running because the UI thread is blocked.  
public async Task<string> WaitSynchronously()  
{  
    // Add a using directive for System.Threading.  
    Thread.Sleep(10000);  
    return "Finished";  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Programación asincrónica con async y await](../../../csharp/programming-guide/concepts/async/index.md)   
 [Walkthrough: Accessing the Web by Using Async and Await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)  (Tutorial: Acceso a la web con Async y Await)  
 [async](../../../csharp/language-reference/keywords/async.md)


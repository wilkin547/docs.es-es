---
title: "await (Referencia de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "await_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "await [C#]"
  - "palabra clave await [C#]"
ms.assetid: 50725c24-ac76-4ca7-bca1-dd57642ffedb
caps.latest.revision: 36
caps.handback.revision: 36
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# await (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El operador `await` se aplica a una tarea de un método asincrónico para suspender la ejecución del método hasta que la tarea en espera se complete.  La tarea representa el trabajo en curso.  
  
 El método asincrónico en el que `await` se usa se debe modificar con la palabra clave [async](../../../csharp/language-reference/keywords/async.md).  Este tipo de método, que se define mediante el modificador `async` y generalmente contiene una o más expresiones `await`, se denomina *método asincrónico*.  
  
> [!NOTE]
>  Las palabras clave `async` y `await` se incluyeron en Visual Studio 2012.  Para ver una introducción a la programación asincrónica, vea [Programación asincrónica con Async y Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).  
  
 La tarea a la que se aplica el operador `await` suele ser el valor devuelto de una llamada a un método que implementa el [patrón asincrónico basado en tareas](http://go.microsoft.com/fwlink/?LinkId=204847).  Algunos ejemplos son los valores de tipo <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>.  
  
 En el siguiente código, el método <xref:System.Net.Http.HttpClient> <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> devuelve un `Task\<byte[]>`, `getContentsTask`.  La tarea garantiza que la matriz de bytes real se generará cuando finalice la tarea.  El operador `await` se aplica a `getContentsTask` para suspender la ejecución en `SumPageSizesAsync` hasta que se complete `getContentsTask`.  Mientras tanto, el control vuelve al llamador de `SumPageSizesAsync`.  Cuando `getContentsTask` haya finalizado, la expresión `await` se evalúa como una matriz de bytes.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
> [!IMPORTANT]
>  Para ver un ejemplo completo, vea el [Walkthrough: Acceso a web usando Async y Await](../Topic/Walkthrough:%20Accessing%20the%20Web%20by%20Using%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).  Puede descargar el ejemplo de los [códigos de ejemplo de desarrollador](http://go.microsoft.com/fwlink/?LinkID=255191&clcid=0x409) en el sitio Web de Microsoft.  El ejemplo está en el proyecto AsyncWalkthrough\_HttpClient.  
  
 Tal y como se muestra en el ejemplo anterior, si `await` se aplica al resultado de una llamada al método que devuelve `Task<TResult>`, el tipo de la expresión `await` será TResult.  Si `await` se aplica al resultado de una llamada al método que devuelve `Task`, el tipo de la expresión `await` es nulo.  En el siguiente ejemplo se ilustra la diferencia.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 Una expresión `await` no bloquea el subproceso en el que se ejecuta.  En su lugar, hace que el compilador suscriba el resto del método asincrónico como una continuación de la tarea esperada.  A continuación, el control vuelve al llamador del método asincrónico.  Cuando la tarea se completa, invoca su continuación y la ejecución del método asincrónico se reanuda donde se quedó.  
  
 Una expresión `await` solo puede aparecer en el cuerpo de un método envolvente inmediato, una expresión lambda o un método anónimo marcados con el modificador `async`.  El término *await* solo sirve como palabra clave en ese contexto.  En cualquier otra parte, se interpretará como identificador.  Dentro del método, expresión lambda o método anónimo, una expresión `await` no se puede producir en el cuerpo de una función sincrónica, en una expresión de consulta, en el bloque de una [instrucción lock](../../../csharp/language-reference/keywords/lock-statement.md) ni en un contexto [unsafe](../../../csharp/language-reference/keywords/unsafe.md).  
  
## Excepciones  
 La mayoría de los métodos asincrónicos devuelven un objeto <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>.  Las propiedades de la tarea devuelta llevan información acerca de su estado e historial, por ejemplo, si la tarea se ha completado, si el método asincrónico produjo una excepción o si se ha cancelado y cuál es el resultado final.  El operador `await` tiene acceso a esas propiedades.  
  
 Si espera un método asincrónico que devuelve una tarea y causa una excepción, el operador `await` volverá a generar la excepción.  
  
 Si espera un método asincrónico que devuelve una tarea y se cancela, el operador `await` volverá a generar <xref:System.OperationCanceledException>.  
  
 Una única tarea en estado de error puede reflejar varias excepciones.  Por ejemplo, la tarea podría ser el resultado de una llamada a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.  Cuando espera dicha tarea, la operación await vuelve a generar únicamente una de las excepciones.  Sin embargo, no se puede predecir cuál de las excepciones se vuelve a generar.  
  
 Para obtener ejemplos de control de errores en métodos asincrónicos, vea [try\-catch](../../../csharp/language-reference/keywords/try-catch.md).  
  
## Ejemplo  
 El ejemplo siguiente de Windows Forms muestra el uso de `await` en un método asincrónico, `WaitAsynchronouslyAsync`.  Compare el comportamiento de dicho método con el de `WaitSynchronously`.  Sin un operador `await` aplicado a una tarea, `WaitSynchronously` se ejecuta sincrónicamente a pesar del uso del modificador `async` en su definición y una llamada a <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName> en el cuerpo.  
  
```c#  
  
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
  
## Vea también  
 [Programación asincrónica con Async y Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)   
 [Walkthrough: Acceso a web usando Async y Await](../Topic/Walkthrough:%20Accessing%20the%20Web%20by%20Using%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)   
 [async](../../../csharp/language-reference/keywords/async.md)
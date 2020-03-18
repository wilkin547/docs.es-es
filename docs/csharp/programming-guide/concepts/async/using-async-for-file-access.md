---
title: Usar Async en acceso a archivos (C#)
ms.date: 07/20/2015
ms.assetid: bb018fea-5313-4c80-ab3f-7c24b2145bd9
ms.openlocfilehash: e6b0370049d9b9315de6a72d0e84c080aac12481
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "69595535"
---
# <a name="using-async-for-file-access-c"></a>Usar Async en acceso a archivos (C#)
Puede usar la característica async para acceder a archivos. Con la característica async, se puede llamar a métodos asincrónicos sin usar devoluciones de llamada ni dividir el código en varios métodos o expresiones lambda. Para convertir código sincrónico en asincrónico, basta con llamar a un método asincrónico y no a un método sincrónico y agregar algunas palabras clave al código.  
  
 Podrían considerarse los siguientes motivos para agregar asincronía a las llamadas de acceso a archivos:  
  
- La asincronía hace que las aplicaciones de interfaz de usuario tengan mayor capacidad de respuesta porque el subproceso de interfaz de usuario que inicia la operación puede realizar otro trabajo. Si el subproceso de interfaz de usuario debe ejecutar código que tarda mucho tiempo (por ejemplo, más de 50 milisegundos), puede inmovilizar la interfaz de usuario hasta que la E/S se complete y el subproceso de interfaz de usuario pueda volver a procesar la entrada de teclado y de mouse y otros eventos.  
  
- La asincronía mejora la escalabilidad de ASP.NET y otras aplicaciones basadas en servidor reduciendo la necesidad de subproceso. Si la aplicación usa un subproceso dedicado por respuesta y se procesa un millar de solicitudes simultáneamente, se necesitan mil subprocesos. Las operaciones asincrónicas no suelen necesitar un subproceso durante la espera. Usan el subproceso existente de finalización de E/S brevemente al final.  
  
- Puede que la latencia de una operación de acceso a archivos sea muy baja en las condiciones actuales, pero puede aumentar mucho en el futuro. Por ejemplo, se puede mover un archivo a un servidor que está a escala mundial.  
  
- La sobrecarga resultante de usar la característica Async es pequeña.  
  
- Las tareas asincrónicas se pueden ejecutar fácilmente en paralelo.  
  
## <a name="running-the-examples"></a>Ejecutar los ejemplos  
 Para ejecutar los ejemplos de este tema, puede crear una **aplicación WPF** o una **aplicación de Windows Forms** y luego agregar un **botón**. En el evento `Click` del botón, agregue una llamada al primer método de cada ejemplo.  
  
 En los ejemplos siguientes, se incluyen las instrucciones `using` siguientes.  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Diagnostics;  
using System.IO;  
using System.Text;  
using System.Threading.Tasks;  
```  
  
## <a name="use-of-the-filestream-class"></a>Uso de la clase FileStream  
 En los ejemplos de este tema se usa la clase <xref:System.IO.FileStream>, que tiene una opción que hace que la E/S asincrónica se produzca en el nivel del sistema operativo. Si usa esta opción, puede evitar bloquear un subproceso ThreadPool en muchos casos. Para habilitar esta opción, especifique el argumento `useAsync=true` o `options=FileOptions.Asynchronous` en la llamada al constructor.  
  
 No puede usar esta opción con <xref:System.IO.StreamReader> y <xref:System.IO.StreamWriter> si los abre directamente al especificar una ruta de acceso de archivo. En cambio, puede usar esta opción si les proporciona un <xref:System.IO.Stream> que ha abierto la clase <xref:System.IO.FileStream>. Tenga en cuenta que las llamadas asincrónicas son más rápidas en aplicaciones de interfaz de usuario aunque un subproceso ThreadPool se bloquee, porque el subproceso de interfaz de usuario no se bloquea durante la espera.  
  
## <a name="writing-text"></a>Escribir texto  
 En el ejemplo siguiente se escribe texto en un archivo. En cada instrucción await, el método finaliza inmediatamente. Cuando se complete la E/S de archivo, el método se reanuda en la instrucción que sigue a la instrucción await. Tenga en cuenta que el modificador async se encuentra en la definición de métodos que usan la instrucción await.  
  
```csharp  
public async Task ProcessWriteAsync()  
{  
    string filePath = @"temp2.txt";  
    string text = "Hello World\r\n";  
  
    await WriteTextAsync(filePath, text);  
}  
  
private async Task WriteTextAsync(string filePath, string text)  
{  
    byte[] encodedText = Encoding.Unicode.GetBytes(text);  
  
    using (FileStream sourceStream = new FileStream(filePath,  
        FileMode.Append, FileAccess.Write, FileShare.None,  
        bufferSize: 4096, useAsync: true))  
    {  
        await sourceStream.WriteAsync(encodedText, 0, encodedText.Length);  
    };  
}  
```  
  
 El ejemplo original incluye la instrucción `await sourceStream.WriteAsync(encodedText, 0, encodedText.Length);`, que es una contracción de las dos instrucciones siguientes:  
  
```csharp  
Task theTask = sourceStream.WriteAsync(encodedText, 0, encodedText.Length);  
await theTask;  
```  
  
 La primera instrucción devuelve una tarea e inicia el procesamiento de archivos. La segunda instrucción con await finaliza el método inmediatamente y devuelve otra tarea. Después, cuando se complete el procesamiento de archivos, la ejecución vuelve a la instrucción que sigue a la instrucción await. Para obtener más información, vea [Control Flow in Async Programs (C#)](./control-flow-in-async-programs.md) (Flujo de control en programas asincrónicos [C#]).  
  
## <a name="reading-text"></a>Leer texto  
 En el ejemplo siguiente se lee texto de un archivo. El texto se almacena en búfer y, en este caso, se coloca en un <xref:System.Text.StringBuilder>. A diferencia del ejemplo anterior, la evaluación de la instrucción await genera un valor. El método <xref:System.IO.Stream.ReadAsync%2A> devuelve un <xref:System.Threading.Tasks.Task>\<<xref:System.Int32>>, por lo que la evaluación de la espera genera un valor `Int32` (`numRead`) después de que se complete la operación. Para obtener más información, consulte [Tipos de valor devueltos asincrónicos (C#)](./async-return-types.md).  
  
```csharp  
public async Task ProcessReadAsync()  
{  
    string filePath = @"temp2.txt";  
  
    if (File.Exists(filePath) == false)  
    {  
        Debug.WriteLine("file not found: " + filePath);  
    }  
    else  
    {  
        try  
        {  
            string text = await ReadTextAsync(filePath);  
            Debug.WriteLine(text);  
        }  
        catch (Exception ex)  
        {  
            Debug.WriteLine(ex.Message);  
        }  
    }  
}  
  
private async Task<string> ReadTextAsync(string filePath)  
{  
    using (FileStream sourceStream = new FileStream(filePath,  
        FileMode.Open, FileAccess.Read, FileShare.Read,  
        bufferSize: 4096, useAsync: true))  
    {  
        StringBuilder sb = new StringBuilder();  
  
        byte[] buffer = new byte[0x1000];  
        int numRead;  
        while ((numRead = await sourceStream.ReadAsync(buffer, 0, buffer.Length)) != 0)  
        {  
            string text = Encoding.Unicode.GetString(buffer, 0, numRead);  
            sb.Append(text);  
        }  
  
        return sb.ToString();  
    }  
}  
```  
  
## <a name="parallel-asynchronous-io"></a>E/S asincrónica en paralelo  
 En el ejemplo siguiente se muestra el procesamiento paralelo escribiendo 10 archivos de texto. Para cada archivo, el método <xref:System.IO.Stream.WriteAsync%2A> devuelve una tarea que luego se agrega a una lista de tareas. La instrucción `await Task.WhenAll(tasks);` finaliza el método y se reanuda en el método cuando el procesamiento de archivos se completa para todas las tareas.  
  
 Tras completar las tareas, el ejemplo cierra todas las instancias de <xref:System.IO.FileStream> de un bloque `finally`. Si en lugar de ello, cada `FileStream` se ha creado en una instrucción `using`, la `FileStream` se podría desechar antes de completarse la tarea.  
  
 Tenga en cuenta que cualquier aumento del rendimiento se debe casi por completo al procesamiento en paralelo y no al procesamiento asincrónico. Las ventajas de la asincronía estriban en que no inmoviliza varios subprocesos ni el subproceso de interfaz de usuario.  
  
```csharp  
public async Task ProcessWriteMultAsync()  
{  
    string folder = @"tempfolder\";  
    List<Task> tasks = new List<Task>();  
    List<FileStream> sourceStreams = new List<FileStream>();  
  
    try  
    {  
        for (int index = 1; index <= 10; index++)  
        {  
            string text = "In file " + index.ToString() + "\r\n";  
  
            string fileName = "thefile" + index.ToString("00") + ".txt";  
            string filePath = folder + fileName;  
  
            byte[] encodedText = Encoding.Unicode.GetBytes(text);  
  
            FileStream sourceStream = new FileStream(filePath,  
                FileMode.Append, FileAccess.Write, FileShare.None,  
                bufferSize: 4096, useAsync: true);  
  
            Task theTask = sourceStream.WriteAsync(encodedText, 0, encodedText.Length);  
            sourceStreams.Add(sourceStream);  
  
            tasks.Add(theTask);  
        }  
  
        await Task.WhenAll(tasks);  
    }  
  
    finally  
    {  
        foreach (FileStream sourceStream in sourceStreams)  
        {  
            sourceStream.Close();  
        }  
    }  
}  
```  
  
 Al usar los métodos <xref:System.IO.Stream.WriteAsync%2A> y <xref:System.IO.Stream.ReadAsync%2A>, puede especificar un <xref:System.Threading.CancellationToken>, que puede usar para cancelar la operación en mitad de la secuencia. Para obtener más información, vea [Ajustar una aplicación asincrónica (C#)](./fine-tuning-your-async-application.md) y [Cancelación en subprocesos administrados](../../../../standard/threading/cancellation-in-managed-threads.md).  
  
## <a name="see-also"></a>Vea también

- [Asynchronous Programming with async and await (C#)](./index.md) (Programación asincrónica con async y await (C#))
- [Async Return Types (C#)](./async-return-types.md) (Tipos de valor devuelto de async [C#])
- [Control Flow in Async Programs (C#)](./control-flow-in-async-programs.md) (Flujo de control en programas asincrónicos [C#])

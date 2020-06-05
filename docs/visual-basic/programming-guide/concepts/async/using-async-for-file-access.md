---
title: Usar Async en acceso a archivos
ms.date: 07/20/2015
ms.assetid: c989305f-08e3-4687-95c3-948465cda202
ms.openlocfilehash: 2ee1efa69f4b13224be65fe802ebf5f834c941aa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400776"
---
# <a name="using-async-for-file-access-visual-basic"></a>Usar Async en acceso a archivos (Visual Basic)
Puede usar la característica Async para tener acceso a los archivos. Mediante la característica Async, se puede llamar a métodos asincrónicos sin definir continuaciones ni dividir el código en varios métodos o expresiones lambda. Para convertir código sincrónico en asincrónico, basta con llamar a un método asincrónico y no a un método sincrónico y agregar algunas palabras clave al código.  
  
 Podrían considerarse los siguientes motivos para agregar asincronía a las llamadas de acceso a archivos:  
  
- La asincronía hace que las aplicaciones de interfaz de usuario tengan mayor capacidad de respuesta porque el subproceso de interfaz de usuario que inicia la operación puede realizar otro trabajo. Si el subproceso de interfaz de usuario debe ejecutar código que tarda mucho tiempo (por ejemplo, más de 50 milisegundos), puede inmovilizar la interfaz de usuario hasta que la E/S se complete y el subproceso de interfaz de usuario pueda volver a procesar la entrada de teclado y de mouse y otros eventos.  
  
- La asincronía mejora la escalabilidad de ASP.NET y otras aplicaciones basadas en servidor reduciendo la necesidad de subproceso. Si la aplicación usa un subproceso dedicado por respuesta y se procesa un millar de solicitudes simultáneamente, se necesitan mil subprocesos. Las operaciones asincrónicas no suelen necesitar un subproceso durante la espera. Usan el subproceso existente de finalización de E/S brevemente al final.  
  
- Puede que la latencia de una operación de acceso a archivos sea muy baja en las condiciones actuales, pero puede aumentar mucho en el futuro. Por ejemplo, se puede mover un archivo a un servidor que está a escala mundial.  
  
- La sobrecarga resultante de usar la característica Async es pequeña.  
  
- Las tareas asincrónicas se pueden ejecutar fácilmente en paralelo.  
  
## <a name="running-the-examples"></a>Ejecutar los ejemplos  
 Para ejecutar los ejemplos de este tema, puede crear una **aplicación WPF** o una **aplicación de Windows Forms** y luego agregar un **botón**. En el evento `Click` del botón, agregue una llamada al primer método de cada ejemplo.  
  
 En los ejemplos siguientes, se incluyen las instrucciones `Imports` siguientes.  
  
```vb  
Imports System  
Imports System.Collections.Generic  
Imports System.Diagnostics  
Imports System.IO  
Imports System.Text  
Imports System.Threading.Tasks  
```  
  
## <a name="use-of-the-filestream-class"></a>Uso de la clase FileStream  
 En los ejemplos de este tema se usa la clase <xref:System.IO.FileStream>, que tiene una opción que hace que la E/S asincrónica se produzca en el nivel del sistema operativo. Si usa esta opción, puede evitar bloquear un subproceso ThreadPool en muchos casos. Para habilitar esta opción, especifique el argumento `useAsync=true` o `options=FileOptions.Asynchronous` en la llamada al constructor.  
  
 No puede usar esta opción con <xref:System.IO.StreamReader> y <xref:System.IO.StreamWriter> si los abre directamente al especificar una ruta de acceso de archivo. En cambio, puede usar esta opción si les proporciona un <xref:System.IO.Stream> que ha abierto la clase <xref:System.IO.FileStream>. Tenga en cuenta que las llamadas asincrónicas son más rápidas en aplicaciones de interfaz de usuario aunque un subproceso ThreadPool se bloquee, porque el subproceso de interfaz de usuario no se bloquea durante la espera.  
  
## <a name="writing-text"></a>Escribir texto  
 En el ejemplo siguiente se escribe texto en un archivo. En cada instrucción await, el método finaliza inmediatamente. Cuando se complete la E/S de archivo, el método se reanuda en la instrucción que sigue a la instrucción await. Tenga en cuenta que el modificador async se encuentra en la definición de métodos que usan la instrucción await.  
  
```vb  
Public Async Sub ProcessWrite()  
    Dim filePath = "temp2.txt"  
    Dim text = "Hello World" & ControlChars.CrLf  
  
    Await WriteTextAsync(filePath, text)  
End Sub  
  
Private Async Function WriteTextAsync(filePath As String, text As String) As Task  
    Dim encodedText As Byte() = Encoding.Unicode.GetBytes(text)  
  
    Using sourceStream As New FileStream(filePath,  
        FileMode.Append, FileAccess.Write, FileShare.None,  
        bufferSize:=4096, useAsync:=True)  
  
        Await sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
    End Using  
End Function  
```  
  
 El ejemplo original incluye la instrucción `Await sourceStream.WriteAsync(encodedText, 0, encodedText.Length)`, que es una contracción de las dos instrucciones siguientes:  
  
```vb  
Dim theTask As Task = sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
Await theTask  
```  
  
 La primera instrucción devuelve una tarea e inicia el procesamiento de archivos. La segunda instrucción con await finaliza el método inmediatamente y devuelve otra tarea. Después, cuando se complete el procesamiento de archivos, la ejecución vuelve a la instrucción que sigue a la instrucción await. Para obtener más información, vea [flujo de control en programas Async (Visual Basic)](control-flow-in-async-programs.md).  
  
## <a name="reading-text"></a>Leer texto  
 En el ejemplo siguiente se lee texto de un archivo. El texto se almacena en búfer y, en este caso, se coloca en un <xref:System.Text.StringBuilder>. A diferencia del ejemplo anterior, la evaluación de la instrucción await genera un valor. El método <xref:System.IO.Stream.ReadAsync%2A> devuelve un <xref:System.Threading.Tasks.Task>\<<xref:System.Int32>>, por lo que la evaluación de la espera genera un valor `Int32` (`numRead`) después de que se complete la operación. Para obtener más información, vea [tipos de valor devueltos Async (Visual Basic)](async-return-types.md).  
  
```vb  
Public Async Sub ProcessRead()  
    Dim filePath = "temp2.txt"  
  
    If File.Exists(filePath) = False Then  
        Debug.WriteLine("file not found: " & filePath)  
    Else  
        Try  
            Dim text As String = Await ReadTextAsync(filePath)  
            Debug.WriteLine(text)  
        Catch ex As Exception  
            Debug.WriteLine(ex.Message)  
        End Try  
    End If  
End Sub  
  
Private Async Function ReadTextAsync(filePath As String) As Task(Of String)  
  
    Using sourceStream As New FileStream(filePath,  
        FileMode.Open, FileAccess.Read, FileShare.Read,  
        bufferSize:=4096, useAsync:=True)  
  
        Dim sb As New StringBuilder  
  
        Dim buffer As Byte() = New Byte(&H1000) {}  
        Dim numRead As Integer  
        numRead = Await sourceStream.ReadAsync(buffer, 0, buffer.Length)  
        While numRead <> 0  
            Dim text As String = Encoding.Unicode.GetString(buffer, 0, numRead)  
            sb.Append(text)  
  
            numRead = Await sourceStream.ReadAsync(buffer, 0, buffer.Length)  
        End While  
  
        Return sb.ToString  
    End Using  
End Function  
```  
  
## <a name="parallel-asynchronous-io"></a>E/S asincrónica en paralelo  
 En el ejemplo siguiente se muestra el procesamiento paralelo escribiendo 10 archivos de texto. Para cada archivo, el método <xref:System.IO.Stream.WriteAsync%2A> devuelve una tarea que luego se agrega a una lista de tareas. La instrucción `Await Task.WhenAll(tasks)` finaliza el método y se reanuda en el método cuando el procesamiento de archivos se completa para todas las tareas.  
  
 Tras completar las tareas, el ejemplo cierra todas las instancias de <xref:System.IO.FileStream> de un bloque `Finally`. Si en lugar de ello, cada `FileStream` se ha creado en una instrucción `Imports`, la `FileStream` se podría desechar antes de completarse la tarea.  
  
 Tenga en cuenta que cualquier aumento del rendimiento se debe casi por completo al procesamiento en paralelo y no al procesamiento asincrónico. Las ventajas de la asincronía estriban en que no inmoviliza varios subprocesos ni el subproceso de interfaz de usuario.  
  
```vb  
Public Async Sub ProcessWriteMult()  
    Dim folder = "tempfolder\"  
    Dim tasks As New List(Of Task)  
    Dim sourceStreams As New List(Of FileStream)  
  
    Try  
        For index = 1 To 10  
            Dim text = "In file " & index.ToString & ControlChars.CrLf  
  
            Dim fileName = "thefile" & index.ToString("00") & ".txt"  
            Dim filePath = folder & fileName  
  
            Dim encodedText As Byte() = Encoding.Unicode.GetBytes(text)  
  
            Dim sourceStream As New FileStream(filePath,  
                FileMode.Append, FileAccess.Write, FileShare.None,  
                bufferSize:=4096, useAsync:=True)  
  
            Dim theTask As Task = sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
            sourceStreams.Add(sourceStream)  
  
            tasks.Add(theTask)  
        Next  
  
        Await Task.WhenAll(tasks)  
    Finally  
        For Each sourceStream As FileStream In sourceStreams  
            sourceStream.Close()  
        Next  
    End Try  
End Sub  
```  
  
 Al usar los métodos <xref:System.IO.Stream.WriteAsync%2A> y <xref:System.IO.Stream.ReadAsync%2A>, puede especificar un <xref:System.Threading.CancellationToken>, que puede usar para cancelar la operación en mitad de la secuencia. Para obtener más información, vea ajustar [la aplicación asincrónica (Visual Basic)](fine-tuning-your-async-application.md) y la [cancelación en subprocesos administrados](../../../../standard/threading/cancellation-in-managed-threads.md).  
  
## <a name="see-also"></a>Vea también

- [Programación asincrónica con Async y Await (Visual Basic)](index.md)
- [Async Return Types (Visual Basic)](async-return-types.md) (Tipos de valor devuelto de Async [Visual Basic])
- [Control Flow in Async Programs (Visual Basic)](control-flow-in-async-programs.md) (Flujo de control en programas asincrónicos [Visual Basic])

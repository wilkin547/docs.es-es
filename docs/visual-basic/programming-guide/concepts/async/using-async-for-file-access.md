---
title: Usar Async en acceso a archivos (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: c989305f-08e3-4687-95c3-948465cda202
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e0e548989b1d2c32b9faf5ce0dd90ae371dfc028
ms.lasthandoff: 03/13/2017

---
# <a name="using-async-for-file-access-visual-basic"></a>Usar Async en acceso a archivos (Visual Basic)
Puede usar la característica Async para tener acceso a archivos. Mediante la característica Async, se puede llamar a métodos asincrónicos sin definir continuaciones ni dividir el código en varios métodos o expresiones lambda. Para convertir código sincrónico en asincrónico, simplemente llame a un método asincrónico en lugar de un método sincrónico y agregar algunas palabras clave en el código.  
  
 Podría agregar asincronía a las llamadas de acceso de archivo de los siguientes motivos:  
  
-   Asincronía hace que las aplicaciones de interfaz de usuario más capacidad de respuesta porque el subproceso de interfaz de usuario que inicia la operación puede realizar otro trabajo. Si el subproceso de interfaz de usuario debe ejecutar código que tarda mucho tiempo (por ejemplo, más de 50 milisegundos), puede inmovilizar la interfaz de usuario hasta que la E/S está completa y el subproceso de interfaz de usuario puede volver a procesar teclado entrados y otros eventos del mouse.  
  
-   Asincronía mejora la escalabilidad de ASP.NET y otras aplicaciones basadas en servidor reduciendo la necesidad de subprocesos. Si la aplicación utiliza un subproceso dedicado por respuesta y controla las solicitudes de mil simultáneamente, son necesarios los subprocesos de miles. Operaciones asincrónicas a menudo no es necesario utilizar un subproceso durante la espera. Usan el subproceso existente de finalización de E/S brevemente al final.  
  
-   La latencia de una operación de acceso de archivo puede ser muy baja en las condiciones actuales, pero la latencia puede aumentar en gran medida en el futuro. Por ejemplo, se puede mover un archivo a un servidor que está en todo el mundo.  
  
-   La sobrecarga resultante de usar la característica Async es pequeño.  
  
-   Las tareas asincrónicas fácilmente se pueden ejecutar en paralelo.  
  
## <a name="running-the-examples"></a>Ejecutar los ejemplos  
 Para ejecutar los ejemplos de este tema, puede crear un **aplicación WPF** o un **aplicación de Windows Forms** y, a continuación, agregue un **botón**. En el botón `Click` evento, agregue una llamada al primer método en cada ejemplo.  
  
 En los ejemplos siguientes, se incluyen los siguientes `Imports` instrucciones.  
  
```vb  
Imports System  
Imports System.Collections.Generic  
Imports System.Diagnostics  
Imports System.IO  
Imports System.Text  
Imports System.Threading.Tasks  
```  
  
## <a name="use-of-the-filestream-class"></a>Uso de la clase FileStream  
 Los ejemplos de este tema usan la <xref:System.IO.FileStream>clase, que tiene una opción que ocasiona la E/S asincrónica que se produzca en el nivel de sistema operativo.</xref:System.IO.FileStream> Mediante esta opción, puede evitar bloquear un subproceso de ThreadPool en muchos casos. Para habilitar esta opción, especifique la `useAsync=true` o `options=FileOptions.Asynchronous` argumento en la llamada al constructor.  
  
 No puede utilizar esta opción con <xref:System.IO.StreamReader>y <xref:System.IO.StreamWriter>Si se abran especificando una ruta de acceso de archivo.</xref:System.IO.StreamWriter> </xref:System.IO.StreamReader> Sin embargo, puede utilizar esta opción si agregas un <xref:System.IO.Stream>que la <xref:System.IO.FileStream>clase abierto.</xref:System.IO.FileStream> </xref:System.IO.Stream> Tenga en cuenta que las llamadas asincrónicas son más rápidas en aplicaciones de interfaz de usuario incluso si se bloquea un subproceso ThreadPool, porque no se bloquea el subproceso de interfaz de usuario durante la espera.  
  
## <a name="writing-text"></a>Escribir texto  
 En el ejemplo siguiente se escribe texto en un archivo. En cada instrucción await, el método finaliza inmediatamente. Una vez completada la E/S de archivo, el método se reanuda en la instrucción que sigue a la instrucción await. Tenga en cuenta que el modificador async en la definición de métodos que utilizan la instrucción await.  
  
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
  
 El ejemplo original tiene la instrucción `Await sourceStream.WriteAsync(encodedText, 0, encodedText.Length)`, que es una contracción de las dos instrucciones siguientes:  
  
```vb  
Dim theTask As Task = sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
Await theTask  
```  
  
 La primera instrucción devuelve una tarea y hace que el procesamiento de archivos al iniciar. La segunda instrucción a la instrucción await hace que el método salir inmediatamente y devolver una tarea diferente. Cuando se completa el procesamiento posterior de archivos, la ejecución vuelve a la instrucción que sigue a la instrucción await. Para obtener más información, consulte [flujo de Control en programas Async (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md).  
  
## <a name="reading-text"></a>Leer texto  
 En el ejemplo siguiente se lee el texto de un archivo. El texto se almacena en búfer y, en este caso, se colocan en un <xref:System.Text.StringBuilder>.</xref:System.Text.StringBuilder> A diferencia del ejemplo anterior, la evaluación de la instrucción await genera un valor. El <xref:System.IO.Stream.ReadAsync%2A>método devuelve un <xref:System.Threading.Tasks.Task> \< <xref:System.Int32>>, por lo que la evaluación de la espera se produce un `Int32` valor (`numRead`) una vez finalizada la operación.</xref:System.Int32> </xref:System.Threading.Tasks.Task> </xref:System.IO.Stream.ReadAsync%2A> Para obtener más información, consulte [Async devolver tipos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
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
 En el ejemplo siguiente se muestra el procesamiento paralelo escribiendo 10 archivos de texto. Para cada archivo, la <xref:System.IO.Stream.WriteAsync%2A>método devuelve una tarea que se agrega a una lista de tareas.</xref:System.IO.Stream.WriteAsync%2A> El `Await Task.WhenAll(tasks)` instrucción finaliza el método y se reanuda en el método cuando el procesamiento de archivos complete para todas las tareas.  
  
 El ejemplo cierra todos <xref:System.IO.FileStream>instancias en un `Finally` bloquear una vez completadas las tareas.</xref:System.IO.FileStream> Si cada `FileStream` en su lugar se creó en un `Imports` instrucción, el `FileStream` podría eliminarse antes de completarse la tarea.  
  
 Tenga en cuenta que cualquier aumento del rendimiento es casi por completo en el procesamiento en paralelo y no el procesamiento asincrónico. Las ventajas de asincronía son no ocupar varios subprocesos y no ocupar el subproceso de interfaz de usuario.  
  
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
  
 Cuando se usa el <xref:System.IO.Stream.WriteAsync%2A>y <xref:System.IO.Stream.ReadAsync%2A>métodos, puede especificar un <xref:System.Threading.CancellationToken>, que puede usar para cancelar el flujo de la operación intermedia.</xref:System.Threading.CancellationToken> </xref:System.IO.Stream.ReadAsync%2A> </xref:System.IO.Stream.WriteAsync%2A> Para obtener más información, consulte [Fine su aplicación de Async (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) y [cancelación en subprocesos administrados](http://msdn.microsoft.com/library/eea11fe5-d8b0-4314-bb5d-8a58166fb1c3).  
  
## <a name="see-also"></a>Vea también  
 [Programación asincrónica con Async y Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)   
 [Tipos de valor devueltos de Async (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)   
 [Flujo de control en programas Async (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)

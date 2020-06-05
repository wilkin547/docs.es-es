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
# <a name="using-async-for-file-access-visual-basic"></a><span data-ttu-id="7e61c-102">Usar Async en acceso a archivos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7e61c-102">Using Async for File Access (Visual Basic)</span></span>
<span data-ttu-id="7e61c-103">Puede usar la característica Async para tener acceso a los archivos.</span><span class="sxs-lookup"><span data-stu-id="7e61c-103">You can use the Async feature to access files.</span></span> <span data-ttu-id="7e61c-104">Mediante la característica Async, se puede llamar a métodos asincrónicos sin definir continuaciones ni dividir el código en varios métodos o expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="7e61c-104">By using the Async feature, you can call into asynchronous methods without using callbacks or splitting your code across multiple methods or lambda expressions.</span></span> <span data-ttu-id="7e61c-105">Para convertir código sincrónico en asincrónico, basta con llamar a un método asincrónico y no a un método sincrónico y agregar algunas palabras clave al código.</span><span class="sxs-lookup"><span data-stu-id="7e61c-105">To make synchronous code asynchronous, you just call an asynchronous method instead of a synchronous method and add a few keywords to the code.</span></span>  
  
 <span data-ttu-id="7e61c-106">Podrían considerarse los siguientes motivos para agregar asincronía a las llamadas de acceso a archivos:</span><span class="sxs-lookup"><span data-stu-id="7e61c-106">You might consider the following reasons for adding asynchrony to file access calls:</span></span>  
  
- <span data-ttu-id="7e61c-107">La asincronía hace que las aplicaciones de interfaz de usuario tengan mayor capacidad de respuesta porque el subproceso de interfaz de usuario que inicia la operación puede realizar otro trabajo.</span><span class="sxs-lookup"><span data-stu-id="7e61c-107">Asynchrony makes UI applications more responsive because the UI thread that launches the operation can perform other work.</span></span> <span data-ttu-id="7e61c-108">Si el subproceso de interfaz de usuario debe ejecutar código que tarda mucho tiempo (por ejemplo, más de 50 milisegundos), puede inmovilizar la interfaz de usuario hasta que la E/S se complete y el subproceso de interfaz de usuario pueda volver a procesar la entrada de teclado y de mouse y otros eventos.</span><span class="sxs-lookup"><span data-stu-id="7e61c-108">If the UI thread must execute code that takes a long time (for example, more than 50 milliseconds), the UI may freeze until the I/O is complete and the UI thread can again process keyboard and mouse input and other events.</span></span>  
  
- <span data-ttu-id="7e61c-109">La asincronía mejora la escalabilidad de ASP.NET y otras aplicaciones basadas en servidor reduciendo la necesidad de subproceso.</span><span class="sxs-lookup"><span data-stu-id="7e61c-109">Asynchrony improves the scalability of ASP.NET and other server-based applications by reducing the need for threads.</span></span> <span data-ttu-id="7e61c-110">Si la aplicación usa un subproceso dedicado por respuesta y se procesa un millar de solicitudes simultáneamente, se necesitan mil subprocesos.</span><span class="sxs-lookup"><span data-stu-id="7e61c-110">If the application uses a dedicated thread per response and a thousand requests are being handled simultaneously, a thousand threads are needed.</span></span> <span data-ttu-id="7e61c-111">Las operaciones asincrónicas no suelen necesitar un subproceso durante la espera.</span><span class="sxs-lookup"><span data-stu-id="7e61c-111">Asynchronous operations often don’t need to use a thread during the wait.</span></span> <span data-ttu-id="7e61c-112">Usan el subproceso existente de finalización de E/S brevemente al final.</span><span class="sxs-lookup"><span data-stu-id="7e61c-112">They use the existing I/O completion thread briefly at the end.</span></span>  
  
- <span data-ttu-id="7e61c-113">Puede que la latencia de una operación de acceso a archivos sea muy baja en las condiciones actuales, pero puede aumentar mucho en el futuro.</span><span class="sxs-lookup"><span data-stu-id="7e61c-113">The latency of a file access operation might be very low under current conditions, but the latency may greatly increase in the future.</span></span> <span data-ttu-id="7e61c-114">Por ejemplo, se puede mover un archivo a un servidor que está a escala mundial.</span><span class="sxs-lookup"><span data-stu-id="7e61c-114">For example, a file may be moved to a server that's across the world.</span></span>  
  
- <span data-ttu-id="7e61c-115">La sobrecarga resultante de usar la característica Async es pequeña.</span><span class="sxs-lookup"><span data-stu-id="7e61c-115">The added overhead of using the Async feature is small.</span></span>  
  
- <span data-ttu-id="7e61c-116">Las tareas asincrónicas se pueden ejecutar fácilmente en paralelo.</span><span class="sxs-lookup"><span data-stu-id="7e61c-116">Asynchronous tasks can easily be run in parallel.</span></span>  
  
## <a name="running-the-examples"></a><span data-ttu-id="7e61c-117">Ejecutar los ejemplos</span><span class="sxs-lookup"><span data-stu-id="7e61c-117">Running the Examples</span></span>  
 <span data-ttu-id="7e61c-118">Para ejecutar los ejemplos de este tema, puede crear una **aplicación WPF** o una **aplicación de Windows Forms** y luego agregar un **botón**.</span><span class="sxs-lookup"><span data-stu-id="7e61c-118">To run the examples in this topic, you can create a **WPF Application** or a **Windows Forms Application** and then add a **Button**.</span></span> <span data-ttu-id="7e61c-119">En el evento `Click` del botón, agregue una llamada al primer método de cada ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7e61c-119">In the button's `Click` event, add a call to the first method in each example.</span></span>  
  
 <span data-ttu-id="7e61c-120">En los ejemplos siguientes, se incluyen las instrucciones `Imports` siguientes.</span><span class="sxs-lookup"><span data-stu-id="7e61c-120">In the following examples, include the following `Imports` statements.</span></span>  
  
```vb  
Imports System  
Imports System.Collections.Generic  
Imports System.Diagnostics  
Imports System.IO  
Imports System.Text  
Imports System.Threading.Tasks  
```  
  
## <a name="use-of-the-filestream-class"></a><span data-ttu-id="7e61c-121">Uso de la clase FileStream</span><span class="sxs-lookup"><span data-stu-id="7e61c-121">Use of the FileStream Class</span></span>  
 <span data-ttu-id="7e61c-122">En los ejemplos de este tema se usa la clase <xref:System.IO.FileStream>, que tiene una opción que hace que la E/S asincrónica se produzca en el nivel del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7e61c-122">The examples in this topic use the <xref:System.IO.FileStream> class, which has an option that causes asynchronous I/O to occur at the operating system level.</span></span> <span data-ttu-id="7e61c-123">Si usa esta opción, puede evitar bloquear un subproceso ThreadPool en muchos casos.</span><span class="sxs-lookup"><span data-stu-id="7e61c-123">By using this option, you can avoid blocking a ThreadPool thread in many cases.</span></span> <span data-ttu-id="7e61c-124">Para habilitar esta opción, especifique el argumento `useAsync=true` o `options=FileOptions.Asynchronous` en la llamada al constructor.</span><span class="sxs-lookup"><span data-stu-id="7e61c-124">To enable this option, you specify the `useAsync=true` or `options=FileOptions.Asynchronous` argument in the constructor call.</span></span>  
  
 <span data-ttu-id="7e61c-125">No puede usar esta opción con <xref:System.IO.StreamReader> y <xref:System.IO.StreamWriter> si los abre directamente al especificar una ruta de acceso de archivo.</span><span class="sxs-lookup"><span data-stu-id="7e61c-125">You can’t use this option with <xref:System.IO.StreamReader> and <xref:System.IO.StreamWriter> if you open them directly by specifying a file path.</span></span> <span data-ttu-id="7e61c-126">En cambio, puede usar esta opción si les proporciona un <xref:System.IO.Stream> que ha abierto la clase <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="7e61c-126">However, you can use this option if you provide them a <xref:System.IO.Stream> that the <xref:System.IO.FileStream> class opened.</span></span> <span data-ttu-id="7e61c-127">Tenga en cuenta que las llamadas asincrónicas son más rápidas en aplicaciones de interfaz de usuario aunque un subproceso ThreadPool se bloquee, porque el subproceso de interfaz de usuario no se bloquea durante la espera.</span><span class="sxs-lookup"><span data-stu-id="7e61c-127">Note that asynchronous calls are faster in UI apps even if a ThreadPool thread is blocked, because the UI thread isn’t blocked during the wait.</span></span>  
  
## <a name="writing-text"></a><span data-ttu-id="7e61c-128">Escribir texto</span><span class="sxs-lookup"><span data-stu-id="7e61c-128">Writing Text</span></span>  
 <span data-ttu-id="7e61c-129">En el ejemplo siguiente se escribe texto en un archivo.</span><span class="sxs-lookup"><span data-stu-id="7e61c-129">The following example writes text to a file.</span></span> <span data-ttu-id="7e61c-130">En cada instrucción await, el método finaliza inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="7e61c-130">At each await statement, the method immediately exits.</span></span> <span data-ttu-id="7e61c-131">Cuando se complete la E/S de archivo, el método se reanuda en la instrucción que sigue a la instrucción await.</span><span class="sxs-lookup"><span data-stu-id="7e61c-131">When the file I/O is complete, the method resumes at the statement that follows the await statement.</span></span> <span data-ttu-id="7e61c-132">Tenga en cuenta que el modificador async se encuentra en la definición de métodos que usan la instrucción await.</span><span class="sxs-lookup"><span data-stu-id="7e61c-132">Note that the async modifier is in the definition of methods that use the await statement.</span></span>  
  
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
  
 <span data-ttu-id="7e61c-133">El ejemplo original incluye la instrucción `Await sourceStream.WriteAsync(encodedText, 0, encodedText.Length)`, que es una contracción de las dos instrucciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="7e61c-133">The original example has the statement `Await sourceStream.WriteAsync(encodedText, 0, encodedText.Length)`, which is a contraction of the following two statements:</span></span>  
  
```vb  
Dim theTask As Task = sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
Await theTask  
```  
  
 <span data-ttu-id="7e61c-134">La primera instrucción devuelve una tarea e inicia el procesamiento de archivos.</span><span class="sxs-lookup"><span data-stu-id="7e61c-134">The first statement returns a task and causes file processing to start.</span></span> <span data-ttu-id="7e61c-135">La segunda instrucción con await finaliza el método inmediatamente y devuelve otra tarea.</span><span class="sxs-lookup"><span data-stu-id="7e61c-135">The second statement with the await causes the method to immediately exit and return a different task.</span></span> <span data-ttu-id="7e61c-136">Después, cuando se complete el procesamiento de archivos, la ejecución vuelve a la instrucción que sigue a la instrucción await.</span><span class="sxs-lookup"><span data-stu-id="7e61c-136">When the file processing later completes, execution returns to the statement that follows the await.</span></span> <span data-ttu-id="7e61c-137">Para obtener más información, vea [flujo de control en programas Async (Visual Basic)](control-flow-in-async-programs.md).</span><span class="sxs-lookup"><span data-stu-id="7e61c-137">For more information, see  [Control Flow in Async Programs (Visual Basic)](control-flow-in-async-programs.md).</span></span>  
  
## <a name="reading-text"></a><span data-ttu-id="7e61c-138">Leer texto</span><span class="sxs-lookup"><span data-stu-id="7e61c-138">Reading Text</span></span>  
 <span data-ttu-id="7e61c-139">En el ejemplo siguiente se lee texto de un archivo.</span><span class="sxs-lookup"><span data-stu-id="7e61c-139">The following example reads text from a file.</span></span> <span data-ttu-id="7e61c-140">El texto se almacena en búfer y, en este caso, se coloca en un <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="7e61c-140">The text is buffered and, in this case, placed into a <xref:System.Text.StringBuilder>.</span></span> <span data-ttu-id="7e61c-141">A diferencia del ejemplo anterior, la evaluación de la instrucción await genera un valor.</span><span class="sxs-lookup"><span data-stu-id="7e61c-141">Unlike in the previous example, the evaluation of the await produces a value.</span></span> <span data-ttu-id="7e61c-142">El método <xref:System.IO.Stream.ReadAsync%2A> devuelve un <xref:System.Threading.Tasks.Task>\<<xref:System.Int32>>, por lo que la evaluación de la espera genera un valor `Int32` (`numRead`) después de que se complete la operación.</span><span class="sxs-lookup"><span data-stu-id="7e61c-142">The <xref:System.IO.Stream.ReadAsync%2A> method returns a <xref:System.Threading.Tasks.Task>\<<xref:System.Int32>>, so the evaluation of the await produces an `Int32` value (`numRead`) after the operation completes.</span></span> <span data-ttu-id="7e61c-143">Para obtener más información, vea [tipos de valor devueltos Async (Visual Basic)](async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="7e61c-143">For more information, see [Async Return Types (Visual Basic)](async-return-types.md).</span></span>  
  
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
  
## <a name="parallel-asynchronous-io"></a><span data-ttu-id="7e61c-144">E/S asincrónica en paralelo</span><span class="sxs-lookup"><span data-stu-id="7e61c-144">Parallel Asynchronous I/O</span></span>  
 <span data-ttu-id="7e61c-145">En el ejemplo siguiente se muestra el procesamiento paralelo escribiendo 10 archivos de texto.</span><span class="sxs-lookup"><span data-stu-id="7e61c-145">The following example demonstrates parallel processing by writing 10 text files.</span></span> <span data-ttu-id="7e61c-146">Para cada archivo, el método <xref:System.IO.Stream.WriteAsync%2A> devuelve una tarea que luego se agrega a una lista de tareas.</span><span class="sxs-lookup"><span data-stu-id="7e61c-146">For each file, the <xref:System.IO.Stream.WriteAsync%2A> method returns a task that is then added to a list of tasks.</span></span> <span data-ttu-id="7e61c-147">La instrucción `Await Task.WhenAll(tasks)` finaliza el método y se reanuda en el método cuando el procesamiento de archivos se completa para todas las tareas.</span><span class="sxs-lookup"><span data-stu-id="7e61c-147">The `Await Task.WhenAll(tasks)` statement exits the method and resumes within the method when file processing is complete for all of the tasks.</span></span>  
  
 <span data-ttu-id="7e61c-148">Tras completar las tareas, el ejemplo cierra todas las instancias de <xref:System.IO.FileStream> de un bloque `Finally`.</span><span class="sxs-lookup"><span data-stu-id="7e61c-148">The example closes all <xref:System.IO.FileStream> instances in a `Finally` block after the tasks are complete.</span></span> <span data-ttu-id="7e61c-149">Si en lugar de ello, cada `FileStream` se ha creado en una instrucción `Imports`, la `FileStream` se podría desechar antes de completarse la tarea.</span><span class="sxs-lookup"><span data-stu-id="7e61c-149">If each `FileStream` was instead created in a `Imports` statement, the `FileStream` might be disposed of before the task was complete.</span></span>  
  
 <span data-ttu-id="7e61c-150">Tenga en cuenta que cualquier aumento del rendimiento se debe casi por completo al procesamiento en paralelo y no al procesamiento asincrónico.</span><span class="sxs-lookup"><span data-stu-id="7e61c-150">Note that any performance boost is almost entirely from the parallel processing and not the asynchronous processing.</span></span> <span data-ttu-id="7e61c-151">Las ventajas de la asincronía estriban en que no inmoviliza varios subprocesos ni el subproceso de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="7e61c-151">The advantages of asynchrony are that it doesn’t tie up multiple threads, and that it doesn’t tie up the user interface thread.</span></span>  
  
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
  
 <span data-ttu-id="7e61c-152">Al usar los métodos <xref:System.IO.Stream.WriteAsync%2A> y <xref:System.IO.Stream.ReadAsync%2A>, puede especificar un <xref:System.Threading.CancellationToken>, que puede usar para cancelar la operación en mitad de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="7e61c-152">When using the <xref:System.IO.Stream.WriteAsync%2A> and <xref:System.IO.Stream.ReadAsync%2A> methods, you can specify a <xref:System.Threading.CancellationToken>, which you can use to cancel the operation mid-stream.</span></span> <span data-ttu-id="7e61c-153">Para obtener más información, vea ajustar [la aplicación asincrónica (Visual Basic)](fine-tuning-your-async-application.md) y la [cancelación en subprocesos administrados](../../../../standard/threading/cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="7e61c-153">For more information, see [Fine-Tuning Your Async Application (Visual Basic)](fine-tuning-your-async-application.md) and [Cancellation in Managed Threads](../../../../standard/threading/cancellation-in-managed-threads.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e61c-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e61c-154">See also</span></span>

- [<span data-ttu-id="7e61c-155">Programación asincrónica con Async y Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7e61c-155">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](index.md)
- <span data-ttu-id="7e61c-156">[Async Return Types (Visual Basic)](async-return-types.md) (Tipos de valor devuelto de Async [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="7e61c-156">[Async Return Types (Visual Basic)](async-return-types.md)</span></span>
- <span data-ttu-id="7e61c-157">[Control Flow in Async Programs (Visual Basic)](control-flow-in-async-programs.md) (Flujo de control en programas asincrónicos [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="7e61c-157">[Control Flow in Async Programs (Visual Basic)](control-flow-in-async-programs.md)</span></span>

---
title: Usar Async en acceso a archivos (C#)
ms.date: 07/20/2015
ms.assetid: bb018fea-5313-4c80-ab3f-7c24b2145bd9
ms.openlocfilehash: 8e0a62c2263ed3fd11eb4accb54978ef439ac010
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396955"
---
# <a name="using-async-for-file-access-c"></a><span data-ttu-id="43c09-102">Usar Async en acceso a archivos (C#)</span><span class="sxs-lookup"><span data-stu-id="43c09-102">Using Async for File Access (C#)</span></span>
<span data-ttu-id="43c09-103">Puede usar la característica async para acceder a archivos.</span><span class="sxs-lookup"><span data-stu-id="43c09-103">You can use the async feature to access files.</span></span> <span data-ttu-id="43c09-104">Con la característica async, se puede llamar a métodos asincrónicos sin usar devoluciones de llamada ni dividir el código en varios métodos o expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="43c09-104">By using the async feature, you can call into asynchronous methods without using callbacks or splitting your code across multiple methods or lambda expressions.</span></span> <span data-ttu-id="43c09-105">Para convertir código sincrónico en asincrónico, basta con llamar a un método asincrónico y no a un método sincrónico y agregar algunas palabras clave al código.</span><span class="sxs-lookup"><span data-stu-id="43c09-105">To make synchronous code asynchronous, you just call an asynchronous method instead of a synchronous method and add a few keywords to the code.</span></span>  
  
 <span data-ttu-id="43c09-106">Podrían considerarse los siguientes motivos para agregar asincronía a las llamadas de acceso a archivos:</span><span class="sxs-lookup"><span data-stu-id="43c09-106">You might consider the following reasons for adding asynchrony to file access calls:</span></span>  
  
- <span data-ttu-id="43c09-107">La asincronía hace que las aplicaciones de interfaz de usuario tengan mayor capacidad de respuesta porque el subproceso de interfaz de usuario que inicia la operación puede realizar otro trabajo.</span><span class="sxs-lookup"><span data-stu-id="43c09-107">Asynchrony makes UI applications more responsive because the UI thread that launches the operation can perform other work.</span></span> <span data-ttu-id="43c09-108">Si el subproceso de interfaz de usuario debe ejecutar código que tarda mucho tiempo (por ejemplo, más de 50 milisegundos), puede inmovilizar la interfaz de usuario hasta que la E/S se complete y el subproceso de interfaz de usuario pueda volver a procesar la entrada de teclado y de mouse y otros eventos.</span><span class="sxs-lookup"><span data-stu-id="43c09-108">If the UI thread must execute code that takes a long time (for example, more than 50 milliseconds), the UI may freeze until the I/O is complete and the UI thread can again process keyboard and mouse input and other events.</span></span>  
  
- <span data-ttu-id="43c09-109">La asincronía mejora la escalabilidad de ASP.NET y otras aplicaciones basadas en servidor reduciendo la necesidad de subproceso.</span><span class="sxs-lookup"><span data-stu-id="43c09-109">Asynchrony improves the scalability of ASP.NET and other server-based applications by reducing the need for threads.</span></span> <span data-ttu-id="43c09-110">Si la aplicación usa un subproceso dedicado por respuesta y se procesa un millar de solicitudes simultáneamente, se necesitan mil subprocesos.</span><span class="sxs-lookup"><span data-stu-id="43c09-110">If the application uses a dedicated thread per response and a thousand requests are being handled simultaneously, a thousand threads are needed.</span></span> <span data-ttu-id="43c09-111">Las operaciones asincrónicas no suelen necesitar un subproceso durante la espera.</span><span class="sxs-lookup"><span data-stu-id="43c09-111">Asynchronous operations often don’t need to use a thread during the wait.</span></span> <span data-ttu-id="43c09-112">Usan el subproceso existente de finalización de E/S brevemente al final.</span><span class="sxs-lookup"><span data-stu-id="43c09-112">They use the existing I/O completion thread briefly at the end.</span></span>  
  
- <span data-ttu-id="43c09-113">Puede que la latencia de una operación de acceso a archivos sea muy baja en las condiciones actuales, pero puede aumentar mucho en el futuro.</span><span class="sxs-lookup"><span data-stu-id="43c09-113">The latency of a file access operation might be very low under current conditions, but the latency may greatly increase in the future.</span></span> <span data-ttu-id="43c09-114">Por ejemplo, se puede mover un archivo a un servidor que está a escala mundial.</span><span class="sxs-lookup"><span data-stu-id="43c09-114">For example, a file may be moved to a server that's across the world.</span></span>  
  
- <span data-ttu-id="43c09-115">La sobrecarga resultante de usar la característica Async es pequeña.</span><span class="sxs-lookup"><span data-stu-id="43c09-115">The added overhead of using the Async feature is small.</span></span>  
  
- <span data-ttu-id="43c09-116">Las tareas asincrónicas se pueden ejecutar fácilmente en paralelo.</span><span class="sxs-lookup"><span data-stu-id="43c09-116">Asynchronous tasks can easily be run in parallel.</span></span>  
  
## <a name="running-the-examples"></a><span data-ttu-id="43c09-117">Ejecutar los ejemplos</span><span class="sxs-lookup"><span data-stu-id="43c09-117">Running the Examples</span></span>  
 <span data-ttu-id="43c09-118">Para ejecutar los ejemplos de este tema, puede crear una **aplicación WPF** o una **aplicación de Windows Forms** y luego agregar un **botón**.</span><span class="sxs-lookup"><span data-stu-id="43c09-118">To run the examples in this topic, you can create a **WPF Application** or a **Windows Forms Application** and then add a **Button**.</span></span> <span data-ttu-id="43c09-119">En el evento `Click` del botón, agregue una llamada al primer método de cada ejemplo.</span><span class="sxs-lookup"><span data-stu-id="43c09-119">In the button's `Click` event, add a call to the first method in each example.</span></span>  
  
 <span data-ttu-id="43c09-120">En los ejemplos siguientes, se incluyen las directivas `using` siguientes.</span><span class="sxs-lookup"><span data-stu-id="43c09-120">In the following examples, include the following `using` directives.</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Diagnostics;  
using System.IO;  
using System.Text;  
using System.Threading.Tasks;  
```  
  
## <a name="use-of-the-filestream-class"></a><span data-ttu-id="43c09-121">Uso de la clase FileStream</span><span class="sxs-lookup"><span data-stu-id="43c09-121">Use of the FileStream Class</span></span>  
 <span data-ttu-id="43c09-122">En los ejemplos de este tema se usa la clase <xref:System.IO.FileStream>, que tiene una opción que hace que la E/S asincrónica se produzca en el nivel del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="43c09-122">The examples in this topic use the <xref:System.IO.FileStream> class, which has an option that causes asynchronous I/O to occur at the operating system level.</span></span> <span data-ttu-id="43c09-123">Si usa esta opción, puede evitar bloquear un subproceso ThreadPool en muchos casos.</span><span class="sxs-lookup"><span data-stu-id="43c09-123">By using this option, you can avoid blocking a ThreadPool thread in many cases.</span></span> <span data-ttu-id="43c09-124">Para habilitar esta opción, especifique el argumento `useAsync=true` o `options=FileOptions.Asynchronous` en la llamada al constructor.</span><span class="sxs-lookup"><span data-stu-id="43c09-124">To enable this option, you specify the `useAsync=true` or `options=FileOptions.Asynchronous` argument in the constructor call.</span></span>  
  
 <span data-ttu-id="43c09-125">No puede usar esta opción con <xref:System.IO.StreamReader> y <xref:System.IO.StreamWriter> si los abre directamente al especificar una ruta de acceso de archivo.</span><span class="sxs-lookup"><span data-stu-id="43c09-125">You can’t use this option with <xref:System.IO.StreamReader> and <xref:System.IO.StreamWriter> if you open them directly by specifying a file path.</span></span> <span data-ttu-id="43c09-126">En cambio, puede usar esta opción si les proporciona un <xref:System.IO.Stream> que ha abierto la clase <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="43c09-126">However, you can use this option if you provide them a <xref:System.IO.Stream> that the <xref:System.IO.FileStream> class opened.</span></span> <span data-ttu-id="43c09-127">Tenga en cuenta que las llamadas asincrónicas son más rápidas en aplicaciones de interfaz de usuario aunque un subproceso ThreadPool se bloquee, porque el subproceso de interfaz de usuario no se bloquea durante la espera.</span><span class="sxs-lookup"><span data-stu-id="43c09-127">Note that asynchronous calls are faster in UI apps even if a ThreadPool thread is blocked, because the UI thread isn’t blocked during the wait.</span></span>  
  
## <a name="writing-text"></a><span data-ttu-id="43c09-128">Escribir texto</span><span class="sxs-lookup"><span data-stu-id="43c09-128">Writing Text</span></span>  
 <span data-ttu-id="43c09-129">En el ejemplo siguiente se escribe texto en un archivo.</span><span class="sxs-lookup"><span data-stu-id="43c09-129">The following example writes text to a file.</span></span> <span data-ttu-id="43c09-130">En cada instrucción await, el método finaliza inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="43c09-130">At each await statement, the method immediately exits.</span></span> <span data-ttu-id="43c09-131">Cuando se complete la E/S de archivo, el método se reanuda en la instrucción que sigue a la instrucción await.</span><span class="sxs-lookup"><span data-stu-id="43c09-131">When the file I/O is complete, the method resumes at the statement that follows the await statement.</span></span> <span data-ttu-id="43c09-132">Tenga en cuenta que el modificador async se encuentra en la definición de métodos que usan la instrucción await.</span><span class="sxs-lookup"><span data-stu-id="43c09-132">Note that the async modifier is in the definition of methods that use the await statement.</span></span>  
  
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
  
 <span data-ttu-id="43c09-133">El ejemplo original incluye la instrucción `await sourceStream.WriteAsync(encodedText, 0, encodedText.Length);`, que es una contracción de las dos instrucciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="43c09-133">The original example has the statement `await sourceStream.WriteAsync(encodedText, 0, encodedText.Length);`, which is a contraction of the following two statements:</span></span>  
  
```csharp  
Task theTask = sourceStream.WriteAsync(encodedText, 0, encodedText.Length);  
await theTask;  
```  
  
 <span data-ttu-id="43c09-134">La primera instrucción devuelve una tarea e inicia el procesamiento de archivos.</span><span class="sxs-lookup"><span data-stu-id="43c09-134">The first statement returns a task and causes file processing to start.</span></span> <span data-ttu-id="43c09-135">La segunda instrucción con await finaliza el método inmediatamente y devuelve otra tarea.</span><span class="sxs-lookup"><span data-stu-id="43c09-135">The second statement with the await causes the method to immediately exit and return a different task.</span></span> <span data-ttu-id="43c09-136">Después, cuando se complete el procesamiento de archivos, la ejecución vuelve a la instrucción que sigue a la instrucción await.</span><span class="sxs-lookup"><span data-stu-id="43c09-136">When the file processing later completes, execution returns to the statement that follows the await.</span></span> <span data-ttu-id="43c09-137">Para obtener más información, vea [Control Flow in Async Programs (C#)](./control-flow-in-async-programs.md) (Flujo de control en programas asincrónicos [C#]).</span><span class="sxs-lookup"><span data-stu-id="43c09-137">For more information, see  [Control Flow in Async Programs (C#)](./control-flow-in-async-programs.md).</span></span>  
  
## <a name="reading-text"></a><span data-ttu-id="43c09-138">Leer texto</span><span class="sxs-lookup"><span data-stu-id="43c09-138">Reading Text</span></span>  
 <span data-ttu-id="43c09-139">En el ejemplo siguiente se lee texto de un archivo.</span><span class="sxs-lookup"><span data-stu-id="43c09-139">The following example reads text from a file.</span></span> <span data-ttu-id="43c09-140">El texto se almacena en búfer y, en este caso, se coloca en un <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="43c09-140">The text is buffered and, in this case, placed into a <xref:System.Text.StringBuilder>.</span></span> <span data-ttu-id="43c09-141">A diferencia del ejemplo anterior, la evaluación de la instrucción await genera un valor.</span><span class="sxs-lookup"><span data-stu-id="43c09-141">Unlike in the previous example, the evaluation of the await produces a value.</span></span> <span data-ttu-id="43c09-142">El método <xref:System.IO.Stream.ReadAsync%2A> devuelve un <xref:System.Threading.Tasks.Task>\<<xref:System.Int32>>, por lo que la evaluación de la espera genera un valor `Int32` (`numRead`) después de que se complete la operación.</span><span class="sxs-lookup"><span data-stu-id="43c09-142">The <xref:System.IO.Stream.ReadAsync%2A> method returns a <xref:System.Threading.Tasks.Task>\<<xref:System.Int32>>, so the evaluation of the await produces an `Int32` value (`numRead`) after the operation completes.</span></span> <span data-ttu-id="43c09-143">Para obtener más información, consulte [Tipos de valor devueltos asincrónicos (C#)](./async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="43c09-143">For more information, see [Async Return Types (C#)](./async-return-types.md).</span></span>  
  
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
  
## <a name="parallel-asynchronous-io"></a><span data-ttu-id="43c09-144">E/S asincrónica en paralelo</span><span class="sxs-lookup"><span data-stu-id="43c09-144">Parallel Asynchronous I/O</span></span>  
 <span data-ttu-id="43c09-145">En el ejemplo siguiente se muestra el procesamiento paralelo escribiendo 10 archivos de texto.</span><span class="sxs-lookup"><span data-stu-id="43c09-145">The following example demonstrates parallel processing by writing 10 text files.</span></span> <span data-ttu-id="43c09-146">Para cada archivo, el método <xref:System.IO.Stream.WriteAsync%2A> devuelve una tarea que luego se agrega a una lista de tareas.</span><span class="sxs-lookup"><span data-stu-id="43c09-146">For each file, the <xref:System.IO.Stream.WriteAsync%2A> method returns a task that is then added to a list of tasks.</span></span> <span data-ttu-id="43c09-147">La instrucción `await Task.WhenAll(tasks);` finaliza el método y se reanuda en el método cuando el procesamiento de archivos se completa para todas las tareas.</span><span class="sxs-lookup"><span data-stu-id="43c09-147">The `await Task.WhenAll(tasks);` statement exits the method and resumes within the method when file processing is complete for all of the tasks.</span></span>  
  
 <span data-ttu-id="43c09-148">Tras completar las tareas, el ejemplo cierra todas las instancias de <xref:System.IO.FileStream> de un bloque `finally`.</span><span class="sxs-lookup"><span data-stu-id="43c09-148">The example closes all <xref:System.IO.FileStream> instances in a `finally` block after the tasks are complete.</span></span> <span data-ttu-id="43c09-149">Si en lugar de ello, cada `FileStream` se ha creado en una instrucción `using`, la `FileStream` se podría desechar antes de completarse la tarea.</span><span class="sxs-lookup"><span data-stu-id="43c09-149">If each `FileStream` was instead created in a `using` statement, the `FileStream` might be disposed of before the task was complete.</span></span>  
  
 <span data-ttu-id="43c09-150">Tenga en cuenta que cualquier aumento del rendimiento se debe casi por completo al procesamiento en paralelo y no al procesamiento asincrónico.</span><span class="sxs-lookup"><span data-stu-id="43c09-150">Note that any performance boost is almost entirely from the parallel processing and not the asynchronous processing.</span></span> <span data-ttu-id="43c09-151">Las ventajas de la asincronía estriban en que no inmoviliza varios subprocesos ni el subproceso de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="43c09-151">The advantages of asynchrony are that it doesn’t tie up multiple threads, and that it doesn’t tie up the user interface thread.</span></span>  
  
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
  
 <span data-ttu-id="43c09-152">Al usar los métodos <xref:System.IO.Stream.WriteAsync%2A> y <xref:System.IO.Stream.ReadAsync%2A>, puede especificar un <xref:System.Threading.CancellationToken>, que puede usar para cancelar la operación en mitad de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="43c09-152">When using the <xref:System.IO.Stream.WriteAsync%2A> and <xref:System.IO.Stream.ReadAsync%2A> methods, you can specify a <xref:System.Threading.CancellationToken>, which you can use to cancel the operation mid-stream.</span></span> <span data-ttu-id="43c09-153">Para obtener más información, vea [Ajustar una aplicación asincrónica (C#)](./fine-tuning-your-async-application.md) y [Cancelación en subprocesos administrados](../../../../standard/threading/cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="43c09-153">For more information, see [Fine-Tuning Your Async Application (C#)](./fine-tuning-your-async-application.md) and [Cancellation in Managed Threads](../../../../standard/threading/cancellation-in-managed-threads.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43c09-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="43c09-154">See also</span></span>

- [<span data-ttu-id="43c09-155">Programación asincrónica con Async y Await (C#)</span><span class="sxs-lookup"><span data-stu-id="43c09-155">Asynchronous Programming with async and await (C#)</span></span>](./index.md)
- [<span data-ttu-id="43c09-156">Tipos de valor devueltos asincrónicos (C#)</span><span class="sxs-lookup"><span data-stu-id="43c09-156">Async Return Types (C#)</span></span>](./async-return-types.md)
- [<span data-ttu-id="43c09-157">Controlar el flujo en los programas asincrónicos (C#)</span><span class="sxs-lookup"><span data-stu-id="43c09-157">Control Flow in Async Programs (C#)</span></span>](./control-flow-in-async-programs.md)

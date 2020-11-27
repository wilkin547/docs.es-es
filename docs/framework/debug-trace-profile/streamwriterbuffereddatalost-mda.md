---
title: MDA de streamWriterBufferedDataLost
description: Revise el Asistente para la depuración administrada (MDA) streamWriterBufferedDataLost, que puede activarse si StreamWriter no escribe los últimos 1 – 4 KB de datos en un archivo.
ms.date: 03/30/2017
helpviewer_keywords:
- StreamWriter class, data buffering problems
- managed debugging assistants (MDAs), StreamWriter data buffering
- buffers, StreamWriter problems
- MDAs (managed debugging assistants), StreamWriter data buffering
- StreamWriter buffered data lost
- data buffering problems
- streamWriterBufferedDataLost MDA
ms.assetid: 6e5c07be-bc5b-437a-8398-8779e23126ab
ms.openlocfilehash: 23a8146bfa5acc08000e689917abb844c5540fec
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267083"
---
# <a name="streamwriterbuffereddatalost-mda"></a><span data-ttu-id="e8e84-103">MDA de streamWriterBufferedDataLost</span><span class="sxs-lookup"><span data-stu-id="e8e84-103">streamWriterBufferedDataLost MDA</span></span>

<span data-ttu-id="e8e84-104">El Asistente para la depuración administrada (MDA) `streamWriterBufferedDataLost` se activa cuando se escribe un <xref:System.IO.StreamWriter>, pero después no se llama al método <xref:System.IO.StreamWriter.Flush%2A> o <xref:System.IO.StreamWriter.Close%2A> antes de que se destruya la instancia del <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="e8e84-104">The `streamWriterBufferedDataLost` managed debugging assistant (MDA) is activated when a <xref:System.IO.StreamWriter> is written to, but the <xref:System.IO.StreamWriter.Flush%2A> or <xref:System.IO.StreamWriter.Close%2A> method is not subsequently called before the instance of the <xref:System.IO.StreamWriter> is destroyed.</span></span> <span data-ttu-id="e8e84-105">Cuando este MDA está habilitado, el tiempo de ejecución determina si los datos almacenados en búfer todavía existen en <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="e8e84-105">When this MDA is enabled, the runtime determines whether any buffered data still exists within the <xref:System.IO.StreamWriter>.</span></span> <span data-ttu-id="e8e84-106">Si existen datos almacenados en búfer, se activa el MDA.</span><span class="sxs-lookup"><span data-stu-id="e8e84-106">If buffered data does exist, the MDA is activated.</span></span> <span data-ttu-id="e8e84-107">Llamar a los métodos <xref:System.GC.Collect%2A> y <xref:System.GC.WaitForPendingFinalizers%2A> puede forzar la ejecución de los finalizadores.</span><span class="sxs-lookup"><span data-stu-id="e8e84-107">Calling the <xref:System.GC.Collect%2A> and <xref:System.GC.WaitForPendingFinalizers%2A> methods can force finalizers to run.</span></span> <span data-ttu-id="e8e84-108">En caso contrario, los finalizadores se ejecutarán en momentos aparentemente arbitrarios y posiblemente no lo hagan en la salida del proceso.</span><span class="sxs-lookup"><span data-stu-id="e8e84-108">Finalizers will otherwise run at seemingly arbitrary times, and possibly not at all on process exit.</span></span> <span data-ttu-id="e8e84-109">La ejecución explícita de los finalizadores con este MDA habilitado ayudará a reproducir este tipo de problema de forma más confiable.</span><span class="sxs-lookup"><span data-stu-id="e8e84-109">Explicitly running finalizers with this MDA enabled will help to more reliably reproduce this type of problem.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="e8e84-110">Síntomas</span><span class="sxs-lookup"><span data-stu-id="e8e84-110">Symptoms</span></span>  

 <span data-ttu-id="e8e84-111"><xref:System.IO.StreamWriter> no escribe los últimos 1-4 KB de datos en un archivo.</span><span class="sxs-lookup"><span data-stu-id="e8e84-111">A <xref:System.IO.StreamWriter> does not write the last 1–4 KB of data to a file.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="e8e84-112">Causa</span><span class="sxs-lookup"><span data-stu-id="e8e84-112">Cause</span></span>  

 <span data-ttu-id="e8e84-113"><xref:System.IO.StreamWriter> almacena en búfer los datos internamente, lo que requiere que se llame al método <xref:System.IO.StreamWriter.Close%2A> o <xref:System.IO.StreamWriter.Flush%2A> para escribir los datos almacenados en búfer en el almacén de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="e8e84-113">The <xref:System.IO.StreamWriter> buffers data internally, which requires that the <xref:System.IO.StreamWriter.Close%2A> or <xref:System.IO.StreamWriter.Flush%2A> method be called to write the buffered data to the underlying data store.</span></span> <span data-ttu-id="e8e84-114">Si no se llama a <xref:System.IO.StreamWriter.Close%2A> o <xref:System.IO.StreamWriter.Flush%2A> adecuadamente, es posible que los datos almacenados en búfer en la instancia de <xref:System.IO.StreamWriter> no se escriban de la forma esperada.</span><span class="sxs-lookup"><span data-stu-id="e8e84-114">If <xref:System.IO.StreamWriter.Close%2A> or <xref:System.IO.StreamWriter.Flush%2A> is not appropriately called, data buffered in the <xref:System.IO.StreamWriter> instance might not be written as expected.</span></span>  
  
 <span data-ttu-id="e8e84-115">El siguiente es un ejemplo de código mal escrito que este MDA debería detectar.</span><span class="sxs-lookup"><span data-stu-id="e8e84-115">The following is an example of poorly written code that this MDA should catch.</span></span>  
  
```csharp  
// Poorly written code.  
void Write()
{  
    StreamWriter sw = new StreamWriter("file.txt");  
    sw.WriteLine("Data");  
    // Problem: forgot to close the StreamWriter.  
}  
```  
  
 <span data-ttu-id="e8e84-116">El código anterior activará este MDA de una manera más confiable si se desencadena una recolección de elementos no utilizados y después se suspende hasta que hayan terminado los finalizadores.</span><span class="sxs-lookup"><span data-stu-id="e8e84-116">The preceding code will activate this MDA more reliably if a garbage collection is triggered and then suspended until finalizers have finished.</span></span> <span data-ttu-id="e8e84-117">Para realizar un seguimiento de este tipo de problema, puede agregar el código siguiente al final del método anterior en una compilación de depuración.</span><span class="sxs-lookup"><span data-stu-id="e8e84-117">To track down this type of problem, you can add the following code to the end of the preceding method in a debug build.</span></span> <span data-ttu-id="e8e84-118">Esto ayudará a activar el MDA de forma confiable, pero por supuesto no soluciona la causa del problema.</span><span class="sxs-lookup"><span data-stu-id="e8e84-118">This will help to reliably activate the MDA, but of course it does not fix the cause of the problem.</span></span>  
  
```csharp
GC.Collect();  
GC.WaitForPendingFinalizers();  
```  
  
## <a name="resolution"></a><span data-ttu-id="e8e84-119">Solución</span><span class="sxs-lookup"><span data-stu-id="e8e84-119">Resolution</span></span>  

 <span data-ttu-id="e8e84-120">Asegúrese de que se llama a <xref:System.IO.StreamWriter.Close%2A> o <xref:System.IO.StreamWriter.Flush%2A> en <xref:System.IO.StreamWriter> antes de cerrar una aplicación o cualquier bloque de código que tenga una instancia de <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="e8e84-120">Make sure you call <xref:System.IO.StreamWriter.Close%2A> or <xref:System.IO.StreamWriter.Flush%2A> on the <xref:System.IO.StreamWriter> before closing an application or any code block that has an instance of a <xref:System.IO.StreamWriter>.</span></span> <span data-ttu-id="e8e84-121">Uno de los mejores mecanismos para conseguirlo es crear la instancia con un bloque `using` de C# (`Using` en Visual Basic), que se asegurará de que se invoca el método <xref:System.IO.StreamWriter.Dispose%2A> para el escritor y, como resultado, la instancia se cerrará correctamente.</span><span class="sxs-lookup"><span data-stu-id="e8e84-121">One of the best mechanisms for achieving this is creating the instance with a C# `using` block (`Using` in Visual Basic), which will ensure the <xref:System.IO.StreamWriter.Dispose%2A> method for the writer is invoked, resulting in the instance being correctly closed.</span></span>  
  
```csharp
using(StreamWriter sw = new StreamWriter("file.txt"))
{  
    sw.WriteLine("Data");  
}  
```  
  
 <span data-ttu-id="e8e84-122">En el código siguiente se muestra la misma solución, usando `try/finally` en lugar de `using`.</span><span class="sxs-lookup"><span data-stu-id="e8e84-122">The following code shows the same solution, using `try/finally` instead of `using`.</span></span>  
  
```csharp
StreamWriter sw;  
try
{  
    sw = new StreamWriter("file.txt"));  
    sw.WriteLine("Data");  
}  
finally
{  
    if (sw != null)  
        sw.Close();  
}  
```  
  
 <span data-ttu-id="e8e84-123">Si ninguna de estas soluciones se pueden usar (por ejemplo, si un <xref:System.IO.StreamWriter> se almacena en una variable estática y no se puede ejecutar fácilmente código al final de su duración), llamar a <xref:System.IO.StreamWriter.Flush%2A> en <xref:System.IO.StreamWriter> después de su último uso o establecer la propiedad <xref:System.IO.StreamWriter.AutoFlush%2A> en `true` antes de su primer uso debería evitar este problema.</span><span class="sxs-lookup"><span data-stu-id="e8e84-123">If neither of these solutions can be used (for example, if a <xref:System.IO.StreamWriter> is stored in a static variable and you cannot easily run code at the end of its lifetime), then calling <xref:System.IO.StreamWriter.Flush%2A> on the <xref:System.IO.StreamWriter> after its last use or setting the <xref:System.IO.StreamWriter.AutoFlush%2A> property to `true` before its first use should avoid this problem.</span></span>  
  
```csharp
private static StreamWriter log;  
// static class constructor.  
static WriteToFile()
{  
    StreamWriter sw = new StreamWriter("log.txt");  
    sw.AutoFlush = true;  
  
    // Publish the StreamWriter for other threads.  
    log = sw;  
}  
```  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="e8e84-124">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="e8e84-124">Effect on the Runtime</span></span>  

 <span data-ttu-id="e8e84-125">Este MDA no tiene ningún efecto en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e8e84-125">This MDA has no effect on the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="e8e84-126">Resultados</span><span class="sxs-lookup"><span data-stu-id="e8e84-126">Output</span></span>  

 <span data-ttu-id="e8e84-127">Un mensaje que indica que se produjo esta infracción.</span><span class="sxs-lookup"><span data-stu-id="e8e84-127">A message indicating that this violation occurred.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="e8e84-128">Configuración</span><span class="sxs-lookup"><span data-stu-id="e8e84-128">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <streamWriterBufferedDataLost />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e8e84-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8e84-129">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="e8e84-130">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="e8e84-130">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)

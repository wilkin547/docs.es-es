---
title: Agentes de escucha de seguimiento
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Listener object types
- listeners
- Trace class, listeners
- trace listeners, about trace listeners
- Listeners collection
- trace listeners
- tracing [.NET Framework], trace listeners
- logs, trace listeners
ms.assetid: 444b0d33-67ea-4c36-9e94-79c50f839025
ms.openlocfilehash: a51c046a296fbb62d21c7784cf7c1e78b700f3e9
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216143"
---
# <a name="trace-listeners"></a><span data-ttu-id="4f9e6-102">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="4f9e6-102">Trace Listeners</span></span>
<span data-ttu-id="4f9e6-103">Al usar **Trace**, **Debug** y <xref:System.Diagnostics.TraceSource>, debe disponer de un mecanismo para recopilar y grabar los mensajes que se envíen.</span><span class="sxs-lookup"><span data-stu-id="4f9e6-103">When using **Trace**, **Debug** and <xref:System.Diagnostics.TraceSource>, you must have a mechanism for collecting and recording the messages that are sent.</span></span> <span data-ttu-id="4f9e6-104">Los *agentes de escucha* reciben los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4f9e6-104">Trace messages are received by *listeners*.</span></span> <span data-ttu-id="4f9e6-105">El propósito de un agente de escucha es recopilar, almacenar y transferir mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4f9e6-105">The purpose of a listener is to collect, store, and route tracing messages.</span></span> <span data-ttu-id="4f9e6-106">Los agentes de escucha dirigen el resultado del seguimiento a un destino adecuado, como un registro, una ventana o un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="4f9e6-106">Listeners direct the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
 <span data-ttu-id="4f9e6-107">Los agentes de escucha están disponibles para las clases **Debug**, **Trace** y <xref:System.Diagnostics.TraceSource>, cada una de las cuales puede enviar sus resultados a una variedad de objetos de escucha.</span><span class="sxs-lookup"><span data-stu-id="4f9e6-107">Listeners are available to the **Debug**, **Trace**, and <xref:System.Diagnostics.TraceSource> classes, each of which can send its output to a variety of listener objects.</span></span> <span data-ttu-id="4f9e6-108">A continuación se indican los agentes de escucha predefinidos más usados:</span><span class="sxs-lookup"><span data-stu-id="4f9e6-108">The following are the commonly used predefined listeners:</span></span>  
  
- <span data-ttu-id="4f9e6-109">Un <xref:System.Diagnostics.TextWriterTraceListener> redirige los resultados a una instancia de la clase <xref:System.IO.TextWriter> o a cualquier cosa que sea una clase <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="4f9e6-109">A <xref:System.Diagnostics.TextWriterTraceListener> redirects output to an instance of the <xref:System.IO.TextWriter> class or to anything that is a <xref:System.IO.Stream> class.</span></span> <span data-ttu-id="4f9e6-110">También puede escribir en la consola o en un archivo, ya que ambos son clases <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="4f9e6-110">It can also write to the console or to a file, because these are <xref:System.IO.Stream> classes.</span></span>  
  
- <span data-ttu-id="4f9e6-111">Un <xref:System.Diagnostics.EventLogTraceListener> redirige los resultados a un registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="4f9e6-111">An <xref:System.Diagnostics.EventLogTraceListener> redirects output to an event log.</span></span>  
  
- <span data-ttu-id="4f9e6-112">Un <xref:System.Diagnostics.DefaultTraceListener> emite mensajes **Write** y **WriteLine** a **OutputDebugString** y al método **Debugger.Log**.</span><span class="sxs-lookup"><span data-stu-id="4f9e6-112">A <xref:System.Diagnostics.DefaultTraceListener> emits **Write** and **WriteLine** messages to the **OutputDebugString** and to the **Debugger.Log** method.</span></span> <span data-ttu-id="4f9e6-113">En Visual Studio, esto hace que los mensajes de depuración aparezcan en la ventana Resultados.</span><span class="sxs-lookup"><span data-stu-id="4f9e6-113">In Visual Studio, this causes the debugging messages to appear in the Output window.</span></span> <span data-ttu-id="4f9e6-114">También se envían mensajes **Fail** y **Assert** a la API de Windows **OutputDebugString** y al método **Debugger.Log**, y también hacen que se muestre un cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="4f9e6-114">**Fail** and failed **Assert** messages also emit to the **OutputDebugString** Windows API and the **Debugger.Log** method, and also cause a message box to be displayed.</span></span> <span data-ttu-id="4f9e6-115">Este comportamiento es el predeterminado de los mensajes **Debug** y **Trace**, porque **DefaultTraceListener** se incluye automáticamente en cada colección de `Listeners` y es el único agente de escucha que se incluye automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4f9e6-115">This behavior is the default behavior for **Debug** and **Trace** messages, because **DefaultTraceListener** is automatically included in every `Listeners` collection and is the only listener automatically included.</span></span>  
  
- <span data-ttu-id="4f9e6-116">Un <xref:System.Diagnostics.ConsoleTraceListener> dirige los resultados del seguimiento o de la depuración a los resultados estándar o al flujo de error estándar.</span><span class="sxs-lookup"><span data-stu-id="4f9e6-116">A <xref:System.Diagnostics.ConsoleTraceListener> directs tracing or debugging output to either the standard output or the standard error stream.</span></span>  
  
- <span data-ttu-id="4f9e6-117">Un <xref:System.Diagnostics.DelimitedListTraceListener> dirige los resultados del seguimiento o de la depuración a un escritor de texto, como un escritor de secuencias, o a una secuencia, como una secuencia de archivo.</span><span class="sxs-lookup"><span data-stu-id="4f9e6-117">A <xref:System.Diagnostics.DelimitedListTraceListener> directs tracing or debugging output to a text writer, such as a stream writer, or to a stream, such as a file stream.</span></span> <span data-ttu-id="4f9e6-118">La salida del seguimiento se encuentra en un formato de texto delimitado que usa el delimitador especificado por la propiedad <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A>.</span><span class="sxs-lookup"><span data-stu-id="4f9e6-118">The trace output is in a delimited text format that uses the delimiter specified by the <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> property.</span></span>  
  
- <span data-ttu-id="4f9e6-119">Un <xref:System.Diagnostics.XmlWriterTraceListener> dirige los resultados del seguimiento o de la depuración como datos codificados en XML a un <xref:System.IO.TextWriter> o a un <xref:System.IO.Stream>, como un <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="4f9e6-119">An <xref:System.Diagnostics.XmlWriterTraceListener> directs tracing or debugging output as XML-encoded data to a <xref:System.IO.TextWriter> or to a <xref:System.IO.Stream>, such as a <xref:System.IO.FileStream>.</span></span>  
  
 <span data-ttu-id="4f9e6-120">Si quiere que algún agente de escucha además del <xref:System.Diagnostics.DefaultTraceListener> reciba los resultados de **Debug**, **Trace** y <xref:System.Diagnostics.TraceSource>, debe agregarlo a la colección de `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="4f9e6-120">If you want any listener besides the <xref:System.Diagnostics.DefaultTraceListener> to receive **Debug**, **Trace** and <xref:System.Diagnostics.TraceSource> output, you must add it to the `Listeners` collection.</span></span> <span data-ttu-id="4f9e6-121">Para más información, vea [Cómo: Crear e inicializar agentes de escucha de seguimiento](how-to-create-and-initialize-trace-listeners.md) y [Cómo: Utilizar TraceSource y filtros con agentes de escucha de seguimiento](how-to-use-tracesource-and-filters-with-trace-listeners.md).</span><span class="sxs-lookup"><span data-stu-id="4f9e6-121">For more information, see [How to: Create and Initialize Trace Listeners](how-to-create-and-initialize-trace-listeners.md) and [How to: Use TraceSource and Filters with Trace Listeners](how-to-use-tracesource-and-filters-with-trace-listeners.md).</span></span> <span data-ttu-id="4f9e6-122">Todos los agentes de escucha de la colección **Listeners** reciben los mismos mensajes de los métodos de resultados de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4f9e6-122">Any listener in the **Listeners** collection gets the same messages from the trace output methods.</span></span> <span data-ttu-id="4f9e6-123">Por ejemplo, supongamos que configura dos agentes de escucha: **TextWriterTraceListener** y **EventLogTraceListener**.</span><span class="sxs-lookup"><span data-stu-id="4f9e6-123">For example, suppose you set up two listeners: a **TextWriterTraceListener** and an **EventLogTraceListener**.</span></span> <span data-ttu-id="4f9e6-124">Cada agente de escucha recibe el mismo mensaje.</span><span class="sxs-lookup"><span data-stu-id="4f9e6-124">Each listener receives the same message.</span></span> <span data-ttu-id="4f9e6-125">**TextWriterTraceListener** dirigiría sus resultados a una secuencia y **EventLogTraceListener** dirigiría los suyos a un registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="4f9e6-125">The **TextWriterTraceListener** would direct its output to a stream, and the **EventLogTraceListener** would direct its output to an event log.</span></span>  
  
 <span data-ttu-id="4f9e6-126">En el siguiente ejemplo se muestra cómo enviar resultados a la colección **Listeners**.</span><span class="sxs-lookup"><span data-stu-id="4f9e6-126">The following example shows how to send output to the **Listeners** collection.</span></span>  
  
```vb  
' Use this example when debugging.  
Debug.WriteLine("Error in Widget 42")  
' Use this example when tracing.  
Trace.WriteLine("Error in Widget 42")  
```  
  
```csharp  
// Use this example when debugging.  
System.Diagnostics.Debug.WriteLine("Error in Widget 42");  
// Use this example when tracing.  
System.Diagnostics.Trace.WriteLine("Error in Widget 42");  
```  
  
 <span data-ttu-id="4f9e6-127">La depuración y el seguimiento comparten la misma colección **Listeners**, por lo que si se agrega un objeto de escucha a una colección de **Debug.Listeners** en la aplicación, se agrega también a la colección **Trace.Listeners**.</span><span class="sxs-lookup"><span data-stu-id="4f9e6-127">Debug and trace share the same **Listeners** collection, so if you add a listener object to a **Debug.Listeners** collection in your application, it gets added to the **Trace.Listeners** collection as well.</span></span>  
  
 <span data-ttu-id="4f9e6-128">En el siguiente ejemplo se indica cómo utilizar un agente de escucha para enviar información de seguimiento a una consola:</span><span class="sxs-lookup"><span data-stu-id="4f9e6-128">The following example shows how to use a listener to send tracing information to a console:</span></span>  
  
```vb  
Trace.Listeners.Clear()  
Trace.Listeners.Add(New TextWriterTraceListener(Console.Out))  
```  
  
```csharp  
System.Diagnostics.Trace.Listeners.Clear();  
System.Diagnostics.Trace.Listeners.Add(  
   new System.Diagnostics.TextWriterTraceListener(Console.Out));  
```  
  
## <a name="developer-defined-listeners"></a><span data-ttu-id="4f9e6-129">Agentes de escucha definidos por el desarrollador</span><span class="sxs-lookup"><span data-stu-id="4f9e6-129">Developer-Defined Listeners</span></span>  
 <span data-ttu-id="4f9e6-130">Puede definir sus propios agentes de escucha heredándolos de la clase base **TraceListener** y reemplazando los métodos de esa clase por métodos personalizados.</span><span class="sxs-lookup"><span data-stu-id="4f9e6-130">You can define your own listeners by inheriting from the **TraceListener** base class and overriding its methods with your customized methods.</span></span> <span data-ttu-id="4f9e6-131">Para obtener más información sobre cómo crear agentes de escucha definidos por el desarrollador, consulte <xref:System.Diagnostics.TraceListener> en la documentación de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4f9e6-131">For more information on creating developer-defined listeners, see <xref:System.Diagnostics.TraceListener> in the .NET Framework reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f9e6-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4f9e6-132">See also</span></span>

- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="4f9e6-133">Traza e instrumentación de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="4f9e6-133">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)
- [<span data-ttu-id="4f9e6-134">Modificadores de seguimiento</span><span class="sxs-lookup"><span data-stu-id="4f9e6-134">Trace Switches</span></span>](trace-switches.md)

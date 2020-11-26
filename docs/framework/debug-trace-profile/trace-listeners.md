---
title: Agentes de escucha de seguimiento
description: Explore los agentes de escucha de seguimiento, que son un mecanismo para recopilar y registrar los mensajes de seguimiento enviados en .NET. Un agente de escucha recopila, almacena y enruta los mensajes.
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
ms.openlocfilehash: 8cd79d21d66d23f834b7ef0012d8360884028ac6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238124"
---
# <a name="trace-listeners"></a><span data-ttu-id="a5e43-104">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="a5e43-104">Trace Listeners</span></span>

<span data-ttu-id="a5e43-105">Al usar **Trace**, **Debug** y <xref:System.Diagnostics.TraceSource>, debe disponer de un mecanismo para recopilar y grabar los mensajes que se envíen.</span><span class="sxs-lookup"><span data-stu-id="a5e43-105">When using **Trace**, **Debug** and <xref:System.Diagnostics.TraceSource>, you must have a mechanism for collecting and recording the messages that are sent.</span></span> <span data-ttu-id="a5e43-106">Los *agentes de escucha* reciben los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a5e43-106">Trace messages are received by *listeners*.</span></span> <span data-ttu-id="a5e43-107">Un agente de escucha se encarga de recopilar, almacenar y enrutar los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a5e43-107">The purpose of a listener is to collect, store, and route tracing messages.</span></span> <span data-ttu-id="a5e43-108">Los agentes de escucha dirigen los resultados del seguimiento a un destino apropiado, como un registro, una ventana o un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="a5e43-108">Listeners direct the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
 <span data-ttu-id="a5e43-109">Los agentes de escucha están disponibles para las clases **Debug**, **Trace** y <xref:System.Diagnostics.TraceSource>, cada una de las cuales puede enviar sus resultados a una variedad de objetos de escucha.</span><span class="sxs-lookup"><span data-stu-id="a5e43-109">Listeners are available to the **Debug**, **Trace**, and <xref:System.Diagnostics.TraceSource> classes, each of which can send its output to a variety of listener objects.</span></span> <span data-ttu-id="a5e43-110">A continuación se indican los agentes de escucha predefinidos más usados:</span><span class="sxs-lookup"><span data-stu-id="a5e43-110">The following are the commonly used predefined listeners:</span></span>  
  
- <span data-ttu-id="a5e43-111">Un <xref:System.Diagnostics.TextWriterTraceListener> redirige los resultados a una instancia de la clase <xref:System.IO.TextWriter> o a cualquier cosa que sea una clase <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="a5e43-111">A <xref:System.Diagnostics.TextWriterTraceListener> redirects output to an instance of the <xref:System.IO.TextWriter> class or to anything that is a <xref:System.IO.Stream> class.</span></span> <span data-ttu-id="a5e43-112">También puede escribir en la consola o en un archivo, ya que ambos son clases <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="a5e43-112">It can also write to the console or to a file, because these are <xref:System.IO.Stream> classes.</span></span>  
  
- <span data-ttu-id="a5e43-113">Un <xref:System.Diagnostics.EventLogTraceListener> redirige los resultados a un registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="a5e43-113">An <xref:System.Diagnostics.EventLogTraceListener> redirects output to an event log.</span></span>  
  
- <span data-ttu-id="a5e43-114">Un <xref:System.Diagnostics.DefaultTraceListener> emite mensajes **Write** y **WriteLine** a **OutputDebugString** y al método **Debugger.Log**.</span><span class="sxs-lookup"><span data-stu-id="a5e43-114">A <xref:System.Diagnostics.DefaultTraceListener> emits **Write** and **WriteLine** messages to the **OutputDebugString** and to the **Debugger.Log** method.</span></span> <span data-ttu-id="a5e43-115">En Visual Studio, esto hace que los mensajes de depuración aparezcan en la ventana Resultados.</span><span class="sxs-lookup"><span data-stu-id="a5e43-115">In Visual Studio, this causes the debugging messages to appear in the Output window.</span></span> <span data-ttu-id="a5e43-116">También se envían mensajes **Fail** y **Assert** a la API de Windows **OutputDebugString** y al método **Debugger.Log**, y también hacen que se muestre un cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="a5e43-116">**Fail** and failed **Assert** messages also emit to the **OutputDebugString** Windows API and the **Debugger.Log** method, and also cause a message box to be displayed.</span></span> <span data-ttu-id="a5e43-117">Este comportamiento es el predeterminado de los mensajes **Debug** y **Trace**, porque **DefaultTraceListener** se incluye automáticamente en cada colección de `Listeners` y es el único agente de escucha que se incluye automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a5e43-117">This behavior is the default behavior for **Debug** and **Trace** messages, because **DefaultTraceListener** is automatically included in every `Listeners` collection and is the only listener automatically included.</span></span>  
  
- <span data-ttu-id="a5e43-118">Un <xref:System.Diagnostics.ConsoleTraceListener> dirige los resultados del seguimiento o de la depuración a los resultados estándar o al flujo de error estándar.</span><span class="sxs-lookup"><span data-stu-id="a5e43-118">A <xref:System.Diagnostics.ConsoleTraceListener> directs tracing or debugging output to either the standard output or the standard error stream.</span></span>  
  
- <span data-ttu-id="a5e43-119">Un <xref:System.Diagnostics.DelimitedListTraceListener> dirige los resultados del seguimiento o de la depuración a un escritor de texto, como un escritor de secuencias, o a una secuencia, como una secuencia de archivo.</span><span class="sxs-lookup"><span data-stu-id="a5e43-119">A <xref:System.Diagnostics.DelimitedListTraceListener> directs tracing or debugging output to a text writer, such as a stream writer, or to a stream, such as a file stream.</span></span> <span data-ttu-id="a5e43-120">La salida del seguimiento se encuentra en un formato de texto delimitado que usa el delimitador especificado por la <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="a5e43-120">The trace output is in a delimited text format that uses the delimiter specified by the <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> property.</span></span>  
  
- <span data-ttu-id="a5e43-121">Un <xref:System.Diagnostics.XmlWriterTraceListener> dirige los resultados del seguimiento o de la depuración como datos codificados en XML a un <xref:System.IO.TextWriter> o a un <xref:System.IO.Stream>, como un <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="a5e43-121">An <xref:System.Diagnostics.XmlWriterTraceListener> directs tracing or debugging output as XML-encoded data to a <xref:System.IO.TextWriter> or to a <xref:System.IO.Stream>, such as a <xref:System.IO.FileStream>.</span></span>  
  
 <span data-ttu-id="a5e43-122">Si quiere que algún agente de escucha además del <xref:System.Diagnostics.DefaultTraceListener> reciba los resultados de **Debug**, **Trace** y <xref:System.Diagnostics.TraceSource>, debe agregarlo a la colección de `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="a5e43-122">If you want any listener besides the <xref:System.Diagnostics.DefaultTraceListener> to receive **Debug**, **Trace** and <xref:System.Diagnostics.TraceSource> output, you must add it to the `Listeners` collection.</span></span> <span data-ttu-id="a5e43-123">Para más información, vea [Cómo: Crear e inicializar agentes de escucha de seguimiento](how-to-create-and-initialize-trace-listeners.md) y [Cómo: Utilizar TraceSource y filtros con agentes de escucha de seguimiento](how-to-use-tracesource-and-filters-with-trace-listeners.md).</span><span class="sxs-lookup"><span data-stu-id="a5e43-123">For more information, see [How to: Create and Initialize Trace Listeners](how-to-create-and-initialize-trace-listeners.md) and [How to: Use TraceSource and Filters with Trace Listeners](how-to-use-tracesource-and-filters-with-trace-listeners.md).</span></span> <span data-ttu-id="a5e43-124">Todos los agentes de escucha de la colección **Listeners** reciben los mismos mensajes de los métodos de resultados de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a5e43-124">Any listener in the **Listeners** collection gets the same messages from the trace output methods.</span></span> <span data-ttu-id="a5e43-125">Por ejemplo, supongamos que configura dos agentes de escucha: **TextWriterTraceListener** y **EventLogTraceListener**.</span><span class="sxs-lookup"><span data-stu-id="a5e43-125">For example, suppose you set up two listeners: a **TextWriterTraceListener** and an **EventLogTraceListener**.</span></span> <span data-ttu-id="a5e43-126">Cada agente de escucha recibe el mismo mensaje.</span><span class="sxs-lookup"><span data-stu-id="a5e43-126">Each listener receives the same message.</span></span> <span data-ttu-id="a5e43-127">**TextWriterTraceListener** dirigiría sus resultados a una secuencia y **EventLogTraceListener** dirigiría los suyos a un registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="a5e43-127">The **TextWriterTraceListener** would direct its output to a stream, and the **EventLogTraceListener** would direct its output to an event log.</span></span>  
  
 <span data-ttu-id="a5e43-128">En el siguiente ejemplo se muestra cómo enviar resultados a la colección **Listeners**.</span><span class="sxs-lookup"><span data-stu-id="a5e43-128">The following example shows how to send output to the **Listeners** collection.</span></span>  
  
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
  
 <span data-ttu-id="a5e43-129">La depuración y el seguimiento comparten la misma colección **Listeners**, por lo que si se agrega un objeto de escucha a una colección de **Debug.Listeners** en la aplicación, se agrega también a la colección **Trace.Listeners**.</span><span class="sxs-lookup"><span data-stu-id="a5e43-129">Debug and trace share the same **Listeners** collection, so if you add a listener object to a **Debug.Listeners** collection in your application, it gets added to the **Trace.Listeners** collection as well.</span></span>  
  
 <span data-ttu-id="a5e43-130">En el siguiente ejemplo se indica cómo utilizar un agente de escucha para enviar información de seguimiento a una consola:</span><span class="sxs-lookup"><span data-stu-id="a5e43-130">The following example shows how to use a listener to send tracing information to a console:</span></span>  
  
```vb  
Trace.Listeners.Clear()  
Trace.Listeners.Add(New TextWriterTraceListener(Console.Out))  
```  
  
```csharp  
System.Diagnostics.Trace.Listeners.Clear();  
System.Diagnostics.Trace.Listeners.Add(  
   new System.Diagnostics.TextWriterTraceListener(Console.Out));  
```  
  
## <a name="developer-defined-listeners"></a><span data-ttu-id="a5e43-131">Agentes de escucha definidos por el desarrollador</span><span class="sxs-lookup"><span data-stu-id="a5e43-131">Developer-Defined Listeners</span></span>  

 <span data-ttu-id="a5e43-132">Puede definir sus propios agentes de escucha heredándolos de la clase base **TraceListener** y reemplazando los métodos de esa clase por métodos personalizados.</span><span class="sxs-lookup"><span data-stu-id="a5e43-132">You can define your own listeners by inheriting from the **TraceListener** base class and overriding its methods with your customized methods.</span></span> <span data-ttu-id="a5e43-133">Para obtener más información sobre cómo crear agentes de escucha definidos por el desarrollador, consulte <xref:System.Diagnostics.TraceListener> en la documentación de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a5e43-133">For more information on creating developer-defined listeners, see <xref:System.Diagnostics.TraceListener> in the .NET Framework reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5e43-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5e43-134">See also</span></span>

- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="a5e43-135">Seguimiento e instrumentación de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="a5e43-135">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)
- [<span data-ttu-id="a5e43-136">Modificadores de seguimiento</span><span class="sxs-lookup"><span data-stu-id="a5e43-136">Trace Switches</span></span>](trace-switches.md)

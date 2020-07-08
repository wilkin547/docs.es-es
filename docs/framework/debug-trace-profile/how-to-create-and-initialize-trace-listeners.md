---
title: Procedimiento para crear e inicializar agentes de escucha de seguimiento
description: Aprenda a crear e inicializar agentes de escucha de seguimiento mediante el uso de clases como System. Diagnostics. DefaultTraceListener en .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- initializing trace listeners
- trace listeners, creating
- trace listeners, initializing
- tracing [.NET Framework], trace listeners
- logs, trace listeners
ms.assetid: 21726de1-61ee-4fdc-9dd0-3be49324d066
ms.openlocfilehash: 752306124e41a7fb7458daccc8c2891631eb9616
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051212"
---
# <a name="how-to-create-and-initialize-trace-listeners"></a><span data-ttu-id="0757c-103">Procedimiento para crear e inicializar agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="0757c-103">How to: Create and Initialize Trace Listeners</span></span>

<span data-ttu-id="0757c-104">Las clases <xref:System.Diagnostics.Debug?displayProperty=nameWithType> y <xref:System.Diagnostics.Trace?displayProperty=nameWithType> envían mensajes a objetos denominados agentes de escucha que reciben y procesan estos mensajes.</span><span class="sxs-lookup"><span data-stu-id="0757c-104">The <xref:System.Diagnostics.Debug?displayProperty=nameWithType> and <xref:System.Diagnostics.Trace?displayProperty=nameWithType> classes send messages to objects called listeners that receive and process these messages.</span></span> <span data-ttu-id="0757c-105">Un agente de escucha de este tipo, <xref:System.Diagnostics.DefaultTraceListener?displayProperty=nameWithType>, se crea y se inicializa automáticamente si la traza o la depuración está habilitada.</span><span class="sxs-lookup"><span data-stu-id="0757c-105">One such listener, the <xref:System.Diagnostics.DefaultTraceListener?displayProperty=nameWithType>, is automatically created and initialized when tracing or debugging is enabled.</span></span> <span data-ttu-id="0757c-106">Si desea que los resultados de <xref:System.Diagnostics.Trace> o <xref:System.Diagnostics.Debug> se envíen a otros destinos adicionales, deberá crear e inicializar agentes de escucha adicionales.</span><span class="sxs-lookup"><span data-stu-id="0757c-106">If you want <xref:System.Diagnostics.Trace> or <xref:System.Diagnostics.Debug> output to be directed to any additional sources, you must create and initialize additional trace listeners.</span></span>

<span data-ttu-id="0757c-107">Los agentes de escucha que cree deben reflejar las necesidades de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0757c-107">The listeners you create should reflect your application's needs.</span></span> <span data-ttu-id="0757c-108">Por ejemplo, si desea un registro de texto de todo el resultado de traza, cree un agente de escucha <xref:System.Diagnostics.TextWriterTraceListener>, que escribe todo el resultado en un nuevo archivo de texto cuando se habilita.</span><span class="sxs-lookup"><span data-stu-id="0757c-108">For example, if you want a text record of all trace output, create a <xref:System.Diagnostics.TextWriterTraceListener> listener, which writes all output to a new text file when it is enabled.</span></span> <span data-ttu-id="0757c-109">Por otra parte, si desea ver el resultado solo durante la ejecución de la aplicación, cree un agente de escucha <xref:System.Diagnostics.ConsoleTraceListener>, que envía todo el resultado a una ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="0757c-109">On the other hand, if you want to view output only during application execution, create a <xref:System.Diagnostics.ConsoleTraceListener> listener, which directs all output to a console window.</span></span> <span data-ttu-id="0757c-110"><xref:System.Diagnostics.EventLogTraceListener> puede dirigir el resultado de traza a un registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="0757c-110">The <xref:System.Diagnostics.EventLogTraceListener> can direct trace output to an event log.</span></span> <span data-ttu-id="0757c-111">Para obtener más información, vea [agentes de escucha de seguimiento](trace-listeners.md).</span><span class="sxs-lookup"><span data-stu-id="0757c-111">For more information, see [Trace Listeners](trace-listeners.md).</span></span>

<span data-ttu-id="0757c-112">Puede crear agentes de escucha de seguimiento en un [archivo de configuración de la aplicación](../configure-apps/index.md) o en el código.</span><span class="sxs-lookup"><span data-stu-id="0757c-112">You can create trace listeners in an [application configuration file](../configure-apps/index.md) or in your code.</span></span> <span data-ttu-id="0757c-113">Se recomienda el uso de archivos de configuración de la aplicación, ya que permiten agregar, modificar o quitar agentes de escucha de traza sin necesidad de modificar el código.</span><span class="sxs-lookup"><span data-stu-id="0757c-113">We recommend the use of application configuration files, because they let you add, modify, or remove trace listeners without having to change your code.</span></span>

### <a name="to-create-and-use-a-trace-listener-by-using-a-configuration-file"></a><span data-ttu-id="0757c-114">Para crear y usar un agente de escucha de traza mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="0757c-114">To create and use a trace listener by using a configuration file</span></span>

1. <span data-ttu-id="0757c-115">Declare el agente de escucha de traza en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0757c-115">Declare your trace listener in your application configuration file.</span></span> <span data-ttu-id="0757c-116">Si el agente de escucha que va a crear requiere otros objetos, declárelos también.</span><span class="sxs-lookup"><span data-stu-id="0757c-116">If the listener you are creating requires any other objects, declare them as well.</span></span> <span data-ttu-id="0757c-117">En el ejemplo siguiente, se muestra cómo crear un agente de escucha denominado `myListener` que escribe en el archivo de texto `TextWriterOutput.log`.</span><span class="sxs-lookup"><span data-stu-id="0757c-117">The following example shows how to create a listener called `myListener` that writes to the text file `TextWriterOutput.log`.</span></span>

    ```xml
    <configuration>
      <system.diagnostics>
        <trace autoflush="false" indentsize="4">
          <listeners>
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener" initializeData="TextWriterOutput.log" />
            <remove name="Default" />
          </listeners>
        </trace>
      </system.diagnostics>
    </configuration>
    ```

2. <span data-ttu-id="0757c-118">Utilice la clase <xref:System.Diagnostics.Trace> en el código para escribir un mensaje a los agentes de escucha de traza. </span><span class="sxs-lookup"><span data-stu-id="0757c-118">Use the <xref:System.Diagnostics.Trace> class in your code to write a message to the trace listeners.</span></span>

    ```vb
    Trace.TraceInformation("Test message.")
    ' You must close or flush the trace to empty the output buffer.
    Trace.Flush()
    ```

    ```csharp
    Trace.TraceInformation("Test message.");
    // You must close or flush the trace to empty the output buffer.
    Trace.Flush();
    ```

### <a name="to-create-and-use-a-trace-listener-in-code"></a><span data-ttu-id="0757c-119">Crear y utilizar un agente de escucha de traza en el código</span><span class="sxs-lookup"><span data-stu-id="0757c-119">To create and use a trace listener in code</span></span>

- <span data-ttu-id="0757c-120">Agregue el agente de escucha de traza a la colección <xref:System.Diagnostics.Trace.Listeners%2A> y envíe información de traza a los agentes de escucha.</span><span class="sxs-lookup"><span data-stu-id="0757c-120">Add the trace listener to the <xref:System.Diagnostics.Trace.Listeners%2A> collection and send trace information to the listeners.</span></span>

    ```vb
    Trace.Listeners.Add(New TextWriterTraceListener("TextWriterOutput.log", "myListener"))
    Trace.TraceInformation("Test message.")
    ' You must close or flush the trace to empty the output buffer.
    Trace.Flush()
    ```

    ```csharp
    Trace.Listeners.Add(new TextWriterTraceListener("TextWriterOutput.log", "myListener"));
    Trace.TraceInformation("Test message.");
    // You must close or flush the trace to empty the output buffer.
    Trace.Flush();
    ```

    <span data-ttu-id="0757c-121">\- o -</span><span class="sxs-lookup"><span data-stu-id="0757c-121">\- or -</span></span>

- <span data-ttu-id="0757c-122">Si no desea que el agente de escucha reciba el resultado de la traza, no lo agregue a la colección <xref:System.Diagnostics.Trace.Listeners%2A>.</span><span class="sxs-lookup"><span data-stu-id="0757c-122">If you do not want your listener to receive trace output, do not add it to the <xref:System.Diagnostics.Trace.Listeners%2A> collection.</span></span> <span data-ttu-id="0757c-123">Puede emitir la salida a través de un agente de escucha independientemente de la colección <xref:System.Diagnostics.Trace.Listeners%2A>, llamando a los propios métodos de salida del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="0757c-123">You can emit output through a listener independent of the <xref:System.Diagnostics.Trace.Listeners%2A> collection by calling the listener's own output methods.</span></span> <span data-ttu-id="0757c-124">El siguiente ejemplo muestra cómo escribir una línea a un agente de escucha que no se encuentra en la colección <xref:System.Diagnostics.Trace.Listeners%2A>: </span><span class="sxs-lookup"><span data-stu-id="0757c-124">The following example shows how to write a line to a listener that is not in the <xref:System.Diagnostics.Trace.Listeners%2A> collection.</span></span>

    ```vb
    Dim myListener As New TextWriterTraceListener("TextWriterOutput.log", "myListener")
    myListener.WriteLine("Test message.")
    ' You must close or flush the trace listener to empty the output buffer.
    myListener.Flush()
    ```

    ```csharp
    TextWriterTraceListener myListener = new TextWriterTraceListener("TextWriterOutput.log", "myListener");
    myListener.WriteLine("Test message.");
    // You must close or flush the trace listener to empty the output buffer.
    myListener.Flush();
    ```

## <a name="see-also"></a><span data-ttu-id="0757c-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="0757c-125">See also</span></span>

- [<span data-ttu-id="0757c-126">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="0757c-126">Trace Listeners</span></span>](trace-listeners.md)
- [<span data-ttu-id="0757c-127">Modificadores de seguimiento</span><span class="sxs-lookup"><span data-stu-id="0757c-127">Trace Switches</span></span>](trace-switches.md)
- [<span data-ttu-id="0757c-128">Procedimiento para agregar instrucciones de seguimiento al código de una aplicación</span><span class="sxs-lookup"><span data-stu-id="0757c-128">How to: Add Trace Statements to Application Code</span></span>](how-to-add-trace-statements-to-application-code.md)
- [<span data-ttu-id="0757c-129">Seguimiento e instrumentación de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="0757c-129">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)

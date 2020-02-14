---
title: 'Cómo: Crear e inicializar agentes de escucha de seguimiento'
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
ms.openlocfilehash: ce0df0af32d6798c89c8db6761d18febc1c398bb
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217443"
---
# <a name="how-to-create-and-initialize-trace-listeners"></a><span data-ttu-id="e4d07-102">Cómo: Crear e inicializar agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="e4d07-102">How to: Create and Initialize Trace Listeners</span></span>

<span data-ttu-id="e4d07-103">Las clases <xref:System.Diagnostics.Debug?displayProperty=nameWithType> y <xref:System.Diagnostics.Trace?displayProperty=nameWithType> envían mensajes a objetos denominados agentes de escucha que reciben y procesan estos mensajes.</span><span class="sxs-lookup"><span data-stu-id="e4d07-103">The <xref:System.Diagnostics.Debug?displayProperty=nameWithType> and <xref:System.Diagnostics.Trace?displayProperty=nameWithType> classes send messages to objects called listeners that receive and process these messages.</span></span> <span data-ttu-id="e4d07-104">Un agente de escucha de este tipo, <xref:System.Diagnostics.DefaultTraceListener?displayProperty=nameWithType>, se crea y se inicializa automáticamente si la traza o la depuración está habilitada.</span><span class="sxs-lookup"><span data-stu-id="e4d07-104">One such listener, the <xref:System.Diagnostics.DefaultTraceListener?displayProperty=nameWithType>, is automatically created and initialized when tracing or debugging is enabled.</span></span> <span data-ttu-id="e4d07-105">Si desea que los resultados de <xref:System.Diagnostics.Trace> o <xref:System.Diagnostics.Debug> se envíen a otros destinos adicionales, deberá crear e inicializar agentes de escucha adicionales.</span><span class="sxs-lookup"><span data-stu-id="e4d07-105">If you want <xref:System.Diagnostics.Trace> or <xref:System.Diagnostics.Debug> output to be directed to any additional sources, you must create and initialize additional trace listeners.</span></span>

<span data-ttu-id="e4d07-106">Los agentes de escucha que cree deben reflejar las necesidades de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4d07-106">The listeners you create should reflect your application's needs.</span></span> <span data-ttu-id="e4d07-107">Por ejemplo, si desea un registro de texto de todo el resultado de traza, cree un agente de escucha <xref:System.Diagnostics.TextWriterTraceListener>, que escribe todo el resultado en un nuevo archivo de texto cuando se habilita.</span><span class="sxs-lookup"><span data-stu-id="e4d07-107">For example, if you want a text record of all trace output, create a <xref:System.Diagnostics.TextWriterTraceListener> listener, which writes all output to a new text file when it is enabled.</span></span> <span data-ttu-id="e4d07-108">Por otra parte, si desea ver el resultado solo durante la ejecución de la aplicación, cree un agente de escucha <xref:System.Diagnostics.ConsoleTraceListener>, que envía todo el resultado a una ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="e4d07-108">On the other hand, if you want to view output only during application execution, create a <xref:System.Diagnostics.ConsoleTraceListener> listener, which directs all output to a console window.</span></span> <span data-ttu-id="e4d07-109"><xref:System.Diagnostics.EventLogTraceListener> puede dirigir el resultado de traza a un registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="e4d07-109">The <xref:System.Diagnostics.EventLogTraceListener> can direct trace output to an event log.</span></span> <span data-ttu-id="e4d07-110">Para más información, vea [Agentes de escucha de seguimiento](trace-listeners.md).</span><span class="sxs-lookup"><span data-stu-id="e4d07-110">For more information, see [Trace Listeners](trace-listeners.md).</span></span>

<span data-ttu-id="e4d07-111">Puede crear agentes de escucha de seguimiento en un [archivo de configuración de la aplicación](../configure-apps/index.md) o en el código.</span><span class="sxs-lookup"><span data-stu-id="e4d07-111">You can create trace listeners in an [application configuration file](../configure-apps/index.md) or in your code.</span></span> <span data-ttu-id="e4d07-112">Se recomienda el uso de archivos de configuración de la aplicación, ya que permiten agregar, modificar o quitar agentes de escucha de traza sin necesidad de modificar el código.</span><span class="sxs-lookup"><span data-stu-id="e4d07-112">We recommend the use of application configuration files, because they let you add, modify, or remove trace listeners without having to change your code.</span></span>

### <a name="to-create-and-use-a-trace-listener-by-using-a-configuration-file"></a><span data-ttu-id="e4d07-113">Para crear y usar un agente de escucha de traza mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="e4d07-113">To create and use a trace listener by using a configuration file</span></span>

1. <span data-ttu-id="e4d07-114">Declare el agente de escucha de traza en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4d07-114">Declare your trace listener in your application configuration file.</span></span> <span data-ttu-id="e4d07-115">Si el agente de escucha que va a crear requiere otros objetos, declárelos también.</span><span class="sxs-lookup"><span data-stu-id="e4d07-115">If the listener you are creating requires any other objects, declare them as well.</span></span> <span data-ttu-id="e4d07-116">En el ejemplo siguiente, se muestra cómo crear un agente de escucha denominado `myListener` que escribe en el archivo de texto `TextWriterOutput.log`.</span><span class="sxs-lookup"><span data-stu-id="e4d07-116">The following example shows how to create a listener called `myListener` that writes to the text file `TextWriterOutput.log`.</span></span>

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

2. <span data-ttu-id="e4d07-117">Utilice la clase <xref:System.Diagnostics.Trace> en el código para escribir un mensaje a los agentes de escucha de traza.</span><span class="sxs-lookup"><span data-stu-id="e4d07-117">Use the <xref:System.Diagnostics.Trace> class in your code to write a message to the trace listeners.</span></span>

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

### <a name="to-create-and-use-a-trace-listener-in-code"></a><span data-ttu-id="e4d07-118">Crear y utilizar un agente de escucha de traza en el código</span><span class="sxs-lookup"><span data-stu-id="e4d07-118">To create and use a trace listener in code</span></span>

- <span data-ttu-id="e4d07-119">Agregue el agente de escucha de traza a la colección <xref:System.Diagnostics.Trace.Listeners%2A> y envíe información de traza a los agentes de escucha.</span><span class="sxs-lookup"><span data-stu-id="e4d07-119">Add the trace listener to the <xref:System.Diagnostics.Trace.Listeners%2A> collection and send trace information to the listeners.</span></span>

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

    <span data-ttu-id="e4d07-120">\- O bien</span><span class="sxs-lookup"><span data-stu-id="e4d07-120">\- or -</span></span>

- <span data-ttu-id="e4d07-121">Si no desea que el agente de escucha reciba el resultado de la traza, no lo agregue a la colección <xref:System.Diagnostics.Trace.Listeners%2A>.</span><span class="sxs-lookup"><span data-stu-id="e4d07-121">If you do not want your listener to receive trace output, do not add it to the <xref:System.Diagnostics.Trace.Listeners%2A> collection.</span></span> <span data-ttu-id="e4d07-122">Puede emitir la salida a través de un agente de escucha independientemente de la colección <xref:System.Diagnostics.Trace.Listeners%2A>, llamando a los propios métodos de salida del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="e4d07-122">You can emit output through a listener independent of the <xref:System.Diagnostics.Trace.Listeners%2A> collection by calling the listener's own output methods.</span></span> <span data-ttu-id="e4d07-123">El siguiente ejemplo muestra cómo escribir una línea a un agente de escucha que no se encuentra en la colección <xref:System.Diagnostics.Trace.Listeners%2A>:</span><span class="sxs-lookup"><span data-stu-id="e4d07-123">The following example shows how to write a line to a listener that is not in the <xref:System.Diagnostics.Trace.Listeners%2A> collection.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e4d07-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e4d07-124">See also</span></span>

- [<span data-ttu-id="e4d07-125">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="e4d07-125">Trace Listeners</span></span>](trace-listeners.md)
- [<span data-ttu-id="e4d07-126">Modificadores de seguimiento</span><span class="sxs-lookup"><span data-stu-id="e4d07-126">Trace Switches</span></span>](trace-switches.md)
- [<span data-ttu-id="e4d07-127">Adición de instrucciones de seguimiento al código de la aplicación</span><span class="sxs-lookup"><span data-stu-id="e4d07-127">How to: Add Trace Statements to Application Code</span></span>](how-to-add-trace-statements-to-application-code.md)
- [<span data-ttu-id="e4d07-128">Traza e instrumentación de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="e4d07-128">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)

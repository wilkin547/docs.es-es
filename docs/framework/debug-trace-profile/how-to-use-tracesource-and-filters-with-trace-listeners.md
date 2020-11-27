---
title: Procedimiento para usar TraceSource y filtros con agentes de escucha de seguimiento
description: Utilice la clase TraceSource y filtros con agentes de escucha de seguimiento en .NET. TraceSource reemplaza los métodos estáticos de las clases anteriores de seguimiento y de depuración.
ms.date: 03/30/2017
helpviewer_keywords:
- initializing trace listeners
- configuration files [.NET Framework], trace listeners
- app.config files, trace listeners
- levels of writing trace messages
- trace listeners, TraceSource class
- application configuration files, trace listeners
- filters, trace listeners
- TraceSource class, trace listeners
- trace listeners, creating
- trace listeners, filters
- trace listeners, initializing
ms.assetid: 21dc2169-947d-453a-b0e2-3dac3ba0cc9f
ms.openlocfilehash: 94af872e0417941f17c043710688c7b723cd4004
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272805"
---
# <a name="how-to-use-tracesource-and-filters-with-trace-listeners"></a><span data-ttu-id="63f22-104">Procedimiento para usar TraceSource y filtros con agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="63f22-104">How to: Use TraceSource and Filters with Trace Listeners</span></span>

<span data-ttu-id="63f22-105">Una de las nuevas características de la versión 2.0 de .NET Framework es un sistema de seguimiento mejorado.</span><span class="sxs-lookup"><span data-stu-id="63f22-105">One of the new features in the .NET Framework version 2.0 is an enhanced tracing system.</span></span> <span data-ttu-id="63f22-106">La idea básica no se ha modificado: se envían mensajes de seguimiento a través de conmutadores a agentes de escucha, que notifican los datos a un medio de salida asociado.</span><span class="sxs-lookup"><span data-stu-id="63f22-106">The basic premise is unchanged: tracing messages are sent through switches to listeners, which report the data to an associated output medium.</span></span> <span data-ttu-id="63f22-107">Una diferencia principal de la versión 2.0 es que los seguimientos se pueden iniciar a través de instancias de la clase <xref:System.Diagnostics.TraceSource>.</span><span class="sxs-lookup"><span data-stu-id="63f22-107">A primary difference for version 2.0 is that traces can be initiated through instances of the <xref:System.Diagnostics.TraceSource> class.</span></span> <span data-ttu-id="63f22-108"><xref:System.Diagnostics.TraceSource> está pensada para funcionar como un sistema de seguimiento mejorado y se puede usar en lugar de los métodos estáticos de las clases anteriores de seguimiento <xref:System.Diagnostics.Trace> y <xref:System.Diagnostics.Debug>.</span><span class="sxs-lookup"><span data-stu-id="63f22-108"><xref:System.Diagnostics.TraceSource> is intended to function as an enhanced tracing system and can be used in place of the static methods of the older <xref:System.Diagnostics.Trace> and <xref:System.Diagnostics.Debug> tracing classes.</span></span> <span data-ttu-id="63f22-109">Las clases <xref:System.Diagnostics.Trace> y <xref:System.Diagnostics.Debug> conocidas siguen existiendo, pero la práctica recomendada es usar la clase <xref:System.Diagnostics.TraceSource> para realizar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="63f22-109">The familiar <xref:System.Diagnostics.Trace> and <xref:System.Diagnostics.Debug> classes still exist, but the recommended practice is to use the <xref:System.Diagnostics.TraceSource> class for tracing.</span></span>  
  
 <span data-ttu-id="63f22-110">En este tema se describe el uso de <xref:System.Diagnostics.TraceSource> junto con un archivo de configuración de aplicación.</span><span class="sxs-lookup"><span data-stu-id="63f22-110">This topic describes the use of a <xref:System.Diagnostics.TraceSource> coupled with an application configuration file.</span></span>  <span data-ttu-id="63f22-111">Es posible, aunque no aconsejable, realizar el seguimiento mediante <xref:System.Diagnostics.TraceSource> sin el uso de un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="63f22-111">It is possible, although not recommended, to trace using a <xref:System.Diagnostics.TraceSource> without the use of a configuration file.</span></span> <span data-ttu-id="63f22-112">Para obtener información sobre el seguimiento sin un archivo de configuración, vea [Cómo: Crear e inicializar orígenes de seguimiento](how-to-create-and-initialize-trace-sources.md).</span><span class="sxs-lookup"><span data-stu-id="63f22-112">For information on tracing without a configuration file, see [How to: Create and Initialize Trace Sources](how-to-create-and-initialize-trace-sources.md).</span></span>  
  
### <a name="to-create-and-initialize-your-trace-source"></a><span data-ttu-id="63f22-113">Para crear e inicializar el origen de seguimiento</span><span class="sxs-lookup"><span data-stu-id="63f22-113">To create and initialize your trace source</span></span>  
  
1. <span data-ttu-id="63f22-114">El primer paso para instrumentar una aplicación con el seguimiento es crear un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="63f22-114">The first step to instrumenting an application with tracing is to create a trace source.</span></span> <span data-ttu-id="63f22-115">En proyectos grandes con diversos componentes, puede crear un origen de seguimiento independiente para cada componente.</span><span class="sxs-lookup"><span data-stu-id="63f22-115">In large projects with various components, you can create a separate trace source for each component.</span></span> <span data-ttu-id="63f22-116">La práctica recomendada es usar el nombre de la aplicación para el nombre del origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="63f22-116">The recommended practice is to use the application name for the trace source name.</span></span> <span data-ttu-id="63f22-117">Así resultará más fácil separar los distintos seguimientos.</span><span class="sxs-lookup"><span data-stu-id="63f22-117">This will make it easier to keep the different traces separate.</span></span> <span data-ttu-id="63f22-118">En el código siguiente se crea un nuevo origen de seguimiento (`mySource)`) y se llama a un método (`Activity1`) que realiza el seguimiento de eventos.</span><span class="sxs-lookup"><span data-stu-id="63f22-118">The following code creates a new trace source (`mySource)` and calls a method (`Activity1`) that traces events.</span></span>  <span data-ttu-id="63f22-119">El agente de escucha de seguimiento predeterminado escribe los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="63f22-119">The trace messages are written by the default trace listener.</span></span>  
  
    ```csharp
    using System;  
    using System.Diagnostics;  
    using System.Threading;  
  
    namespace TraceSourceApp  
    {  
        class Program  
        {  
            private static TraceSource mySource =
                new TraceSource("TraceSourceApp");  
            static void Main(string[] args)  
            {  
                Activity1();  
                mySource.Close();  
                return;  
            }  
            static void Activity1()  
            {  
                mySource.TraceEvent(TraceEventType.Error, 1,
                    "Error message.");  
                mySource.TraceEvent(TraceEventType.Warning, 2,
                    "Warning message.");  
            }  
        }  
    }  
    ```  
  
### <a name="to-create-and-initialize-trace-listeners-and-filters"></a><span data-ttu-id="63f22-120">Para crear e inicializar agentes de escucha de seguimiento y filtros</span><span class="sxs-lookup"><span data-stu-id="63f22-120">To create and initialize trace listeners and filters</span></span>  
  
1. <span data-ttu-id="63f22-121">El código en el primer procedimiento no identifica mediante programación ningún agente de escucha de seguimiento ni ningún filtro.</span><span class="sxs-lookup"><span data-stu-id="63f22-121">The code in the first procedure does not programmatically identify any trace listeners or filters.</span></span> <span data-ttu-id="63f22-122">El resultado del código es que los mensajes de seguimiento se escriben en el agente de escucha de seguimiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="63f22-122">The code alone results in the trace messages being written to the default trace listener.</span></span> <span data-ttu-id="63f22-123">Para configurar agentes de escucha de seguimiento específicos y sus filtros asociados, edite el archivo de configuración que se corresponde con el nombre de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="63f22-123">To configure specific trace listeners and their associated filters, edit the configuration file that corresponds to the name of your application.</span></span> <span data-ttu-id="63f22-124">En este archivo, puede agregar o quitar un agente de escucha, establecer las propiedades y el filtro para un agente de escucha o quitar agentes de escucha.</span><span class="sxs-lookup"><span data-stu-id="63f22-124">In this file, you can add or remove a listener, set the properties and filter for a listener, or remove listeners.</span></span> <span data-ttu-id="63f22-125">En el siguiente archivo de configuración de ejemplo se muestra cómo inicializar un agente de escucha de seguimiento de consola y un agente de escucha de seguimiento de escritor de texto para el origen de seguimiento creado en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="63f22-125">The following configuration file example shows how to initialize a console trace listener and a text writer trace listener for the trace source that is created in the preceding procedure.</span></span> <span data-ttu-id="63f22-126">Además de configurar los agentes de escucha de seguimiento, el archivo de configuración crea filtros para ambos agentes de escucha y un modificador de origen para el origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="63f22-126">In addition to configuring the trace listeners, the configuration file creates filters for both of the listeners and creates a source switch for the trace source.</span></span> <span data-ttu-id="63f22-127">Para agregar agentes de escucha de traza se muestran dos técnicas: agregar directamente el agente de escucha al origen de traza y agregar un agente de escucha a la colección de agentes compartidos y después agregarlo por su nombre al origen de traza.</span><span class="sxs-lookup"><span data-stu-id="63f22-127">Two techniques are shown for adding trace listeners: adding the listener directly to the trace source and adding a listener to the shared listeners collection and then adding it by name to the trace source.</span></span> <span data-ttu-id="63f22-128">Los filtros identificados para los dos agentes de escucha se inicializan con niveles de origen diferentes.</span><span class="sxs-lookup"><span data-stu-id="63f22-128">The filters identified for the two listeners are initialized with different source levels.</span></span> <span data-ttu-id="63f22-129">Esto tiene como resultado que algunos mensajes se escriban mediante solo uno de los dos agentes de escucha.</span><span class="sxs-lookup"><span data-stu-id="63f22-129">This results in some messages being written by only one of the two listeners.</span></span>  
  
    ```xml  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <source name="TraceSourceApp"
            switchName="sourceSwitch"
            switchType="System.Diagnostics.SourceSwitch">  
            <listeners>  
              <add name="console"
                type="System.Diagnostics.ConsoleTraceListener">  
                <filter type="System.Diagnostics.EventTypeFilter"
                  initializeData="Warning"/>  
              </add>  
              <add name="myListener"/>  
              <remove name="Default"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="sourceSwitch" value="Warning"/>  
        </switches>  
        <sharedListeners>  
          <add name="myListener"
            type="System.Diagnostics.TextWriterTraceListener"
            initializeData="myListener.log">  
            <filter type="System.Diagnostics.EventTypeFilter"
              initializeData="Error"/>  
          </add>  
        </sharedListeners>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
### <a name="to-change-the-level-at-which-a-listener-writes-a-trace-message"></a><span data-ttu-id="63f22-130">Para cambiar el nivel en el que un agente de escucha escribe un mensaje de seguimiento</span><span class="sxs-lookup"><span data-stu-id="63f22-130">To change the level at which a listener writes a trace message</span></span>  
  
1. <span data-ttu-id="63f22-131">El archivo de configuración inicializa la configuración para el origen de traza en el momento en que se inicializa la aplicación.</span><span class="sxs-lookup"><span data-stu-id="63f22-131">The configuration file initializes the settings for the trace source at the time the application is initialized.</span></span> <span data-ttu-id="63f22-132">Para cambiar esa configuración, debe cambiar el archivo de configuración y reiniciar la aplicación, o actualizarla mediante programación usando el método <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="63f22-132">To change those settings you must change the configuration file and restart the application or programmatically refresh the application using the <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="63f22-133">La aplicación puede cambiar dinámicamente las propiedades establecidas por el archivo de configuración para reemplazar cualquier configuración especificada por el usuario.</span><span class="sxs-lookup"><span data-stu-id="63f22-133">The application can dynamically change the properties set by the configuration file to override any settings specified by the user.</span></span>  <span data-ttu-id="63f22-134">Por ejemplo, es posible que quiera asegurarse de que los mensajes críticos siempre se envíen a un archivo de texto, independientemente de las opciones de configuración actuales.</span><span class="sxs-lookup"><span data-stu-id="63f22-134">For example, you might want to assure that critical messages are always sent to a text file, regardless of the current configuration settings.</span></span>  
  
    ```csharp
    using System;  
    using System.Diagnostics;  
    using System.Threading;  
  
    namespace TraceSourceApp  
    {  
        class Program  
        {  
            private static TraceSource mySource =
                new TraceSource("TraceSourceApp");  
            static void Main(string[] args)  
            {  
                Activity1();  
  
                // Change the event type for which tracing occurs.  
                // The console trace listener must be specified
                // in the configuration file. First, save the original  
                // settings from the configuration file.  
                EventTypeFilter configFilter =
                    (EventTypeFilter)mySource.Listeners["console"].Filter;  
  
                // Then create a new event type filter that ensures
                // critical messages will be written.  
                mySource.Listeners["console"].Filter =  
                    new EventTypeFilter(SourceLevels.Critical);  
                Activity2();  
  
                // Allow the trace source to send messages to listeners
                // for all event types. This statement will override
                // any settings in the configuration file.  
                mySource.Switch.Level = SourceLevels.All;  
  
                // Restore the original filter settings.  
                mySource.Listeners["console"].Filter = configFilter;  
                Activity3();  
                mySource.Close();  
                return;  
            }  
            static void Activity1()  
            {  
                mySource.TraceEvent(TraceEventType.Error, 1,
                    "Error message.");  
                mySource.TraceEvent(TraceEventType.Warning, 2,
                    "Warning message.");  
            }  
            static void Activity2()  
            {  
                mySource.TraceEvent(TraceEventType.Critical, 3,
                    "Critical message.");  
                mySource.TraceInformation("Informational message.");  
            }  
            static void Activity3()  
            {  
                mySource.TraceEvent(TraceEventType.Error, 4,
                    "Error message.");  
                mySource.TraceInformation("Informational message.");  
            }  
        }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="63f22-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="63f22-135">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventTypeFilter>
- [<span data-ttu-id="63f22-136">Procedimiento para crear e inicializar orígenes de seguimiento</span><span class="sxs-lookup"><span data-stu-id="63f22-136">How to: Create and Initialize Trace Sources</span></span>](how-to-create-and-initialize-trace-sources.md)
- [<span data-ttu-id="63f22-137">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="63f22-137">Trace Listeners</span></span>](trace-listeners.md)

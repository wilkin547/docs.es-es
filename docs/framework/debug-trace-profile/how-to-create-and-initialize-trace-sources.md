---
title: 'Cómo: Crear e inicializar orígenes de seguimiento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- trace sources
- initializing trace sources
- configuration files [.NET Framework], trace sources
ms.assetid: f88dda6f-5fda-45be-9b3c-745a9b708c4d
ms.openlocfilehash: cc2987499aa094960c08d220940fe1aed5440b2d
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449964"
---
# <a name="how-to-create-and-initialize-trace-sources"></a><span data-ttu-id="06e75-102">Cómo: Crear e inicializar orígenes de seguimiento</span><span class="sxs-lookup"><span data-stu-id="06e75-102">How to: Create and Initialize Trace Sources</span></span>
<span data-ttu-id="06e75-103">Las aplicaciones utilizan la clase <xref:System.Diagnostics.TraceSource> para generar seguimientos que pueden asociarse con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="06e75-103">The <xref:System.Diagnostics.TraceSource> class is used by applications to produce traces that can be associated with the application.</span></span> <span data-ttu-id="06e75-104"><xref:System.Diagnostics.TraceSource> proporciona métodos de traza que permiten rastrear fácilmente eventos y datos, así como emitir seguimientos de información.</span><span class="sxs-lookup"><span data-stu-id="06e75-104"><xref:System.Diagnostics.TraceSource> provides tracing methods that allow you to easily trace events, trace data, and issue informational traces.</span></span> <span data-ttu-id="06e75-105">El resultado del seguimiento de <xref:System.Diagnostics.TraceSource> se puede crear e inicializar con o sin archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="06e75-105">Trace output from <xref:System.Diagnostics.TraceSource> can be created and initialized with or without the use of configuration files.</span></span> <span data-ttu-id="06e75-106">En este tema se proporcionan instrucciones para ambas opciones.</span><span class="sxs-lookup"><span data-stu-id="06e75-106">This topic provides instructions for both options.</span></span> <span data-ttu-id="06e75-107">Sin embargo, se recomienda usar archivos de configuración para facilitar la reconfiguración de las trazas generadas por los orígenes de traza en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="06e75-107">However, we recommend that you use configuration files to facilitate the reconfiguration of the traces produced by trace sources at run time.</span></span>  
  
### <a name="to-create-and-initialize-a-trace-source-using-a-configuration-file"></a><span data-ttu-id="06e75-108">Para crear e inicializar un origen de traza mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="06e75-108">To create and initialize a trace source using a configuration file</span></span>  
  
1. <span data-ttu-id="06e75-109">Cree un proyecto de aplicación de consola de Visual Studio (.NET Framework) y reemplace el código proporcionado por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="06e75-109">Create a Visual Studio console application project (.NET Framework) and replace the supplied code with the following code.</span></span> <span data-ttu-id="06e75-110">Este código registra errores y advertencias, y muestra algunos de ellos en la consola y otros en el archivo myListener creado por las entradas del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="06e75-110">This code logs errors and warnings and outputs some of them to the console, and some of them to the myListener file that is created by the entries in the configuration file.</span></span>  
  
     [!code-csharp[TraceSourceExample1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tracesourceexample1/cs/program.cs#1)]
     [!code-vb[TraceSourceExample1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tracesourceexample1/vb/program.vb#1)]  
  
2. <span data-ttu-id="06e75-111">Agregue al proyecto un archivo de configuración de la aplicación (si no hay uno) para inicializar el origen de seguimiento denominado `TraceSourceApp` en el ejemplo de código del paso 1.</span><span class="sxs-lookup"><span data-stu-id="06e75-111">Add an application configuration file, if one is not present, to the project to initialize the trace source named `TraceSourceApp` in the code example in step 1.</span></span>  
  
3. <span data-ttu-id="06e75-112">Reemplace el contenido del archivo de configuración predeterminado con la configuración siguiente para inicializar un agente de escucha de seguimiento de consola y un agente de escucha de seguimiento de escritor de texto para el origen de seguimiento creado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="06e75-112">Replace the default configuration file content with the following settings to initialize a console trace listener and a text writer trace listener for the trace source that was created in step 1.</span></span>  
  
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
                  initializeData="Error"/>  
              </add>  
              <add name="myListener"/>  
              <remove name="Default"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="sourceSwitch" value="Error"/>  
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
  
     <span data-ttu-id="06e75-113">Además de configurar los agentes de escucha de traza, el archivo de configuración crea filtros para ambos agentes de escucha y crea un modificador de origen para el origen de traza.</span><span class="sxs-lookup"><span data-stu-id="06e75-113">In addition to configuring the trace listeners, the configuration file creates filters for both listeners and creates a source switch for the trace source.</span></span> <span data-ttu-id="06e75-114">Para agregar agentes de escucha de traza se muestran dos técnicas: agregar directamente el agente de escucha al origen de traza y agregar un agente de escucha a la colección de agentes compartidos y después agregarlo por su nombre al origen de traza.</span><span class="sxs-lookup"><span data-stu-id="06e75-114">Two techniques are shown for adding trace listeners: adding the listener directly to the trace source and adding a listener to the shared listeners collection and then adding it by name to the trace source.</span></span> <span data-ttu-id="06e75-115">Los filtros identificados para los dos agentes de escucha se inicializan con niveles de origen diferentes.</span><span class="sxs-lookup"><span data-stu-id="06e75-115">The filters identified for the two listeners are initialized with different source levels.</span></span> <span data-ttu-id="06e75-116">Esto tiene como resultado que algunos mensajes se escriban mediante solo uno de los dos agentes de escucha.</span><span class="sxs-lookup"><span data-stu-id="06e75-116">This results in some messages being written by only one of the two listeners.</span></span>  
  
     <span data-ttu-id="06e75-117">El archivo de configuración inicializa la configuración para el origen de traza en el momento en que se inicializa la aplicación.</span><span class="sxs-lookup"><span data-stu-id="06e75-117">The configuration file initializes the settings for the trace source at the time the application is initialized.</span></span> <span data-ttu-id="06e75-118">La aplicación puede cambiar dinámicamente las propiedades establecidas por el archivo de configuración para reemplazar cualquier configuración especificada por el usuario.</span><span class="sxs-lookup"><span data-stu-id="06e75-118">The application can dynamically change the properties set by the configuration file to override any settings specified by the user.</span></span> <span data-ttu-id="06e75-119">Por ejemplo, quizás desee asegurarse de que los mensajes críticos siempre se envíen a un archivo de texto, cualesquiera que sean las opciones de configuración actuales.</span><span class="sxs-lookup"><span data-stu-id="06e75-119">For example, you might want to ensure that critical messages are always sent to a text file, regardless of the current configuration settings.</span></span> <span data-ttu-id="06e75-120">En el ejemplo de código se muestra cómo reemplazar la configuración del archivo de configuración para garantizar que los mensajes críticos se envíen a los agentes de escucha de traza.</span><span class="sxs-lookup"><span data-stu-id="06e75-120">The example code demonstrates how to override configuration file settings to ensure that critical messages are output to the trace listeners.</span></span>  
  
     <span data-ttu-id="06e75-121">Cambiar los ajustes del archivo de configuración mientras la aplicación se está ejecutando no cambia la configuración inicial.</span><span class="sxs-lookup"><span data-stu-id="06e75-121">Changing the configuration file settings while the application is executing does not change the initial settings.</span></span> <span data-ttu-id="06e75-122">Para cambiar la configuración, debe reiniciar la aplicación o actualizar la aplicación mediante programación usando el método <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="06e75-122">To change the settings, you must either restart the application or programmatically refresh the application by using the <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=nameWithType> method.</span></span>  
  
### <a name="to-initialize-trace-sources-listeners-and-filters-without-a-configuration-file"></a><span data-ttu-id="06e75-123">Para inicializar orígenes de traza, agentes de escucha y filtros sin archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="06e75-123">To initialize trace sources, listeners, and filters without a configuration file</span></span>  
  
- <span data-ttu-id="06e75-124">Use el código de ejemplo siguiente para habilitar la traza a través de un origen de traza sin usar un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="06e75-124">Use the following example code to enable tracing through a trace source without using a configuration file.</span></span> <span data-ttu-id="06e75-125">No es un procedimiento recomendado, pero puede haber circunstancias en las que no desee depender de archivos de configuración para garantizar la traza.</span><span class="sxs-lookup"><span data-stu-id="06e75-125">This is not a recommended practice, but there may be circumstances in which you do not want to depend on configuration files to ensure tracing.</span></span>  
  
     [!code-csharp[TraceSourceExample2#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tracesourceexample2/cs/program.cs#1)]
     [!code-vb[TraceSourceExample2#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tracesourceexample2/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="06e75-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="06e75-126">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventTypeFilter>
- [<span data-ttu-id="06e75-127">Traza e instrumentación de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="06e75-127">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)

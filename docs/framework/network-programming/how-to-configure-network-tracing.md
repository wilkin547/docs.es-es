---
title: Procedimiento para configurar el seguimiento de la red
ms.date: 03/30/2017
helpviewer_keywords:
- formatting [.NET Framework], network tracing
- network tracing, configuring
- level attribute
- app.config files, network tracing
- configuration files [.NET Framework], network tracing
- protocol-level trace output
- application configuration files, network tracing
- sockets, trace output
ms.assetid: 5ef9fe4b-8d3d-490e-9259-1d014b2181af
ms.openlocfilehash: cc08faba7edede3dd527b7c05fe47f6408e18a04
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59151559"
---
# <a name="how-to-configure-network-tracing"></a><span data-ttu-id="762b1-102">Procedimiento para configurar el seguimiento de la red</span><span class="sxs-lookup"><span data-stu-id="762b1-102">How to: Configure Network Tracing</span></span>
<span data-ttu-id="762b1-103">El archivo de configuración de la aplicación o equipo contiene la configuración que determina el formato y el contenido del seguimiento de red.</span><span class="sxs-lookup"><span data-stu-id="762b1-103">The application or computer configuration file holds the settings that determine the format and content of network traces.</span></span> <span data-ttu-id="762b1-104">Antes de realizar este procedimiento, asegúrese de que el seguimiento está habilitado.</span><span class="sxs-lookup"><span data-stu-id="762b1-104">Before performing this procedure, be sure tracing is enabled.</span></span> <span data-ttu-id="762b1-105">Para obtener información sobre cómo habilitar el seguimiento de red, vea [Enabling Network Tracing](../../../docs/framework/network-programming/enabling-network-tracing.md) (Habilitar el seguimiento de red).</span><span class="sxs-lookup"><span data-stu-id="762b1-105">For information about enabling tracing, see [Enabling Network Tracing](../../../docs/framework/network-programming/enabling-network-tracing.md).</span></span>  
  
 <span data-ttu-id="762b1-106">El archivo de configuración del equipo, machine.config, se almacena en la carpeta %Windir%\Microsoft.NET\Framework en el directorio donde se instaló Windows.</span><span class="sxs-lookup"><span data-stu-id="762b1-106">The computer configuration file, machine.config, is stored in the %Windir%\Microsoft.NET\Framework folder in the directory where Windows was installed.</span></span> <span data-ttu-id="762b1-107">Hay un archivo machine.config distinto en las carpetas de %Windir%\Microsoft.NET\Framework por cada versión de .NET Framework que haya instalada en el equipo (por ejemplo, C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config o C:\Windows\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config).</span><span class="sxs-lookup"><span data-stu-id="762b1-107">There is a separate machine.config file in the folders under %Windir%\Microsoft.NET\Framework for each version of the .NET Framework installed on the computer (for example, C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config or C:\Windows\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config.).</span></span>  
  
 <span data-ttu-id="762b1-108">Estos valores se pueden crear también en el archivo de configuración de la aplicación, que tiene prioridad sobre el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="762b1-108">These settings can also be made in the configuration file for the application, which has precedence over the computer configuration file.</span></span>  
  
### <a name="to-configure-network-tracing"></a><span data-ttu-id="762b1-109">Para configurar el seguimiento de la red</span><span class="sxs-lookup"><span data-stu-id="762b1-109">To configure network tracing</span></span>  
  
-   <span data-ttu-id="762b1-110">Agregue las siguientes líneas al archivo de configuración correspondiente.</span><span class="sxs-lookup"><span data-stu-id="762b1-110">Add the following lines to the appropriate configuration file.</span></span> <span data-ttu-id="762b1-111">Los valores y las opciones de estos valores se describen en las tablas siguientes.</span><span class="sxs-lookup"><span data-stu-id="762b1-111">The values and options for these settings are described in the tables below.</span></span>  
  
    ```xml  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <source name="System.Net" tracemode="includehex" maxdatasize="1024">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
          <source name="System.Net.Cache">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
          <source name="System.Net.Http">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
          <source name="System.Net.Sockets">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
          <source name="System.Net.WebSockets">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="System.Net" value="Verbose"/>  
          <add name="System.Net.Cache" value="Verbose"/>  
          <add name="System.Net.Http" value="Verbose"/>  
          <add name="System.Net.Sockets" value="Verbose"/>  
          <add name="System.Net.WebSockets" value="Verbose"/>  
        </switches>  
        <sharedListeners>  
          <add name="System.Net"  
            type="System.Diagnostics.TextWriterTraceListener"  
            initializeData="network.log"
            traceOutputOptions="ProcessId, DateTime" 
          />  
        </sharedListeners>  
        <trace autoflush="true"/>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
 <span data-ttu-id="762b1-112">Al agregar un nombre al bloque `<switches>`, el resultado del seguimiento incluye información de algunos métodos relacionados con el nombre.</span><span class="sxs-lookup"><span data-stu-id="762b1-112">When you add a name to the `<switches>` block, the trace output includes information from some methods related to the name.</span></span> <span data-ttu-id="762b1-113">En la siguiente tabla se describe el resultado.</span><span class="sxs-lookup"><span data-stu-id="762b1-113">The following table describes the output.</span></span>  
  
|<span data-ttu-id="762b1-114">nombre</span><span class="sxs-lookup"><span data-stu-id="762b1-114">Name</span></span>|<span data-ttu-id="762b1-115">Resultado de</span><span class="sxs-lookup"><span data-stu-id="762b1-115">Output from</span></span>|  
|----------|-----------------|  
|`System.Net.Sockets`|<span data-ttu-id="762b1-116">Algunos métodos públicos de las clases <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient> y <xref:System.Net.Dns></span><span class="sxs-lookup"><span data-stu-id="762b1-116">Some public methods of the <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient>, and <xref:System.Net.Dns> classes</span></span>|  
|`System.Net`|<span data-ttu-id="762b1-117">Algunos métodos públicos de las clases <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest> y <xref:System.Net.FtpWebResponse>, e información de depuración de SSL (certificados no válidos, lista de emisores que faltan y errores del certificado cliente).</span><span class="sxs-lookup"><span data-stu-id="762b1-117">Some public methods of the <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest>, and <xref:System.Net.FtpWebResponse> classes, and SSL debug information (invalid certificates, missing issuers list, and client certificate errors.)</span></span>|  
|`System.Net.HttpListener`|<span data-ttu-id="762b1-118">Algunos métodos públicos de las clases <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest> y <xref:System.Net.HttpListenerResponse>.</span><span class="sxs-lookup"><span data-stu-id="762b1-118">Some public methods of the <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest>, and <xref:System.Net.HttpListenerResponse> classes.</span></span>|  
|`System.Net.Cache`|<span data-ttu-id="762b1-119">Algunos métodos privados e internos de `System.Net.Cache`.</span><span class="sxs-lookup"><span data-stu-id="762b1-119">Some private and internal methods in `System.Net.Cache`.</span></span>|  
|`System.Net.Http`|<span data-ttu-id="762b1-120">Algunos métodos públicos de las clases <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.DelegatingHandler>, <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>, <xref:System.Net.Http.MessageProcessingHandler> y <xref:System.Net.Http.WebRequestHandler>.</span><span class="sxs-lookup"><span data-stu-id="762b1-120">Some public methods of the  <xref:System.Net.Http.HttpClient>,  <xref:System.Net.Http.DelegatingHandler>,  <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>,  <xref:System.Net.Http.MessageProcessingHandler>, and  <xref:System.Net.Http.WebRequestHandler> classes.</span></span>|  
|`System.Net.WebSockets.WebSocket`|<span data-ttu-id="762b1-121">Algunos métodos públicos de las clases <xref:System.Net.WebSockets.ClientWebSocket> y <xref:System.Net.WebSockets.WebSocket>.</span><span class="sxs-lookup"><span data-stu-id="762b1-121">Some public methods of the <xref:System.Net.WebSockets.ClientWebSocket> and <xref:System.Net.WebSockets.WebSocket> classes.</span></span>|  
  
 <span data-ttu-id="762b1-122">Los atributos mostrados en la tabla siguiente configuran el resultado de la traza.</span><span class="sxs-lookup"><span data-stu-id="762b1-122">The attributes listed in the following table configure trace output.</span></span>  
  
|<span data-ttu-id="762b1-123">Nombre del atributo</span><span class="sxs-lookup"><span data-stu-id="762b1-123">Attribute name</span></span>|<span data-ttu-id="762b1-124">Valor del atributo</span><span class="sxs-lookup"><span data-stu-id="762b1-124">Attribute value</span></span>|  
|--------------------|---------------------|  
|`Value`|<span data-ttu-id="762b1-125">El atributo <xref:System.String> es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="762b1-125">Required <xref:System.String> attribute.</span></span> <span data-ttu-id="762b1-126">Establece el nivel de detalle del resultado.</span><span class="sxs-lookup"><span data-stu-id="762b1-126">Sets the verbosity of the output.</span></span> <span data-ttu-id="762b1-127">Los valores permitidos son `Critical`, `Error`, `Verbose`, `Warning` y `Information`.</span><span class="sxs-lookup"><span data-stu-id="762b1-127">Legitimate values are `Critical`, `Error`, `Verbose`, `Warning`, and `Information`.</span></span><br /><br /> <span data-ttu-id="762b1-128">Este atributo debe establecerse en el elemento \<add name> del elemento \<switches> como se muestra en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="762b1-128">This attribute must be set on the \<add name> element of the \<switches> element as shown in the example.</span></span> <span data-ttu-id="762b1-129">Se produce una excepción si este atributo se establece en el elemento \<source>.</span><span class="sxs-lookup"><span data-stu-id="762b1-129">An exception is thrown if this attribute is set on the \<source> element.</span></span>|  
|`maxdatasize`|<span data-ttu-id="762b1-130">Atributo <xref:System.Int32> opcional.</span><span class="sxs-lookup"><span data-stu-id="762b1-130">Optional <xref:System.Int32> attribute.</span></span> <span data-ttu-id="762b1-131">Establece el número máximo de bytes de datos de red incluidos en cada seguimiento de línea.</span><span class="sxs-lookup"><span data-stu-id="762b1-131">Sets the maximum number of bytes of network data included in each line trace.</span></span> <span data-ttu-id="762b1-132">El valor predeterminado es 1024.</span><span class="sxs-lookup"><span data-stu-id="762b1-132">The default value is 1024.</span></span><br /><br /> <span data-ttu-id="762b1-133">Este atributo debe establecerse en el elemento \<source> como se muestra en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="762b1-133">This attribute must be set on the \<source> element as shown in the example.</span></span> <span data-ttu-id="762b1-134">Se produce una excepción si este atributo se establece en un elemento bajo el elemento \<switches>.</span><span class="sxs-lookup"><span data-stu-id="762b1-134">An exception is thrown if this attribute is set on an element under the \<switches> element.</span></span>|  
|`Tracemode`|<span data-ttu-id="762b1-135">Atributo <xref:System.String> opcional.</span><span class="sxs-lookup"><span data-stu-id="762b1-135">Optional <xref:System.String> attribute.</span></span> <span data-ttu-id="762b1-136">Establezca este atributo en `includehex` para mostrar el seguimiento del protocolo en formato hexadecimal y de texto.</span><span class="sxs-lookup"><span data-stu-id="762b1-136">Set to `includehex` to show protocol traces in hexadecimal and text format.</span></span> <span data-ttu-id="762b1-137">Establezca este atributo en `protocolonly` para mostrar solo texto.</span><span class="sxs-lookup"><span data-stu-id="762b1-137">Set to `protocolonly` to show only text.</span></span> <span data-ttu-id="762b1-138">El valor predeterminado es `includehex`.</span><span class="sxs-lookup"><span data-stu-id="762b1-138">The default value is `includehex`.</span></span><br /><br /> <span data-ttu-id="762b1-139">Este atributo debe establecerse en el elemento \<switches> como se muestra en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="762b1-139">This attribute must be set on the \<switches> element as shown in the example.</span></span> <span data-ttu-id="762b1-140">Se produce una excepción si este atributo se establece en un elemento bajo el elemento \<source>.</span><span class="sxs-lookup"><span data-stu-id="762b1-140">An exception is thrown if this attribute is set on an element under the \<source> element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="762b1-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="762b1-141">See also</span></span>

- [<span data-ttu-id="762b1-142">Interpretación del seguimiento de red</span><span class="sxs-lookup"><span data-stu-id="762b1-142">Interpreting Network Tracing</span></span>](../../../docs/framework/network-programming/interpreting-network-tracing.md)
- [<span data-ttu-id="762b1-143">Network Tracing in the .NET Framework (Seguimiento de red en .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="762b1-143">Network Tracing in the .NET Framework</span></span>](../../../docs/framework/network-programming/network-tracing.md)
- [<span data-ttu-id="762b1-144">Habilitar el seguimiento de red</span><span class="sxs-lookup"><span data-stu-id="762b1-144">Enabling Network Tracing</span></span>](../../../docs/framework/network-programming/enabling-network-tracing.md)
- [<span data-ttu-id="762b1-145">Seguimiento e instrumentación de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="762b1-145">Tracing and Instrumenting Applications</span></span>](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)

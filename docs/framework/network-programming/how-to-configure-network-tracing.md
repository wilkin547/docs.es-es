---
title: "Cómo: configurar el seguimiento de red"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "23"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: b58887dc2614ab31a422eb74ce8d0805cf8153bf
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-configure-network-tracing"></a><span data-ttu-id="e5ac5-102">Cómo: configurar el seguimiento de red</span><span class="sxs-lookup"><span data-stu-id="e5ac5-102">How to: Configure Network Tracing</span></span>
<span data-ttu-id="e5ac5-103">El archivo de configuración de la aplicación o equipo contiene la configuración que determina el formato y el contenido del seguimiento de red.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-103">The application or computer configuration file holds the settings that determine the format and content of network traces.</span></span> <span data-ttu-id="e5ac5-104">Antes de realizar este procedimiento, asegúrese de que el seguimiento está habilitado.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-104">Before performing this procedure, be sure tracing is enabled.</span></span> <span data-ttu-id="e5ac5-105">Para obtener información sobre cómo habilitar el seguimiento de red, vea [Enabling Network Tracing](../../../docs/framework/network-programming/enabling-network-tracing.md) (Habilitar el seguimiento de red).</span><span class="sxs-lookup"><span data-stu-id="e5ac5-105">For information about enabling tracing, see [Enabling Network Tracing](../../../docs/framework/network-programming/enabling-network-tracing.md).</span></span>  
  
 <span data-ttu-id="e5ac5-106">El archivo de configuración del equipo, machine.config, se almacena en la carpeta %Windir%\Microsoft.NET\Framework en el directorio donde se instaló Windows.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-106">The computer configuration file, machine.config, is stored in the %Windir%\Microsoft.NET\Framework folder in the directory where Windows was installed.</span></span> <span data-ttu-id="e5ac5-107">Hay un archivo machine.config distinto en las carpetas bajo %Windir%\Microsoft.NET\Framework para cada versión de .NET Framework instalada en el equipo (por ejemplo, C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config o C:\Windows\ Microsoft.NET\Framework64\v4.0.30319\Config\machine.config.).</span><span class="sxs-lookup"><span data-stu-id="e5ac5-107">There is a separate machine.config file in the folders under %Windir%\Microsoft.NET\Framework for each version of the .NET Framework installed on the computer (for example, C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config or C:\Windows\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config.).</span></span>  
  
 <span data-ttu-id="e5ac5-108">Estos valores se pueden crear también en el archivo de configuración de la aplicación, que tiene prioridad sobre el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-108">These settings can also be made in the configuration file for the application, which has precedence over the computer configuration file.</span></span>  
  
### <a name="to-configure-network-tracing"></a><span data-ttu-id="e5ac5-109">Para configurar el seguimiento de la red</span><span class="sxs-lookup"><span data-stu-id="e5ac5-109">To configure network tracing</span></span>  
  
-   <span data-ttu-id="e5ac5-110">Agregue las siguientes líneas al archivo de configuración correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-110">Add the following lines to the appropriate configuration file.</span></span> <span data-ttu-id="e5ac5-111">Los valores y las opciones de estos valores se describen en las tablas siguientes.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-111">The values and options for these settings are described in the tables below.</span></span>  
  
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
          />  
        </sharedListeners>  
        <trace autoflush="true"/>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
 <span data-ttu-id="e5ac5-112">Al agregar un nombre al bloque `<switches>`, el resultado del seguimiento incluye información de algunos métodos relacionados con el nombre.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-112">When you add a name to the `<switches>` block, the trace output includes information from some methods related to the name.</span></span> <span data-ttu-id="e5ac5-113">En la siguiente tabla se describe el resultado.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-113">The following table describes the output.</span></span>  
  
|<span data-ttu-id="e5ac5-114">nombre</span><span class="sxs-lookup"><span data-stu-id="e5ac5-114">Name</span></span>|<span data-ttu-id="e5ac5-115">Resultado de</span><span class="sxs-lookup"><span data-stu-id="e5ac5-115">Output from</span></span>|  
|----------|-----------------|  
|`System.Net.Sockets`|<span data-ttu-id="e5ac5-116">Algunos métodos públicos de las clases <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient> y <xref:System.Net.Dns></span><span class="sxs-lookup"><span data-stu-id="e5ac5-116">Some public methods of the <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient>, and <xref:System.Net.Dns> classes</span></span>|  
|`System.Net`|<span data-ttu-id="e5ac5-117">Algunos métodos públicos de las clases <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest> y <xref:System.Net.FtpWebResponse>, e información de depuración de SSL (certificados no válidos, lista de emisores que faltan y errores del certificado cliente).</span><span class="sxs-lookup"><span data-stu-id="e5ac5-117">Some public methods of the <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest>, and <xref:System.Net.FtpWebResponse> classes, and SSL debug information (invalid certificates, missing issuers list, and client certificate errors.)</span></span>|  
|`System.Net.HttpListener`|<span data-ttu-id="e5ac5-118">Algunos métodos públicos de las clases <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest> y <xref:System.Net.HttpListenerResponse>.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-118">Some public methods of the <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest>, and <xref:System.Net.HttpListenerResponse> classes.</span></span>|  
|`System.Net.Cache`|<span data-ttu-id="e5ac5-119">Algunos métodos privados e internos de `System.Net.Cache`.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-119">Some private and internal methods in `System.Net.Cache`.</span></span>|  
|`System.Net.Http`|<span data-ttu-id="e5ac5-120">Algunos métodos públicos de las clases <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.DelegatingHandler>, <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>, <xref:System.Net.Http.MessageProcessingHandler> y <xref:System.Net.Http.WebRequestHandler>.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-120">Some public methods of the  <xref:System.Net.Http.HttpClient>,  <xref:System.Net.Http.DelegatingHandler>,  <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>,  <xref:System.Net.Http.MessageProcessingHandler>, and  <xref:System.Net.Http.WebRequestHandler> classes.</span></span>|  
|`System.Net.WebSockets.WebSocket`|<span data-ttu-id="e5ac5-121">Algunos métodos públicos de las clases <xref:System.Net.WebSockets.ClientWebSocket> y <xref:System.Net.WebSockets.WebSocket>.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-121">Some public methods of the <xref:System.Net.WebSockets.ClientWebSocket> and <xref:System.Net.WebSockets.WebSocket> classes.</span></span>|  
  
 <span data-ttu-id="e5ac5-122">Los atributos mostrados en la tabla siguiente configuran el resultado de la traza.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-122">The attributes listed in the following table configure trace output.</span></span>  
  
|<span data-ttu-id="e5ac5-123">Nombre del atributo</span><span class="sxs-lookup"><span data-stu-id="e5ac5-123">Attribute name</span></span>|<span data-ttu-id="e5ac5-124">Valor del atributo</span><span class="sxs-lookup"><span data-stu-id="e5ac5-124">Attribute value</span></span>|  
|--------------------|---------------------|  
|`Value`|<span data-ttu-id="e5ac5-125">El atributo <xref:System.String> es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-125">Required <xref:System.String> attribute.</span></span> <span data-ttu-id="e5ac5-126">Establece el nivel de detalle del resultado.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-126">Sets the verbosity of the output.</span></span> <span data-ttu-id="e5ac5-127">Los valores permitidos son `Critical`, `Error`, `Verbose`, `Warning` y `Information`.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-127">Legitimate values are `Critical`, `Error`, `Verbose`, `Warning`, and `Information`.</span></span><br /><br /> <span data-ttu-id="e5ac5-128">Este atributo debe establecerse en el elemento \<add name> del elemento \<switches> como se muestra en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-128">This attribute must be set on the \<add name> element of the \<switches> element as shown in the example.</span></span> <span data-ttu-id="e5ac5-129">Se produce una excepción si este atributo se establece en el elemento \<source>.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-129">An exception is thrown if this attribute is set on the \<source> element.</span></span>|  
|`maxdatasize`|<span data-ttu-id="e5ac5-130">Atributo <xref:System.Int32> opcional.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-130">Optional <xref:System.Int32> attribute.</span></span> <span data-ttu-id="e5ac5-131">Establece el número máximo de bytes de datos de red incluidos en cada seguimiento de línea.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-131">Sets the maximum number of bytes of network data included in each line trace.</span></span> <span data-ttu-id="e5ac5-132">El valor predeterminado es 1024.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-132">The default value is 1024.</span></span><br /><br /> <span data-ttu-id="e5ac5-133">Este atributo debe establecerse en el elemento \<source> como se muestra en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-133">This attribute must be set on the \<source> element as shown in the example.</span></span> <span data-ttu-id="e5ac5-134">Se produce una excepción si este atributo se establece en un elemento bajo el elemento \<switches>.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-134">An exception is thrown if this attribute is set on an element under the \<switches> element.</span></span>|  
|`Tracemode`|<span data-ttu-id="e5ac5-135">Atributo <xref:System.String> opcional.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-135">Optional <xref:System.String> attribute.</span></span> <span data-ttu-id="e5ac5-136">Establezca este atributo en `includehex` para mostrar el seguimiento del protocolo en formato hexadecimal y de texto.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-136">Set to `includehex` to show protocol traces in hexadecimal and text format.</span></span> <span data-ttu-id="e5ac5-137">Establezca este atributo en `protocolonly` para mostrar solo texto.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-137">Set to `protocolonly` to show only text.</span></span> <span data-ttu-id="e5ac5-138">El valor predeterminado es `includehex`.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-138">The default value is `includehex`.</span></span><br /><br /> <span data-ttu-id="e5ac5-139">Este atributo debe establecerse en el elemento \<switches> como se muestra en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-139">This attribute must be set on the \<switches> element as shown in the example.</span></span> <span data-ttu-id="e5ac5-140">Se produce una excepción si este atributo se establece en un elemento bajo el elemento \<source>.</span><span class="sxs-lookup"><span data-stu-id="e5ac5-140">An exception is thrown if this attribute is set on an element under the \<source> element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e5ac5-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5ac5-141">See Also</span></span>  
 [<span data-ttu-id="e5ac5-142">Interpretación del seguimiento de red</span><span class="sxs-lookup"><span data-stu-id="e5ac5-142">Interpreting Network Tracing</span></span>](../../../docs/framework/network-programming/interpreting-network-tracing.md)  
 [<span data-ttu-id="e5ac5-143">Network Tracing in the .NET Framework (Seguimiento de red en .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="e5ac5-143">Network Tracing in the .NET Framework</span></span>](../../../docs/framework/network-programming/network-tracing.md)  
 [<span data-ttu-id="e5ac5-144">Habilitar el seguimiento de red</span><span class="sxs-lookup"><span data-stu-id="e5ac5-144">Enabling Network Tracing</span></span>](../../../docs/framework/network-programming/enabling-network-tracing.md)  
 [<span data-ttu-id="e5ac5-145">Introducción a la instrumentación y el seguimiento</span><span class="sxs-lookup"><span data-stu-id="e5ac5-145">Introduction to Instrumentation and Tracing</span></span>](http://msdn.microsoft.com/library/e924e57c-33cf-4b0e-9e7f-a45d13e38f2c)

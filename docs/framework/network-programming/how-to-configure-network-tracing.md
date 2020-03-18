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
ms.openlocfilehash: 06132509860b16d1e22cfdf7e3226c968d16b7cf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73040641"
---
# <a name="how-to-configure-network-tracing"></a><span data-ttu-id="60255-102">Procedimiento configurar el seguimiento de red</span><span class="sxs-lookup"><span data-stu-id="60255-102">How to: Configure network tracing</span></span>

<span data-ttu-id="60255-103">El archivo de configuración de la aplicación o equipo contiene la configuración que determina el formato y el contenido del seguimiento de red.</span><span class="sxs-lookup"><span data-stu-id="60255-103">The application or computer configuration file holds the settings that determine the format and content of network traces.</span></span> <span data-ttu-id="60255-104">Antes de realizar este procedimiento, asegúrese de que el seguimiento está habilitado.</span><span class="sxs-lookup"><span data-stu-id="60255-104">Before performing this procedure, be sure tracing is enabled.</span></span> <span data-ttu-id="60255-105">Para obtener más información, consulte [Habilitación de seguimiento de red](enabling-network-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="60255-105">For more information, see [Enable network tracing](enabling-network-tracing.md).</span></span>

<span data-ttu-id="60255-106">El archivo de configuración del equipo, *machine.config*, se almacena en la carpeta *%windir%\Microsoft.NET\Framework*.</span><span class="sxs-lookup"><span data-stu-id="60255-106">The computer configuration file, *machine.config*, is stored in the *%windir%\Microsoft.NET\Framework* folder.</span></span> <span data-ttu-id="60255-107">Hay un archivo *machine.config* independiente en las carpetas situadas bajo *%windir%\Microsoft.NET\Framework* para cada versión de .NET Framework instalada en el equipo, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="60255-107">There is a separate *machine.config* file in the folders under *%windir%\Microsoft.NET\Framework* for each version of the .NET Framework installed on the computer, for example:</span></span>

- <span data-ttu-id="60255-108">*C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\Config\machine.config*</span><span class="sxs-lookup"><span data-stu-id="60255-108">*C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\Config\machine.config*</span></span>
- <span data-ttu-id="60255-109">*C:\WINDOWS\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config*</span><span class="sxs-lookup"><span data-stu-id="60255-109">*C:\WINDOWS\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config*</span></span>

<span data-ttu-id="60255-110">Estos valores se pueden crear también en el archivo de configuración de la aplicación, que tiene prioridad sobre el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="60255-110">These settings can also be made in the configuration file for the application, which has precedence over the computer configuration file.</span></span>

## <a name="configure-network-tracing"></a><span data-ttu-id="60255-111">Configuración del seguimiento de red</span><span class="sxs-lookup"><span data-stu-id="60255-111">Configure network tracing</span></span>

<span data-ttu-id="60255-112">Para configurar el seguimiento de red, agregue las líneas siguientes al archivo de configuración adecuado.</span><span class="sxs-lookup"><span data-stu-id="60255-112">To configure network tracing, add the following lines to the appropriate configuration file.</span></span> <span data-ttu-id="60255-113">Los valores y las opciones de estos valores se describen en las tablas siguientes.</span><span class="sxs-lookup"><span data-stu-id="60255-113">The values and options for these settings are described in the tables below.</span></span>

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

### <a name="trace-output-from-methods"></a><span data-ttu-id="60255-114">Resultado de seguimiento de los métodos</span><span class="sxs-lookup"><span data-stu-id="60255-114">Trace output from methods</span></span>

<span data-ttu-id="60255-115">Al agregar un nombre al bloque `<switches>`, el resultado del seguimiento incluye información de algunos métodos relacionados con el nombre.</span><span class="sxs-lookup"><span data-stu-id="60255-115">When you add a name to the `<switches>` block, the trace output includes information from some methods related to the name.</span></span> <span data-ttu-id="60255-116">En la tabla siguiente se describe el resultado:</span><span class="sxs-lookup"><span data-stu-id="60255-116">The following table describes the output:</span></span>

|<span data-ttu-id="60255-117">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="60255-117">Name</span></span>|<span data-ttu-id="60255-118">Resultado de</span><span class="sxs-lookup"><span data-stu-id="60255-118">Output from</span></span>|
|----------|-----------------|
|`System.Net.Sockets`|<span data-ttu-id="60255-119">Algunos métodos públicos de las clases <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient> y <xref:System.Net.Dns>.</span><span class="sxs-lookup"><span data-stu-id="60255-119">Some public methods of the <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient>, and <xref:System.Net.Dns> classes.</span></span>|
|`System.Net`|<span data-ttu-id="60255-120">Algunos métodos públicos de las clases <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest> y <xref:System.Net.FtpWebResponse>, e información de depuración de SSL (certificados no válidos, lista de emisores que faltan y errores del certificado cliente).</span><span class="sxs-lookup"><span data-stu-id="60255-120">Some public methods of the <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest>, and <xref:System.Net.FtpWebResponse> classes, and SSL debug information (invalid certificates, missing issuers list, and client certificate errors).</span></span>|
|`System.Net.HttpListener`|<span data-ttu-id="60255-121">Algunos métodos públicos de las clases <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest> y <xref:System.Net.HttpListenerResponse>.</span><span class="sxs-lookup"><span data-stu-id="60255-121">Some public methods of the <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest>, and <xref:System.Net.HttpListenerResponse> classes.</span></span>|
|`System.Net.Cache`|<span data-ttu-id="60255-122">Algunos métodos privados e internos de `System.Net.Cache`.</span><span class="sxs-lookup"><span data-stu-id="60255-122">Some private and internal methods in `System.Net.Cache`.</span></span>|
|`System.Net.Http`|<span data-ttu-id="60255-123">Algunos métodos públicos de las clases <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.DelegatingHandler>, <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>, <xref:System.Net.Http.MessageProcessingHandler> y <xref:System.Net.Http.WebRequestHandler>.</span><span class="sxs-lookup"><span data-stu-id="60255-123">Some public methods of the  <xref:System.Net.Http.HttpClient>,  <xref:System.Net.Http.DelegatingHandler>,  <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>,  <xref:System.Net.Http.MessageProcessingHandler>, and  <xref:System.Net.Http.WebRequestHandler> classes.</span></span>|
|`System.Net.WebSockets.WebSocket`|<span data-ttu-id="60255-124">Algunos métodos públicos de las clases <xref:System.Net.WebSockets.ClientWebSocket> y <xref:System.Net.WebSockets.WebSocket>.</span><span class="sxs-lookup"><span data-stu-id="60255-124">Some public methods of the <xref:System.Net.WebSockets.ClientWebSocket> and <xref:System.Net.WebSockets.WebSocket> classes.</span></span>|

### <a name="trace-output-attributes"></a><span data-ttu-id="60255-125">Atributos de resultado de seguimiento</span><span class="sxs-lookup"><span data-stu-id="60255-125">Trace output attributes</span></span>

<span data-ttu-id="60255-126">Los atributos mostrados en la tabla siguiente configuran el resultado de seguimiento:</span><span class="sxs-lookup"><span data-stu-id="60255-126">The attributes listed in the following table configure trace output:</span></span>

|<span data-ttu-id="60255-127">Nombre del atributo</span><span class="sxs-lookup"><span data-stu-id="60255-127">Attribute name</span></span>|<span data-ttu-id="60255-128">Valor del atributo</span><span class="sxs-lookup"><span data-stu-id="60255-128">Attribute value</span></span>|
|--------------------|---------------------|
|`value`|<span data-ttu-id="60255-129">El atributo <xref:System.String> es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="60255-129">Required <xref:System.String> attribute.</span></span> <span data-ttu-id="60255-130">Establece el nivel de detalle del resultado.</span><span class="sxs-lookup"><span data-stu-id="60255-130">Sets the verbosity of the output.</span></span> <span data-ttu-id="60255-131">Los valores permitidos son `Critical`, `Error`, `Verbose`, `Warning` y `Information`.</span><span class="sxs-lookup"><span data-stu-id="60255-131">Legitimate values are `Critical`, `Error`, `Verbose`, `Warning`, and `Information`.</span></span><br /><br /><span data-ttu-id="60255-132">Este atributo debe establecerse en el elemento **add** del elemento **switches**.</span><span class="sxs-lookup"><span data-stu-id="60255-132">This attribute must be set on the **add** element of the **switches** element.</span></span> <span data-ttu-id="60255-133">Si este atributo se establece en el elemento **source**, se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="60255-133">An exception is thrown if this attribute is set on the **source** element.</span></span><br/><br/><span data-ttu-id="60255-134">Ejemplo: `<add name="System.Net" value="Verbose"/>`</span><span class="sxs-lookup"><span data-stu-id="60255-134">Example: `<add name="System.Net" value="Verbose"/>`</span></span>|
|`maxdatasize`|<span data-ttu-id="60255-135">Atributo <xref:System.Int32> opcional.</span><span class="sxs-lookup"><span data-stu-id="60255-135">Optional <xref:System.Int32> attribute.</span></span> <span data-ttu-id="60255-136">Establece el número máximo de bytes de datos de red incluidos en cada seguimiento de línea.</span><span class="sxs-lookup"><span data-stu-id="60255-136">Sets the maximum number of bytes of network data included in each line trace.</span></span> <span data-ttu-id="60255-137">El valor predeterminado es 1024.</span><span class="sxs-lookup"><span data-stu-id="60255-137">The default value is 1024.</span></span><br /><br /><span data-ttu-id="60255-138">Este atributo debe establecerse en el elemento **source**.</span><span class="sxs-lookup"><span data-stu-id="60255-138">This attribute must be set on the **source** element.</span></span> <span data-ttu-id="60255-139">Si este atributo se establece en un elemento que está en el elemento **switches**, se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="60255-139">An exception is thrown if this attribute is set on an element under the **switches** element.</span></span><br/><br/><span data-ttu-id="60255-140">Ejemplo: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span><span class="sxs-lookup"><span data-stu-id="60255-140">Example: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span></span>|
|`tracemode`|<span data-ttu-id="60255-141">Atributo <xref:System.String> opcional.</span><span class="sxs-lookup"><span data-stu-id="60255-141">Optional <xref:System.String> attribute.</span></span> <span data-ttu-id="60255-142">Establezca este atributo en `includehex` para mostrar el seguimiento del protocolo en formato hexadecimal y de texto.</span><span class="sxs-lookup"><span data-stu-id="60255-142">Set to `includehex` to show protocol traces in hexadecimal and text format.</span></span> <span data-ttu-id="60255-143">Establezca este atributo en `protocolonly` para mostrar solo texto.</span><span class="sxs-lookup"><span data-stu-id="60255-143">Set to `protocolonly` to show only text.</span></span> <span data-ttu-id="60255-144">El valor predeterminado es `includehex`.</span><span class="sxs-lookup"><span data-stu-id="60255-144">The default value is `includehex`.</span></span><br /><br /><span data-ttu-id="60255-145">Este atributo debe establecerse en el elemento **source**.</span><span class="sxs-lookup"><span data-stu-id="60255-145">This attribute must be set on the **source** element.</span></span> <span data-ttu-id="60255-146">Si este atributo se establece en un elemento que está en el elemento **switches**, se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="60255-146">An exception is thrown if this attribute is set on an element under the **switches** element.</span></span><br/><br/><span data-ttu-id="60255-147">Ejemplo: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span><span class="sxs-lookup"><span data-stu-id="60255-147">Example: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span></span>|

## <a name="see-also"></a><span data-ttu-id="60255-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="60255-148">See also</span></span>

- [<span data-ttu-id="60255-149">Interpretación del seguimiento de red</span><span class="sxs-lookup"><span data-stu-id="60255-149">Interpreting Network Tracing</span></span>](interpreting-network-tracing.md)
- [<span data-ttu-id="60255-150">Network Tracing in the .NET Framework (Seguimiento de red en .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="60255-150">Network Tracing in the .NET Framework</span></span>](network-tracing.md)
- [<span data-ttu-id="60255-151">Habilitar el seguimiento de red</span><span class="sxs-lookup"><span data-stu-id="60255-151">Enabling Network Tracing</span></span>](enabling-network-tracing.md)
- [<span data-ttu-id="60255-152">Seguimiento e instrumentación de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="60255-152">Tracing and Instrumenting Applications</span></span>](../debug-trace-profile/tracing-and-instrumenting-applications.md)

---
title: Procedimiento para configurar el seguimiento de la red
description: Obtenga información sobre cómo configurar el seguimiento de red en el archivo de configuración del equipo o en el archivo de configuración de la aplicación. El archivo de configuración de la aplicación tiene preferencia.
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
ms.openlocfilehash: b089746e9838c591ed5ccc9ac9aaeedb217de9a9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502566"
---
# <a name="how-to-configure-network-tracing"></a>Procedimiento configurar el seguimiento de red

El archivo de configuración de la aplicación o equipo contiene la configuración que determina el formato y el contenido del seguimiento de red. Antes de realizar este procedimiento, asegúrese de que el seguimiento está habilitado. Para obtener más información, consulte [Habilitación de seguimiento de red](enabling-network-tracing.md).

El archivo de configuración del equipo, *machine.config*, se almacena en la carpeta *%windir%\Microsoft.NET\Framework*. Hay un archivo *machine.config* independiente en las carpetas situadas bajo *%windir%\Microsoft.NET\Framework* para cada versión de .NET Framework instalada en el equipo, por ejemplo:

- *C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\Config\machine.config*
- *C:\WINDOWS\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config*

Estos valores se pueden crear también en el archivo de configuración de la aplicación, que tiene prioridad sobre el archivo de configuración del equipo.

## <a name="configure-network-tracing"></a>Configuración del seguimiento de red

Para configurar el seguimiento de red, agregue las líneas siguientes al archivo de configuración adecuado. Los valores y las opciones de estos valores se describen en las tablas siguientes.

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

### <a name="trace-output-from-methods"></a>Resultado de seguimiento de los métodos

Al agregar un nombre al bloque `<switches>`, el resultado del seguimiento incluye información de algunos métodos relacionados con el nombre. En la tabla siguiente se describe el resultado:

|NOMBRE|Resultado de|
|----------|-----------------|
|`System.Net.Sockets`|Algunos métodos públicos de las clases <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient> y <xref:System.Net.Dns>.|
|`System.Net`|Algunos métodos públicos de las clases <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest> y <xref:System.Net.FtpWebResponse>, e información de depuración de SSL (certificados no válidos, lista de emisores que faltan y errores del certificado cliente).|
|`System.Net.HttpListener`|Algunos métodos públicos de las clases <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest> y <xref:System.Net.HttpListenerResponse>.|
|`System.Net.Cache`|Algunos métodos privados e internos de `System.Net.Cache`.|
|`System.Net.Http`|Algunos métodos públicos de las clases <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.DelegatingHandler>, <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>, <xref:System.Net.Http.MessageProcessingHandler> y <xref:System.Net.Http.WebRequestHandler>.|
|`System.Net.WebSockets.WebSocket`|Algunos métodos públicos de las clases <xref:System.Net.WebSockets.ClientWebSocket> y <xref:System.Net.WebSockets.WebSocket>.|

### <a name="trace-output-attributes"></a>Atributos de resultado de seguimiento

Los atributos mostrados en la tabla siguiente configuran el resultado de seguimiento:

|Nombre del atributo|Valor del atributo|
|--------------------|---------------------|
|`value`|El atributo <xref:System.String> es obligatorio. Establece el nivel de detalle del resultado. Los valores permitidos son `Critical`, `Error`, `Verbose`, `Warning` y `Information`.<br /><br />Este atributo debe establecerse en el elemento **add** del elemento **switches**. Si este atributo se establece en el elemento **source**, se produce una excepción.<br/><br/>Ejemplo: `<add name="System.Net" value="Verbose"/>`|
|`maxdatasize`|Atributo <xref:System.Int32> opcional. Establece el número máximo de bytes de datos de red incluidos en cada seguimiento de línea. El valor predeterminado es 1024.<br /><br />Este atributo debe establecerse en el elemento **source**. Si este atributo se establece en un elemento que está en el elemento **switches**, se produce una excepción.<br/><br/>Ejemplo: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`|
|`tracemode`|Atributo <xref:System.String> opcional. Establezca este atributo en `includehex` para mostrar el seguimiento del protocolo en formato hexadecimal y de texto. Establezca este atributo en `protocolonly` para mostrar solo texto. El valor predeterminado es `includehex`.<br /><br />Este atributo debe establecerse en el elemento **source**. Si este atributo se establece en un elemento que está en el elemento **switches**, se produce una excepción.<br/><br/>Ejemplo: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`|

## <a name="see-also"></a>Vea también

- [Interpretación del seguimiento de red](interpreting-network-tracing.md)
- [Network Tracing in the .NET Framework (Seguimiento de red en .NET Framework)](network-tracing.md)
- [Habilitar el seguimiento de red](enabling-network-tracing.md)
- [Seguimiento e instrumentación de aplicaciones](../debug-trace-profile/tracing-and-instrumenting-applications.md)

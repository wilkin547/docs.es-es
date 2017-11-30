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
ms.openlocfilehash: 12f328d58ef568c78d1e2c8a8ff564839cba9f3b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-configure-network-tracing"></a>Cómo: configurar el seguimiento de red
El archivo de configuración de la aplicación o equipo contiene la configuración que determina el formato y el contenido del seguimiento de red. Antes de realizar este procedimiento, asegúrese de que el seguimiento está habilitado. Para obtener información sobre cómo habilitar el seguimiento de red, vea [Enabling Network Tracing](../../../docs/framework/network-programming/enabling-network-tracing.md) (Habilitar el seguimiento de red).  
  
 El archivo de configuración del equipo, machine.config, se almacena en la carpeta %Windir%\Microsoft.NET\Framework en el directorio donde se instaló Windows. Hay un archivo machine.config distinto en las carpetas bajo %Windir%\Microsoft.NET\Framework para cada versión de .NET Framework instalada en el equipo (por ejemplo, C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config o C:\Windows\ Microsoft.NET\Framework64\v4.0.30319\Config\machine.config.).  
  
 Estos valores se pueden crear también en el archivo de configuración de la aplicación, que tiene prioridad sobre el archivo de configuración del equipo.  
  
### <a name="to-configure-network-tracing"></a>Para configurar el seguimiento de la red  
  
-   Agregue las siguientes líneas al archivo de configuración correspondiente. Los valores y las opciones de estos valores se describen en las tablas siguientes.  
  
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
  
 Al agregar un nombre al bloque `<switches>`, el resultado del seguimiento incluye información de algunos métodos relacionados con el nombre. En la siguiente tabla se describe el resultado.  
  
|Nombre|Resultado de|  
|----------|-----------------|  
|`System.Net.Sockets`|Algunos métodos públicos de las clases <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient> y <xref:System.Net.Dns>|  
|`System.Net`|Algunos métodos públicos de las clases <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest> y <xref:System.Net.FtpWebResponse>, e información de depuración de SSL (certificados no válidos, lista de emisores que faltan y errores del certificado cliente).|  
|`System.Net.HttpListener`|Algunos métodos públicos de las clases <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest> y <xref:System.Net.HttpListenerResponse>.|  
|`System.Net.Cache`|Algunos métodos privados e internos de `System.Net.Cache`.|  
|`System.Net.Http`|Algunos métodos públicos de las clases <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.DelegatingHandler>, <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>, <xref:System.Net.Http.MessageProcessingHandler> y <xref:System.Net.Http.WebRequestHandler>.|  
|`System.Net.WebSockets.WebSocket`|Algunos métodos públicos de las clases <xref:System.Net.WebSockets.ClientWebSocket> y <xref:System.Net.WebSockets.WebSocket>.|  
  
 Los atributos mostrados en la tabla siguiente configuran el resultado de la traza.  
  
|Nombre del atributo|Valor del atributo|  
|--------------------|---------------------|  
|`Value`|El atributo <xref:System.String> es obligatorio. Establece el nivel de detalle del resultado. Los valores permitidos son `Critical`, `Error`, `Verbose`, `Warning` y `Information`.<br /><br /> Este atributo debe establecerse en el elemento \<add name> del elemento \<switches> como se muestra en el ejemplo. Se produce una excepción si este atributo se establece en el elemento \<source>.|  
|`maxdatasize`|Atributo <xref:System.Int32> opcional. Establece el número máximo de bytes de datos de red incluidos en cada seguimiento de línea. El valor predeterminado es 1024.<br /><br /> Este atributo debe establecerse en el elemento \<source> como se muestra en el ejemplo. Se produce una excepción si este atributo se establece en un elemento bajo el elemento \<switches>.|  
|`Tracemode`|Atributo <xref:System.String> opcional. Establezca este atributo en `includehex` para mostrar el seguimiento del protocolo en formato hexadecimal y de texto. Establezca este atributo en `protocolonly` para mostrar solo texto. El valor predeterminado es `includehex`.<br /><br /> Este atributo debe establecerse en el elemento \<switches> como se muestra en el ejemplo. Se produce una excepción si este atributo se establece en un elemento bajo el elemento \<source>.|  
  
## <a name="see-also"></a>Vea también  
 [Interpretar el seguimiento de red](../../../docs/framework/network-programming/interpreting-network-tracing.md)  
 [Network Tracing in the .NET Framework (Seguimiento de red en .NET Framework)](../../../docs/framework/network-programming/network-tracing.md)  
 [Habilitar el seguimiento de red](../../../docs/framework/network-programming/enabling-network-tracing.md)  
 [Introducción a la instrumentación y el seguimiento](http://msdn.microsoft.com/en-us/e924e57c-33cf-4b0e-9e7f-a45d13e38f2c)

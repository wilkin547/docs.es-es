---
title: "C&#243;mo: Configurar la traza de la red | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "app.config (archivos), traza de la red"
  - "archivos de configuración de la aplicación, traza de la red"
  - "archivos de configuración [.NET Framework], traza de la red"
  - "dar formato [.NET Framework], traza de la red"
  - "atributo level"
  - "traza de la red, configurar"
  - "resultado de traza de protocolo- nivel"
  - "sockets, resultado de traza"
ms.assetid: 5ef9fe4b-8d3d-490e-9259-1d014b2181af
caps.latest.revision: 23
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 23
---
# C&#243;mo: Configurar la traza de la red
El archivo de configuración de la aplicación o equipo contiene la configuración que determina el formato y el contenido del seguimiento de red. Antes de realizar este procedimiento, asegúrese de que el seguimiento está habilitado. Para obtener más información acerca de cómo habilitar el seguimiento, vea [Habilitación del seguimiento de red](../../../docs/framework/network-programming/enabling-network-tracing.md).  
  
 El archivo de configuración del equipo, machine.config, se almacena en la carpeta %Windir%\\Microsoft.NET\\Framework en el directorio donde se instaló Windows. Hay un archivo machine.config distinto en las carpetas bajo %Windir%\\Microsoft.NET\\Framework para cada versión de .NET Framework instalada en el equipo \(por ejemplo, C:\\WINDOWS\\Microsoft.NET\\Framework\\v2.0.50727\\machine.config\).  
  
 Estos valores se pueden crear también en el archivo de configuración de la aplicación, que tiene prioridad sobre el archivo de configuración del equipo.  
  
### Para configurar el seguimiento de la red  
  
-   Agregue las siguientes líneas al archivo de configuración correspondiente. Los valores y las opciones de estos valores se describen en las tablas siguientes.  
  
    ```  
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
|------------|------------------|  
|`System.Net.Sockets`|Algunos métodos públicos de las clases <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient> y <xref:System.Net.Dns>|  
|`System.Net`|Algunos métodos públicos de las clases <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest> y <xref:System.Net.FtpWebResponse>, e información de depuración de SSL \(certificados no válidos, lista de emisores que faltan y errores del certificado cliente\).|  
|`System.Net.HttpListener`|Algunos métodos públicos de las clases <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest> y <xref:System.Net.HttpListenerResponse>.|  
|`System.Net.Cache`|Algunos métodos privados e internos de `System.Net.Cache`.|  
|`System.Net.Http`|Algunos métodos públicos de las clases <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.DelegatingHandler>, <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>, <xref:System.Net.Http.MessageProcessingHandler> y <xref:System.Net.Http.WebRequestHandler>.|  
|`System.Net.WebSockets.WebSocket`|Algunos métodos públicos de las clases <xref:System.Net.WebSockets.ClientWebSocket> y <xref:System.Net.WebSockets.WebSocket>.|  
  
 Los atributos mostrados en la tabla siguiente configuran el resultado de la traza.  
  
|Nombre del atributo|Valor del atributo|  
|-------------------------|------------------------|  
|`Value`|El atributo <xref:System.String> es obligatorio. Establece el nivel de detalle del resultado. Los valores permitidos son `Critical`, `Error`, `Verbose`, `Warning` y `Information`.<br /><br /> Este atributo debe establecerse en el elemento \<add name\> del elemento \<switches\> como se muestra en el ejemplo. Se produce una excepción si este atributo se establece en el elemento \<source\>.|  
|`maxdatasize`|Atributo <xref:System.Int32> opcional. Establece el número máximo de bytes de datos de red incluidos en cada seguimiento de línea. El valor predeterminado es 1024.<br /><br /> Este atributo debe establecerse en el elemento \<source\> como se muestra en el ejemplo. Se produce una excepción si este atributo se establece en un elemento bajo el elemento \<switches\>.|  
|`Tracemode`|Atributo <xref:System.String> opcional. Establezca este atributo en `includehex` para mostrar el seguimiento del protocolo en formato hexadecimal y de texto. Establezca este atributo en `protocolonly` para mostrar solo texto. El valor predeterminado es `includehex`.<br /><br /> Este atributo debe establecerse en el elemento \<switches\> como se muestra en el ejemplo. Se produce una excepción si este atributo se establece en un elemento bajo el elemento \<source\>.|  
  
## Vea también  
 [Interpretar el seguimiento de red](../../../docs/framework/network-programming/interpreting-network-tracing.md)   
 [Traza de la red en .NET Framework](../../../docs/framework/network-programming/network-tracing.md)   
 [Habilitación del seguimiento de red](../../../docs/framework/network-programming/enabling-network-tracing.md)   
 [Introducción a la instrumentación y el seguimiento](http://msdn.microsoft.com/es-es/e924e57c-33cf-4b0e-9e7f-a45d13e38f2c)
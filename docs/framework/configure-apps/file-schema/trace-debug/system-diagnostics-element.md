---
title: "Elemento &lt;system.diagnostics&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<system.diagnostics> (elemento)"
  - "system.diagnostics (elemento)"
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
caps.latest.revision: 17
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# Elemento &lt;system.diagnostics&gt;
Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, y el nivel donde se establece un modificador de seguimiento.  
  
## Sintaxis  
  
```  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<assert\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|Especifica si aparecerá o no un cuadro de mensaje al llamar al método <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>; también especifica el nombre del archivo donde se escriben los mensajes.|  
|[\<performanceCounters\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|Especifica el tamaño de la memoria global compartida por los contadores de rendimiento.|  
|[\<sharedListeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|Contiene agentes de escucha a los que puede hacer referencia cualquier origen o elemento de traza.  Los agentes de escucha identificados como agentes de escucha compartidos se pueden agregar por nombre a los orígenes o trazas.|  
|[\<orígenes\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|Especifica orígenes de traza que inician mensajes de traza.|  
|[\<Modificadores\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|Contiene modificadores de traza y los niveles donde éstos se establecen.|  
|[\<trace\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|Contiene agentes de escucha que recopilan, almacenan y enrutan mensajes de traza.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
  
## Ejemplo  
 El ejemplo siguiente se muestra cómo insertar un modificador de traza y un agente de escucha dentro del elemento de **\<system.diagnostics\>** .  El modificador de traza `General` se establece en el nivel [TraceLevel.Error](frlrfSystemDiagnosticsTraceLevelClassTopic).  El agente de escucha de traza `myListener` crea un archivo denominado `MyListener.log` y escribe el resultado en el archivo.  
  
> [!NOTE]
>  En la versión 2.0 de .NET Framework, se puede utilizar texto para especificar el valor de un modificador.  Por ejemplo, puede especificar `true` para <xref:System.Diagnostics.BooleanSwitch> o el texto que representa un valor de enumeración como `Error` para <xref:System.Diagnostics.TraceSwitch>.  La línea `<add name="myTraceSwitch" value="Error" />` es equivalente a `<add name="myTraceSwitch" value="1" />`.  
  
```  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
      </switches>  
      <trace autoflush="true" indentsize="2">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="MyListener.log" traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Diagnostics.Trace>   
 <xref:System.Diagnostics.Debug>   
 [Esquema de la configuración de seguimiento y depuración](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
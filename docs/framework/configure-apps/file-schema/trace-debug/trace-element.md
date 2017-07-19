---
title: "Elemento &lt;trace&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#trace"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<trace> (elemento)"
  - "agentes de escucha"
  - "trace (elemento)"
  - "agente de escucha de seguimiento, <trace> (elemento)"
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# Elemento &lt;trace&gt;
Contiene agentes de escucha que recopilan, almacenan y enrutan mensajes de traza.  
  
## Sintaxis  
  
```  
<trace autoflush="true|false"   
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`autoflush`|Atributo opcional.<br /><br /> Especifica si los agentes de escucha de traza vacían automáticamente o no el búfer de resultados después de cada operación de escritura.|  
|`indentsize`|Atributo opcional.<br /><br /> Especifica el número de espacios para la sangría.|  
|`useGlobalLock`|Atributo opcional.<br /><br /> Indica si se debe utilizar el bloqueo global.|  
  
## Atributo autoflush  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|No vacía automáticamente el búfer de resultados.  Éste es el valor predeterminado.|  
|`true`|Vacía automáticamente el búfer de resultados.|  
  
## Atributo useGlobalLock  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|No utiliza el bloqueo global si el agente de escucha es seguro para subprocesos; en caso contrario, utiliza el bloqueo global.|  
|`true`|Utiliza el bloqueo global sin tener en cuenta si el agente de escucha es seguro para subprocesos.  Éste es el valor predeterminado.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<escuchas\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|Especifica un agente de escucha que recopila, almacena y enruta mensajes.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, y el nivel donde se establece un modificador de seguimiento.|  
  
## Ejemplo  
 En los ejemplos siguientes se muestra el uso del elemento `<trace>` para agregar el agente de escucha `MyListener` a la colección `Listeners`.  `MyListener` crea un archivo denominado `MyListener.log` y escribe el resultado en el archivo.  El atributo `useGlobalLock` está establecido en `false`, lo que provoca que no se utilice el bloqueo global si el agente de escucha de traza es seguro para subprocesos.  El atributo `autoflush` se establece en `true`, lo que provoca que el agente de escucha de traza escriba en el archivo, independientemente de que se llame o no al método <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=fullName>.  El atributo `indentsize` está establecido en 0 \(cero\), lo que provoca que el agente de escucha aplique una sangría de cero espacios cuando se llama al método <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=fullName>.  
  
```  
<configuration>  
   <system.diagnostics>  
      <trace useGlobalLock="false" autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Diagnostics.TraceListener>   
 <xref:System.Diagnostics.DefaultTraceListener>   
 <xref:System.Diagnostics.TextWriterTraceListener>   
 <xref:System.Diagnostics.EventLogTraceListener>   
 [Esquema de la configuración de seguimiento y depuración](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
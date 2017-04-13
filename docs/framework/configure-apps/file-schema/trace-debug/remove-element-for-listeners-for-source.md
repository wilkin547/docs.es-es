---
title: "Elemento &lt;remove&gt; de &lt;listeners&gt; de &lt;source&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<remove> (elemento) para <listeners> de <source>"
  - "remove (elemento) para <listeners> de <source>"
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# Elemento &lt;remove&gt; de &lt;listeners&gt; de &lt;source&gt;
Quita un agente de escucha de la colección `Listeners` para un origen de traza.  
  
## Sintaxis  
  
```  
<remove name="listenerName" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`name`|Atributo necesario.<br /><br /> Nombre del agente de escucha que se va a quitar de la colección `Listeners`.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, y el nivel donde se establece un modificador de seguimiento.|  
|`sources`|Contiene orígenes de traza que inician mensajes de traza.|  
|`source`|Especifica un origen de traza que inicia mensajes de traza.|  
|`listeners`|Especifica agentes de escucha que recopilan, almacenan y enrutan mensajes.|  
  
## Comentarios  
 El elemento `<remove>` quita un agente de escucha especificado de la colección `Listeners` para un origen de traza.  
  
 Puede quitar mediante programación un elemento de la colección `Listeners` para un origen de traza llamando al método <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> en la propiedad <xref:System.Diagnostics.TraceSource.Listeners%2A> de la instancia <xref:System.Diagnostics.TraceSource>.  
  
 Este elemento se puede utilizar en el archivo de configuración del equipo \(Machine.config\) y en el archivo de configuración de la aplicación.  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo utilizar el elemento `<remove>` antes de usar el elemento `<add>` para agregar el agente de escucha `console` a la colección `Listeners` para el origen de traza `TraceSourceApp`.  
  
```  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch" >  
         <listeners>  
           <remove name="Default"/>  
           <add name="console"   
             type="System.Diagnostics.ConsoleTraceListener" />  
         </listeners>  
      </source>  
    </sources>  
  </system.diagnostics>  
</configuration>   
```  
  
## Vea también  
 <xref:System.Diagnostics.TraceSource.Listeners%2A>   
 <xref:System.Diagnostics.TraceSource>   
 [Esquema de la configuración de seguimiento y depuración](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)   
 [\<clear\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)   
 [Trace Listeners](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
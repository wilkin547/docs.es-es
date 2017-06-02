---
title: "&lt;sharedListeners&gt; (Elemento) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#sharedListeners"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<sharedListeners> (elemento)"
  - "agentes de escucha"
  - "agentes de escucha compartidos"
  - "sharedListeners (elemento)"
  - "agentes de escucha de seguimiento, <sharedListeners> (elemento)"
ms.assetid: de200534-19dd-4156-86cf-c50521802c4c
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# &lt;sharedListeners&gt; (Elemento)
Contiene agentes de escucha a los que puede hacer referencia cualquier origen o elemento de traza.  Estos agentes de escucha no reciben de forma predeterminada ningún seguimiento y no es posible recuperar estos agentes de escucha en tiempo de ejecución.  Los agentes de escucha identificados como agentes de escucha compartidos se pueden agregar por nombre a los orígenes o trazas.  
  
## Sintaxis  
  
```  
<sharedListeners>   
  <add>...</add>  
</sharedListeners>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|Agrega un agente de escucha a la colección `sharedListeners`.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`Configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica el elemento raíz de la sección de configuración de ASP.NET.|  
  
## Comentarios  
 Agregar un agente de escucha a la colección de agentes de escucha compartidos no la convierte en un agente de escucha activo.  Todavía es necesario agregarla a un origen de seguimiento o a un seguimiento incluyéndola en la colección `Listeners` de ese elemento de seguimiento.  Las clases de agente de escucha incluidas en .NET Framework se derivan de la clase <xref:System.Diagnostics.TraceListener>.  
  
 Este elemento se puede utilizar en el archivo de configuración del equipo \(Machine.config\) y en el archivo de configuración de la aplicación.  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo utilizar el elemento `<sharedListeners>` para agregar el agente de escucha `console` a la colección `Listeners` para ambas clases, <xref:System.Diagnostics.TraceSource> y <xref:System.Diagnostics.Trace>.  El agente de escucha de seguimiento de la consola escribe información de seguimiento en la consola a través de llamadas a <xref:System.Diagnostics.TraceSource> o <xref:System.Diagnostics.Trace>.  
  
```  
<configuration>  
  <system.diagnostics>  
    <sharedListeners>  
      <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"  
          initializeData="Warning" />  
      </add>  
    </sharedListeners>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"  >  
        <listeners>  
          <add name="console" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Verbose"/>  
    </switches>  
    <trace>  
      <listeners>  
        <add name="console" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration></system.diagnostics>   
```  
  
## Vea también  
 <xref:System.Diagnostics.TraceListener>   
 [Esquema de la configuración de seguimiento y depuración](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)   
 [Trace Listeners](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
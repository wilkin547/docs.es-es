---
title: "Elemento &lt;listeners&gt; para &lt;trace&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<listeners> (elemento)"
  - "listeners (elemento)"
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
caps.latest.revision: 17
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 17
---
# Elemento &lt;listeners&gt; para &lt;trace&gt;
Especifica un agente de escucha que recopila, almacena y enruta mensajes.  Los agentes de escucha dirigen el resultado de la traza a un destino apropiado.  
  
## Sintaxis  
  
```  
<listeners>   
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|Agrega un agente de escucha a la colección `Listeners`.|  
|[\<clear\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-trace.md)|Borra la colección `Listeners` para traza.|  
|[\<remove\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)|Quita un agente de escucha de la colección `Listeners`.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica el elemento raíz de la sección de configuración de ASP.NET.|  
|`trace`|Contiene agentes de escucha que recopilan, almacenan y enrutan mensajes de traza.|  
  
## Comentarios  
 Las clases <xref:System.Diagnostics.Debug> y <xref:System.Diagnostics.Trace> comparten la misma colección **Listeners**.  Si se agrega un objeto de agente de escucha a la colección en una de estas clases, la otra clase utilizará el mismo agente de escucha.  Las clases de agente de escucha incluidas en .NET Framework se derivan de la clase <xref:System.Diagnostics.TraceListener>.  
  
## Archivo de configuración  
 Este elemento se puede utilizar en el archivo de configuración del equipo \(Machine.config\) y en el archivo de configuración de la aplicación.  
  
## Ejemplo  
 El ejemplo siguiente se muestra cómo utilizar el elemento de **\<listeners\>** para agregar agentes de escucha `MyListener` y `MyEventListener` a la colección de **Listeners** .  `MyListener` crea un archivo denominado `MyListener.log` y escribe el resultado en el archivo.  `MyEventListener` crea una entrada en el registro de eventos.  
  
```  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="true" indentsize="0">  
      <listeners>  
        <add name="myListener"   
          type="System.Diagnostics.TextWriterTraceListener,   
            system, version=1.0.3300.0, Culture=neutral,   
            PublicKeyToken=b77a5c561934e089"   
          initializeData="c:\myListener.log" />  
        <add name="MyEventListener"  
          type="System.Diagnostics.EventLogTraceListener,   
            system, version=1.0.3300.0, Culture=neutral,   
            PublicKeyToken=b77a5c561934e089"  
          initializeData="MyConfigEventLog"/>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Diagnostics.TraceListener>   
 [Esquema de la configuración de seguimiento y depuración](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
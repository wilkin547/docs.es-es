---
title: "Elemento &lt;remove&gt; de &lt;listeners&gt; de &lt;trace&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<remove> (elemento)"
  - "remove (elemento)"
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# Elemento &lt;remove&gt; de &lt;listeners&gt; de &lt;trace&gt;
Quita un agente de escucha de la colección **Listeners**.  
  
## Sintaxis  
  
```  
  
<remove name="listener name" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|**nombre**|Atributo necesario.<br /><br /> Nombre del agente de escucha que se va a quitar de la colección **Listeners**.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`listeners`|Especifica un agente de escucha que recopila, almacena y enruta mensajes.  Los agentes de escucha dirigen el resultado de la traza a un destino apropiado.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, y el nivel donde se establece un modificador de seguimiento.|  
|`trace`|Configura el servicio de traza de ASP.NET.|  
  
## Comentarios  
  
> [!NOTE]
>  Al quitar <xref:System.Diagnostics.DefaultTraceListener> de la colección `Listeners`, se modifica el comportamiento de los métodos <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=fullName> y <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=fullName>.  Llamar al método `Assert` o `Fail` genera normalmente la aparición de un cuadro de mensaje, pero éste no se muestra si <xref:System.Diagnostics.DefaultTraceListener> no está en la colección `Listeners`.  
  
## Ejemplo  
 En el siguiente ejemplo se muestra cómo quitar el agente de escucha de traza predeterminado de la colección **Listeners**.  
  
```  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <remove name="Default" />  
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
---
title: "Elemento &lt;clear&gt; de &lt;listeners&gt; de &lt;trace&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<clear> (elemento) para <listeners> de <trace>"
  - "clear (elemento) para <listeners> de <trace>"
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Elemento &lt;clear&gt; de &lt;listeners&gt; de &lt;trace&gt;
Borra la colección `Listeners` para traza.  
  
## Sintaxis  
  
```  
<clear/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, y el nivel donde se establece un modificador de seguimiento.|  
|`trace`|Contiene agentes de escucha que recopilan, almacenan y enrutan mensajes de traza.|  
|`listeners`|Contiene agentes de escucha que recopilan, almacenan y enrutan mensajes.  Los agentes de escucha dirigen el resultado de la traza a un destino apropiado.|  
  
## Comentarios  
 El elemento `<clear>` quita todos los agentes de escucha de la colección `Listeners` para traza.  Puede utilizar el elemento `<clear>` antes de utilizar el elemento `<add>` para asegurarse de que no hay ningún otro agente de escucha activo en la colección.  
  
 Puede borrar mediante programación la colección `Listeners` llamando al método <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> de la propiedad <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=fullName> \(`System.Diagnostics.Trace.Listeners.Clear()`\).  
  
 Este elemento se puede utilizar en el archivo de configuración del equipo \(Machine.config\) y en el archivo de configuración de la aplicación.  
  
> [!NOTE]
>  El elemento `<clear>` quita <xref:System.Diagnostics.DefaultTraceListener> de la colección `Listeners`, modificando el comportamiento de los métodos <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=fullName> y <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=fullName>.  Llamar a un método `Assert` o `Fail` normalmente desencadena la aparición de un cuadro de mensaje.  Sin embargo, el cuadro de mensaje no se muestra si <xref:System.Diagnostics.DefaultTraceListener> no está en la colección `Listeners`.  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo utilizar el elemento `<clear>` antes de usar el elemento `<add>` para agregar el agente de escucha `console` a la colección `Listeners` para el origen de traza.  
  
```  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <clear/>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>   
```  
  
## Vea también  
 <xref:System.Diagnostics.Trace.Listeners%2A>   
 <xref:System.Diagnostics.Trace>   
 <xref:System.Diagnostics.Debug>   
 <xref:System.Diagnostics.TraceSource>   
 [Esquema de la configuración de seguimiento y depuración](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)   
 [\<remove\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)   
 [Trace Listeners](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
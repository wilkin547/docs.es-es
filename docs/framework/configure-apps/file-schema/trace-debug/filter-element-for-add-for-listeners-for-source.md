---
title: "Elemento &lt;filter&gt; para &lt;add&gt; de &lt;listeners&gt; de &lt;source&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#filter"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<filter> (elemento) para <add> de <listeners> de <source>"
  - "filter (elemento) para <add> de <listeners> de <source>"
  - "initializeData (atributo)"
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# Elemento &lt;filter&gt; para &lt;add&gt; de &lt;listeners&gt; de &lt;source&gt;
Agrega un filtro a un agente de escucha de la colección `Listeners` para un origen de traza.  
  
## Sintaxis  
  
```  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`type`|Atributo necesario.<br /><br /> Especifica el tipo del filtro, que debería heredar de la clase <xref:System.Diagnostics.TraceFilter>.  Puede utilizar el nombre del tipo completo con el espacio de nombres, que corresponde a la propiedad <xref:System.Type.FullName%2A> del tipo, o bien, usar el nombre de tipo completo incluyendo la información del ensamblado, que corresponde a la propiedad <xref:System.Type.AssemblyQualifiedName%2A>.  Para obtener información detallada sobre los nombres completos de tipos, vea [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Atributo opcional.<br /><br /> Cadena pasada al constructor de la clase de filtro especificada.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, y el nivel donde se establece un modificador de seguimiento.|  
|`sources`|Contiene orígenes de traza que inician mensajes de traza.|  
|`source`|Especifica un origen de traza que inicia mensajes de traza.|  
|`listeners`|Contiene agentes de escucha que recopilan, almacenan y enrutan mensajes.  Los agentes de escucha dirigen el resultado de la traza a un destino apropiado.|  
|`add`|Agrega un agente de escucha a la colección `Listeners` de un origen de traza.|  
  
## Comentarios  
 El elemento `<filter>` debe estar contenido en un elemento `<add>` de un agente de origen de escucha de traza que especifica el tipo del agente de escucha, no sólo el nombre de un agente de escucha definido en un [\<sharedListeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).  Si el agente de escucha está definido en [\<sharedListeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), el filtro de ese agente de escucha debe estar definido en ese elemento.  
  
 Este elemento se puede utilizar en el archivo de configuración del equipo \(Machine.config\) y en el archivo de configuración de la aplicación.  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo utilizar el elemento `<filter>` para agregar un filtro al agente de escucha `console` de la colección `Listeners` del origen de traza `myTraceSource`, especificando el nivel de eventos del filtro como `Error`.  
  
```  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" switchName="SourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="SourceSwitch" value="Warning" />  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Diagnostics.TraceSource>   
 <xref:System.Diagnostics.TraceListener>   
 <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=fullName>   
 <xref:System.Diagnostics.TraceFilter>   
 [Esquema de la configuración de seguimiento y depuración](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
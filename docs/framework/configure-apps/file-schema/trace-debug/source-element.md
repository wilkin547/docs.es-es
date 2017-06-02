---
title: "&lt;source&gt; (Elemento) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#source"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<source> (elemento)"
  - "source (elemento)"
ms.assetid: ecf86505-735d-4844-aaba-266fdd134218
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# &lt;source&gt; (Elemento)
Especifica un origen de traza que inicia mensajes de traza.  
  
## Sintaxis  
  
```  
<source>   
  <listeners>...</listeners>  
</source>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`name`|Atributo opcional.<br /><br /> Especifica el nombre del origen de traza.|  
|`switchName`|Atributo opcional.<br /><br /> Especifica el nombre de una instancia de modificador de traza en la aplicación.  Si el modificador no se identifica en un elemento `<switches>`, el valor especifica el nivel del modificador.|  
|`switchType`|Atributo opcional.<br /><br /> Especifica el tipo del modificador de traza.  Si está presente, el tipo debe ser un nombre de clase válido y no puede ser una cadena vacía.|  
|`extraAttribute`|Atributo opcional.<br /><br /> Especifica el valor para una traza que el atributo específico del origen identificado por el método <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> de ese origen de traza.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<listeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|Contiene agentes de escucha que recopilan, almacenan y enrutan mensajes.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, y el nivel donde se establece un modificador de seguimiento.|  
|`sources`|Contiene orígenes de traza que inician mensajes de traza.|  
  
## Comentarios  
 Este elemento se puede utilizar en el archivo de configuración del equipo \(Machine.config\) y en el archivo de configuración de la aplicación.  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo utilizar el elemento `<source>`  para agregar el origen de traza `mySource` y establecer el nivel del modificador de origen denominado `sourceSwitch`.  Se agrega un agente de escucha de traza de la consola que escribe información de traza en la consola.  
  
```  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch" switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter" initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
        <switches>  
           <add name="sourceSwitch" value="Warning" />  
        </switches>    
  </system.diagnostics>   
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de seguimiento y depuración](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)   
 [Trace Switches](../../../../../docs/framework/debug-trace-profile/trace-switches.md)
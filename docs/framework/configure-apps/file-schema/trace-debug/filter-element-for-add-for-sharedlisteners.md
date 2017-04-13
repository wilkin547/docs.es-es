---
title: "Elemento &lt;filter&gt; de &lt;add&gt; de &lt;sharedListeners&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add/filter"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<filter> (elemento) para <add> de <sharedListeners>"
  - "filter (elemento) para <add> de <sharedListeners>"
  - "filtros, agentes de escucha de seguimiento"
  - "initializeData (atributo)"
  - "agentes de escucha de seguimiento, filtros"
ms.assetid: 7d4e7faa-2e4e-4379-ac76-f6cd7f2f8fac
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# Elemento &lt;filter&gt; de &lt;add&gt; de &lt;sharedListeners&gt;
Agrega un filtro a un agente de escucha contenido en la colección `sharedListeners`.  
  
## Sintaxis  
  
```  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|**type**|Atributo necesario.<br /><br /> Especifica el tipo del filtro.  Puede utilizar sólo el nombre completo del tipo \(con el formato de la propiedad <xref:System.Type.FullName%2A?displayProperty=fullName>\), o bien utilizar el nombre de tipo completo que incluya la información del ensamblado \(con el formato de la propiedad <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=fullName>\).  Para obtener información sobre cómo crear un nombre de tipo completo, vea [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|**initializeData**|Atributo opcional.<br /><br /> Cadena pasada al constructor de la clase especificada.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, y el nivel donde se establece un modificador de seguimiento.|  
|`sharedListeners`|Colección de agentes de escucha a los que puede hacer referencia cualquier origen o elemento de seguimiento.|  
|`add`|Agrega un agente de escucha a la colección **sharedListeners**.|  
  
## Comentarios  
 Si hay un agente de escucha definido en un elemento `<add>` del elemento `<sharedListeners>`, el filtro de ese agente de escucha se debe definir en un elemento `<filter>` que sea secundario del elemento `<add>`.  
  
 Este elemento se puede utilizar en el archivo de configuración del equipo \(Machine.config\) y en el archivo de configuración de la aplicación.  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo utilizar el elemento `<filter>` para agregar un filtro al agente de escucha `console` de la colección `sharedListeners`.  
  
```  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" >  
        <listeners>  
          <add name="console" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="console"   
        type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"   
          initializeData="Error" />  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Diagnostics.TraceFilter>   
 <xref:System.Diagnostics.TraceListener>   
 <xref:System.Diagnostics.TraceSource>   
 [Esquema de la configuración de seguimiento y depuración](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
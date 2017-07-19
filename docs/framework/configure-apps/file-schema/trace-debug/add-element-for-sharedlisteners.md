---
title: "Elemento &lt;add&gt; para &lt;sharedListeners&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<add> (elemento) para <sharedListeners>"
  - "agregar elemento para <sharedListeners>"
  - "initializeData (atributo)"
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# Elemento &lt;add&gt; para &lt;sharedListeners&gt;
Agrega un agente de escucha a la colección `sharedListeners`.  `sharedListeners` es una colección de agentes de escucha a los que puede hacer referencia cualquier [\<source\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) o [\<trace\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md).  De forma predeterminada, los agentes de escucha de la colección `sharedListeners` no se colocan en una colección `Listeners`.  Deben agregarse por nombre al [\<source\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) o [\<trace\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md).  No es posible obtener los agentes de escucha en la colección `sharedListeners` mediante código en tiempo de ejecución.  
  
## Sintaxis  
  
```  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`name`|Atributo necesario.<br /><br /> Especifica el nombre del agente de escucha utilizado para agregar el agente de escucha compartido a una colección `Listeners`.|  
|`type`|Atributo necesario.<br /><br /> Especifica el tipo del agente de escucha.  Debe utilizar una cadena que cumpla los requisitos enumerados en [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Atributo opcional.<br /><br /> Cadena pasada al constructor de la clase especificada.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<filter\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|Agrega un filtro a un agente de escucha contenido en la colección `sharedListeners`.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, y el nivel donde se establece un modificador de seguimiento.|  
|`sharedListeners`|Colección de agentes de escucha a los que puede hacer referencia cualquier origen o elemento de seguimiento.|  
  
## Comentarios  
 Las clases de agente de escucha incluidas en .NET Framework se derivan de la clase <xref:System.Diagnostics.TraceListener>.  El valor del atributo `name` se utiliza para agregar el agente de escucha compartido a una colección `Listeners` para un seguimiento o un origen de seguimiento.  El valor del atributo `initializeData` depende del tipo de agente de escucha que se cree.  No todos los agentes de escucha de traza requieren que se especifique `initializeData`.  
  
> [!NOTE]
>  Cuando se utiliza el atributo `initializeData`, puede aparecer la advertencia del compilador "No se ha declarado el atributo 'initializeData'". Esta advertencia se produce porque la configuración se valida con arreglo a la clase base abstracta <xref:System.Diagnostics.TraceListener>, que no reconoce el atributo `initializeData`.  Por lo general, puede hacer caso omiso de esta advertencia en las implementaciones de agentes de escucha de traza que tienen un constructor que toma un parámetro.  
  
 En la tabla siguiente se muestran los agentes de escucha de traza incluidos en .NET Framework y se describe el valor de sus atributos `initializeData`.  
  
|Clase de agente de escucha de traza|Valor del atributo initializeData|  
|-----------------------------------------|---------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|El valor de `useErrorStream` para el constructor <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>.  Establezca el atributo `initializeData` en "`true`" para escribir los resultados de la traza y la depuración en el flujo estándar de error; establézcalo en "`false`" para escribir en el flujo de salida estándar.|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|Nombre del archivo en el que <xref:System.Diagnostics.DelimitedListTraceListener> va a escribir.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=fullName>|Nombre de un origen existente del registro de eventos.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=fullName>|Nombre del archivo en el que escribe <xref:System.Diagnostics.EventSchemaTraceListener>.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=fullName>|Nombre del archivo en el que escribe <xref:System.Diagnostics.TextWriterTraceListener>.|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|Nombre del archivo en el que escribe <xref:System.Diagnostics.XmlWriterTraceListener>.|  
  
## Archivo de configuración  
 Este elemento se puede utilizar en el archivo de configuración del equipo \(Machine.config\) y en el archivo de configuración de la aplicación.  
  
## Ejemplo  
 El ejemplo siguiente se muestra cómo utilizar los elementos de `<add>` para agregar <xref:System.Diagnostics.TextWriterTraceListener>`textListener` a la colección de `sharedListeners` .   `textListener` se agrega por nombre a la colección de `Listeners` para el origen de traza `TraceSourceApp`.  El agente de escucha `textListener` escribe el resultado de la traza en el archivo myListener.log.  
  
```  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"   
        type="System.Diagnostics.TextWriterTraceListener"   
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>   
```  
  
## Vea también  
 <xref:System.Diagnostics.TraceSource>   
 <xref:System.Diagnostics.TraceListener>   
 [Esquema de la configuración de seguimiento y depuración](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)   
 [Trace Listeners](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
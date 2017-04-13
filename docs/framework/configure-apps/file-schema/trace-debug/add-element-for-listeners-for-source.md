---
title: "Elemento &lt;add&gt; de &lt;listeners&gt; de &lt;source&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<add> (elemento) para <listeners> de <source>"
  - "add (elemento) para <listeners> de <source>"
  - "initializeData (atributo)"
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# Elemento &lt;add&gt; de &lt;listeners&gt; de &lt;source&gt;
Agrega un agente de escucha a la colección `Listeners` de un origen de traza.  
  
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
|`type`|Atributo necesario.<br /><br /> Especifica el tipo del agente de escucha.  Debe utilizar una cadena que cumpla los requisitos enumerados en [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Atributo opcional.<br /><br /> Cadena pasada al constructor de la clase especificada.  Si la clase no tiene un constructor que toma una cadena, se inicia una excepción <xref:System.Configuration.ConfigurationException>.|  
|`name`|Atributo opcional.<br /><br /> Especifica el nombre del agente de escucha.|  
|`traceOutputOptions`|Atributo opcional.<br /><br /> Especifica el valor de propiedad <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> para el agente de escucha de traza.|  
|\[atributos personalizados\]|Atributos opcionales.<br /><br /> Especifica el valor para los atributos específicos del agente de escucha identificados por el método <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> de ese agente de escucha.  <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> es un ejemplo de un atributo adicional único de la clase <xref:System.Diagnostics.DelimitedListTraceListener>.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<filter\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-source.md)|Agrega un filtro a un agente de escucha de la colección `Listeners` para un origen de traza.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, y el nivel donde se establece un modificador de seguimiento.|  
|`sources`|Contiene orígenes de traza que inician mensajes de traza.|  
|`source`|Especifica un origen de traza que inicia mensajes de traza.|  
|`listeners`|Especifica agentes de escucha que recopilan, almacenan y enrutan mensajes.|  
  
## Comentarios  
 Las clases de agente de escucha incluidas en .NET Framework se derivan de la clase <xref:System.Diagnostics.TraceListener>.  
  
 Si no especifica el atributo `name` del agente de escucha de traza, la propiedad <xref:System.Diagnostics.TraceListener.Name%2A> del agente de escucha de traza tiene como valor predeterminado una cadena vacía \(""\).  Si su aplicación tiene sólo un agente de escucha, puede agregarlo sin especificar un nombre y quitarlo especificando una cadena vacía para el nombre.  Sin embargo, si su aplicación tiene más de un agente de escucha, debe especificar un nombre único para cada agente de escucha de traza, de forma que pueda identificar y administrar los agentes de escucha de traza individualmente dentro de la colección <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=fullName>.  
  
> [!NOTE]
>  Agregar más de un agente de escucha de traza del mismo tipo y con el mismo nombre tiene como resultado que sólo se agregue a la colección `Listeners` un agente de escucha de traza con ese tipo y nombre.  Sin embargo, puede agregar mediante programación varios agentes de escucha idénticos a la colección `Listeners`.  
  
 El valor del atributo `initializeData` depende del tipo de agente de escucha que se cree.  No todos los agentes de escucha de traza requieren que se especifique `initializeData`.  
  
> [!NOTE]
>  Cuando se utiliza el atributo `initializeData`, puede aparecer la advertencia del compilador "No se ha declarado el atributo 'initializeData'". Esta advertencia se produce porque la configuración se valida con arreglo a la clase base abstracta <xref:System.Diagnostics.TraceListener>, que no reconoce el atributo `initializeData`.  Por lo general, puede hacer caso omiso de esta advertencia en las implementaciones de agentes de escucha de traza que tienen un constructor que toma un parámetro.  
  
 En la tabla siguiente se muestran los agentes de escucha de traza incluidos en .NET Framework y se describe el valor de sus atributos `initializeData`.  
  
|Clase de agente de escucha de traza|Valor del atributo initializeData|  
|-----------------------------------------|---------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=fullName>|El valor de `useErrorStream` para el constructor <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>.  Establezca el atributo `initializeData` en "`true`" para escribir los resultados de la traza y la depuración en el flujo estándar de error; establézcalo en "`false`" para escribir en el flujo de salida estándar.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=fullName>|Nombre del archivo en el que <xref:System.Diagnostics.DelimitedListTraceListener> va a escribir.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=fullName>|Nombre de un origen existente del registro de eventos.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=fullName>|Nombre del archivo en el que escribe <xref:System.Diagnostics.EventSchemaTraceListener>.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=fullName>|Nombre del archivo en el que escribe <xref:System.Diagnostics.TextWriterTraceListener>.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=fullName>|Nombre del archivo en el que escribe <xref:System.Diagnostics.XmlWriterTraceListener>.|  
  
## Archivo de configuración  
 Este elemento se puede utilizar en el archivo de configuración del equipo \(Machine.config\) y en el archivo de configuración de la aplicación.  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo utilizar elementos `<add>` para agregar los agentes de escucha `console` y `textListener` a la colección `Listeners` del origen de traza `TraceSourceApp`.  El agente de escucha `textListener` escribe el resultado de la traza en el archivo myListener.log.  
  
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
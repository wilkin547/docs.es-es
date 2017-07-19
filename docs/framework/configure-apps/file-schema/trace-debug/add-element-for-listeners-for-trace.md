---
title: "Elemento &lt;add&gt; de &lt;listeners&gt; de &lt;trace&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<add> (elemento) para <listeners>"
  - "agregar elemento para <listeners>"
  - "initializeData (atributo)"
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
caps.latest.revision: 24
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 22
---
# Elemento &lt;add&gt; de &lt;listeners&gt; de &lt;trace&gt;
Agrega un agente de escucha a la colección **Listeners**.  
  
## Sintaxis  
  
```  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|**type**|Atributo necesario.<br /><br /> Especifica el tipo del agente de escucha.  Se debe utilizar una cadena que cumpla los requisitos especificados en [Especificar nombres de tipo completos](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|**initializeData**|Atributo opcional.<br /><br /> Cadena pasada al constructor de la clase especificada.|  
|**nombre**|Atributo opcional.<br /><br /> Especifica el nombre del agente de escucha.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<filter\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|Agrega un filtro a un agente de escucha de la colección `Listeners` para una traza.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`listeners`|Especifica un agente de escucha que recopila, almacena y enruta mensajes.  Los agentes de escucha dirigen el resultado de la traza a un destino apropiado.|  
|`system.diagnostics`|Especifica el elemento raíz de la sección de configuración de ASP.NET.|  
|`trace`|Contiene agentes de escucha que recopilan, almacenan y enrutan mensajes de traza.|  
  
## Comentarios  
 Las clases <xref:System.Diagnostics.Debug> y <xref:System.Diagnostics.Trace> comparten la misma colección **Listeners**.  Si se agrega un objeto de agente de escucha a la colección en una de estas clases, la otra clase utilizará el mismo agente de escucha.  Las clases de agente de escucha derivan de la [clase TraceListener](frlrfSystemDiagnosticsTraceListenerClassTopic).  
  
 Si no especifica el atributo `name` del agente de escucha de traza, el atributo <xref:System.Diagnostics.TraceListener.Name%2A> del agente de escucha de traza tiene como valor predefinido una cadena vacía \(""\).  Si su aplicación tiene sólo un agente de escucha, puede agregarlo sin especificar un nombre y quitarlo especificando una cadena vacía para el nombre.  Sin embargo, si su aplicación tiene más de un agente de escucha, debe especificar nombres únicos para cada agente de escucha de traza, de forma que pueda identificar y administrar los agentes de escucha de traza individualmente dentro de las colecciones <xref:System.Diagnostics.Debug.Listeners%2A> y <xref:System.Diagnostics.Trace.Listeners%2A>.  
  
> [!NOTE]
>  Agregar más de un agente de escucha de traza del mismo tipo y con el mismo nombre tiene como resultado que sólo se agregue a la colección `Listeners` un agente de escucha de traza con ese tipo y nombre.  Sin embargo, puede agregar mediante programación varios agentes de escucha idénticos a la colección `Listeners`.  
  
 El valor del atributo **initializeData** depende del tipo de agente de escucha que se cree.  No todos los agentes de escucha de traza requieren que se especifique **initializeData**.  
  
> [!NOTE]
>  Cuando se utiliza el atributo `initializeData`, puede aparecer la advertencia del compilador "No se ha declarado el atributo 'initializeData'". Esta advertencia se produce porque la configuración se valida con arreglo a la clase base abstracta <xref:System.Diagnostics.TraceListener>, que no reconoce el atributo `initializeData`.  Por lo general, puede hacer caso omiso de esta advertencia en las implementaciones de agentes de escucha de traza que tienen un constructor que toma un parámetro.  
  
 En la tabla siguiente se muestran los agentes de escucha de traza incluidos en .NET Framework y se describe el valor de sus atributos **initializeData**.  
  
|Clase de agente de escucha de traza|Valor del atributo initializeData|  
|-----------------------------------------|---------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=fullName>|El valor de `useErrorStream` para el constructor <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>.  Establezca el atributo `initializeData` en "`true`" para escribir los resultados de traza y depuración en <xref:System.Console.Error%2A?displayProperty=fullName>; establézcalo en "`false`" para escribir en <xref:System.Console.Out%2A?displayProperty=fullName>.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=fullName>|Nombre del archivo en el que <xref:System.Diagnostics.DelimitedListTraceListener> va a escribir.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=fullName>|El nombre del nombre de un origen de registro de eventos existente.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=fullName>|Nombre del archivo en el que escribe <xref:System.Diagnostics.EventSchemaTraceListener>.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=fullName>|Nombre del archivo en el que escribe <xref:System.Diagnostics.TextWriterTraceListener>.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=fullName>|Nombre del archivo en el que escribe <xref:System.Diagnostics.XmlWriterTraceListener>.|  
  
## Ejemplo  
 El ejemplo siguiente se muestra cómo utilizar los elementos de **\<agregar\>** para agregar agentes de escucha `MyListener` y `MyEventListener` a la colección de **Listeners** .  `MyListener` crea un archivo denominado `MyListener.log` y escribe el resultado en el archivo.  `MyEventListener` crea una entrada en el registro de eventos.  
  
```  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
            <add name="MyEventListener"  
                 type="System.Diagnostics.EventLogTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"                 initializeData="MyConfigEventLog"/>  
            <add name="configConsoleListener"  
                 type="System.Diagnostics.ConsoleTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Diagnostics.Trace>   
 <xref:System.Diagnostics.Debug>   
 <xref:System.Diagnostics.EventLogTraceListener>   
 <xref:System.Diagnostics.ConsoleTraceListener>   
 <xref:System.Diagnostics.TextWriterTraceListener>   
 [Esquema de la configuración de seguimiento y depuración](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)   
 [Trace Listeners](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
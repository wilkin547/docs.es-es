---
title: <add> elemento de <listeners> para <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: eb3e9cf4a6d138998cfde865cda8ed4146be26d0
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088985"
---
# <a name="add-element-for-listeners-for-trace"></a>\<agregar > elemento para \<agentes de escucha > para \<> de seguimiento
Agrega un agente de escucha a la colección **Listeners** .  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](trace-element.md) > de seguimiento\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**agentes de escucha**](listeners-element-for-trace.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**agregar >**

## <a name="syntax"></a>Sintaxis  
  
```xml  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|**type**|Atributo necesario.<br /><br /> Especifica el tipo del agente de escucha. Debe utilizar una cadena que cumpla los requisitos especificados en [especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|**initializeData**|Atributo opcional.<br /><br /> Cadena pasada al constructor de la clase especificada.|  
|**name**|Atributo opcional.<br /><br /> Especifica el nombre del agente de escucha.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-listeners-for-trace.md)|Agrega un filtro a un agente de escucha en la colección de `Listeners` para un seguimiento.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`listeners`|Especifica un agente de escucha que recopila, almacena y enruta los mensajes. Los agentes de escucha dirigen los resultados del seguimiento a un destino adecuado.|  
|`system.diagnostics`|Especifica el elemento raíz de la sección de configuración de ASP.NET.|  
|`trace`|Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.|  
  
## <a name="remarks"></a>Comentarios  
 Las clases <xref:System.Diagnostics.Debug> y <xref:System.Diagnostics.Trace> comparten la misma colección **Listeners** . Si agrega un objeto de escucha a la colección en una de estas clases, la otra clase utiliza el mismo agente de escucha. Las clases de agente de escucha derivan de la <xref:System.Diagnostics.TraceListener>.  
  
 Si no especifica el atributo `name` del agente de escucha de seguimiento, el <xref:System.Diagnostics.TraceListener.Name%2A> del agente de escucha de seguimiento tiene como valor predeterminado una cadena vacía (""). Si la aplicación tiene solo un agente de escucha, puede agregarlo sin especificar un nombre y quitarlo especificando una cadena vacía para el nombre. Sin embargo, si la aplicación tiene más de un agente de escucha, debe especificar nombres únicos para cada agente de escucha de seguimiento, lo que le permite identificar y administrar agentes de escucha de seguimiento individuales dentro de las colecciones <xref:System.Diagnostics.Debug.Listeners%2A> y <xref:System.Diagnostics.Trace.Listeners%2A>.  
  
> [!NOTE]
> Al agregar más de un agente de escucha de seguimiento del mismo tipo y con el mismo nombre, solo se agrega un agente de escucha de seguimiento de ese tipo y nombre a la colección de `Listeners`. Sin embargo, puede agregar mediante programación varios agentes de escucha idénticos a la colección de `Listeners`.  
  
 El valor del atributo **initializeData** depende del tipo de agente de escucha que se cree. No todos los agentes de escucha de seguimiento requieren que se especifique **initializeData**.  
  
> [!NOTE]
> Al usar el atributo `initializeData`, puede obtener la advertencia del compilador "el atributo ' initializeData ' no se ha declarado". Esta advertencia se produce porque los valores de configuración se validan con la clase base abstracta <xref:System.Diagnostics.TraceListener>, que no reconoce el atributo `initializeData`. Normalmente, puede omitir esta advertencia para las implementaciones del agente de escucha de seguimiento que tienen un constructor que toma un parámetro.  
  
 En la tabla siguiente se muestran los agentes de escucha de seguimiento incluidos en el .NET Framework y se describe el valor de sus atributos **initializeData** .  
  
|Clase de agente de escucha de seguimiento|valor del atributo initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|El valor `useErrorStream` del constructor de <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>.  Establezca el atributo `initializeData` en "`true`" para escribir los resultados de seguimiento y depuración en <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" para escribir en <xref:System.Console.Out%2A?displayProperty=nameWithType>.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Nombre del archivo en el que se escribe el <xref:System.Diagnostics.DelimitedListTraceListener>.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Nombre del nombre de un origen de registro de eventos existente.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Nombre del archivo en el que escribe el <xref:System.Diagnostics.EventSchemaTraceListener>.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Nombre del archivo en el que escribe el <xref:System.Diagnostics.TextWriterTraceListener>.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Nombre del archivo en el que escribe el <xref:System.Diagnostics.XmlWriterTraceListener>.|  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar **\<agregar >** elementos para agregar los agentes de escucha `MyListener` y `MyEventListener` a la colección **Listeners** . `MyListener` crea un archivo denominado `MyListener.log` y escribe el resultado en el archivo. `MyEventListener` crea una entrada en el registro de eventos.  
  
```xml  
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
  
## <a name="see-also"></a>Vea también

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [Esquema de la configuración de seguimiento y depuración](index.md)
- [Agentes de escucha de seguimiento](../../../debug-trace-profile/trace-listeners.md)

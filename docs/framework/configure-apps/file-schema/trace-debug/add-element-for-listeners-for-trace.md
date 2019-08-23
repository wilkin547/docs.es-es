---
title: <add>(Elemento <listeners> ) para<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: d4ff919991ab1505b2845a225706d32cc1e57d0a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920571"
---
# <a name="add-element-for-listeners-for-trace"></a>\<Agregar > elemento para \<los agentes de escucha \<> para el seguimiento >
Agrega un agente de escucha a la colección Listeners.  
  
 \<configuration>  
\<system.diagnostics>  
\<> de seguimiento  
\<listeners>  
\<add>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|**type**|Atributo necesario.<br /><br /> Especifica el tipo del agente de escucha. Debe utilizar una cadena que cumpla los requisitos especificados en [especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|**initializeData**|Atributo opcional.<br /><br /> Cadena pasada al constructor de la clase especificada.|  
|**name**|Atributo opcional.<br /><br /> Especifica el nombre del agente de escucha.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-listeners-for-trace.md)|Agrega un filtro a un agente de escucha de `Listeners` la colección para un seguimiento.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`listeners`|Especifica un agente de escucha que recopila, almacena y enruta los mensajes. Los agentes de escucha dirigen los resultados del seguimiento a un destino adecuado.|  
|`system.diagnostics`|Especifica el elemento raíz de la sección de configuración de ASP.NET.|  
|`trace`|Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.|  
  
## <a name="remarks"></a>Comentarios  
 Las <xref:System.Diagnostics.Debug> clases <xref:System.Diagnostics.Trace> y comparten la misma colección Listeners. Si agrega un objeto de escucha a la colección en una de estas clases, la otra clase utiliza el mismo agente de escucha. Las clases de agente de escucha derivan de <xref:System.Diagnostics.TraceListener>.  
  
 Si no se especifica el `name` atributo del agente de escucha de seguimiento, el <xref:System.Diagnostics.TraceListener.Name%2A> del agente de escucha de seguimiento tiene como valor predeterminado una cadena vacía (""). Si la aplicación tiene solo un agente de escucha, puede agregarlo sin especificar un nombre y quitarlo especificando una cadena vacía para el nombre. Sin embargo, si la aplicación tiene más de un agente de escucha, debe especificar nombres únicos para cada agente de escucha de seguimiento, lo que le permite identificar y administrar agentes de escucha <xref:System.Diagnostics.Debug.Listeners%2A> de <xref:System.Diagnostics.Trace.Listeners%2A> seguimiento individuales dentro de las colecciones y.  
  
> [!NOTE]
> Agregar más de un agente de escucha de seguimiento del mismo tipo y con el mismo nombre da como resultado que solo se agregue a la `Listeners` colección un agente de escucha de seguimiento de ese tipo y nombre. Sin embargo, puede agregar mediante programación varios agentes de escucha idénticos `Listeners` a la colección.  
  
 El valor del atributo **initializeData** depende del tipo de agente de escucha que se cree. No todos los agentes de escucha de seguimiento requieren que se especifique **initializeData**.  
  
> [!NOTE]
> Al usar el `initializeData` atributo, puede obtener la advertencia del compilador "el atributo ' initializeData ' no se ha declarado". Esta advertencia se produce porque la configuración se valida con respecto a la clase <xref:System.Diagnostics.TraceListener>base abstracta, que no reconoce el `initializeData` atributo. Normalmente, puede omitir esta advertencia para las implementaciones del agente de escucha de seguimiento que tienen un constructor que toma un parámetro.  
  
 En la tabla siguiente se muestran los agentes de escucha de seguimiento incluidos en el .NET Framework y se describe el valor de sus atributos **initializeData** .  
  
|Clase de agente de escucha de seguimiento|valor del atributo initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|`useErrorStream` Valor<xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> del constructor.  Establezca el `initializeData` atributo en "`true`" para escribir el resultado de seguimiento y <xref:System.Console.Error%2A?displayProperty=nameWithType>de depuración en; "`false`" para escribir en <xref:System.Console.Out%2A?displayProperty=nameWithType>.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Nombre del archivo <xref:System.Diagnostics.DelimitedListTraceListener> en el que escribe.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Nombre del nombre de un origen de registro de eventos existente.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Nombre del archivo en el que <xref:System.Diagnostics.EventSchemaTraceListener> escribe.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Nombre del archivo en el que <xref:System.Diagnostics.TextWriterTraceListener> escribe.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Nombre del archivo en el que <xref:System.Diagnostics.XmlWriterTraceListener> escribe.|  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar  **\<agregar >** elementos para `MyListener` agregar los agentes de `MyEventListener` escucha y a la colección Listeners. `MyListener`crea un archivo denominado `MyListener.log` y escribe el resultado en el archivo. `MyEventListener`crea una entrada en el registro de eventos.  
  
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

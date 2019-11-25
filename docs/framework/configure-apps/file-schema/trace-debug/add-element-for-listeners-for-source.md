---
title: <add> elemento de <listeners> para <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: c32205310f9fc451a5a55a943f925ee52f65c8a8
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089001"
---
# <a name="add-element-for-listeners-for-source"></a>\<agregar > elemento para \<agentes de escucha > para \<origen >
Agrega un agente de escucha a la colección `Listeners` para un origen de seguimiento.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<orígenes**](sources-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**origen**](source-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**agentes de escucha**](listeners-element-for-source.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**agregar >**

## <a name="syntax"></a>Sintaxis  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`type`|Atributo required, a menos que haga referencia a un agente de escucha en la colección de `sharedListeners`, en cuyo caso solo necesita hacer referencia a él por su nombre (vea el [ejemplo](#example)).<br /><br /> Especifica el tipo del agente de escucha. Debe utilizar una cadena que cumpla los requisitos especificados en [especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Atributo opcional.<br /><br /> Cadena pasada al constructor de la clase especificada. Se produce una <xref:System.Configuration.ConfigurationException> si la clase no tiene un constructor que toma una cadena.|  
|`name`|Atributo opcional.<br /><br /> Especifica el nombre del agente de escucha.|  
|`traceOutputOptions`|Atributo opcional.<br /><br /> Especifica el valor de propiedad <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> para el agente de escucha de seguimiento.|  
|[atributos personalizados]|Atributos opcionales.<br /><br /> Especifica el valor de los atributos específicos del agente de escucha identificados por el método <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> para ese agente de escucha. <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> es un ejemplo de un atributo adicional que es único para la clase <xref:System.Diagnostics.DelimitedListTraceListener>.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-listeners-for-source.md)|Agrega un filtro a un agente de escucha en la colección `Listeners` para un origen de seguimiento.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.|  
|`sources`|Contiene orígenes de seguimiento que inician mensajes de seguimiento.|  
|`source`|Contiene un origen de seguimiento que inicia mensajes de seguimiento.|  
|`listeners`|Especifica los agentes de escucha que recopilan, almacenan y enrutan los mensajes.|  
  
## <a name="remarks"></a>Comentarios  
 Las clases de agente de escucha incluidas con el .NET Framework derivan de la clase <xref:System.Diagnostics.TraceListener>.  
  
 Si no especifica el atributo `name` del agente de escucha de seguimiento, la propiedad <xref:System.Diagnostics.TraceListener.Name%2A> del agente de escucha de seguimiento tiene como valor predeterminado una cadena vacía (""). Si la aplicación tiene solo un agente de escucha, puede agregarlo sin especificar un nombre y puede quitarlo si especifica una cadena vacía para el nombre. Sin embargo, si la aplicación tiene más de un agente de escucha, debe especificar un nombre único para cada agente de escucha de seguimiento, lo que le permite identificar y administrar agentes de escucha de seguimiento individuales en la colección de <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType>.  
  
> [!NOTE]
> Al agregar más de un agente de escucha de seguimiento del mismo tipo y con el mismo nombre, solo se agrega un agente de escucha de seguimiento de ese tipo y nombre a la colección de `Listeners`. Sin embargo, puede agregar mediante programación varios agentes de escucha idénticos a la colección de `Listeners`.  
  
 El valor del atributo `initializeData` depende del tipo de agente de escucha que se cree. No todos los agentes de escucha de seguimiento requieren que se especifique `initializeData`.  
  
> [!NOTE]
> Al usar el atributo `initializeData`, puede obtener la advertencia del compilador "el atributo ' initializeData ' no se ha declarado". Esta advertencia se produce porque los valores de configuración se validan con la clase base abstracta <xref:System.Diagnostics.TraceListener>, que no reconoce el atributo `initializeData`. Normalmente, puede omitir esta advertencia para las implementaciones del agente de escucha de seguimiento que tienen un constructor que toma un parámetro.  
  
 En la tabla siguiente se muestran los agentes de escucha de seguimiento incluidos en el .NET Framework y se describe el valor de sus atributos `initializeData`.  
  
|Clase de agente de escucha de seguimiento|valor del atributo initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|El valor `useErrorStream` del constructor de <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>.  Establezca el atributo `initializeData` en "`true`" para escribir el resultado de seguimiento y de depuración en la secuencia de error estándar. establézcalo en "`false`" para escribir en el flujo de salida estándar.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Nombre del archivo en el que se escribe el <xref:System.Diagnostics.DelimitedListTraceListener>.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Nombre de un origen de registro de eventos existente.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Nombre del archivo en el que escribe el <xref:System.Diagnostics.EventSchemaTraceListener>.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Nombre del archivo en el que escribe el <xref:System.Diagnostics.TextWriterTraceListener>.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Nombre del archivo en el que escribe el <xref:System.Diagnostics.XmlWriterTraceListener>.|  
  
## <a name="configuration-file"></a>Archivo de configuración  
 Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar los elementos `<add>` para agregar los agentes de escucha `console` y `textListener` a la colección de `Listeners` para la `TraceSourceApp`de origen de seguimiento. El agente de escucha de `textListener` escribe la salida del seguimiento en el archivo myListener. log.  
  
```xml  
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
  
## <a name="see-also"></a>Vea también

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [Esquema de la configuración de seguimiento y depuración](index.md)
- [Agentes de escucha de seguimiento](../../../debug-trace-profile/trace-listeners.md)

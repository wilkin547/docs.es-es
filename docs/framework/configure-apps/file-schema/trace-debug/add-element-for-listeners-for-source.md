---
title: <add>(Elemento <listeners> ) para<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: 883eef32172c5a7f900197995b4c57c3d5a84e19
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153690"
---
# <a name="add-element-for-listeners-for-source"></a>\<add>(Elemento \<listeners> ) para\<source>
Agrega un agente de escucha a la colección `Listeners` para un origen de seguimiento.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

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
|`type`|Atributo required, a menos que haga referencia a un agente de escucha en la `sharedListeners` colección, en cuyo caso solo necesita hacer referencia a él por su nombre (vea el [ejemplo](#example)).<br /><br /> Especifica el tipo del agente de escucha. Debe utilizar una cadena que cumpla los requisitos especificados en [especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Atributo opcional.<br /><br /> Cadena pasada al constructor de la clase especificada. <xref:System.Configuration.ConfigurationException>Se produce una excepción si la clase no tiene un constructor que toma una cadena.|  
|`name`|Atributo opcional.<br /><br /> Especifica el nombre del agente de escucha.|  
|`traceOutputOptions`|Atributo opcional.<br /><br /> Especifica el <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> valor de propiedad para el agente de escucha de seguimiento.|  
|[atributos personalizados]|Atributos opcionales.<br /><br /> Especifica el valor para los atributos específicos del agente de escucha identificados por el <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> método para ese agente de escucha. <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A>es un ejemplo de un atributo adicional que es único para la <xref:System.Diagnostics.DelimitedListTraceListener> clase.|  
  
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
 Las clases de agente de escucha incluidas con el .NET Framework derivan de la <xref:System.Diagnostics.TraceListener> clase.  
  
 Si no especifica el `name` atributo del agente de escucha de seguimiento, la <xref:System.Diagnostics.TraceListener.Name%2A> propiedad del agente de escucha de seguimiento tiene como valor predeterminado una cadena vacía (""). Si la aplicación tiene solo un agente de escucha, puede agregarlo sin especificar un nombre y puede quitarlo si especifica una cadena vacía para el nombre. Sin embargo, si la aplicación tiene más de un agente de escucha, debe especificar un nombre único para cada agente de escucha de seguimiento, lo que le permite identificar y administrar agentes de escucha de seguimiento individuales en la <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> colección.  
  
> [!NOTE]
> Agregar más de un agente de escucha de seguimiento del mismo tipo y con el mismo nombre da como resultado que solo se agregue a la colección un agente de escucha de seguimiento de ese tipo y nombre `Listeners` . Sin embargo, puede agregar mediante programación varios agentes de escucha idénticos a la `Listeners` colección.  
  
 El valor del `initializeData` atributo depende del tipo de agente de escucha que se cree. No todos los agentes de escucha de seguimiento requieren que se especifique `initializeData` .  
  
> [!NOTE]
> Al usar el `initializeData` atributo, puede obtener la advertencia del compilador "el atributo ' initializeData ' no se ha declarado". Esta advertencia se produce porque la configuración se valida con respecto a la clase base abstracta <xref:System.Diagnostics.TraceListener> , que no reconoce el `initializeData` atributo. Normalmente, puede omitir esta advertencia para las implementaciones del agente de escucha de seguimiento que tienen un constructor que toma un parámetro.  
  
 En la tabla siguiente se muestran los agentes de escucha de seguimiento incluidos en el .NET Framework y se describe el valor de sus `initializeData` atributos.  
  
|Clase de agente de escucha de seguimiento|valor del atributo initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|`useErrorStream`Valor del <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.  Establezca el `initializeData` atributo en " `true` " para escribir el resultado de seguimiento y depuración en la secuencia de error estándar; establézcalo en " `false` " para escribir en el flujo de salida estándar.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Nombre del archivo en el que <xref:System.Diagnostics.DelimitedListTraceListener> va a escribir.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Nombre de un origen existente del registro de eventos.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Nombre del archivo en el que <xref:System.Diagnostics.EventSchemaTraceListener> escribe.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Nombre del archivo en el que <xref:System.Diagnostics.TextWriterTraceListener> escribe.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Nombre del archivo en el que <xref:System.Diagnostics.XmlWriterTraceListener> escribe.|  
  
## <a name="configuration-file"></a>Archivo de configuración  
 Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar `<add>` los elementos para agregar los agentes `console` de escucha y `textListener` a la `Listeners` colección para el origen de seguimiento `TraceSourceApp` . El `textListener` agente de escucha escribe la salida del seguimiento en el archivo myListener. log.  
  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [Esquema de la configuración de seguimiento y depuración](index.md)
- [Agentes de escucha de seguimiento](../../../debug-trace-profile/trace-listeners.md)

---
title: <add>Elemento <listeners> para for<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: 883eef32172c5a7f900197995b4c57c3d5a84e19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153690"
---
# <a name="add-element-for-listeners-for-source"></a>\<agregue> \<Element para \<los agentes de escucha> para el origen>
Agrega un agente de escucha a la colección `Listeners` para un origen de seguimiento.  

[**\<configuración>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<fuentes>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<fuente>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oyentes>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<añadir>**

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
|`type`|Atributo requerido, a menos que haga `sharedListeners` referencia a un agente de escucha de la colección, en cuyo caso solo necesita hacer referencia a él por su nombre (consulte el [ejemplo](#example)).<br /><br /> Especifica el tipo del agente de escucha. Debe utilizar una cadena que cumpla los requisitos especificados en Especificación de nombres de [tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Atributo opcional.<br /><br /> La cadena que se pasa al constructor de la clase especificada. A <xref:System.Configuration.ConfigurationException> se produce si la clase no tiene un constructor que toma una cadena.|  
|`name`|Atributo opcional.<br /><br /> Especifica el nombre del agente de escucha.|  
|`traceOutputOptions`|Atributo opcional.<br /><br /> Especifica el <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> valor de propiedad para el agente de escucha de seguimiento.|  
|[atributos personalizados]|Atributos opcionales.<br /><br /> Especifica el valor de los atributos <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> específicos del agente de escucha identificados por el método para ese agente de escucha. <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A>es un ejemplo de un <xref:System.Diagnostics.DelimitedListTraceListener> atributo adicional único para la clase.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<>de filtro](filter-element-for-add-for-listeners-for-source.md)|Agrega un filtro a un agente de escucha en la colección `Listeners` para un origen de seguimiento.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.|  
|`sources`|Contiene orígenes de seguimiento que inician mensajes de seguimiento.|  
|`source`|Contiene un origen de seguimiento que inicia mensajes de seguimiento.|  
|`listeners`|Especifica los agentes de escucha que recopilan, almacenan y enrutan mensajes.|  
  
## <a name="remarks"></a>Observaciones  
 Las clases de agente de escucha <xref:System.Diagnostics.TraceListener> incluidas con .NET Framework derivan de la clase.  
  
 Si no especifica `name` el atributo del agente <xref:System.Diagnostics.TraceListener.Name%2A> de escucha de seguimiento, la propiedad del agente de escucha de seguimiento tiene como valor predeterminado una cadena vacía (""). Si la aplicación solo tiene un agente de escucha, puede agregarlo sin especificar un nombre y puede quitarlo especificando una cadena vacía para el nombre. Sin embargo, si la aplicación tiene más de un agente de escucha, debe especificar un nombre <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> único para cada agente de escucha de seguimiento, lo que le permite identificar y administrar agentes de escucha de seguimiento individuales en la colección.  
  
> [!NOTE]
> Agregar más de un agente de escucha de seguimiento del mismo tipo y con el `Listeners` mismo nombre da como resultado que solo se agregue un agente de escucha de seguimiento de ese tipo y nombre a la colección. Sin embargo, puede agregar mediante programación varios agentes de escucha idénticos a la `Listeners` colección.  
  
 El valor `initializeData` del atributo depende del tipo de agente de escucha que cree. No todos los agentes `initializeData`de escucha de seguimiento requieren que especifique .  
  
> [!NOTE]
> Cuando se `initializeData` utiliza el atributo, puede obtener la advertencia del compilador "El atributo 'initializeData' no se declara." Esta advertencia se produce porque los valores de <xref:System.Diagnostics.TraceListener>configuración se validan con la clase base abstracta, que no reconoce el `initializeData` atributo. Normalmente, puede omitir esta advertencia para las implementaciones de agente de escucha de seguimiento que tienen un constructor que toma un parámetro.  
  
 En la tabla siguiente se muestran los agentes de escucha de `initializeData` seguimiento que se incluyen con .NET Framework y se describe el valor de sus atributos.  
  
|Clase de escucha de seguimiento|initializeData valor del atributo|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|El `useErrorStream` valor <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> del constructor.  Establezca `initializeData` el atributo`true`en " " para escribir la salida de seguimiento y depuración en la secuencia de errores estándar; establecerlo en`false`" " para escribir en el flujo de salida estándar.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Nombre del archivo en el que <xref:System.Diagnostics.DelimitedListTraceListener> va a escribir.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Nombre de un origen existente del registro de eventos.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|El nombre del archivo <xref:System.Diagnostics.EventSchemaTraceListener> en el que escribe el archivo.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|El nombre del archivo <xref:System.Diagnostics.TextWriterTraceListener> en el que escribe el archivo.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|El nombre del archivo <xref:System.Diagnostics.XmlWriterTraceListener> en el que escribe el archivo.|  
  
## <a name="configuration-file"></a>Archivo de configuración  
 Este elemento se puede utilizar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente `<add>` se muestra cómo `console` `textListener` utilizar `Listeners` elementos para `TraceSourceApp`agregar los agentes de escucha y a la colección para el origen de seguimiento. El `textListener` agente de escucha escribe la salida de seguimiento en el archivo myListener.log.  
  
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
- [Esquema de configuración de seguimiento y depuración](index.md)
- [Agentes de escucha de seguimiento](../../../debug-trace-profile/trace-listeners.md)

---
title: Elemento <add> para <sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
ms.openlocfilehash: 5588892ec75a791eda1eb043936c0af95e79354e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153612"
---
# <a name="add-element-for-sharedlisteners"></a>\<agregue> \<Element para sharedListeners>
Agrega un agente de escucha a la colección `sharedListeners`. `sharedListeners`es una colección de [ \<](source-element.md) agentes de escucha a los que puede hacer referencia cualquier>de origen o [ \<>](trace-element.md) de seguimiento.  De forma predeterminada, `sharedListeners` los agentes de `Listeners` escucha de la colección no se colocan en una colección. Deben agregarse por nombre al [ \<>](source-element.md) de origen o [ \<seguimiento>](trace-element.md). No es posible obtener los agentes de escucha de la `sharedListeners` colección en código en tiempo de ejecución.  

[**\<configuración>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<añadir>**

## <a name="syntax"></a>Sintaxis  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`name`|Atributo necesario.<br /><br /> Especifica el nombre del agente de escucha que se `Listeners` usa para agregar el agente de escucha compartido a una colección.|  
|`type`|Atributo necesario.<br /><br /> Especifica el tipo del agente de escucha. Debe utilizar una cadena que cumpla los requisitos especificados en Especificación de nombres de [tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Atributo opcional.<br /><br /> La cadena que se pasa al constructor de la clase especificada.|  
|`traceOutputOptions`|Atributo opcional.<br/><br/>Representación de cadena <xref:System.Diagnostics.TraceOptions> de uno o varios miembros de enumeración que indica los datos que se van a escribir en la salida de seguimiento. Varios elementos están separados por comas. El valor predeterminado es "Ninguno".|

### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<>de filtro](filter-element-for-add-for-sharedlisteners.md)|Agrega un filtro a un agente de escucha en la colección `sharedListeners`.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.|  
|`sharedListeners`|Colección de agentes de escucha a los que puede hacer referencia cualquier elemento de origen o de seguimiento.|  
  
## <a name="remarks"></a>Observaciones  
 Las clases de agente de escucha <xref:System.Diagnostics.TraceListener> incluidas con .NET Framework derivan de la clase. El valor `name` del atributo se utiliza para `Listeners` agregar el agente de escucha compartido a una colección para un seguimiento o un origen de seguimiento. El valor `initializeData` del atributo depende del tipo de agente de escucha que cree. No todos los agentes `initializeData`de escucha de seguimiento requieren que especifique .  
  
> [!NOTE]
> Cuando se `initializeData` utiliza el atributo, puede obtener la advertencia del compilador "El atributo 'initializeData' no se declara." Esta advertencia se produce porque los valores de <xref:System.Diagnostics.TraceListener>configuración se validan con la clase base abstracta, que no reconoce el `initializeData` atributo. Normalmente, puede omitir esta advertencia para las implementaciones de agente de escucha de seguimiento que tienen un constructor que toma un parámetro.  
  
 En la tabla siguiente se muestran los agentes de escucha de `initializeData` seguimiento que se incluyen con .NET Framework y se describe el valor de sus atributos.  
  
|Clase de escucha de seguimiento|initializeData valor del atributo|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|El `useErrorStream` valor <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> del constructor.  Establezca `initializeData` el atributo`true`en " " para escribir la salida de seguimiento y depuración en la secuencia de errores estándar; establecerlo en`false`" " para escribir en el flujo de salida estándar.|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|Nombre del archivo en el que <xref:System.Diagnostics.DelimitedListTraceListener> va a escribir.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Nombre de un origen existente del registro de eventos.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|El nombre del archivo <xref:System.Diagnostics.EventSchemaTraceListener> en el que escribe el archivo.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|El nombre del archivo <xref:System.Diagnostics.TextWriterTraceListener> en el que escribe el archivo.|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|El nombre del archivo <xref:System.Diagnostics.XmlWriterTraceListener> en el que escribe el archivo.|  
  
## <a name="configuration-file"></a>Archivo de configuración  
 Este elemento se puede utilizar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente `<add>` se muestra <xref:System.Diagnostics.TextWriterTraceListener> `textListener` cómo `sharedListeners` utilizar elementos para agregar el a la colección.   `textListener`se agrega por `Listeners` nombre a la `TraceSourceApp`colección para el origen de seguimiento. El `textListener` agente de escucha escribe la salida de seguimiento en el archivo myListener.log.  
  
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

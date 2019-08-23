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
ms.openlocfilehash: c4b83834fb7aaf64a696b85bd2c8da47cfba2397
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927212"
---
# <a name="add-element-for-sharedlisteners"></a>\<Agregue > elemento para \<sharedListeners >
Agrega un agente de escucha a la colección `sharedListeners`. `sharedListeners`es una colección de agentes de escucha a los que puede hacer referencia cualquier [ \<> de origen](source-element.md) o [ \<> de seguimiento](trace-element.md) .  De forma predeterminada, los agentes de `sharedListeners` escucha de la colección no se `Listeners` colocan en una colección. Se deben agregar por nombre al [ \<> de origen](source-element.md) o [ \<> de seguimiento](trace-element.md). No es posible obtener los agentes de escucha de la colección `sharedListeners` en el código en tiempo de ejecución.  
  
 \<configuration>  
&nbsp;&nbsp;\<system.diagnostics>  
&nbsp;&nbsp;&nbsp;&nbsp;\<sharedListeners > elemento  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<add>  
  
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
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|`name`|Atributo necesario.<br /><br /> Especifica el nombre del agente de escucha que se usa para agregar el agente de escucha compartido a `Listeners` una colección.|  
|`type`|Atributo necesario.<br /><br /> Especifica el tipo del agente de escucha. Debe utilizar una cadena que cumpla los requisitos especificados en [especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Atributo opcional.<br /><br /> Cadena pasada al constructor de la clase especificada.|  
|`traceOutputOptions`|Atributo opcional.<br/><br/>Representación de cadena de uno o más <xref:System.Diagnostics.TraceOptions> miembros de la enumeración que indica los datos que se van a escribir en el resultado del seguimiento. Varios elementos se separan mediante comas. El valor predeterminado es "none".|

### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-sharedlisteners.md)|Agrega un filtro a un agente de escucha en la colección `sharedListeners`.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.|  
|`sharedListeners`|Colección de agentes de escucha a los que puede hacer referencia cualquier origen o elemento de seguimiento.|  
  
## <a name="remarks"></a>Comentarios  
 Las clases de agente de escucha incluidas con el .NET Framework derivan de la <xref:System.Diagnostics.TraceListener> clase. El valor `name` del atributo se usa para agregar el agente de escucha compartido a una `Listeners` colección para un seguimiento o un origen de seguimiento. El valor `initializeData` del atributo depende del tipo de agente de escucha que se cree. No todos los agentes de escucha de seguimiento requieren `initializeData`que se especifique.  
  
> [!NOTE]
> Al usar el `initializeData` atributo, puede obtener la advertencia del compilador "el atributo ' initializeData ' no se ha declarado". Esta advertencia se produce porque la configuración se valida con respecto a la clase <xref:System.Diagnostics.TraceListener>base abstracta, que no reconoce el `initializeData` atributo. Normalmente, puede omitir esta advertencia para las implementaciones del agente de escucha de seguimiento que tienen un constructor que toma un parámetro.  
  
 En la tabla siguiente se muestran los agentes de escucha de seguimiento incluidos en el .NET Framework y se describe el `initializeData` valor de sus atributos.  
  
|Clase de agente de escucha de seguimiento|valor del atributo initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|`useErrorStream` Valor<xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> del constructor.  Establezca el `initializeData` atributo en "`true`" para escribir el resultado de seguimiento y depuración en la secuencia de error estándar`false`; establézcalo en "" para escribir en el flujo de salida estándar.|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|Nombre del archivo <xref:System.Diagnostics.DelimitedListTraceListener> en el que escribe.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Nombre de un origen de registro de eventos existente.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Nombre del archivo en el que <xref:System.Diagnostics.EventSchemaTraceListener> escribe.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Nombre del archivo en el que <xref:System.Diagnostics.TextWriterTraceListener> escribe.|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|Nombre del archivo en el que <xref:System.Diagnostics.XmlWriterTraceListener> escribe.|  
  
## <a name="configuration-file"></a>Archivo de configuración  
 Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo `<add>` utilizar los elementos para <xref:System.Diagnostics.TextWriterTraceListener> `textListener` agregar a `sharedListeners` la colección.   `textListener`se agrega por nombre a la `Listeners` colección para el origen `TraceSourceApp`de seguimiento. El `textListener` agente de escucha escribe la salida del seguimiento en el archivo myListener. log.  
  
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

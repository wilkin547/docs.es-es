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
ms.openlocfilehash: 116a9633d16b8dd36c82f07a8e727f6f9f98f0ee
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088966"
---
# <a name="add-element-for-sharedlisteners"></a>\<agregar > elemento para \<sharedListeners >
Agrega un agente de escucha a la colección `sharedListeners`. `sharedListeners` es una colección de agentes de escucha a los que puede hacer referencia cualquier [> de origen de\<](source-element.md) o > de seguimiento de [\<](trace-element.md) .  De forma predeterminada, los agentes de escucha de la colección de `sharedListeners` no se colocan en una colección de `Listeners`. Se deben agregar por nombre al > de [origen de\<](source-element.md) o [\<> de seguimiento](trace-element.md). No es posible obtener los agentes de escucha de la colección de `sharedListeners` en el código en tiempo de ejecución.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<sharedListeners**](sharedlisteners-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**agregar >**

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
|`name`|Atributo necesario.<br /><br /> Especifica el nombre del agente de escucha que se usa para agregar el agente de escucha compartido a una colección de `Listeners`.|  
|`type`|Atributo necesario.<br /><br /> Especifica el tipo del agente de escucha. Debe utilizar una cadena que cumpla los requisitos especificados en [especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Atributo opcional.<br /><br /> Cadena pasada al constructor de la clase especificada.|  
|`traceOutputOptions`|Atributo opcional.<br/><br/>Representación de cadena de uno o más <xref:System.Diagnostics.TraceOptions> miembros de enumeración que indica los datos que se van a escribir en el resultado del seguimiento. Varios elementos se separan mediante comas. El valor predeterminado es "none".|

### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-sharedlisteners.md)|Agrega un filtro a un agente de escucha en la colección `sharedListeners`.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.|  
|`sharedListeners`|Colección de agentes de escucha a los que puede hacer referencia cualquier origen o elemento de seguimiento.|  
  
## <a name="remarks"></a>Comentarios  
 Las clases de agente de escucha incluidas con el .NET Framework derivan de la clase <xref:System.Diagnostics.TraceListener>. El valor del atributo `name` se usa para agregar el agente de escucha compartido a una colección de `Listeners` para un seguimiento o un origen de seguimiento. El valor del atributo `initializeData` depende del tipo de agente de escucha que se cree. No todos los agentes de escucha de seguimiento requieren que se especifique `initializeData`.  
  
> [!NOTE]
> Al usar el atributo `initializeData`, puede obtener la advertencia del compilador "el atributo ' initializeData ' no se ha declarado". Esta advertencia se produce porque los valores de configuración se validan con la clase base abstracta <xref:System.Diagnostics.TraceListener>, que no reconoce el atributo `initializeData`. Normalmente, puede omitir esta advertencia para las implementaciones del agente de escucha de seguimiento que tienen un constructor que toma un parámetro.  
  
 En la tabla siguiente se muestran los agentes de escucha de seguimiento incluidos en el .NET Framework y se describe el valor de sus atributos `initializeData`.  
  
|Clase de agente de escucha de seguimiento|valor del atributo initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|El valor `useErrorStream` del constructor de <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>.  Establezca el atributo `initializeData` en "`true`" para escribir el resultado de seguimiento y de depuración en la secuencia de error estándar. establézcalo en "`false`" para escribir en el flujo de salida estándar.|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|Nombre del archivo en el que se escribe el <xref:System.Diagnostics.DelimitedListTraceListener>.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Nombre de un origen de registro de eventos existente.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Nombre del archivo en el que escribe el <xref:System.Diagnostics.EventSchemaTraceListener>.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Nombre del archivo en el que escribe el <xref:System.Diagnostics.TextWriterTraceListener>.|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|Nombre del archivo en el que escribe el <xref:System.Diagnostics.XmlWriterTraceListener>.|  
  
## <a name="configuration-file"></a>Archivo de configuración  
 Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar los elementos `<add>` para agregar el `textListener` de <xref:System.Diagnostics.TextWriterTraceListener>a la colección de `sharedListeners`.   `textListener` se agrega por nombre a la colección de `Listeners` para el `TraceSourceApp`de origen de seguimiento. El agente de escucha de `textListener` escribe la salida del seguimiento en el archivo myListener. log.  
  
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

---
title: <filter>Elemento <add> para <listeners> for for<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
ms.openlocfilehash: 0cb668782de263d5f784691f46cb8b74541d942b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153521"
---
# <a name="filter-element-for-add-for-listeners-for-source"></a>\<filtrar> \<elemento para \<agregar> \<para los agentes de escucha> para el origen>
Agrega un filtro a un agente de escucha en la colección `Listeners` para un origen de seguimiento.  

[**\<configuración>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<fuentes>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<fuente>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oyentes>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<añadir>**](add-element-for-listeners-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>de filtro**

## <a name="syntax"></a>Sintaxis  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`type`|Atributo necesario.<br /><br /> Especifica el tipo del filtro, que <xref:System.Diagnostics.TraceFilter> debe heredar de la clase. Puede usar el nombre completo del espacio de nombres del <xref:System.Type.FullName%2A> tipo, que corresponde a la propiedad del tipo, o puede <xref:System.Type.AssemblyQualifiedName%2A> usar el nombre de tipo completo, incluida la información del ensamblado, que corresponde a la propiedad. Para obtener información acerca de los nombres de tipo completos, vea Especificar nombres de [tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Atributo opcional.<br /><br /> La cadena que se pasa al constructor para la clase de filtro especificada.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.|  
|`sources`|Contiene orígenes de seguimiento que inician mensajes de seguimiento.|  
|`source`|Contiene un origen de seguimiento que inicia mensajes de seguimiento.|  
|`listeners`|Contiene agentes de escucha que recopilan, almacenan y enrutan mensajes. Los agentes de escucha dirigen la salida de seguimiento a un destino adecuado.|  
|`add`|Agrega un agente de escucha a la colección `Listeners` para un origen de seguimiento.|  
  
## <a name="remarks"></a>Observaciones  
 El `<filter>` elemento debe estar `<add>` contenido en un elemento para un agente de escucha de origen de seguimiento que especifica el tipo del agente de escucha, no solo el nombre de un agente de escucha definido en un [ \<sharedListeners>](sharedlisteners-element.md). Si el agente de escucha se define en un [ \<sharedListeners>](sharedlisteners-element.md), el filtro de ese agente de escucha debe definirse en ese elemento.  
  
 Este elemento se puede utilizar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente `<filter>` se muestra cómo utilizar `console` el `Listeners` elemento para agregar `myTraceSource`un filtro al agente `Error`de escucha de la colección para el origen de seguimiento, especificando el nivel de evento de filtro como .  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" switchName="SourceSwitch"
        switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console"
            type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter"
              initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="SourceSwitch" value="Warning" />  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [Esquema de configuración de seguimiento y depuración](index.md)

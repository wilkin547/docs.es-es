---
title: <filter> elemento de <add> para <listeners> para <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: cc970240ac07ad3ea72be50d1e9af452da638fa9
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088893"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a>\<filtro > elemento para \<agregar > para \<agentes de escucha > \<> de seguimiento
Agrega un filtro a un agente de escucha en la colección de `Listeners` para un seguimiento.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](trace-element.md) > de seguimiento\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**agentes de escucha**](listeners-element-for-trace.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**agregar >** ](add-element-for-listeners-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**filtro** >

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
|`type`|Atributo necesario.<br /><br /> Especifica el tipo de filtro, que debe heredar de la clase <xref:System.Diagnostics.TraceFilter>. Puede usar el nombre completo del espacio de nombres del tipo, que corresponde a la propiedad <xref:System.Type.FullName%2A> del tipo, o puede usar el nombre de tipo completo, incluida la información del ensamblado, que corresponde a la propiedad <xref:System.Type.AssemblyQualifiedName%2A>. Para obtener información sobre los nombres de tipo completos, vea [especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Atributo opcional.<br /><br /> Cadena pasada al constructor de la clase de filtro especificada.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.|  
|`trace`|Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.|  
|`listeners`|Contiene agentes de escucha que recopilan, almacenan y enrutan mensajes. Los agentes de escucha dirigen los resultados del seguimiento a un destino adecuado.|  
|`add`|Agrega un agente de escucha a la colección `Listeners`.|  
  
## <a name="remarks"></a>Comentarios  
 El elemento `<filter>` debe estar incluido en un elemento `<add>` para un agente de escucha de seguimiento que especifique el tipo del agente de escucha, no solo el nombre de un agente de escucha definido en una [> sharedListeners\<](sharedlisteners-element.md). Si el agente de escucha se define en una [\<sharedListeners >](sharedlisteners-element.md), el filtro para ese agente de escucha debe definirse en ese elemento.  
  
 Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar el elemento `<filter>` para agregar un filtro a la `console` del agente de escucha de la colección de `Listeners` para el seguimiento, especificando el nivel de evento de filtro como `Error`.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
        <remove name="Default" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [Esquema de la configuración de seguimiento y depuración](index.md)

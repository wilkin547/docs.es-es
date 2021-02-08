---
description: 'Más información sobre: <filter> elemento para <add> para <listeners><source>'
title: <filter>(Elemento <add> ) para para <listeners><source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
ms.openlocfilehash: 65233aa2d9ea000d1d27d0241c734bee7097b7ca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782265"
---
# <a name="filter-element-for-add-for-listeners-for-source"></a>\<filter>(Elemento \<add> ) para para \<listeners>\<source>

Agrega un filtro a un agente de escucha en la colección `Listeners` para un origen de seguimiento.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**

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
|`type`|Atributo necesario.<br /><br /> Especifica el tipo del filtro, que debe heredar de la <xref:System.Diagnostics.TraceFilter> clase. Puede usar el nombre completo del espacio de nombres del tipo, que corresponde a la propiedad del tipo <xref:System.Type.FullName%2A> , o puede usar el nombre de tipo completo, incluida la información de ensamblado, que corresponde a la <xref:System.Type.AssemblyQualifiedName%2A> propiedad. Para obtener información sobre los nombres de tipo completos, vea [especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Atributo opcional.<br /><br /> Cadena pasada al constructor de la clase de filtro especificada.|  
  
### <a name="child-elements"></a>Elementos secundarios  

 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.|  
|`sources`|Contiene orígenes de seguimiento que inician mensajes de seguimiento.|  
|`source`|Contiene un origen de seguimiento que inicia mensajes de seguimiento.|  
|`listeners`|Contiene agentes de escucha que recopilan, almacenan y enrutan mensajes. Los agentes de escucha dirigen los resultados del seguimiento a un destino adecuado.|  
|`add`|Agrega un agente de escucha a la colección `Listeners` para un origen de seguimiento.|  
  
## <a name="remarks"></a>Observaciones  

 El `<filter>` elemento debe estar contenido en un `<add>` elemento para un agente de escucha de origen de seguimiento que especifique el tipo del agente de escucha, no solo el nombre de un agente de escucha definido en [\<sharedListeners>](sharedlisteners-element.md) . Si el agente de escucha se define en [\<sharedListeners>](sharedlisteners-element.md) , el filtro para ese agente de escucha debe definirse en ese elemento.  
  
 Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y en el archivo de configuración de la aplicación.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo usar el `<filter>` elemento para agregar un filtro al agente `console` de escucha de la `Listeners` colección para el origen de seguimiento `myTraceSource` , especificando el nivel de evento de filtro como `Error` .  
  
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
  
## <a name="see-also"></a>Vea también

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [Esquema de configuración de seguimiento y depuración](index.md)

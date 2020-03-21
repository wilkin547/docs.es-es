---
title: <clear>Elemento <listeners> para for<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 905dad8274fede80f4809ff3c7a014049f9df450
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153547"
---
# <a name="clear-element-for-listeners-for-trace"></a>\<desactive> \<Element para \<los agentes de escucha> para el seguimiento>
Borra la colección `Listeners` de un seguimiento.  

[**\<configuración>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<rastreo>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oyentes>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>claro**

## <a name="syntax"></a>Sintaxis  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.|  
|`trace`|Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.|  
|`listeners`|Contiene agentes de escucha que recopilan, almacenan y enrutan mensajes. Los agentes de escucha dirigen la salida de seguimiento a un destino adecuado.|  
  
## <a name="remarks"></a>Observaciones  
 El `<clear>` elemento quita todos los `Listeners` agentes de escucha de la colección para el seguimiento. Puede usar `<clear>` el elemento `<add>` antes de usar el elemento para estar seguro de que no hay otros agentes de escucha activos en la colección.  
  
 Puede borrar `Listeners` la colección mediante <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> programación <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> llamando`System.Diagnostics.Trace.Listeners.Clear()`al método de la propiedad ( ).  
  
 Este elemento se puede utilizar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.  
  
> [!NOTE]
> El `<clear>` elemento quita <xref:System.Diagnostics.DefaultTraceListener> el `Listeners` de la colección, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>modificando el comportamiento de los métodos , , <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>. <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> Llamar `Assert` a `Fail` un método o o normalmente da como resultado la visualización de un cuadro de mensaje. Sin embargo, el cuadro de <xref:System.Diagnostics.DefaultTraceListener> mensaje no `Listeners` se muestra si no está en la colección.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente `<clear>` se muestra `<add>` cómo utilizar el `console` elemento `Listeners` antes de usar el elemento para agregar el agente de escucha a la colección para el seguimiento.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <clear/>  
        <add name="console"
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"
            initializeData="Error" />  
        </add>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [Esquema de configuración de seguimiento y depuración](index.md)
- [\<eliminar>](remove-element-for-listeners-for-trace.md)
- [Agentes de escucha de seguimiento](../../../debug-trace-profile/trace-listeners.md)

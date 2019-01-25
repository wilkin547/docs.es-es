---
title: '&lt;Borrar&gt; (elemento) para &lt;los agentes de escucha&gt; para &lt;seguimiento&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 2e0970fe197ecf6e0fbcf94f410364cb59d267e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732614"
---
# <a name="ltcleargt-element-for-ltlistenersgt-for-lttracegt"></a>&lt;Borrar&gt; (elemento) para &lt;los agentes de escucha&gt; para &lt;seguimiento&gt;
Borra la colección `Listeners` de un seguimiento.  
  
 \<configuration>  
\<system.diagnostics>  
\<trace>  
\<listeners>  
\<clear>  
  
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
|`listeners`|Contiene los agentes de escucha que recopilarán, almacenan y enrutan los mensajes. Los agentes de escucha dirigen los resultados de seguimiento a un destino apropiado.|  
  
## <a name="remarks"></a>Comentarios  
 El `<clear>` elemento quita todos los agentes de escucha desde el `Listeners` colección de seguimiento. Puede usar el `<clear>` elemento antes de usar el `<add>` elemento que esté seguro de que no hay ningún otros agentes de escucha activos en la colección.  
  
 Puede borrar el `Listeners` colección mediante programación mediante una llamada a la <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> método en el <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> propiedad (`System.Diagnostics.Trace.Listeners.Clear()`).  
  
 Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.  
  
> [!NOTE]
>  El `<clear>` elemento quita el <xref:System.Diagnostics.DefaultTraceListener> desde el `Listeners` colección, alterar el comportamiento de la <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, y <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> métodos. Una llamada a un `Assert` o `Fail` método normalmente da como resultado de la presentación de un cuadro de mensaje. Sin embargo, no se muestra el cuadro de mensaje si el <xref:System.Diagnostics.DefaultTraceListener> no está en el `Listeners` colección.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar el `<clear>` elemento antes de usar el `<add>` elemento para agregar el agente de escucha `console` a la `Listeners` recopilación para el seguimiento.  
  
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
  
## <a name="see-also"></a>Vea también
- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [Esquema de la configuración de seguimiento y depuración](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [\<remove>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)
- [Agentes de escucha de seguimiento](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)

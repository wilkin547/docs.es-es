---
title: '&lt;quitar&gt; (elemento) para &lt;los agentes de escucha&gt; para &lt;origen&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 8beb3ef041b153535afcb8bd92e1c29787e1f161
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654417"
---
# <a name="ltremovegt-element-for-ltlistenersgt-for-ltsourcegt"></a>&lt;quitar&gt; (elemento) para &lt;los agentes de escucha&gt; para &lt;origen&gt;
Quita un agente de escucha de la colección `Listeners` para un origen de seguimiento.  
  
 \<configuration>  
\<system.diagnostics>  
\<orígenes >  
\<source>  
\<listeners>  
\<remove>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`name`|Atributo necesario.<br /><br /> El nombre del agente de escucha que se quitará el `Listeners` colección.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.|  
|`sources`|Contiene orígenes de seguimiento que inician mensajes de seguimiento.|  
|`source`|Contiene un origen de seguimiento que inicia mensajes de seguimiento.|  
|`listeners`|Especifica los agentes de escucha que recopilarán, almacenan y enrutan los mensajes.|  
  
## <a name="remarks"></a>Comentarios  
 El `<remove>` elemento quita un agente de escucha especificado desde el `Listeners` colección para un origen de seguimiento.  
  
 Puede quitar un elemento de la `Listeners` colección para un origen de seguimiento mediante programación mediante una llamada a la <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> método en el <xref:System.Diagnostics.TraceSource.Listeners%2A> propiedad de la <xref:System.Diagnostics.TraceSource> instancia.  
  
 Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo usar el `<remove>` elemento antes de usar el `<add>` elemento para agregar el agente de escucha `console` a la `Listeners` recopilación para el origen de seguimiento `TraceSourceApp`.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch" >  
         <listeners>  
           <remove name="Default"/>  
           <add name="console"   
             type="System.Diagnostics.ConsoleTraceListener" />  
         </listeners>  
      </source>  
    </sources>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a>Vea también
- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [Esquema de la configuración de seguimiento y depuración](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [\<clear>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)
- [Agentes de escucha de seguimiento](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)

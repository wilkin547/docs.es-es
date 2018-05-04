---
title: '&lt;Borrar&gt; (elemento) para &lt;los agentes de escucha&gt; para &lt;origen&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 8c6ef51dae36e94fa4a4fdc5ad8983380e78bde3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltcleargt-element-for-ltlistenersgt-for-ltsourcegt"></a>&lt;Borrar&gt; (elemento) para &lt;los agentes de escucha&gt; para &lt;origen&gt;
Borra la colección `Listeners` de un origen de seguimiento.  
  
 \<configuration>  
\<System.Diagnostics >  
\<orígenes >  
\<origen >  
\<los agentes de escucha >  
\<Borrar >  
  
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
|`sources`|Contiene orígenes de seguimiento que inician mensajes de seguimiento.|  
|`source`|Contiene un origen de seguimiento que inicia mensajes de seguimiento.|  
|`listeners`|Especifica los agentes de escucha que recopilarán, almacenan y enrutan los mensajes.|  
  
## <a name="remarks"></a>Comentarios  
 El `<clear>` elemento quita todos los agentes de escucha de la `Listeners` colección para un origen de seguimiento, incluido el <xref:System.Diagnostics.DefaultTraceListener>. Puede usar el `<clear>` elemento antes de usar el `<add>` elemento para estar seguro de que no hay ningún otro agente de escucha activo en la colección.  
  
## <a name="configuration-file"></a>Archivo de configuración  
 Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de aplicación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar el `<clear>` elemento antes de usar el `<add>` elementos que se agregan los agentes de escucha `console` y `textListener` a la `Listeners` colección para el origen de seguimiento `TraceSourceApp`.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
       <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <clear/>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
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
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.TraceListener>  
 [Esquema de la configuración de seguimiento y depuración](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [Agentes de escucha de seguimiento](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)

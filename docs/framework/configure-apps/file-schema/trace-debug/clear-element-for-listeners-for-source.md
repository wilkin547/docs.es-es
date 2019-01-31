---
title: Elemento <clear> de <listeners> de <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: ee4d5f1880cf6b7aac871149bf7bf59a06903bf2
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55286746"
---
# <a name="clear-element-for-listeners-for-source"></a>\<Borrar > (elemento) para \<los agentes de escucha > para \<origen >
Borra la colección `Listeners` de un origen de seguimiento.  
  
 \<configuration>  
\<system.diagnostics>  
\<orígenes >  
\<source>  
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
|`sources`|Contiene orígenes de seguimiento que inician mensajes de seguimiento.|  
|`source`|Contiene un origen de seguimiento que inicia mensajes de seguimiento.|  
|`listeners`|Especifica los agentes de escucha que recopilarán, almacenan y enrutan los mensajes.|  
  
## <a name="remarks"></a>Comentarios  
 El `<clear>` elemento quita todos los agentes de escucha desde el `Listeners` colección para un origen de seguimiento, incluido el <xref:System.Diagnostics.DefaultTraceListener>. Puede usar el `<clear>` elemento antes de usar el `<add>` elemento que esté seguro de que no hay ningún otros agentes de escucha activos en la colección.  
  
## <a name="configuration-file"></a>Archivo de configuración  
 Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo usar el `<clear>` elemento antes de usar el `<add>` elementos para agregar los agentes de escucha `console` y `textListener` a la `Listeners` recopilación para el origen de seguimiento `TraceSourceApp`.  
  
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
- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [Esquema de la configuración de seguimiento y depuración](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [Agentes de escucha de seguimiento](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)

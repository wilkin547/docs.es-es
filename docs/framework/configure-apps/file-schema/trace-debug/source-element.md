---
title: '&lt;origen&gt; elemento'
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 493c6ab72ff5554294279b62af49d311026d6e37
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624020"
---
# <a name="ltsourcegt-element"></a>&lt;origen&gt; elemento
Contiene un origen de seguimiento que inicia mensajes de seguimiento.  
  
 \<configuration>  
\<system.diagnostics>  
\<orígenes >  
\<source>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<source>   
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`name`|Atributo opcional.<br /><br /> Especifica el nombre del origen de seguimiento.|  
|`switchName`|Atributo opcional.<br /><br /> Especifica el nombre de una instancia de conmutador de seguimiento en la aplicación. Si el conmutador no se identifica en un `<switches>` elemento, el valor especifica el nivel del modificador.|  
|`switchType`|Atributo opcional.<br /><br /> Especifica el tipo del modificador de seguimiento. Si está presente, el tipo debe ser un nombre de clase válido y no puede ser una cadena vacía.|  
|`extraAttribute`|Atributo opcional.<br /><br /> Especifica el valor de un atributo específico del origen de seguimiento identificado por el <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> método para ese origen de seguimiento.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<listeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|Contiene los agentes de escucha que recopilarán, almacenan y enrutan los mensajes.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.|  
|`sources`|Contiene orígenes de seguimiento que inician mensajes de seguimiento.|  
  
## <a name="remarks"></a>Comentarios  
 Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo usar el `<source>` elemento va a agregar el origen de seguimiento `mySource` y establecer el nivel del modificador de origen denominado `sourceSwitch`. Se agrega un agente de escucha de seguimiento de consola que escribe información de seguimiento en la consola.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch" switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter" initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
        <switches>  
           <add name="sourceSwitch" value="Warning" />  
        </switches>    
  </system.diagnostics>   
</configuration>  
```  
  
## <a name="see-also"></a>Vea también
- [Esquema de la configuración de seguimiento y depuración](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [Modificadores de seguimiento](../../../../../docs/framework/debug-trace-profile/trace-switches.md)

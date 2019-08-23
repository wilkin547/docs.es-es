---
title: <source> (Elemento)
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: 55120e292ac2a2c822c5510563d1aa167ca921e4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920451"
---
# <a name="source-element"></a>\<Elemento > de origen
Contiene un origen de seguimiento que inicia mensajes de seguimiento.  
  
 \<configuration>  
\<system.diagnostics>  
\<orígenes >  
\<> de origen  
  
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
|`switchName`|Atributo opcional.<br /><br /> Especifica el nombre de una instancia del modificador de seguimiento en la aplicación. Si no se identifica el modificador en `<switches>` un elemento, el valor especifica el nivel del modificador.|  
|`switchType`|Atributo opcional.<br /><br /> Especifica el tipo del modificador de seguimiento. Si está presente, el tipo debe ser un nombre de clase válido y no puede ser una cadena vacía.|  
|`extraAttribute`|Atributo opcional.<br /><br /> Especifica el valor de un atributo específico del origen de seguimiento identificado por <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> el método para ese origen de seguimiento.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<listeners>](listeners-element-for-source.md)|Contiene agentes de escucha que recopilan, almacenan y enrutan mensajes.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.|  
|`sources`|Contiene orígenes de seguimiento que inician mensajes de seguimiento.|  
  
## <a name="remarks"></a>Comentarios  
 Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar `<source>` el elemento para agregar el origen `mySource` de seguimiento y establecer el nivel para el modificador `sourceSwitch`de origen denominado. Se agrega un agente de escucha de seguimiento de consola que escribe información de seguimiento en la consola.  
  
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

- [Esquema de la configuración de seguimiento y depuración](index.md)
- [Modificadores de seguimiento](../../../debug-trace-profile/trace-switches.md)

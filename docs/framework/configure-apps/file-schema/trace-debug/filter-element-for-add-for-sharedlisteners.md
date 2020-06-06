---
title: <filter>(Elemento <add> ) para<sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add/filter
helpviewer_keywords:
- filter element for <add> for <sharedListeners>
- initializeData attribute
- <filter> element for <add> for <sharedListeners>
- filters, trace listeners
- trace listeners, filters
ms.assetid: 7d4e7faa-2e4e-4379-ac76-f6cd7f2f8fac
ms.openlocfilehash: 6fb52cdfa5792ab6059b60d8dbb91c107cd666ca
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153458"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a>\<filter>(Elemento \<add> ) para\<sharedListeners>
Agrega un filtro a un agente de escucha en la colección `sharedListeners`.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-sharedlisteners.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**

## <a name="syntax"></a>Sintaxis  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|**type**|Atributo necesario.<br /><br /> Especifica el tipo del filtro. Solo se puede usar el nombre completo del tipo (en el formato de la <xref:System.Type.FullName%2A?displayProperty=nameWithType> propiedad), o bien se puede usar el nombre de tipo completo, incluida la información de ensamblado (en el formato de la <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> propiedad). Para obtener información sobre cómo crear un nombre de tipo completo, vea [especificar nombres de tipos completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|**initializeData**|Atributo opcional.<br /><br /> Cadena pasada al constructor de la clase especificada.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.|  
|`sharedListeners`|Colección de agentes de escucha a los que puede hacer referencia cualquier origen o elemento de seguimiento.|  
|`add`|Agrega un agente de escucha a la colección **sharedListeners** .|  
  
## <a name="remarks"></a>Comentarios  
 Si se define un agente de escucha en un `<add>` elemento del `<sharedListeners>` elemento, el filtro para ese agente de escucha debe definirse en un `<filter>` elemento secundario del `<add>` elemento.  
  
 Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar el `<filter>` elemento para agregar un filtro al agente de escucha `console` de seguimiento de la `sharedListeners` colección.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" >  
        <listeners>  
          <add name="console" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="console"
        type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"
          initializeData="Error" />  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [Esquema de la configuración de seguimiento y depuración](index.md)

---
title: '&lt;Thread_UseAllCpuGroups&gt; elemento'
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47d8bcdb9bbb7ec6f5a5386a5ac5951ad8891c28
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745596"
---
# <a name="ltthreaduseallcpugroupsgt-element"></a>&lt;Thread_UseAllCpuGroups&gt; elemento
Especifica si el runtime distribuye subprocesos administrados en todos los grupos de CPU.  
  
 \<configuration>  
\<en tiempo de ejecución >  
< Thread_UseAllCpuGroups >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml
<Thread_UseAllCpuGroups    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si el runtime distribuye subprocesos administrados en todos los grupos de CPU.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|El tiempo de ejecución no distribuye los subprocesos administrados en varios grupos de CPU. Este es el valor predeterminado.|  
|`true`|El runtime distribuye los subprocesos administrados en varios grupos de CPU, si el equipo tiene varios grupos de CPU y la [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) elemento está habilitado.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 Cuando un equipo tiene varios grupos de CPU, si se habilita este elemento, el runtime pueda distribuir subprocesos administrados en todos los grupos de CPU. Para usar esta característica, debe habilitar también la [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) elemento, que extiende la recolección para todos los grupos de CPU y tiene en cuenta al crear y equilibra montones todos los núcleos. Habilitar la [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) elemento requiere la habilitación de la [ \<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) elemento. Si estos elementos no están habilitados, habilitar la `<Thread_UseAllCpuGroups>` elemento no tiene ningún efecto.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo habilitar la compatibilidad con varios grupos de CPU.  
  
```xml  
<configuration>  
   <runtime>  
      <Thread_UseAllCpuGroups enabled="true"/>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<GCCpuGroup > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)

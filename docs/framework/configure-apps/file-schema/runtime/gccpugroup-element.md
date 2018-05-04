---
title: '&lt;GCCpuGroup&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4461667bdb47d410c857b4ac2c9dd268438a02f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltgccpugroupgt-element"></a>&lt;GCCpuGroup&gt; elemento
Especifica si la recolección de elementos no utilizados admite varios grupos de CPU.  
  
 \<configuration>  
\<en tiempo de ejecución >  
\<GCCpuGroup >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<GCCpuGroup    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si la recolección de elementos no utilizados admite varios grupos de CPU.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|La recolección de elementos no utilizados no admite varios grupos de CPU. Este es el valor predeterminado.|  
|`true`|La recolección de elementos no utilizados admite varios grupos de CPU, si está habilitada la recolección de elementos no utilizados de servidor.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 Cuando un equipo tiene varios grupos de CPU y la recolección de elementos no utilizados de servidor está habilitado (consulte la [ \<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) elemento), habilitar este elemento extiende la recolección en todos los grupos de CPU y tiene todos los núcleos en cuenta al crear y equilibra montones.  
  
> [!NOTE]
>  Este elemento solo se aplica a los subprocesos de recolección de elementos no utilizados. Para habilitar el runtime pueda distribuir subprocesos de usuario en todos los grupos de CPU, también debe habilitar la [< Thread_UseAllCpuGroups >](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) elemento.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo habilitar la recolección de elementos no utilizados para varios grupos de CPU.  
  
```xml  
<configuration>  
   <runtime>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Cómo: deshabilitar la recolección de elementos no utilizados simultánea](http://msdn.microsoft.com/library/ba2c6c67-5778-497c-9fac-5f793b5500c7)  
 [Recolección de estación de trabajo y servidor](../../../../../docs/standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)

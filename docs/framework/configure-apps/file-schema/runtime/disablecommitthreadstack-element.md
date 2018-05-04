---
title: '&lt;disableCommitThreadStack&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCommitThreadStack
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCommitThreadStack
helpviewer_keywords:
- <disableCommitThreadStack> element
- disableCommitThreadStack element
ms.assetid: 3559d46a-7640-4c72-9a11-7e980768929e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4d8724d16a25cdec040fa5b1f5472da06b11f669
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltdisablecommitthreadstackgt-element"></a>&lt;disableCommitThreadStack&gt; elemento
Especifica si se confirma la pila de subprocesos completa cuando se inicia un subproceso.  
  
 \<configuration>  
\<en tiempo de ejecución >  
\<disableCommitThreadStack >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<disableCommitThreadStack enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|enabled|Atributo necesario.<br /><br /> Especifica si la confirmación de la pila de subprocesos completa cuando se inicia el subproceso (comportamiento predeterminado) está deshabilitada.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|0|No deshabilite el comportamiento predeterminado de Common Language Runtime, que consiste en confirmar la pila de subprocesos completa cuando se inicia un subproceso.|  
|1|Deshabilite el comportamiento predeterminado de Common Language Runtime, que consiste en confirmar la pila de subprocesos completa cuando se inicia un subproceso.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] .|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 El comportamiento predeterminado de Common Language Runtime consiste en confirmar la pila de subprocesos completa cuando se inicia un subproceso. Si se debe crear un gran número de subprocesos en un servidor con memoria limitada y la mayoría de estos subprocesos usarán muy poco espacio de pila, el servidor mejorará su rendimiento si Common Language Runtime no confirma la pila de subprocesos completa inmediatamente cuando se inicia un subproceso.  
  
> [!NOTE]
>  Los hosts no administrados pueden usar la marca de inicio `STARTUP_DISABLE_COMMITTHREADSTACK` en la enumeración [STARTUP_FLAGS](../../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) para lograr el mismo resultado.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo deshabilitar el comportamiento predeterminado de Common Language Runtime, que consiste en confirmar la pila de subprocesos completa cuando se inicia un subproceso.  
  
```xml  
<configuration>  
   <runtime>  
      <disableCommitThreadStack enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)

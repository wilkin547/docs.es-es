---
title: '&lt;disableCommitThreadStack&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCommitThreadStack
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCommitThreadStack
helpviewer_keywords:
- <disableCommitThreadStack> element
- disableCommitThreadStack element
ms.assetid: 3559d46a-7640-4c72-9a11-7e980768929e
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8d74566b71501cf21081ac894048bb1c29e0ad94
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
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

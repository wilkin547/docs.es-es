---
title: '&lt;UseSmallInternalThreadStacks&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2558423b412333a4d6ac9f650ad8ff3dab449d74
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltusesmallinternalthreadstacksgt-element"></a>&lt;UseSmallInternalThreadStacks&gt; elemento
Usan las solicitudes que common language runtime (CLR) reduce la memoria mediante la especificación de tamaños de pila explícitos cuando crea ciertos subprocesos que utiliza internamente, en lugar de usar el tamaño de pila predeterminado para esos subprocesos.  
  
 \<Configuración > elemento  
\<en tiempo de ejecución > elemento  
\<UseSmallInternalThreadStacks > elemento  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|enabled|Atributo necesario.<br /><br /> Especifica si se solicita que los tamaños de pila explícito de uso CLR en lugar del tamaño de pila predeterminado cuando crea ciertos subprocesos que utiliza internamente. Los tamaños de pila explícitos son menores que el tamaño de pila predeterminado de 1 MB.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|true|Tamaños de pila explícito de la solicitud.|  
|false|Usar el tamaño de pila predeterminado. Este es el valor predeterminado para el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 Este elemento de configuración se usa para solicitar el uso de memoria virtual reducida en un proceso, porque los tamaños de subproceso explícitos que usa CLR para sus subprocesos internos, si se respeta la solicitud, son menores que el tamaño predeterminado.  
  
> [!IMPORTANT]
>  Este elemento de configuración es una solicitud a CLR en lugar de un requisito imprescindible. En el [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], la solicitud solo se admite para la x86 arquitectura. Este elemento podría omite por completo en versiones futuras de CLR, o se reemplaza por tamaños de pila explícitos que se usan siempre para los subprocesos internos seleccionados.  
  
 Especificar que este elemento de configuración reduce la confiabilidad pero menor uso de memoria virtual si el CLR admite la solicitud, porque el tamaño de pila menor podría provocar pila desborda más frecuente.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo solicitar que el CLR use tamaños de pila explícitos para ciertos subprocesos que utiliza internamente.  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)

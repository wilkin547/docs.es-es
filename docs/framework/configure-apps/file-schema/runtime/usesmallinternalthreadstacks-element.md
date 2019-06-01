---
title: <UseSmallInternalThreadStacks> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f098065cc005c59ec558ffa1f95202715624e7d
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456113"
---
# <a name="usesmallinternalthreadstacks-element"></a>\<UseSmallInternalThreadStacks > elemento
Usan las solicitudes que common language runtime (CLR) Reduzca la memoria mediante la especificación de tamaños de pila explícitos al crear determinados subprocesos que utiliza internamente, en lugar de usar el tamaño de pila predeterminado para esos subprocesos.  
  
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
|enabled|Atributo necesario.<br /><br /> Especifica si se solicita que los tamaños de pila explícitos de uso CLR en lugar del tamaño de pila predeterminado al crear determinados subprocesos que utiliza internamente. Los tamaños de pila explícitos son menores que el tamaño de pila predeterminado de 1 MB.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|true|Solicitar los tamaños de pila explícito.|  
|False|Use el tamaño de pila predeterminado. Este es el valor predeterminado para el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 Este elemento de configuración se utiliza para solicitar el uso de memoria virtual reducido en un proceso, ya que los tamaños de subproceso explícitos que usa CLR para sus subprocesos internos, si se respeta la solicitud, son menores que el tamaño predeterminado.  
  
> [!IMPORTANT]
>  Este elemento de configuración es una solicitud a CLR en lugar de un requisito imprescindible. En .NET Framework 4, la solicitud solo se admite para la x86 arquitectura. Este elemento podría omite completamente en futuras versiones de CLR, o reemplazado por los tamaños de pila explícitos que se utilizan siempre para los subprocesos internos seleccionados.  
  
 Especificando que este elemento de configuración transacciones de confiabilidad para su uso de memoria virtual más pequeño si CLR respeta la solicitud, porque los tamaños de pila más pequeños podrían hacer que stack desborda es más probable.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo solicitar que el CLR use tamaños de pila explícitos para determinados subprocesos que utiliza internamente.  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)

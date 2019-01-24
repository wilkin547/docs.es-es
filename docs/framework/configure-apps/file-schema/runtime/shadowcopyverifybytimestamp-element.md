---
title: '&lt;shadowCopyVerifyByTimestamp&gt; Element'
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a37e41aa653fb3cd5990b75f3c5467a88660113
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54622265"
---
# <a name="ltshadowcopyverifybytimestampgt-element"></a>&lt;shadowCopyVerifyByTimestamp&gt; Element
Especifica si la creación de instantáneas usa el comportamiento de inicio predeterminado especificado en [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] o se revierte el comportamiento de inicio de versiones anteriores de .NET Framework.  
  
 \<Configuración > elemento  
\<en tiempo de ejecución > elemento  
\<shadowCopyVerifyByTimestamp> Element  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|enabled|Atributo necesario.<br /><br /> Especifica si los dominios de aplicación que utilizan instantáneas comparan las marcas de tiempo del ensamblado al iniciarse, para determinar si se ha actualizado un ensamblado antes de la instantánea del ensamblado.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|true|En el inicio, copia solo los ensamblados que se han actualizado desde que se copiaron por última vez en el directorio de instantáneas. Este es el valor predeterminado para el [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].|  
|False|Revierte el comportamiento de inicio de las versiones anteriores de .NET Framework, lo que era copiar todos los archivos en el inicio.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 A partir de la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], los ensamblados son instantáneas sólo si sus marcas de tiempo indican que han cambiado desde que se copiaron por última vez en el directorio de instantáneas. Esto mejora los tiempos de inicio para muchas aplicaciones que utilizan instantáneas, como se describe en [copias sombra de ensamblados](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md). Las aplicaciones que tienen un alto porcentaje y una frecuencia de actualizaciones del ensamblado no pueden beneficiarse de este cambio de comportamiento. En ese caso, puede usar este elemento para restaurar el comportamiento de las versiones anteriores de .NET Framework.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo deshabilitar el comportamiento de inicio predeterminado de las instantáneas en el [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]y revertir al comportamiento de inicio de las versiones anteriores de .NET Framework.  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también
- [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Copias sombra de ensamblados](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md)

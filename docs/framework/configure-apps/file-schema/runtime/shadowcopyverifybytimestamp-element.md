---
title: <shadowCopyVerifyByTimestamp> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f3ea57364832553d16c7e34fc887b1c9f821602
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663447"
---
# <a name="shadowcopyverifybytimestamp-element"></a>Elemento \<shadowCopyVerifyByTimestamp>
Especifica si la copia sombra usa el comportamiento de inicio predeterminado introducido en el .NET Framework 4, o revierte al comportamiento de inicio de versiones anteriores de la .NET Framework.  
  
 \<Elemento Configuration >  
\<Elemento > en tiempo de ejecución  
Elemento \<shadowCopyVerifyByTimestamp>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|enabled|Atributo necesario.<br /><br /> Especifica si los dominios de aplicación que usan la copia sombra comparan las marcas de tiempo de ensamblado al iniciarse, para determinar si se ha actualizado un ensamblado antes de copiar las instantáneas del ensamblado.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|DESCRIPCIÓN|  
|-----------|-----------------|  
|true|En el inicio, copia solo los ensamblados que se han actualizado desde que se copiaron por última vez en el directorio de instantáneas. Este es el valor predeterminado para el .NET Framework 4.|  
|false|Revierte al comportamiento de inicio de las versiones anteriores del .NET Framework, que era copiar todos los archivos en el inicio.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 A partir de la .NET Framework 4, los ensamblados solo se copian con instantáneas si sus marcas de tiempo indican que han cambiado desde que se copiaron por última vez en el directorio de instantáneas. Esto mejora los tiempos de inicio de muchas aplicaciones que usan la copia sombra, como se describe en instantáneas de [copia](../../../app-domains/shadow-copy-assemblies.md)de ensamblados. Es posible que las aplicaciones que tienen un alto porcentaje y la frecuencia de las actualizaciones del ensamblado no se beneficien de este cambio de comportamiento. En ese caso, puede usar este elemento para restaurar el comportamiento de versiones anteriores de la .NET Framework.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo deshabilitar el comportamiento de inicio predeterminado de la copia sombra en el .NET Framework 4 y cómo revertir al comportamiento de inicio de versiones anteriores de la .NET Framework.  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
- [Copias sombra de ensamblados](../../../app-domains/shadow-copy-assemblies.md)

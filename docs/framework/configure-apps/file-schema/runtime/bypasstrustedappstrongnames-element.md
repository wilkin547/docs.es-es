---
title: '&lt;bypassTrustedAppStrongNames&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6988be28e3129748ee7f7996a66c728ccde3c70b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltbypasstrustedappstrongnamesgt-element"></a>&lt;bypassTrustedAppStrongNames&gt; elemento
Especifica si se debe omitir la validación de nombres seguros en los ensamblados de plena confianza que se cargan en plena confianza <xref:System.AppDomain>.  
  
 \<configuration>  
\<en tiempo de ejecución >  
\<bypassTrustedAppStrongNames >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<bypassTrustedAppStrongNames    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si está habilitada la característica de omisión que evite la validación de nombres seguros para los ensamblados de plena confianza. Cuando esta característica está habilitada, no se validan los nombres seguros son correctos cuando se carga el ensamblado. De manera predeterminada, es `true`.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`true`|Las firmas de nombre seguro de ensamblados de plena confianza no se validan cuando los ensamblados se cargan en plena confianza <xref:System.AppDomain>. Este es el valor predeterminado.|  
|`false`|Las firmas de nombre seguro en los ensamblados de plena confianza se validan cuando los ensamblados se cargan en plena confianza <xref:System.AppDomain>. Se comprueba la firma de nombre seguro solo para la exactitud de la firma; no se compara con otro nombre seguro para una coincidencia.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 La característica de omisión de nombres seguros evita la sobrecarga de la comprobación de firma de nombre seguro de ensamblados de plena confianza.  
  
 La característica de omisión se aplica a cualquier ensamblado que esté firmado con un nombre seguro y que:  
  
-   Plena confianza sin el <xref:System.Security.Policy.StrongName> evidencia (por ejemplo, tiene `MyComputer` evidencia de zona).  
  
-   se cargue en un <xref:System.AppDomain> de plena confianza;  
  
-   se cargue desde una ubicación en la propiedad <xref:System.AppDomainSetup.ApplicationBase%2A> de ese <xref:System.AppDomain>;  
  
-   no tenga firma retrasada.  
  
> [!NOTE]
>  Si la característica de omisión se ha desactivado para todas las aplicaciones en el equipo mediante el uso de una clave del registro, este archivo de configuración no tiene ningún efecto. Para obtener más información, consulte [Cómo: deshabilitar la característica de omisión de nombres seguros](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo especificar el comportamiento que valida la firma de nombre seguro en los ensamblados de plena confianza.  
  
```xml  
<configuration>  
   <runtime>  
      <bypassTrustedAppStrongNames enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Cómo: Deshabilitar la característica de omisión de nombres seguros](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md).

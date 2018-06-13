---
title: '&lt;NetFx40_LegacySecurityPolicy&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d9312d25842ccfcdf84e678d34b9bfde3fe7dd0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753988"
---
# <a name="ltnetfx40legacysecuritypolicygt-element"></a>&lt;NetFx40_LegacySecurityPolicy&gt; elemento
Especifica si el runtime usa la directiva de seguridad de acceso al código (CAS) heredada.  
  
 \<configuration>  
\<en tiempo de ejecución >  
< NetFx40_LegacySecurityPolicy >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<NetFx40_LegacySecurityPolicy  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si el runtime usa la directiva CAS heredada.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|El tiempo de ejecución no usa la directiva CAS heredada. Este es el valor predeterminado.|  
|`true`|El runtime usa la directiva CAS heredada.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Comentarios  
 En la versión de .NET Framework 3.5 y versiones anteriores, la directiva CAS siempre está en efecto. En el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], debe estar habilitada la directiva CAS.  
  
 La directiva CAS es específico de la versión. Directivas personalizadas de entidades emisoras de certificados que existen en las versiones anteriores de .NET Framework deben especificarla en el [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].  
  
 Aplicar el `<NetFx40_LegacySecurityPolicy>` elemento a una [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] ensamblado no afecta a [código transparente en seguridad](../../../../../docs/framework/misc/security-transparent-code.md); las reglas de transparencia se siguen aplican.  
  
> [!IMPORTANT]
>  Aplicar el `<NetFx40_LegacySecurityPolicy>` elemento puede dar lugar a reducciones importantes del rendimiento para los ensamblados de imagen nativa creados por el [Native Image Generator (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md) que no están instalados en el [caché global de ensamblados ](../../../../../docs/framework/app-domains/gac.md). La degradación del rendimiento se debe a la incapacidad del runtime para cargar los ensamblados como imágenes nativas cuando se aplica el atributo, lo que resulta en los que se va a carga ensamblados como just-in-time.  
  
> [!NOTE]
>  Si especifica una versión de .NET Framework de destino que es anterior a la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] en la configuración del proyecto para el proyecto de Visual Studio, la directiva CAS se habilitará, incluyendo cualquier directiva CAS personalizada que especificó para esa versión. Sin embargo, no podrá utilizar new [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] tipos y miembros. También puede especificar una versión anterior de .NET Framework mediante el [ \<supportedRuntime > elemento](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) en el esquema de configuración de inicio en su [archivo de configuración de aplicación](../../../../../docs/framework/configure-apps/index.md).  
  
> [!NOTE]
>  Sintaxis del archivo de configuración distingue mayúsculas de minúsculas. Debe usar la sintaxis como se indica en las secciones de sintaxis y ejemplo.  
  
## <a name="configuration-file"></a>Archivo de configuración  
 Este elemento se puede usar únicamente en el archivo de configuración de aplicación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo habilitar la directiva CAS heredada para una aplicación.  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)

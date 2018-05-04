---
title: '&lt;developmentMode&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode
- http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode
helpviewer_keywords:
- developmentMode element
- container tags, <developmentMode> element
- <developmentMode> element
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71b4eb1dfb50774cea2f7a50d5e5350b0338f41e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltdevelopmentmodegt-element"></a>&lt;developmentMode&gt; elemento
Especifica si el runtime busca ensamblados en los directorios especificados por la variable de entorno DEVPATH.  
  
 \<configuration>  
\<en tiempo de ejecución >  
\<developmentMode >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|**developerInstallation**|Especifica si el runtime busca ensamblados en los directorios especificados por la variable de entorno DEVPATH.|  
  
## <a name="developerinstallation-attribute"></a>Atributo developerInstallation  
  
|Valor|Descripción|  
|-----------|-----------------|  
|**true**|Busca los ensamblados en los directorios especificados por la variable de entorno DEVPATH.|  
|**false**|No buscar ensamblados en los directorios especificados por la variable de entorno DEVPATH. Este es el valor predeterminado|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 Use esta opción solo en tiempo de desarrollo. El tiempo de ejecución no comprueba las versiones de ensamblados con nombre seguro que se encuentran en la variable DEVPATH. Simplemente utiliza el primer ensamblado que encuentre.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo hacer que el tiempo de ejecución buscar ensamblados en los directorios especificados por la variable de entorno DEVPATH.  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Cómo: Buscar ensamblados mediante DEVPATH](../../../../../docs/framework/configure-apps/how-to-locate-assemblies-by-using-devpath.md)

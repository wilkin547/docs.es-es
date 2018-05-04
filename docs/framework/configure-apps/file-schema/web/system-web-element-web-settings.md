---
title: '&lt;System.Web&gt; elemento (configuración Web)'
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 7527ee9e7528a0da47529bae93e8112705e03a36
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltsystemwebgt-element-web-settings"></a>&lt;System.Web&gt; elemento (configuración Web)
Contiene información acerca de cómo el nivel de hospedaje de ASP.NET administra el comportamiento de todo el proceso.  
  
 \<configuration>  
\<System.Web > elemento (configuración Web)  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<applicationPool>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|Especifica la configuración de grupos de aplicaciones de IIS en un archivo aspnet.config.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Especifica el elemento raíz necesario en cada archivo de configuración usado por Common Language Runtime y por las aplicaciones de [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] .|  
  
## <a name="remarks"></a>Comentarios  
 El `system.web` elemento y su elemento secundario `applicationPool` elemento se agregaron a la [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] de [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]. Al ejecutar [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o versiones posteriores en el modo integrado, esta combinación de elementos permite configurar cómo administra ASP.NET los subprocesos y cómo pone en cola las solicitudes cuando ASP.NET se hospeda en un grupo de aplicaciones de IIS. Si ejecuta [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o versiones posteriores en modo ISAPI o clásico, se pasa por alto esta configuración.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo configurar el comportamiento de todo el proceso ASP.NET en el archivo aspnet.config cuando ASP.NET se hospeda en un grupo de aplicaciones de IIS. En el ejemplo se da por supuesto que está ejecutando IIS en integrado modo y que la aplicación está utilizando el [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] o una versión posterior. Este comportamiento no se produce en las versiones de la [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] anteriores a la [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]. Los valores en el ejemplo son los valores predeterminados.  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool   
        maxConcurrentRequestsPerCPU="5000"   
        maxConcurrentThreadsPerCPU="0"   
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a>Información de elemento  
  
|||  
|-|-|  
|Espacio de nombres||  
|Nombre de esquema||  
|Archivo de validación||  
|Puede estar vacío||  
  
## <a name="see-also"></a>Vea también  
 [Elemento \<applicationPool> (configuración web)](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)

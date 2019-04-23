---
title: Elemento <system.web> (configuración web)
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
ms.openlocfilehash: 50566422c5e28585e93171c991144cf12a6866eb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59131955"
---
# <a name="systemweb-element-web-settings"></a>\<System.Web > elemento (configuración Web)
Contiene información sobre cómo administra el comportamiento de todo el proceso de la capa de hospedaje de ASP.NET.  
  
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
|[\<applicationPool>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|Especifica la configuración para grupos de aplicaciones de IIS en un archivo aspnet.config.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Especifica el elemento raíz necesario en cada archivo de configuración usado por Common Language Runtime y por las aplicaciones de [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] .|  
  
## <a name="remarks"></a>Comentarios  
 El `system.web` elemento y su elemento secundario `applicationPool` elemento se agregaron a la [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] de [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]. Al ejecutar [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o versiones posteriores en el modo integrado, esta combinación de elemento le permite configurar cómo administra los subprocesos de ASP.NET y cómo pone en cola las solicitudes cuando ASP.NET se hospeda en un grupo de aplicaciones de IIS. Si ejecuta [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o versiones posteriores en el modo ISAPI o clásico, se omiten estos valores.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo configurar el comportamiento de todo el proceso ASP.NET en el archivo aspnet.config cuando ASP.NET se hospeda en un grupo de aplicaciones de IIS. El ejemplo se supone que se está ejecutando IIS en integrado modo y que la aplicación está utilizando el [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] o una versión posterior. Este comportamiento no se produce en las versiones de la [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] anterior a la [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]. Los valores en el ejemplo son los valores predeterminados.  
  
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

- [Elemento \<applicationPool> (configuración web)](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)

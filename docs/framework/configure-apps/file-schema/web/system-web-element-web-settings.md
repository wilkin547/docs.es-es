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
ms.openlocfilehash: 3ffd25dae3826df0f02f2afb707f7317b2d92d24
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65584549"
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
|[\<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Especifica el elemento raíz de cada archivo de configuración que usa el common language runtime y aplicaciones de .NET Framework.|  
  
## <a name="remarks"></a>Comentarios  
 El `system.web` elemento y su elemento secundario `applicationPool` elemento se agregaron a partir de .NET Framework [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]. Al ejecutar [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o versiones posteriores en el modo integrado, esta combinación de elemento le permite configurar cómo administra los subprocesos de ASP.NET y cómo pone en cola las solicitudes cuando ASP.NET se hospeda en un grupo de aplicaciones de IIS. Si ejecuta [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o versiones posteriores en el modo ISAPI o clásico, se omiten estos valores.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo configurar el comportamiento de todo el proceso ASP.NET en el archivo aspnet.config cuando ASP.NET se hospeda en un grupo de aplicaciones de IIS. El ejemplo se supone que se está ejecutando IIS en integrado modo y que la aplicación está utilizando el [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] o una versión posterior. Este comportamiento no se produce en las versiones de .NET Framework anteriores a la [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]. Los valores en el ejemplo son los valores predeterminados.  
  
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

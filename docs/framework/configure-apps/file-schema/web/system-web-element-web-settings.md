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
ms.openlocfilehash: 687398e47ad95e3234c29571eeeac0c9d2d83a39
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2019
ms.locfileid: "66832790"
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
 El `system.web` elemento y su elemento secundario `applicationPool` elemento se han agregado a .NET Framework a partir de .NET Framework 3.5 SP1. Al ejecutar [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o versiones posteriores en el modo integrado, esta combinación de elemento le permite configurar cómo administra los subprocesos de ASP.NET y cómo pone en cola las solicitudes cuando ASP.NET se hospeda en un grupo de aplicaciones de IIS. Si ejecuta [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o versiones posteriores en el modo ISAPI o clásico, se omiten estos valores.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo configurar el comportamiento de todo el proceso ASP.NET en el archivo aspnet.config cuando ASP.NET se hospeda en un grupo de aplicaciones de IIS. El ejemplo se supone que se está ejecutando IIS en integrado modo y que la aplicación está utilizando .NET Framework 3.5 SP1 o una versión posterior. Este comportamiento no se produce en las versiones de .NET Framework anteriores a .NET Framework 3.5 SP1. Los valores en el ejemplo son los valores predeterminados.  
  
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

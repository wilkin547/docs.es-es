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
ms.openlocfilehash: b37b05bdf90630251cbfcf86751243a3a8b77663
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152846"
---
# <a name="systemweb-element-web-settings"></a>\<system.web> Element (Configuración web)
Contiene información sobre cómo la capa de hospedaje de ASP.NET administra el comportamiento de todo el proceso.  
  
[**\<configuración>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.web>**  
  
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
|[\<applicationPool>](applicationpool-element-web-settings.md)|Especifica la configuración de los grupos de aplicaciones IIS en un archivo aspnet.config.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<configuración>](../configuration-element.md)|Especifica el elemento raíz en cada archivo de configuración que usan las aplicaciones de Common Language Runtime y .NET Framework.|  
  
## <a name="remarks"></a>Observaciones  

El `system.web` elemento y `applicationPool` su elemento secundario se agregaron a .NET Framework a partir de .NET Framework 3.5 SP1. Al ejecutar IIS 7.0 o versiones posteriores en modo integrado, esta combinación de elementos le permite configurar cómo ASP.NET administra los subprocesos y cómo pone en cola las solicitudes cuando se hospeda ASP.NET en un grupo de aplicaciones IIS. Si ejecuta IIS 7.0 o versiones posteriores en modo clásico o ISAPI, se omite esta configuración.  
  
## <a name="example"></a>Ejemplo  

En el ejemplo siguiente se muestra cómo configurar ASP.NET comportamiento de todo el proceso en el archivo aspnet.config cuando ASP.NET se hospeda en un grupo de aplicaciones IIS. En el ejemplo se supone que IIS se ejecuta en modo integrado y que la aplicación usa .NET Framework 3.5 SP1 o una versión posterior. Este comportamiento no se produce en versiones de .NET Framework anteriores a .NET Framework 3.5 SP1. Los valores del ejemplo son los valores predeterminados.  
  
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
|Nombre del esquema||  
|Archivo de validación||  
|Puede estar vacío||  
  
## <a name="see-also"></a>Consulte también

- [\<ApplicationPool> Element (Configuración web)](applicationpool-element-web-settings.md)

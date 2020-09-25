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
ms.openlocfilehash: c8b01ec217fc1b6b91ccf36c8667922b57f26852
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185592"
---
# <a name="systemweb-element-web-settings"></a>Elemento \<system.web> (configuración web)

Contiene información sobre cómo el nivel de hospedaje de ASP.NET administra el comportamiento de todo el proceso.  
  
[**\<configuration>**](../configuration-element.md)  
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
|[\<applicationPool>](applicationpool-element-web-settings.md)|Especifica los valores de configuración para los grupos de aplicaciones de IIS en un archivo aspnet.config.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|Especifica el elemento raíz de cada archivo de configuración usado por las aplicaciones Common Language Runtime y .NET Framework.|  
  
## <a name="remarks"></a>Observaciones  

El `system.web` elemento y su `applicationPool` elemento secundario se agregaron a la .NET Framework a partir de .NET Framework 3,5 SP1. Al ejecutar IIS 7,0 o versiones posteriores en el modo integrado, esta combinación de elementos le permite configurar el modo en que ASP.NET administra los subprocesos y cómo pone en cola las solicitudes cuando ASP.NET se hospeda en un grupo de aplicaciones de IIS. Si ejecuta IIS 7,0 o versiones posteriores en el modo clásico o ISAPI, se omiten estos valores de configuración.  
  
## <a name="example"></a>Ejemplo  

En el ejemplo siguiente se muestra cómo configurar el comportamiento de todo el proceso de ASP.NET en el archivo de aspnet.config cuando ASP.NET se hospeda en un grupo de aplicaciones de IIS. En el ejemplo se da por supuesto que IIS se ejecuta en modo integrado y que la aplicación está usando .NET Framework 3,5 SP1 o una versión posterior. Este comportamiento no se produce en las versiones de .NET Framework anteriores al .NET Framework 3,5 SP1. Los valores del ejemplo son los valores predeterminados.  
  
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

- [\<applicationPool> (Elemento, configuración Web)](applicationpool-element-web-settings.md)

---
title: '&lt;configuración de&gt; elemento (configuración de red)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#settings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings
helpviewer_keywords:
- settings element
- <settings> element
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 9d6189c736e1f2843a986c3a96f8547e9a231db0
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48033238"
---
# <a name="ltsettingsgt-element-network-settings"></a>&lt;configuración de&gt; elemento (configuración de red)
Configura opciones de red básicas para el espacio de nombres <xref:System.Net?displayProperty=nameWithType>.  
  
 \<configuration>  
\<System.NET >  
\<Configuración >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<settings>  
  <httpListener> … </httpListener>  
  <httpWebRequest> … </httpWebRequest>  
  <ipv6> … </ipv6>  
  <performanceCounters> … </performanceCounters>  
  <servicePointManager> … </servicePointManager>  
  <socket> … </socket>  
  <webProxyScript> … </webProxyScript>  
</settings>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[httpListener](../../../../../docs/framework/configure-apps/file-schema/network/httplistener-element-network-settings.md)|Personaliza los parámetros utilizados por la <xref:System.Net.HttpListener> clase.|  
|[httpWebRequest](../../../../../docs/framework/configure-apps/file-schema/network/httpwebrequest-element-network-settings.md)|Personaliza los parámetros de solicitud Web.|  
|[IPv6](../../../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)|Habilita el protocolo de Internet versión 6 (IPv6) admite.|  
|[\<performanceCounter > elemento (configuración de red)](../../../../../docs/framework/configure-apps/file-schema/network/performancecounter-element-network-settings.md)|Habilita los contadores de rendimiento de red.|  
|[servicePointManager](../../../../../docs/framework/configure-apps/file-schema/network/servicepointmanager-element-network-settings.md)|Configura las conexiones a los recursos de red.|  
|[Socket](../../../../../docs/framework/configure-apps/file-schema/network/socket-element-network-settings.md)|Especifica si las operaciones de socket utilizan puertos de terminación.|  
|[\<webProxyScript > elemento (configuración de red)](../../../../../docs/framework/configure-apps/file-schema/network/webproxyscript-element-network-settings.md)|Configura las características de la secuencia de comandos que se usa para detectar a servidores proxy Web.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[System.NET](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Contiene valores que especifican cómo se conecta .NET Framework a la red.|  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Net?displayProperty=nameWithType>  
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

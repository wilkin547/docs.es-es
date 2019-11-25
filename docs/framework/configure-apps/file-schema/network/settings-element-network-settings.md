---
title: Elemento <settings> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#settings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings
helpviewer_keywords:
- settings element
- <settings> element
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
ms.openlocfilehash: d510c445c585a36005ed415b14188efc4be03984
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089115"
---
# <a name="settings-element-network-settings"></a>Elemento > de configuración de \<(configuración de red)
Configura opciones de red básicas para el espacio de nombres <xref:System.Net?displayProperty=nameWithType>.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<** >

## <a name="syntax"></a>Sintaxis  
  
```xml  
<settings>  
  <httpListener>...</httpListener>  
  <httpWebRequest>...</httpWebRequest>  
  <ipv6>...</ipv6>  
  <performanceCounters>...</performanceCounters>  
  <servicePointManager>...</servicePointManager>  
  <socket>...</socket>  
  <webProxyScript>...</webProxyScript>  
</settings>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[httpListener](httplistener-element-network-settings.md)|Personaliza los parámetros utilizados por la clase <xref:System.Net.HttpListener>.|  
|[httpWebRequest](httpwebrequest-element-network-settings.md)|Personaliza los parámetros de la solicitud Web.|  
|[Protocolo](ipv6-element-network-settings.md)|Habilita la compatibilidad con el protocolo de Internet versión 6 (IPv6).|  
|[\<elemento > performanceCounter (configuración de red)](performancecounter-element-network-settings.md)|Habilita los contadores de rendimiento de red.|  
|[servicePointManager](servicepointmanager-element-network-settings.md)|Configura las conexiones a los recursos de red.|  
|[tomacorriente](socket-element-network-settings.md)|Especifica si las operaciones de socket utilizan puertos de finalización.|  
|[\<elemento > webProxyScript (configuración de red)](webproxyscript-element-network-settings.md)|Configura las características del script que se usan para detectar los proxies Web.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[system.net](system-net-element-network-settings.md)|Contiene valores que especifican cómo se conecta .NET Framework a la red.|  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Net?displayProperty=nameWithType>
- [Esquema de la configuración de red](index.md)

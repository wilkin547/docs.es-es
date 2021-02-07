---
description: 'Más información acerca de: <settings> elemento (configuración de red)'
title: Elemento <settings> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#settings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings
helpviewer_keywords:
- settings element
- <settings> element
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
ms.openlocfilehash: e6ed242e68ac9a9e2c20067d66681bbcd51fcc50
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712979"
---
# <a name="settings-element-network-settings"></a>Elemento \<settings> (configuración de red)

Configura opciones de red básicas para el espacio de nombres <xref:System.Net?displayProperty=nameWithType>.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<settings>**

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
|[httpListener](httplistener-element-network-settings.md)|Personaliza los parámetros utilizados por la <xref:System.Net.HttpListener> clase.|  
|[httpWebRequest](httpwebrequest-element-network-settings.md)|Personaliza los parámetros de la solicitud Web.|  
|[Protocolo](ipv6-element-network-settings.md)|Habilita la compatibilidad con el protocolo de Internet versión 6 (IPv6).|  
|[Elemento \<performanceCounter> (configuración de red)](performancecounter-element-network-settings.md)|Habilita los contadores de rendimiento de red.|  
|[servicePointManager](servicepointmanager-element-network-settings.md)|Configura las conexiones a los recursos de red.|  
|[tomacorriente](socket-element-network-settings.md)|Especifica si las operaciones de socket utilizan puertos de finalización.|  
|[Elemento \<webProxyScript> (configuración de red)](webproxyscript-element-network-settings.md)|Configura las características del script que se usan para detectar los proxies Web.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[system.net](system-net-element-network-settings.md)|Contiene valores que especifican cómo se conecta .NET Framework a la red.|  
  
## <a name="remarks"></a>Observaciones  
  
## <a name="configuration-files"></a>Archivos de configuración  

 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Net?displayProperty=nameWithType>
- [Esquema de la configuración de red](index.md)

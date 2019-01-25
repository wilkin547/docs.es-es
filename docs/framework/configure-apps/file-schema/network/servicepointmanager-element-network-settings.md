---
title: '&lt;servicePointManager&gt; elemento (configuración de red)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
ms.openlocfilehash: e30d38e3b925283b6048730aef2acc865be755b6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54651622"
---
# <a name="ltservicepointmanagergt-element-network-settings"></a>&lt;servicePointManager&gt; elemento (configuración de red)
Configura las conexiones a los recursos de red.  
  
 \<configuration>  
\<system.net>  
\<settings>  
\<servicePointManager>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<servicePointManager  
  checkCertificateName="true|false"  
  checkCertificateRevocationList="true|false"  
  encryptionPolicy="AllowNoEncryption|NoEncryption|RequireEncryption"  
  expect100Continue="true|false"  
  useNagleAlgorithm="true|false"  
  enableDnsRoundRobin="true|false"  
  dnsRefreshTimeout="time"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|**Attribute**|**Descripción**|  
|-------------------|---------------------|  
|`checkCertificateName`|Especifica si el sistema debe comprobar que el nombre del certificado coincide con el nombre de host del servidor antes de usar el certificado. El valor predeterminado es `true`.|  
|`checkCertificateRevocationList`|Especifica si el sistema debe comprobar si se ha revocado el certificado antes de usar el certificado. El valor predeterminado es `false`.|  
|`dnsRefreshTimeout`|Especifica cuánto nombre servicio dominio (DNS) se almacenan en caché las resoluciones junto con la opción de operación por turnos DNS, en milisegundos. El valor predeterminado es 120.000 milisegundos (dos minutos).|  
|`enableDnsRoundRobin`|Especifica si las resoluciones DNS del host de nombres con varias direcciones de protocolo de Internet (IP) devueltas todas las direcciones o solo la primera de ellas. El valor predeterminado es `false`.|  
|`encryptionPolicy`|Especifica la directiva de cifrado que se aplica a una sesión SSL/TLS en un <xref:System.Net.ServicePointManager> instancia. Los valores posibles son equivalentes a los valores de la <xref:System.Net.Security.EncryptionPolicy> enumeración. El uso de <xref:System.Security.Authentication.CipherAlgorithmType.Null> es necesaria cuando la directiva de cifrado se establece en `NoEncryption`. El valor predeterminado es `RequireEncryption`.|  
|`expect100Continue`|Especifica si los métodos POST deben esperar recibir una `100-continue` respuesta del servidor. El valor predeterminado es `true`.|  
|`useNagleAlgorithm`|Especifica si las conexiones controladas por el Administrador de punto de servicio utilizan el algoritmo de Nagle. El valor predeterminado es `true`.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[Configuración](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.|  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

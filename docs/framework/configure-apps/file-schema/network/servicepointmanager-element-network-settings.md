---
title: '&lt;servicePointManager&gt; Element (Network Settings)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 5903174f125938923a63fc031421a8d5a020e56d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltservicepointmanagergt-element-network-settings"></a>&lt;servicePointManager&gt; Element (Network Settings)
Configura las conexiones a los recursos de red.  
  
 \<configuration>  
\<System.NET >  
\<Configuración >  
\<servicePointManager >  
  
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
|`checkCertificateName`|Especifica si el sistema debe comprobar que el nombre del certificado coincide con el nombre de host del servidor antes de utilizar el certificado. El valor predeterminado es `true`.|  
|`checkCertificateRevocationList`|Especifica si el sistema debe comprobar si se ha revocado el certificado antes de usar el certificado. El valor predeterminado es `false`.|  
|`dnsRefreshTimeout`|Especifica cuánto tiempo dominio servicio de nombres (DNS) se almacenan en caché las soluciones junto con la opción de DNS Round Robin, en milisegundos. El valor predeterminado es 120.000 milisegundos (dos minutos).|  
|`enableDnsRoundRobin`|Especifica si las resoluciones DNS de host nombres con varias direcciones de protocolo de Internet (IP) devueltos de todas las direcciones o simplemente la primera de ellas. El valor predeterminado es `false`.|  
|`encryptionPolicy`|Especifica la directiva de cifrado que se aplica a una sesión SSL/TLS en un <xref:System.Net.ServicePointManager> instancia. Los valores posibles son equivalentes a los valores para el <xref:System.Net.Security.EncryptionPolicy> enumeración. El uso de <xref:System.Security.Authentication.CipherAlgorithmType.Null> es necesaria cuando la directiva de cifrado se establece en `NoEncryption`. El valor predeterminado es `RequireEncryption`.|  
|`expect100Continue`|Especifica si los métodos POST deben esperar recibir un `100-continue` respuesta del servidor. El valor predeterminado es `true`.|  
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
 <xref:System.Net.ServicePointManager>  
 <xref:System.Net.Security.EncryptionPolicy>  
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

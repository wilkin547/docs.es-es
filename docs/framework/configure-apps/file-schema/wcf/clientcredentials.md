---
title: <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: ebe976df9af0c316e95a1e089412e57a575a6df1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157240"
---
# <a name="clientcredentials"></a>\<clientCredentials>
Especifica las credenciales usadas para autenticar el cliente en un servicio.  
  
 \<system.ServiceModel>  
\<comportamientos >  
\<endpointBehaviors>  
\<comportamiento >  
\<clientCredentials>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<clientCredentials type="String"
                   supportInteractive="Boolean" >
  <clientCertificate>
  </clientCertificate>
  <digest>
  </digest>
  <isuedToken>
  </isuedToken>
  <peer>
  </peer>
  <serviceCertificate>
  </serviceCertificate>
  <windowsAuthentication>
  </windowsAuthentication>
</clientCredentials>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`supportInteractive`|Un valor booleano que especifica si un usuario interactivo puede estar implicado en la selección de una credencial del cliente en tiempo de ejecución. El valor predeterminado es `true`.|  
|`type`|Una cadena que especifica el tipo de este elemento de configuración.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<clientCertificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md)|Especifica el certificado usado para autenticar el cliente al servicio. Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.|  
|[\<httpDigest>](../../../../../docs/framework/configure-apps/file-schema/wcf/httpdigest-element.md)|Especifica el uso de una autenticación implícita para autenticar el cliente al servicio. Este elemento es del tipo <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.|  
|[\<issuedToken>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|Especifica un tipo de token usado para autenticar el cliente a un servicio de token seguro (STS). Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.|  
|[\<peer>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|Especifica una credencial del mismo nivel actual. Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerCredentialElement>.|  
|[\<serviceCertificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|Especifica el certificado usado para autenticar el servicio al cliente y proporciona una estructura para establecer las opciones de certificado. Este certificado se debe proporcionar fuera de banda del servicio al cliente. Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.|  
|[\<windows>](../../../../../docs/framework/configure-apps/file-schema/wcf/windows-of-clientcredentials-element.md)|Especifica la credencial de Windows. El valor predeterminado es la credencial del subproceso actual. Este elemento es del tipo <xref:System.ServiceModel.Configuration.WindowsClientElement>.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Especifica el comportamiento de un punto de conexión.|  
  
## <a name="remarks"></a>Comentarios  
 Las credenciales de cliente se utilizan para autenticar al cliente en los servicios en casos donde se requiere autenticación mutua. Esta sección de configuración también se puede usar para especificar los certificados de servicio para escenarios donde el cliente debe proteger los mensajes para un servicio con el certificado del servicio.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [Comportamientos de seguridad](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [Protección de clientes](../../../../../docs/framework/wcf/securing-clients.md)

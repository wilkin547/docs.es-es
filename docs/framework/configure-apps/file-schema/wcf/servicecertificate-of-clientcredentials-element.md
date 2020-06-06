---
title: <serviceCertificate>del <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: 4c7489a171bdd5cb4b747ca99f1b7ff6dd65517b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399682"
---
# <a name="servicecertificate-of-clientcredentials-element"></a>\<serviceCertificate>del \<clientCredentials> elemento
Especifica el certificado que se va a utilizar al autenticar un servicio al cliente.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<serviceCertificate />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<defaultCertificate>](defaultcertificate-element.md)|Especifica un certificado X.509 que se usará cuando un servicio o STS no proporcione uno a través de un protocolo de negociación.|  
|[\<scopedCertificates>](scopedcertificates-element.md)|Representa una colección de certificados X.509 proporcionada por servicios concretos (con ámbito) para la autenticación. Esta colección se utiliza normalmente para especificar los certificados de servicio para los servicios de token de seguridad en un escenario asociado externo.|  
|[\<authentication>](authentication-of-servicecertificate-element.md)|Especifica los comportamientos de autenticación para los certificados de servicio utilizados por un cliente.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|Especifica las credenciales utilizadas por el cliente para autenticarse a un servicio.|  
  
## <a name="remarks"></a>Comentarios  
 Este elemento de configuración especifica la configuración utilizada por el cliente para validar el certificado presentado por el servicio utilizando la autenticación SSL. También contiene cualquier certificado para el servicio que se configura explícitamente en el cliente y que se utiliza para cifrar los mensajes para el servicio, utilizando la seguridad de mensaje.  
  
 Los atributos del `serviceCertificate` elemento son idénticos a los atributos de [\<clientCertificate>](clientcertificate-of-clientcredentials-element.md) .  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- [Comportamientos de seguridad](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Protección de clientes](../../../wcf/securing-clients.md)
- [Trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md)
- [Protección de servicios y clientes](../../../wcf/feature-details/securing-services-and-clients.md)

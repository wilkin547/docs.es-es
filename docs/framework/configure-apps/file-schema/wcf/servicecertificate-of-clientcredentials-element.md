---
title: Elemento &lt;serviceCertificate&gt; de &lt;clientCredentials&gt;
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: 1d54c39fd681e0686e419b7b73243703e9184d1f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltservicecertificategt-of-ltclientcredentialsgt-element"></a>Elemento &lt;serviceCertificate&gt; de &lt;clientCredentials&gt;
Especifica el certificado que se va a utilizar al autenticar un servicio al cliente.  
  
 \<system.ServiceModel>  
\<comportamientos >  
\<endpointBehaviors >  
\<comportamiento >  
\<clientCredentials >  
\<serviceCertificate >  
  
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
|[\<defaultCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md)|Especifica un certificado X.509 que se usará cuando un servicio o STS no proporcione uno a través de un protocolo de negociación.|  
|[\<scopedCertificates >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md)|Representa una colección de certificados X.509 proporcionada por servicios concretos (con ámbito) para la autenticación. Esta colección se utiliza normalmente para especificar los certificados de servicio para los servicios de token de seguridad en un escenario asociado externo.|  
|[\<autenticación >](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md)|Especifica los comportamientos de autenticación para los certificados de servicio utilizados por un cliente.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Especifica las credenciales utilizadas por el cliente para autenticarse a un servicio.|  
  
## <a name="remarks"></a>Comentarios  
 Este elemento de configuración especifica la configuración utilizada por el cliente para validar el certificado presentado por el servicio utilizando la autenticación SSL. También contiene cualquier certificado para el servicio que se configura explícitamente en el cliente y que se utiliza para cifrar los mensajes para el servicio, utilizando la seguridad de mensaje.  
  
 Los atributos de la `serviceCertificate` elemento son idénticos a los atributos de la [ \<clientCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 [Comportamientos de seguridad](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Protección de clientes](../../../../../docs/framework/wcf/securing-clients.md)  
 [Trabajo con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)

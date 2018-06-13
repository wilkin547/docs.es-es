---
title: '&lt;clientCertificate&gt; de &lt;serviceCredentials&gt;'
ms.date: 03/30/2017
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
ms.openlocfilehash: c33c6d6a80625028b9d97ab486cf50e4970b8941
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748924"
---
# <a name="ltclientcertificategt-of-ltservicecredentialsgt"></a>&lt;clientCertificate&gt; de &lt;serviceCredentials&gt;
Define un certificado X.509 usado para firmar y cifrar mensajes a un formulario de cliente un servicio en un modelo de comunicación dúplex.  
  
 \<system.ServiceModel>  
\<comportamientos >  
\<serviceBehaviors >  
\<serviceBehaviors >  
\<comportamiento >  
\<serviceCredentials >  
\<clientCertificate >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<clientCertificate>  
 <certificate/>  
 <authentication/>  
</clientCertificate>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<autenticación >](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)|Especifica las opciones de autenticación del certificado de cliente.|  
|[\<certificado >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-clientcertificate-element.md)|Especifica el certificado que se va a usar.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<serviceCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Especifica las credenciales que se van a usar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.|  
  
## <a name="remarks"></a>Comentarios  
 Este elemento se usa cuando el servicio debe tener el certificado del cliente por anticipado para comunicarse de manera segura con el cliente. Esto se produce al utilizar el patrón de comunicación dúplex. En el patrón de solicitud/respuesta más típico, el cliente incluye su certificado en la solicitud, que utiliza el servicio para cifrar i firmar su respuesta de vuelta hasta el cliente. Sin embargo, en el patrón de comunicación dúplex, el servicio no tiene una solicitud del cliente y por consiguiente necesita que el certificado del cliente proteja de antemano el mensaje al cliente. Por tanto, debe obtener el certificado del cliente en una negociación fuera de banda y especificar el certificado usando este elemento. Para obtener más información sobre los servicios dúplex, consulte [Cómo: crear un contrato dúplex](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
 El conjunto de certificados de este elemento se utiliza para cifrar los mensajes para el cliente únicamente para los enlaces que se configuran con `MutualCertificateDuplex` el modo de autenticación de seguridad de mensajes.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>  
 [Creación de un contrato dúplex](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [Comportamientos de seguridad](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Trabajo con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)

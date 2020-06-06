---
title: <security> de <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
ms.openlocfilehash: c8e4f2d000a155eecd2a6c7faaaf4af525b24ca3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738706"
---
# <a name="security-of-basichttpbinding"></a>\<security> de \<basicHttpBinding>
Define las capacidades de seguridad de [\<basicHttpBinding>](basichttpbinding.md) .  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|mode|Opcional. Especifica el tipo de seguridad que se utiliza. De manera predeterminada, es `None`. Este atributo es del tipo <xref:System.ServiceModel.BasicHttpSecurityMode>.|  
  
## <a name="mode-attribute"></a>Atributo de modo  
  
|Value|Descripción|  
|-----------|-----------------|  
|None|: Los mensajes no están protegidos durante la transferencia.|  
|Transporte|La seguridad se proporciona utilizando transporte HTTPS. Los mensajes SOAP están protegidos mediante HTTPS. El servicio se autentica al cliente utilizando el certificado X.509 del servicio. El cliente se autentica utilizando el ClientCredentialType proporcionado. Vea [\<transport>](transport-of-basichttpbinding.md) .|  
|Message|La seguridad se proporciona mediante la seguridad del mensaje SOAP. De forma predeterminada, el cuerpo se cifra y firma. Para este enlace, el sistema requiere que el certificado de servidor se proporcione al cliente fuera de la banda. El único `ClientCredentialType` válido para este enlace es `Certificate`.|  
|TransportWithMessageCredential|La seguridad de transporte proporciona integridad, confidencialidad y autenticación del servidor. La autenticación del cliente se proporciona por medio de la seguridad del mensaje SOAP. Este modo es pertinente cuando el usuario está autenticando utilizando el nombre de usuario/contraseña y existe una implementación del HTTP existente para proteger la transferencia del mensaje.|  
|TransportCredentialOnly|Este modo no proporciona integridad del mensaje y confidencialidad. Proporciona la autenticación del cliente basada en http. Este modo se debe utilizar con precaución. Se debe usar en entornos en los que la seguridad de transporte se proporciona por otros medios (como IPSec) y la infraestructura de WCF proporciona únicamente la autenticación del cliente.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<transport>](transport-of-basichttpbinding.md)|Define los valores de seguridad de transporte para un servicio HTTP básico. Este elemento corresponde a <xref:System.ServiceModel.HttpTransportSecurity>.|  
|[\<message>](message-of-basichttpbinding.md)|Define los valores de modo de seguridad para un servicio HTTP básico. Este elemento corresponde a <xref:System.ServiceModel.BasicHttpMessageSecurity>.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|binding|Elemento de enlace de [\<basicHttpBinding>](basichttpbinding.md) .|  
  
## <a name="remarks"></a>Comentarios  
 De forma predeterminada, no se protege el mensaje SOAP y no se autentica el cliente. Este elemento le permite establecer la configuración de seguridad adicional para el elemento `basicHttpBinding`.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.BasicHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [Protección de servicios y clientes](../../../wcf/feature-details/securing-services-and-clients.md)
- [Selección de tipos de credenciales](../../../wcf/feature-details/selecting-a-credential-type.md)
- [Enlaces](../../../wcf/bindings.md)
- [Configuración de enlaces proporcionados por el sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Utilización de enlaces para configurar servicios y clientes](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)

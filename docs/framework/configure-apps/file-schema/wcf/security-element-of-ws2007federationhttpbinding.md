---
title: <security>elemento de<ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
ms.openlocfilehash: b85c54c6507313522286e0c66504cfd0c8afb2b0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738724"
---
# <a name="security-element-of-ws2007federationhttpbinding"></a>\<security>elemento de\<ws2007FederationHttpBinding>
Define la configuración de seguridad del [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) elemento.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<ws2007FederationBinding>
  <binding>
    <security mode="None/Message/TransportWithMessageCredential">
      <message negotiateServiceCredential="Boolean"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/  Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               defaultProtectionLevel="none/sign/EncryptAndSign"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey">
      </message>
    </security>
  </binding>
</ws2007FederationBinding>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`mode`|Opcional. Especifica el tipo de seguridad que se aplica. El valor predeterminado es `Message`. Este atributo es del tipo <xref:System.ServiceModel.WSFederationHttpSecurityMode>.|  
  
## <a name="mode-attribute"></a>Atributo de modo  
  
|Value|Descripción|  
|-----------|-----------------|  
|None|El mensaje SOAP no es seguro durante la transferencia.|  
|Message|La integridad, confidencialidad, autenticación de servidor y autenticación del cliente se proporciona mediante la seguridad del mensaje SOAP. De forma predeterminada, el cuerpo se cifra y firma. El servicio se debe configurar con un certificado. La autenticación del cliente está basada en el token emitido al cliente por un servicio del token de seguridad.|  
|TransportWithMessageCredential|HTTPS proporciona integridad, confidencialidad y autenticación del servidor. El servicio se debe configurar con un certificado. La autenticación del cliente se proporciona por medio de la seguridad del mensaje SOAP y está basada en el token emitido al cliente por un servicio de token de seguridad.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<message>](message-of-ws2007httpbinding.md)|Define la configuración de seguridad del nivel del mensaje. Este elemento es del tipo <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|Define todas las funciones de enlace de [\<wsDualHttpBinding>](wsdualhttpbinding.md) .|  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [Procedimiento para crear un WSFederationHttpBinding](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [Protección de servicios y clientes](../../../wcf/feature-details/securing-services-and-clients.md)
- [Selección de tipos de credenciales](../../../wcf/feature-details/selecting-a-credential-type.md)
- [Enlaces](../../../wcf/bindings.md)
- [Configuración de enlaces proporcionados por el sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Utilización de enlaces para configurar servicios y clientes](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)

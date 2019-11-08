---
title: <transport> de <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: 4ef08ad73a03dea21d27217364a7bacb46a3848e
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735932"
---
# <a name="transport-of-nettcpbinding"></a>\<transport> de \<netTcpBinding>
Define el tipo de requisitos de seguridad del nivel de mensaje para un extremo configurado con el [\<netTcpBinding](nettcpbinding.md).  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**netTcpBinding**](nettcpbinding.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**seguridad**](security-of-nettcpbinding.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**transporte** >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<netTcpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential">
      <transport clientCredentialType="None|Windows|Certificate"
                 protectionLevel="None|Sign|EncryptAndSign"
                 sslProtocols="Tls|Tls11|Tls12">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</netTcpBinding>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|clientCredentialType|Opcional. Especifica el tipo de credenciales que se van a usar al realizar la autenticación del cliente mediante seguridad de transporte.<br /><br /> -El valor predeterminado es `Windows`.<br />: Este atributo es del tipo <xref:System.ServiceModel.TcpClientCredentialType>.|  
|protectionLevel|Opcional. Define la seguridad en el nivel del transporte del TCP. Al firmar los mensajes se reduce el riesgo de que un tercero manipule el mensaje mientras se transfiere. El cifrado proporciona privacidad de nivel de datos durante el transporte.<br /><br /> El valor predeterminado es `EncryptAndSign`.|  
|sslProtocols|Un valor de marca de enumeración de SslProtocols que especifica qué SslProtocols son compatibles. El valor predeterminado es&#124;TLS&#124;Tls11 Tls12.|  
|policyEnforcement|Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.<br /><br /> 1. Never: la Directiva nunca se aplica (la protección ampliada está deshabilitada).<br />2. WhenSupported: la Directiva solo se aplica si el cliente admite la protección ampliada.<br />3. Always: siempre se aplica la Directiva. Los clientes que no admitan la protección extendida no podrán autenticarse.|  
  
## <a name="clientcredentialtype-attribute"></a>Atributo clientCredentialType  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Ninguno|El cliente es anónimo. Esto requiere un certificado para el servicio.|  
|Windows|Especifica la autenticación de Windows del cliente utilizando Negotiation de SP (negociación de Kerberos).|  
|Certificado|El cliente se autentica utilizando un certificado. Esto utiliza Negotiation de SSL y requiere un certificado para el servicio.|  
  
## <a name="protectionlevel-attribute"></a>Atributo protectionLevel  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Ninguno|Ninguna protección|  
|Signo|Se firman los mensajes.|  
|EncryptAndSign|-Los mensajes se cifran y firman.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<La >](security-of-nettcpbinding.md)|Especifica las capacidades de seguridad del [> de\<netTcpBinding](nettcpbinding.md).|  
  
## <a name="remarks"></a>Comentarios  
 Utilice la seguridad de transporte para la integridad y confidencialidad del mensaje SOAP y para la autenticación mutua. Si este modo de seguridad está seleccionado en un enlace, la pila del canal se configura utilizando un transporte seguro y los mensajes SOAP se protegen utilizando la seguridad de transporte, como Windows (Negotiate) o SSL sobre TCP.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.TcpTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [Protección de servicios y clientes](../../../wcf/feature-details/securing-services-and-clients.md)
- [Enlaces](../../../wcf/bindings.md)
- [Configuración de enlaces proporcionados por el sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Utilización de enlaces para configurar servicios y clientes](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<> de enlace](bindings.md)

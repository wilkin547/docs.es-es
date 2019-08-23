---
title: <transport> de <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: 265b68e058919d1d5c5f1dbcfb1419b57be9aeab
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915547"
---
# <a name="transport-of-nettcpbinding"></a>\<transport> de \<netTcpBinding>
Define el tipo de requisitos de seguridad del nivel de mensaje para un extremo configurado con el [ \<> netTcpBinding](nettcpbinding.md).  
  
 \<system.ServiceModel>  
\<bindings>  
\<netTcpBinding>  
\<binding>  
\<> de seguridad  
\<> de transporte  
  
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
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|clientCredentialType|Opcional. Especifica el tipo de credenciales que se van a usar al realizar la autenticación del cliente mediante seguridad de transporte.<br /><br /> -El valor predeterminado es `Windows`.<br />: Este atributo es del tipo <xref:System.ServiceModel.TcpClientCredentialType>.|  
|protectionLevel|Opcional. Define la seguridad en el nivel del transporte del TCP. Al firmar los mensajes se reduce el riesgo de que un tercero manipule el mensaje mientras se transfiere. El cifrado proporciona privacidad de nivel de datos durante el transporte.<br /><br /> El valor predeterminado es `EncryptAndSign`.|  
|sslProtocols|Un valor de marca de enumeración de SslProtocols que especifica qué SslProtocols son compatibles. El valor predeterminado es&#124;TLS&#124;Tls11 Tls12.|  
|policyEnforcement|Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.<br /><br /> 1.  Never: la directiva nunca se aplica (la protección extendida está deshabilitada).<br />2.  WhenSupported: la directiva solamente se aplica si el cliente admite la protección extendida.<br />3.  Always: la directiva siempre se aplica. Los clientes que no admitan la protección extendida no podrán autenticarse.|  
  
## <a name="clientcredentialtype-attribute"></a>Atributo clientCredentialType  
  
|Valor|DESCRIPCIÓN|  
|-----------|-----------------|  
|None|El cliente es anónimo. Esto requiere un certificado para el servicio.|  
|Windows|Especifica la autenticación de Windows del cliente utilizando Negotiation de SP (negociación de Kerberos).|  
|Certificate|El cliente se autentica utilizando un certificado. Esto utiliza Negotiation de SSL y requiere un certificado para el servicio.|  
  
## <a name="protectionlevel-attribute"></a>Atributo protectionLevel  
  
|Value|DESCRIPCIÓN|  
|-----------|-----------------|  
|None|Ninguna protección|  
|Signo|Se firman los mensajes.|  
|EncryptAndSign|-Los mensajes se cifran y firman.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 None  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<security>](security-of-nettcpbinding.md)|Especifica las capacidades de seguridad de la [ \<> netTcpBinding](nettcpbinding.md).|  
  
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
- [\<binding>](../../../misc/binding.md)

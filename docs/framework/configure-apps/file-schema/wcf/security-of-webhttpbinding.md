---
title: <security> de <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 77009dc950a608da9e0db3a7d09be67e1ed46137
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738639"
---
# <a name="security-of-webhttpbinding"></a>\<> de seguridad de \<webHttpBinding >
Especifica los requisitos de seguridad para un extremo configurado con un [\<webHttpBinding >](webhttpbinding.md).  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**webHttpBinding**](webhttpbinding.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**seguridad** >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.ServiceModel>
  <bindings>
    <webHttpBinding>
      <binding name = "String">
        <security mode="None/Transport/TransportCredentialOnly">
          <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
                     proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
                     realm="String" />
        </security>
      </binding>
    </webHttpBinding>
  </bindings>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|modo|Especifica si un punto de conexión usa la seguridad a nivel de transporte o no usa ninguna. De manera predeterminada, es `None`. Este atributo es del tipo <xref:System.ServiceModel.WebHttpSecurityMode>.|  
  
## <a name="mode-attribute"></a>Atributo de modo  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Ninguno|La seguridad está deshabilitada.|  
|Transporte|La seguridad se proporciona utilizando HTTPS. El servicio necesita ser configurado con certificados SSL. El mensaje se protege completamente utilizando HTTPS y el servicio se autentica por el cliente usando el certificado SSL del servicio. La autenticación del cliente se controla a través del atributo `ClientCredentialType` del [> de transporte de\<](transport-of-webhttpbinding.md).|  
|TransportCredentialOnly|Este modo no proporciona integridad del mensaje y confidencialidad. Proporciona la autenticación del cliente basada en HTTP. Este modo se debe utilizar con precaución. Se debe usar en entornos en los que la seguridad de transporte se proporciona por otros medios (como IPSec) y la infraestructura de WCF proporciona únicamente la autenticación del cliente.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[> de transporte de \<](transport-of-webhttpbinding.md)|Define la configuración de seguridad para el transporte. Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<webHttpBinding>](webhttpbinding.md)|Un elemento de enlace que se utiliza para configurar los extremos de los servicios Web de Windows Communication Foundation (WCF) que responden a las solicitudes HTTP en lugar de a los mensajes SOAP.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [Protección de servicios y clientes](../../../wcf/feature-details/securing-services-and-clients.md)
- [Selección de tipos de credenciales](../../../wcf/feature-details/selecting-a-credential-type.md)
- [Enlaces](../../../wcf/bindings.md)
- [Configuración de enlaces proporcionados por el sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Utilización de enlaces para configurar servicios y clientes](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<> de enlace](bindings.md)
- [Modelo de programación de web HTTP de WCF](../../../wcf/feature-details/wcf-web-http-programming-model.md)

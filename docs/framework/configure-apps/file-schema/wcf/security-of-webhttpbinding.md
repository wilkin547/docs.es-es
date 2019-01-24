---
title: '&lt;security&gt; de &lt;webHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 966dcba7c70419cfb7ca62016b4ee1d24df29827
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54502031"
---
# <a name="ltsecuritygt-of-ltwebhttpbindinggt"></a>&lt;security&gt; de &lt;webHttpBinding&gt;
Especifica los requisitos de seguridad para un extremo configurado con un [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).  
  
 \<system.ServiceModel>  
\<bindings>  
\<webHttpBinding>  
\<binding>  
\<security>  
  
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
|modo|Especifica si un extremo usa la seguridad a nivel de transporte o no usa ninguna. De manera predeterminada, es `None`. Este atributo es del tipo <xref:System.ServiceModel.WebHttpSecurityMode>.|  
  
## <a name="mode-attribute"></a>Atributo de modo  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Ninguna|La seguridad está deshabilitada.|  
|Transporte|La seguridad se proporciona utilizando HTTPS. El servicio necesita ser configurado con certificados SSL. El mensaje se protege completamente utilizando HTTPS y el servicio se autentica por el cliente usando el certificado SSL del servicio. La autenticación del cliente se controla mediante el `ClientCredentialType` atributo de la [ \<transporte >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).|  
|TransportCredentialOnly|Este modo no proporciona integridad del mensaje y confidencialidad. Proporciona la autenticación del cliente basada en HTTP. Este modo se debe utilizar con precaución. Se debe usar en entornos donde la seguridad de transporte se proporciona por otros medios (por ejemplo, IPSec) y la infraestructura de WCF proporciona sólo la autenticación de cliente.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md)|Define la configuración de seguridad para el transporte. Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|Un elemento de enlace que se usa para configurar los puntos de conexión para que responden a solicitudes HTTP en lugar de los mensajes SOAP de los servicios Web de Windows Communication Foundation (WCF).|  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Selección de tipos de credenciales](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [Enlaces](../../../../../docs/framework/wcf/bindings.md)
- [Configuración de enlaces proporcionados por el sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Utilización de enlaces para configurar servicios y clientes](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../../../docs/framework/misc/binding.md)
- [Modelo de programación de web HTTP de WCF](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)

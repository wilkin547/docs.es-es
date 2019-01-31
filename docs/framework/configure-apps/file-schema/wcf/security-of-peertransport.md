---
title: <security> de <peerTransport>
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: aadf2058c66cea4919d5dc9aa5aeab7850fcc395
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283769"
---
# <a name="security-of-peertransport"></a>\<seguridad > de \<peerTransport >
Contiene la configuración de seguridad asociada con un canal del mismo nivel, incluido el tipo de autenticación utilizado y la seguridad utilizada para el transporte del mensaje.  
  
 \<system.serviceModel>  
\<bindings>  
\<customBinding>  
\<binding>  
\<peerTransport>  
\<security>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`mode`|Especifica el tipo de seguridad que se va a aplicar. El valor predeterminado es Mensaje. Este atributo es del tipo <xref:System.ServiceModel.SecurityMode>.|  
  
## <a name="mode-attribute"></a>Atributo de modo  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`None`|La seguridad está deshabilitada.|  
|`Transport`|La seguridad se proporciona utilizando HTTPS.|  
|`Message`|La seguridad SOAP proporciona autenticación, integridad y confidencialidad.|  
|`TransportWithMessageCredential`|HTTPS proporciona autenticación y confidencialidad. Los mensajes SOAP proporcionan tipos de credencial enriquecidos.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-peertransport.md)|Define un transporte del mismo nivel para un enlace personalizado. Este elemento tiene un atributo `clientCredentialType` que especifica las credenciales que se van a usar al interactuar con un servicio. Este atributo es del tipo <xref:System.ServiceModel.PeerTransportCredentialType>.<br /><br /> Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<peerTransport>](../../../../../docs/framework/configure-apps/file-schema/wcf/peertransport.md)|Define un transporte del mismo nivel para un enlace personalizado.|  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Seguridad de transporte](../../../../../docs/framework/wcf/feature-details/transport-security.md)
- [Transportes](../../../../../docs/framework/wcf/feature-details/transports.md)
- [Elección del transporte](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [Enlaces](../../../../../docs/framework/wcf/bindings.md)
- [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

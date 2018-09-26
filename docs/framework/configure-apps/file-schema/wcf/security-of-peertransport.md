---
title: '&lt;security&gt; de &lt;peerTransport&gt;'
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
author: BrucePerlerMS
ms.openlocfilehash: 152087550d3fa881a7a88271d9c91dfcc5c894c8
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47176765"
---
# <a name="ltsecuritygt-of-ltpeertransportgt"></a>&lt;security&gt; de &lt;peerTransport&gt;
Contiene la configuración de seguridad asociada con un canal del mismo nivel, incluido el tipo de autenticación utilizado y la seguridad utilizada para el transporte del mensaje.  
  
 \<system.serviceModel>  
\<enlaces >  
\<customBinding >  
\<enlace >  
\<peerTransport >  
\<seguridad >  
  
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
|[\<transporte >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-peertransport.md)|Define un transporte del mismo nivel para un enlace personalizado. Este elemento tiene un atributo `clientCredentialType` que especifica las credenciales que se van a usar al interactuar con un servicio. Este atributo es del tipo <xref:System.ServiceModel.PeerTransportCredentialType>.<br /><br /> Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<peerTransport >](../../../../../docs/framework/configure-apps/file-schema/wcf/peertransport.md)|Define un transporte del mismo nivel para un enlace personalizado.|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [Seguridad de transporte](../../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [Transportes](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [Elección del transporte](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)  
 [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

---
title: '&lt;transport&gt; de &lt;peerTransport&gt;'
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: d02bb1cb4c20ab7dc482001ea7ce21180394eee7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716588"
---
# <a name="lttransportgt-of-ltpeertransportgt"></a>&lt;transport&gt; de &lt;peerTransport&gt;
Especifica el tipo de transporte para mensajes seguros enviados por pares configurados con este enlace.  
  
 \<system.serviceModel>  
\<bindings>  
\<customBinding>  
\<binding>  
\<peerTransport>  
\<security>  
\<transport>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|credentialType|Opcional. Especifica el tipo de credenciales utilizado para comprobar mensajes enviados con el transporte del mismo nivel. Este atributo es del tipo <xref:System.ServiceModel.PeerTransportCredentialType>.|  
  
## <a name="credentialtype-attribute"></a>Atributo credentialType  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Certificado|La autenticación del transporte de canal del mismo nivel requiere un certificado X509.|  
|Contraseña|La autenticación del transporte de canal del mismo nivel requiere una contraseña correcta.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|Define la configuración de seguridad de un transporte del mismo nivel.|  
  
## <a name="remarks"></a>Comentarios  
 Este elemento se establece únicamente si el atributo de modo de [ \<seguridad >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) está establecido en `Transport` o `TransportWithMessageCredential`.  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Seguridad de transporte](../../../../../docs/framework/wcf/feature-details/transport-security.md)
- [Transportes](../../../../../docs/framework/wcf/feature-details/transports.md)
- [Elección del transporte](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [Enlaces](../../../../../docs/framework/wcf/bindings.md)
- [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

---
title: '&lt;transport&gt; de &lt;peerTransport&gt;'
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: aeadf23b4ae6b4b0be18755c43585cbfea418567
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="lttransportgt-of-ltpeertransportgt"></a>&lt;transport&gt; de &lt;peerTransport&gt;
Especifica el tipo de transporte para mensajes seguros enviados por pares configurados con este enlace.  
  
 \<system.serviceModel>  
\<enlaces >  
\<customBinding >  
\<enlace >  
\<peerTransport >  
\<seguridad >  
\<transporte >  
  
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
|[\<seguridad >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|Define la configuración de seguridad de un transporte del mismo nivel.|  
  
## <a name="remarks"></a>Comentarios  
 Este elemento se establece únicamente si el atributo de modo de [ \<seguridad >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) está establecido en `Transport` o `TransportWithMessageCredential`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>  
 <xref:System.ServiceModel.PeerTransportSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [Seguridad de transporte](../../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [Transportes](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [Elección del transporte](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)  
 [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

---
title: <transport> de <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 837d01540fa63579877ab4085bd8034c78f2fbe0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915562"
---
# <a name="transport-of-netpeertcpbinding"></a>\<> de transporte \<de > netPeerTcpBinding
Especifica la configuración de seguridad de nivel de transporte al usar el [ \<> netPeerTcpBinding](netpeertcpbinding.md).  
  
 \<system.ServiceModel>  
\<bindings>  
\<netPeerTcpBinding>  
\<binding>  
\<> de seguridad  
\<> de transporte  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|credentialType|Opcional. Especifica el tipo de credenciales utilizado para comprobar mensajes enviados con el transporte del mismo nivel. Este atributo es del tipo <xref:System.ServiceModel.PeerTransportCredentialType>.|  
  
## <a name="credentialtype-attribute"></a>Atributo credentialType  
  
|Value|DESCRIPCIÓN|  
|-----------|-----------------|  
|Certificate|La autenticación del transporte de canal del mismo nivel requiere un certificado X509.|  
|Contraseña|La autenticación del transporte de canal del mismo nivel requiere una contraseña correcta.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 None  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<security>](security-of-netpeerbinding.md)|Define la configuración de seguridad para el [ \<> netPeerTcpBinding](netpeertcpbinding.md).|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [Protección de servicios y clientes](../../../wcf/feature-details/securing-services-and-clients.md)
- [Enlaces](../../../wcf/bindings.md)
- [Configuración de enlaces proporcionados por el sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Utilización de enlaces para configurar servicios y clientes](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../misc/binding.md)

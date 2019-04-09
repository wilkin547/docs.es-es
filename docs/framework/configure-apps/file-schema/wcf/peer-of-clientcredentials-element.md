---
title: <peer> de <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: 7074ee992755557d7e5503035c89bdbefd678792
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107242"
---
# <a name="peer-of-clientcredentials-element"></a>\<Peer > de \<clientCredentials > elemento
Especifica las credenciales usadas al autenticar clientes punto a punto.  
  
 \<system.ServiceModel>  
\<comportamientos >  
\<endpointBehaviors>  
\<comportamiento >  
\<clientCredentials>  
\<peer>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)|Especifica un certificado X.509 que se va a usar para firmar y cifrar los mensajes para los clientes punto a punto. .|  
|[\<peerAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)|Especifica las opciones de autenticación para clientes punto a punto.|  
|[\<messageSenderAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)|Especifica las opciones de autenticación para los remitentes del mensaje.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Especifica las credenciales usadas para autenticar un cliente a un servicio.|  
  
## <a name="remarks"></a>Comentarios  
 Este elemento de configuración especifica las credenciales que un nodo del mismo nivel utiliza para autenticarse en otros nodos de la malla, así como los valores de autenticación que un nodo del mismo nivel utiliza para autenticar otros nodos entre pares. Para obtener más información, consulte [autenticación de mensajes del canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) y [proteger aplicaciones de canal del mismo nivel](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [Conexión de redes punto a punto](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [Protección de clientes](../../../../../docs/framework/wcf/securing-clients.md)
- [Autenticación del mensaje del canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))
- [Autenticación personalizada de canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))
- [Protección de las aplicaciones de canal del mismo nivel](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
- [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)

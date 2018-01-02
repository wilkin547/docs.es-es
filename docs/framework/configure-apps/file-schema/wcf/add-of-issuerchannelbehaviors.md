---
title: '&lt;add&gt; de &lt;issuerChannelBehaviors&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bf66b3d3b531ae41329aade6a416c330957d83c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltissuerchannelbehaviorsgt"></a>&lt;add&gt; de &lt;issuerChannelBehaviors&gt;
Agrega un comportamiento del punto de conexión que se va a usar al comunicar con STS.  
  
> [!NOTE]
>  Si cualquier comportamiento de punto de conexión contiene un [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento, se producirá una excepción.  
  
 \<sistema. ServiceModel >  
\<comportamientos >  
sección endpointBehaviors  
\<comportamiento >  
\<clientCredentials >  
\<issuedToken >  
\<issuerChannelBehaviors > elemento  
\<add>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<add issuerAddress="string"  
     behaviorConfiguraton="string" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|issuerAddress|El URI del emisor del token seguridad con el que se va a comunicar.|  
|behaviorConfiguration|El nombre de un comportamiento del punto de conexión definido en el mismo archivo de configuración.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<issuerChannelBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|Contiene una colección de comportamientos del extremo del cliente de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] que se van a usar al comunicar con los servicios de token de servidor especificados.|  
  
## <a name="remarks"></a>Comentarios  
 `issuerAddress` contiene el URI del Servicio de token de seguridad con el que el cliente desea comunicarse. `behaviorConfiguration` apunta a un comportamiento de extremo que la aplicación usa en los canales creados por [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] para obtener los tokens emitidos por los Servicios de token de seguridad.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>  
 [Identidad del servicio y autenticación](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [Comportamientos de seguridad](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Federación y tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Protección de clientes](../../../../../docs/framework/wcf/securing-clients.md)  
 [Creación de un cliente federado](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [Configuración de un emisor local](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [Federación y tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [\<issuerChannelBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)

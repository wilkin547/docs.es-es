---
title: <issuedToken>
ms.date: 03/30/2017
ms.assetid: b6eae4b7-a6cd-4e1a-b0f6-f407022550b0
ms.openlocfilehash: 56439748926ada642018f48a5787634a50d0f180
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "72846860"
---
# \<issuedToken>
Especifica un token personalizado usado para autenticar un cliente en un servicio.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedToken>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<issuedToken cacheIssuedTokens="Boolean"
             defaultKeyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
             issuedTokenRenewalThresholdPercentage = "0 to 100"
             issuerChannelBehaviors="String"
             localIssuerChannelBehaviors="String"
             maxIssuedTokenCachingTime="TimeSpan">
</issuedToken>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`cacheIssuedTokens`|Atributo booleano opcional que especifica si los tokens están almacenados en memoria caché. De manera predeterminada, es `true`.|  
|`defaultKeyEntropyMode`|Atributo de cadena opcional que especifica los valores aleatorios (entropías) que se usan para las operaciones del protocolo en enlace. Los valores incluyen `ClientEntropy`, `ServerEntropy` y `CombinedEntropy`. El valor predeterminado es `CombinedEntropy`. Este atributo es del tipo <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.|  
|`issuedTokenRenewalThresholdPercentage`|Atributo de entero opcional que especifica el porcentaje de un intervalo de tiempo válido (proporcionado por el emisor del token) que puede pasar antes de que se renueve un token. Los valores van de 0 a 100. El valor predeterminado es 60, que especifica el 60% de los pasos de tiempo antes de intentar una renovación.|  
|`issuerChannelBehaviors`|Atributo opcional que especifica los comportamientos del canal que se va a usar al comunicar con el emisor.|  
|`localIssuerChannelBehaviors`|Atributo opcional que especifica los comportamientos del canal que se va a usar al comunicar con el emisor local.|  
|`maxIssuedTokenCachingTime`|Atributo Timespan opcional que especifica la duración que los tokens emitidos están almacenados en memoria caché cuando el emisor del token (un STS) no especifica una hora. El valor predeterminado es "10675199.02:48:05.4775807".|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<localIssuer>](localissuer.md)|Especifica la dirección del emisor local del token y el enlace usado para comunicarse con el punto de conexión.|  
|[\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)|Especifica los comportamientos del punto de conexión que se va a usar al ponerse en contacto con un emisor local.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|Especifica las credenciales usadas para autenticar un cliente a un servicio.|  
  
## <a name="remarks"></a>Comentarios  
 Un token emitido es un tipo de credencial personalizado usado, por ejemplo, al autenticar con un servicio de token seguro (STS) en un escenario aliado. De forma predeterminada, el token es un token de SAML. Para obtener más información, vea [Federación y tokens emitidos](../../../wcf/feature-details/federation-and-issued-tokens.md), y [Federación y tokens emitidos](../../../wcf/feature-details/federation-and-issued-tokens.md).  
  
 Esta sección contiene los elementos utilizados para configurar un emisor local de tokens, o los comportamientos utilizados con un servicio de token seguro. Para obtener instrucciones sobre cómo configurar un cliente para utilizar un emisor local, consulte [How to: Configure a local issuer](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.IssuedToken%2A>
- <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [Comportamientos de seguridad](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Protección de servicios y clientes](../../../wcf/feature-details/securing-services-and-clients.md)
- [Federación y tokens emitidos](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [Protección de clientes](../../../wcf/securing-clients.md)
- [Procedimiento para crear un cliente federado](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [Procedimiento para configurar un emisor local](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [Federación y tokens emitidos](../../../wcf/feature-details/federation-and-issued-tokens.md)

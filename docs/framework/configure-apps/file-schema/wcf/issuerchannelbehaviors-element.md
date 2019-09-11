---
title: <issuerChannelBehaviors> (Elemento)
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
no-loc:
- <system.serviceModel>
- <behaviors>
- <endpointBehaviors>
- <behavior>
- <clientCredentials>
- <issuedToken>
- <issuerChannelBehaviors>
- <dataContractSerializer>
ms.openlocfilehash: cbbfb9d3b5af47a360aa82cf837cd6749f61b641
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2019
ms.locfileid: "70893161"
---
# <a name="issuerchannelbehaviors-element"></a>\<issuerChannelBehaviors >, elemento

Contiene una colección de comportamientos de extremo de cliente de Windows Communication Foundation (WCF) (definidos en la configuración) que se usarán al comunicarse con los servicios de token de servicio especificados. Los comportamientos definidos no pueden incluir [ \<elementos > clientCredentials](clientcredentials.md) .

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<> System. serviceModel](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<comportamientos >](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<> endpointBehaviors](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<comportamiento >](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<clientCredentials >](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<> issuedToken](issuedtoken.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<> issuerChannelBehaviors

## <a name="syntax"></a>Sintaxis

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

Ninguno.

### <a name="child-elements"></a>Elementos secundarios

|Elemento|DESCRIPCIÓN|
|-------------|-----------------|
|[\<add>](add-of-issuerchannelbehaviors.md)|Agrega un comportamiento a la colección.|

### <a name="parent-elements"></a>Elementos primarios

|Elemento|DESCRIPCIÓN|
|-------------|-----------------|
|[\<issuedToken>](issuedtoken.md)|Especifica un token personalizado usado para autenticar un cliente en un servicio.|

## <a name="remarks"></a>Comentarios

Use este elemento cuando se deba utilizar un comportamiento (excepto los comportamientos que incluyen elementos `<clientCredentials>`) para comunicar con un servicio. Por ejemplo, si se [ \<](datacontractserializer-element.md) debe incluir un elemento de comportamiento dataContractSerializer >.

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [Identidad del servicio y autenticación](../../../wcf/feature-details/service-identity-and-authentication.md)
- [Comportamientos de seguridad](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Federación y tokens emitidos](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [Protección de servicios y clientes](../../../wcf/feature-details/securing-services-and-clients.md)
- [Protección de clientes](../../../wcf/securing-clients.md)
- [Cómo: Creación de un cliente federado](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [Cómo: Configuración de un emisor local](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [Federación y tokens emitidos](../../../wcf/feature-details/federation-and-issued-tokens.md)

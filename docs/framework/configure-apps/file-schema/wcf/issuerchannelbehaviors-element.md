---
title: <issuerChannelBehaviors> (Elemento)
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: 3386a287d577681b67bd3ad54a75b0276e29da1f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357253"
---
# <a name="issuerchannelbehaviors-element"></a>\<issuerChannelBehaviors > elemento

Contiene una colección de comportamientos de punto de conexión de cliente de Windows Communication Foundation (WCF) (definido en la configuración) que se usará al comunicarse con los servicios de Token de servicio especificado. Los comportamientos definidos no pueden contener ninguno [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elementos.

\<system.ServiceModel>\
\<comportamientos > \
section\ endpointBehaviors
\<comportamiento > \
\<clientCredentials>\
\<issuedToken>\
\<issuerChannelBehaviors>

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

|Elemento|Descripción|
|-------------|-----------------|
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-issuerchannelbehaviors.md)|Agrega un comportamiento a la colección.|

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|[\<issuedToken>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|Especifica un token personalizado usado para autenticar un cliente en un servicio.|

## <a name="remarks"></a>Comentarios

Use este elemento cuando se deba utilizar un comportamiento (excepto los comportamientos que incluyen elementos `<clientCredentials>`) para comunicar con un servicio. Por ejemplo, si un [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) debe incluirse el elemento de comportamiento.

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [Identidad del servicio y autenticación](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [Comportamientos de seguridad](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [Federación y tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Protección de clientes](../../../../../docs/framework/wcf/securing-clients.md)
- [Cómo: Crear a un cliente federado](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [Cómo: Configurar a un emisor Local](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [Federación y tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)

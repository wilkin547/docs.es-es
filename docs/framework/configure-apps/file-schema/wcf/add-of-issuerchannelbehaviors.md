---
description: 'Más información sobre: <add> de <issuerChannelBehaviors>'
title: <add> de <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: ccd8ba015b7a6837c74ce2c051a794d36ce8ceaa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750304"
---
# <a name="add-of-issuerchannelbehaviors"></a>\<add> de \<issuerChannelBehaviors>

Agrega un comportamiento del punto de conexión que se va a usar al comunicar con STS.

> [!NOTE]
> Si algún comportamiento del extremo contiene un [\<clientCredentials>](clientcredentials.md) elemento, se producirá una excepción.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerChannelBehaviors>**](issuerchannelbehaviors-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  

## <a name="syntax"></a>Sintaxis

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|issuerAddress|El URI del emisor del token seguridad con el que se va a comunicar.|
|behaviorConfiguration|El nombre de un comportamiento del extremo definido en el mismo archivo de configuración.|

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|[\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)|Contiene una colección de comportamientos de extremo de cliente de Windows Communication Foundation (WCF) que se usarán al comunicarse con los servicios de token de servicio especificados.|

## <a name="remarks"></a>Observaciones

`issuerAddress` contiene el URI del Servicio de token de seguridad con el que el cliente desea comunicarse. `behaviorConfiguration` apunta a un comportamiento del extremo que la aplicación utiliza en los canales creados por Windows Communication Foundation (WCF) para obtener los tokens emitidos a partir de los servicios de token de seguridad.

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
- [Procedimiento para crear un cliente federado](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [Procedimiento para configurar un emisor local](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [Federación y tokens emitidos](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)

---
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: bf512c427637ca65a7271ec8300a373a38632108
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913515"
---
# <a name="issuermetadata"></a>\<issuerMetadata>
\<system.serviceModel>  
\<bindings>  
\<wsFederationHttpBinding>  
\<binding>  
\<> de seguridad  
\<message>  
\<issuerMetadata>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<issuerMetadata address="String">
  <headers>
    <add name="String"
         namespace="String" />
  </headers>
  <identity>
    <certificate encodedValue="String" />
    <certificateReference findValue="String"
                          isChainIncluded="Boolean"
                          storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                          storeLocation="LocalMachine/CurrentUser"
                          x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
    <dns value="String" />
    <rsa value="String" />
    <servicePrincipalName value="String" />
    <usePrincipalName value="String" />
  </identity>
</issuerMetadata>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|dirección|El atributo `string` es obligatorio.<br /><br /> Especifica la dirección del punto de conexión. La dirección debe ser un URI absoluto. El valor predeterminado es una cadena vacía.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|Una colección de encabezados de dirección.|  
|[\<identity>](identity.md)|Una identidad que habilita la autenticación de un punto de conexión por otros puntos de conexión que intercambian mensajes con él.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<message>](message-element-of-wsfederationhttpbinding.md)|Define la configuración para la seguridad del nivel de mensaje para [ \<](wsfederationhttpbinding.md) el elemento > de wsFederationHttpBinding.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [Identidad del servicio y autenticación](../../../wcf/feature-details/service-identity-and-authentication.md)
- [Federación y tokens emitidos](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [Funcionalidades de seguridad con enlaces personalizados](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [Federación y tokens emitidos](../../../wcf/feature-details/federation-and-issued-tokens.md)

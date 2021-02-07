---
description: 'Más información sobre: <transport> de <wsHttpBinding>'
title: <transport> de <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
ms.openlocfilehash: 7801148d76aaa9c074eeb7a83c1dd2fa152d871c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749304"
---
# <a name="transport-of-wshttpbinding"></a>\<transport> de \<wsHttpBinding>

Define la configuración de autenticación del transporte HTTP.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wshttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  

## <a name="syntax"></a>Sintaxis

```xml
<wsHttpBinding>
  <binding>
    <security mode="None|Transport|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="Basic|Certificate|Digest|None|Ntlm|Windows"
                 proxyCredentialType="Basic|Digest|None|Ntlm|Windows"
                 realm="string" />
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</wsHttpBinding>
```

## <a name="type"></a>Tipo

<xref:System.ServiceModel.HttpTransportSecurity>

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|`clientCredentialType`|Especifica la credencial utilizada para autenticar el cliente al servicio. Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.|
|`proxyCredentialType`|Especifica la credencial usada para autenticar al cliente en un proxy del dominio. Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.|
|`realm`|Una cadena que especifica el dominio de autenticación para autenticación implícita o básica. El valor predeterminado es una cadena vacía.<br /><br /> Un dominio de autenticación especifica por lo menos el nombre del host que realiza la autenticación. También puede especificar una colección de usuarios que tiene acceso. Un usuario puede consultar el dominio de autenticación para determinar cuál de los posibles nombres de usuario y contraseñas se puede utilizar.|
|`policyEnforcement`|Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.<br /><br /> 1. Never: la Directiva nunca se aplica (la protección ampliada está deshabilitada).<br />2. WhenSupported: la Directiva solo se aplica si el cliente admite la protección ampliada.<br />3. Always: siempre se aplica la Directiva. Los clientes que no admitan la protección extendida no podrán autenticarse.|

## <a name="clientcredentialtype-attribute"></a>Atributo clientCredentialType

|Value|Descripción|
|-----------|-----------------|
|`None`|La seguridad está deshabilitada.|
|`Basic`|Usa la autenticación básica.|
|`Digest`|Usa la autenticación implícita.|
|`Ntlm`|Utiliza la autenticación NTLM como reserva con un dominio de Windows.|
|`Windows`|Utiliza la autenticación de Windows integrada.|
|`Certificate`|Utiliza los certificados X.509 para autenticar al cliente.|

## <a name="proxycredentialtype-attribute"></a>Atributo proxyCredentialType

|Value|Descripción|
|-----------|-----------------|
|`None`|La seguridad está deshabilitada.|
|`Basic`|Usa la autenticación básica.|
|`Digest`|Usa la autenticación implícita.|
|`Ntlm`|Utiliza NTLM como reserva con un dominio de Windows.|
|`Windows`|Utiliza la autenticación de Windows integrada.|
|`Certificate`|Utiliza los certificados X.509 para autenticar al cliente.|

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|[\<security>](security-of-wshttpbinding.md)|Representa las capacidades de seguridad de [\<wsHttpBinding>](wshttpbinding.md) .|

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [Protección de servicios y clientes](../../../wcf/feature-details/securing-services-and-clients.md)
- [Enlaces](../../../wcf/bindings.md)
- [Configuración de enlaces proporcionados por el sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Utilización de enlaces para configurar servicios y clientes](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)

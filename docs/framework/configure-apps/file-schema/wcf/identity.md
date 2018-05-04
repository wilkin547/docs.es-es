---
title: '&lt;identity&gt;'
ms.date: 03/30/2017
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
ms.openlocfilehash: 9cfd1d6cc7c278fd7e95c13df0a6f801cfabbc33
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltidentitygt"></a>&lt;identity&gt;
El elemento de identidad permite a un programador del cliente especificar en tiempo de diseño la identidad esperada del servicio. En el proceso de negociación entre el cliente y el servicio, la infraestructura de Windows Communication Foundation (WCF) asegurará la identidad del servicio esperado coincide con los valores de este elemento y, por tanto, se puede autenticar. Para obtener más información, consulte [autenticación e identidad de servicio](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
 \<system.ServiceModel>  
\<cliente >  
\<punto de conexión >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<identity>  
    <certificate encodedValue="String"/>  
    <certificateReference findValue="String"   
       isChainIncluded="Boolean"  
       storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"storeName="  
       storeLocation="LocalMachine/CurrentUser"  
       X509FindType= Enumeration./>  
    <dns value="String"/>  
    <rsa value="String"/>  
    <servicePrincipalName value="String"/>  
    <usePrincipalName value="String"/>  
</identity>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|certificate|Especifica los valores de un certificado X.509. Este elemento es del tipo <xref:System.ServiceModel.Configuration.CertificateElement>. Contiene un atributo `encodedValue` que es una cadena, que especifica el valor codificado por este certificado.|  
|certificateReference|Especifica los valores para la validación del certificado X.509. Este elemento es del tipo <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.|  
|dns|Especifica el DNS de un certificado X.509 usado para autenticar un servicio. Este elemento contiene un atributo `value` que es una cadena y contiene la identidad real.|  
|rsa|Especifica el valor del campo RSA de un certificado X.509 usado para autenticar un servicio a un cliente. Este elemento contiene un atributo `value` que es una cadena y contiene la identidad real.|  
|servicePrincipalName|Especifica una identidad del nombre de entidad de seguridad de servidor (SPN) que es el nombre de entidad de seguridad usado por un cliente para identificar de manera unívoca una instancia de un servicio. Este elemento contiene un atributo `value` que es una cadena y contiene el nombre de entidad de seguridad real. Este elemento es del tipo <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.|  
|userPrincipalName|Especifica una identidad del nombre principal del usuario (UPN), que es el tipo de nombre de inicio de sesión de un usuario en una red. El nombre principal del usuario se compone del nombre de objeto del usuario usado en Active Directory, seguido por el símbolo (@) y a continuación, normalmente, el dominio primario del Sistema de nombres de dominio (DNS). Por ejemplo, Jeff en el árbol de dominios de Fabrikam.com podría tener el nombre principal de usuario [ jeff@fabrikam.com ](mailto:jeffsmith@fabrikam.com).  Este elemento contiene un atributo `value` que es una cadena y contiene el nombre de entidad de seguridad real. Este elemento es del tipo <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<personalizado >](../../../../../docs/framework/configure-apps/file-schema/wcf/custom.md)|Especifica la resolución del mismo nivel personalizado de un netPeerTcpBinding.|  
|[\<punto de conexión >](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017)|Configura tipos diferentes de puntos de conexión.|  
|[\<emisor >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)|Especifica el servicio de token de seguridad (STS) para el servicio aliado.|  
|[\<issuerMetadata>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)|Especifica el punto de conexión de metadatos para el servicio de token de seguridad (STS) de un servicio aliado.|  
|[\<issuedTokenParameters >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|Define los parámetros para un token emitido en un enlace personalizado.|  
|[\<localIssuer >](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|Especifica un servicio de token de seguridad (STS) local.|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 [Identidad del servicio y autenticación](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [Puntos de conexión: direcciones, enlaces y contratos](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)

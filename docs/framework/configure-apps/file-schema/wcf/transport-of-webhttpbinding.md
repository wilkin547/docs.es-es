---
description: 'Más información sobre: <transport> de <webHttpBinding>'
title: <transport> de <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
ms.openlocfilehash: a845786f4e60a44dcb157201235d28d49ab8d40b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99773451"
---
# <a name="transport-of-webhttpbinding"></a>\<transport> de \<webHttpBinding>

Define los valores de seguridad a nivel de transporte para un punto de conexión de servicio configurado para recibir solicitudes HTTP.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<webHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="string">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</webHttpBinding>
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
|`Certificate`|Utiliza los certificados X.509 para autenticar al cliente.|  
|`Digest`|Usa la autenticación implícita.|  
|`Ntlm`|Utiliza la autenticación NTLM como reserva con un dominio de Windows.|  
|`Windows`|Utiliza la autenticación de Windows integrada.|  
  
## <a name="proxycredentialtype-attribute"></a>Atributo proxyCredentialType  
  
|Value|Descripción|  
|-----------|-----------------|  
|`None`|La seguridad está deshabilitada.|  
|`Basic`|Usa la autenticación básica.|  
|`Digest`|Usa la autenticación implícita.|  
|`Ntlm`|Utiliza NTLM como reserva con un dominio de Windows.|  
|`Windows`|Utiliza la autenticación de Windows integrada.|  
  
### <a name="child-elements"></a>Elementos secundarios  

 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<security>](security-of-webhttpbinding.md)|Representa las funciones de seguridad del [\<wsHttpBinding>](wshttpbinding.md) elemento.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [Protección de servicios y clientes](../../../wcf/feature-details/securing-services-and-clients.md)
- [Enlaces](../../../wcf/bindings.md)
- [Configuración de enlaces proporcionados por el sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Utilización de enlaces para configurar servicios y clientes](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [Modelo de programación de web HTTP de WCF](../../../wcf/feature-details/wcf-web-http-programming-model.md)

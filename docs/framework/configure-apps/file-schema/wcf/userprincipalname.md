---
description: 'Más información acerca de: <userPrincipalName>'
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 73ace3d6f3d5cb88f2630a4a2ae319decf420021
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664423"
---
# \<userPrincipalName>

Especifica el Nombre principal de usuario (UPN) de un servicio que va a autenticar el cliente.  
  
Para obtener más información acerca de cómo establecer el UPN, consulte [identidad de servicio y autenticación](../../../wcf/feature-details/service-identity-and-authentication.md).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userPrincipalName>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|value|Un nombre de cuenta de usuario (a veces denominado nombre de inicio de sesión de usuario) y un nombre de dominio que identifica el dominio en el que se ubica la cuenta de usuario. Éste es el uso estándar para iniciar sesión en un dominio de Windows. El formato es: someone@example.com (como para una dirección de correo electrónico).|  
  
### <a name="child-elements"></a>Elementos secundarios  

 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<identity>](identity.md)|Especifica la identidad del servicio que va a autenticar el cliente.|  
  
## <a name="remarks"></a>Observaciones  

 Un cliente de Windows Communication Foundation seguro (WCF) que se conecta a un punto de conexión con esta identidad utiliza el UPN al realizar la autenticación SSPI con el punto de conexión.  
  
## <a name="example"></a>Ejemplo  

 El código de configuración siguiente especifica el UPN del servicio que va a autenticar el cliente.  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [Identidad del servicio y autenticación](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)

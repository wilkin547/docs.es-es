---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 423a3249a9298675517f0cff08566c3735fa35f1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940510"
---
# <a name="userprincipalname"></a>\<userPrincipalName>
Especifica el Nombre principal de usuario (UPN) de un servicio que va a autenticar el cliente.  
  
 Para obtener más información acerca de cómo establecer el UPN, consulte [identidad de servicio y autenticación](../../../wcf/feature-details/service-identity-and-authentication.md).  
  
\<> de identidad  
\<userPrincipalName>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|valor|Un nombre de cuenta de usuario (a veces denominado nombre de inicio de sesión de usuario) y un nombre de dominio que identifica el dominio en el que se ubica la cuenta de usuario. Éste es el uso estándar para iniciar sesión en un dominio de Windows. El formato es: someone@example.com (como para una dirección de correo electrónico).|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<identity>](identity.md)|Especifica la identidad del servicio que va a autenticar el cliente.|  
  
## <a name="remarks"></a>Comentarios  
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

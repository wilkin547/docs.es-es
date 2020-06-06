---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 0f651377346b1f14a4226128cd5cf7059543adca
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251910"
---
# \<roleClaimType>
Especifica el tipo de notificación que define las notificaciones de tipo de rol en la colección de <xref:System.Security.Claims.ClaimsIdentity> objetos devuelta por el <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> método del controlador de token.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<roleClaimType>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <roleClaimType value=xs:string>  
          </roleClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|value|Una cadena que especifica el URI que representa el tipo de demanda de la demanda que se va a usar para el tipo de notificaciones de rol.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 None  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|Proporciona la configuración para la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> clase, la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase o una clase derivada de cualquiera de estas clases.|  
  
## <a name="remarks"></a>Comentarios  
 El `<roleClaimType>` elemento establece la <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> propiedad cuando <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> se inicializa un objeto a partir de la configuración.  
  
## <a name="example"></a>Ejemplo  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>

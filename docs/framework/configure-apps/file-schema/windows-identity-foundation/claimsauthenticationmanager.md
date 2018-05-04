---
title: '&lt;claimsAuthenticationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 4d4a91e0ed1f437089e26e5902515f73a15d94a8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltclaimsauthenticationmanagergt"></a>&lt;claimsAuthenticationManager&gt;
Registra un administrador de autenticación de notificaciones para las notificaciones entrantes.  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<claimsAuthenticationManager >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|type|Especifica un tipo personalizado que deriva de la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase. Para obtener más información sobre cómo especificar el `type` atributo, consulte la sección [referencias de tipo personalizado].|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Si no hay ningún `type` atributo, o si la `type` las referencias de atributo el <xref:System.Security.Claims.ClaimsAuthenticationManager> (clase), el `<claimsAuthenticationManager>` elemento no tiene elementos secundarios; sin embargo, las clases derivadas de <xref:System.Security.Claims.ClaimsAuthenticationManager> puede definir los elementos de configuración secundarios.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Especifica los valores de identidad de nivel de servicio.|  
  
## <a name="remarks"></a>Comentarios  
 El comportamiento predeterminado proporcionado a través de la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase eco de las notificaciones entrantes. Si no hay ningún `type` se especifica el atributo o si la `type` atributo especifica el <xref:System.Security.Claims.ClaimsAuthenticationManager> (clase), el `<claimsAuthenticationManager>` elemento no tiene elementos secundarios. Puede especificar el `type` atributo para registrar un tipo derivado de la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase para implementar un comportamiento personalizado. Las clases derivadas pueden admitir la configuración a través de los elementos secundarios de la `<claimsAuthenticationManager>` elemento invalidando el <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> método para controlar estos elementos. El esquema definido para los elementos secundarios es hasta el Diseñador de la clase.  
  
 El `<claimsAuthenticationManager>` conjuntos de elementos del <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> propiedad.  
  
## <a name="example"></a>Ejemplo  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</microsoft.identityModel>  
```

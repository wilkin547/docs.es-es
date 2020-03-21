---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: a54fc2cea84bb9d08a9725d846fe38efd7b5475a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152754"
---
# <a name="claimsauthenticationmanager"></a>\<claimsAuthenticationManager>
Registra un administrador de autenticación de notificaciones para las notificaciones entrantes.  
  
[**\<configuración>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**  
  
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
|type|Especifica un tipo personalizado que <xref:System.Security.Claims.ClaimsAuthenticationManager> deriva de la clase. Para obtener más información `type` acerca de cómo especificar el atributo, vea [Referencias de tipo personalizado].|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Si no `type` hay ningún atributo, o si el `type` atributo hace referencia a la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase, el `<claimsAuthenticationManager>` elemento no toma elementos secundarios; sin embargo, <xref:System.Security.Claims.ClaimsAuthenticationManager> las clases derivadas de pueden definir elementos de configuración secundarios.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Especifica la configuración de identidad de nivel de servicio.|  
  
## <a name="remarks"></a>Observaciones  
 El comportamiento predeterminado <xref:System.Security.Claims.ClaimsAuthenticationManager> proporcionado a través de la clase se hace eco de las notificaciones entrantes. Si `type` no se especifica ningún `type` atributo o <xref:System.Security.Claims.ClaimsAuthenticationManager> si `<claimsAuthenticationManager>` el atributo especifica la clase, el elemento no toma elementos secundarios. Puede especificar `type` el atributo para registrar un <xref:System.Security.Claims.ClaimsAuthenticationManager> tipo derivado de la clase para implementar un comportamiento personalizado. Las clases derivadas pueden admitir `<claimsAuthenticationManager>` la configuración a <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> través de elementos secundarios del elemento reemplazando el método para controlar estos elementos. El esquema definido para los elementos secundarios depende del diseñador de la clase.  
  
 El `<claimsAuthenticationManager>` elemento <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> establece la propiedad.  
  
## <a name="example"></a>Ejemplo  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>
    </identityConfiguration>  
</system.identityModel>  
```

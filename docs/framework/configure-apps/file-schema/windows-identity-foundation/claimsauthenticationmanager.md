---
description: 'Más información acerca de: <claimsAuthenticationManager>'
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: 5a94861d6b2684b9f66c7d5e14f72aa419a0c66f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664254"
---
# \<claimsAuthenticationManager>

Registra un administrador de autenticación de notificaciones para las notificaciones entrantes.  
  
[**\<configuration>**](../configuration-element.md)\
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
|type|Especifica un tipo personalizado que deriva de la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase. Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado].|  
  
### <a name="child-elements"></a>Elementos secundarios  

 Si no hay ningún `type` atributo, o si el `type` atributo hace referencia a la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase, el `<claimsAuthenticationManager>` elemento no toma los elementos secundarios; sin embargo, las clases derivadas de <xref:System.Security.Claims.ClaimsAuthenticationManager> pueden definir elementos de configuración secundarios.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Especifica la configuración de identidad de nivel de servicio.|  
  
## <a name="remarks"></a>Observaciones  

 El comportamiento predeterminado proporcionado a través de la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase repite las notificaciones entrantes. Si no `type` se especifica ningún atributo o si el `type` atributo especifica la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase, el `<claimsAuthenticationManager>` elemento no toma los elementos secundarios. Puede especificar el `type` atributo para registrar un tipo derivado de la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase para implementar el comportamiento personalizado. Las clases derivadas pueden admitir la configuración a través de elementos secundarios del `<claimsAuthenticationManager>` elemento invalidando el <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> método para controlar estos elementos. El esquema definido para los elementos secundarios es hasta el diseñador de la clase.  
  
 El `<claimsAuthenticationManager>` elemento establece la <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> propiedad.  
  
## <a name="example"></a>Ejemplo  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>
    </identityConfiguration>  
</system.identityModel>  
```

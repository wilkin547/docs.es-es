---
title: "&lt;claimsAuthenticationManager&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;claimsAuthenticationManager&gt;
Registra un administrador de autenticación de notificaciones para las peticiones de entrada.  
  
## Sintaxis  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Atributos y elementos  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|type|Especifica un tipo personalizado que se derive de la clase de <xref:System.Security.Claims.ClaimsAuthenticationManager> .  Para obtener más información sobre cómo especificar el atributo de `type` , vea [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferencess).|  
  
### Elementos secundarios  
 Si no hay ningún atributo de `type` , o si las referencias de atributo de `type` la clase de <xref:System.Security.Claims.ClaimsAuthenticationManager> , el elemento de `<claimsAuthenticationManager>` no tiene elementos secundarios; sin embargo, las clases derivadas de <xref:System.Security.Claims.ClaimsAuthenticationManager> pueden definir elementos de configuración secundarios.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Especifica valores de identidad de nivel de servicio.|  
  
## Comentarios  
 El comportamiento predeterminado proporcionado a través de la clase de <xref:System.Security.Claims.ClaimsAuthenticationManager> repite las peticiones de entrada.  Si no se especifica ningún atributo de `type` o si el atributo de `type` especifica la clase de <xref:System.Security.Claims.ClaimsAuthenticationManager> , el elemento de `<claimsAuthenticationManager>` no tiene elementos secundarios.  Puede especificar el atributo de `type` para registrar un tipo derivado de la clase de <xref:System.Security.Claims.ClaimsAuthenticationManager> para implementar un comportamiento personalizado.  Las clases derivadas pueden admitir la configuración a través de los elementos secundarios del elemento de `<claimsAuthenticationManager>` invalidando el método de <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> para administrar estos elementos.  El esquema definido para los elementos secundarios es el diseñador de clases.  
  
 El elemento de `<claimsAuthenticationManager>` la propiedad de <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=fullName> .  
  
## Ejemplo  
  
```  
<system.identityModel>  
    <identityConfiguration name=”MyIdentity”>  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</microsoft.identityModel>  
```
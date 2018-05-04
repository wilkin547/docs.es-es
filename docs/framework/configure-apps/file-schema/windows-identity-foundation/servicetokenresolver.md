---
title: '&lt;serviceTokenResolver&gt;'
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: c25ea1fc32c93e7eb57ef8ed06d6f786ae0a670e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltservicetokenresolvergt"></a>&lt;serviceTokenResolver&gt;
Registra a la resolución del token de servicio que usa controladores en la colección de controlador de token. La resolución del token de servicio se utiliza para resolver el token de cifrado de mensajes y los tokens entrantes.  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<securityTokenHandlers>  
\<securityTokenHandlerConfiguration >  
\<serviceTokenResolver >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|type|Especifica el tipo de la resolución del token de servicio. Ya sea la <xref:System.IdentityModel.Selectors.SecurityTokenResolver> tipo o un tipo que deriva de la <xref:System.IdentityModel.Selectors.SecurityTokenResolver> clase. Para obtener más información sobre cómo especificar el `type` atributo, consulte la sección [referencias de tipo personalizado]. Requerido.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Proporciona la configuración para una colección de seguridad controladores de tokens.|  
  
## <a name="remarks"></a>Comentarios  
 La resolución del token de servicio puede utilizarse para resolver el token de cifrado de mensajes y los tokens entrantes. Se utiliza para recuperar la clave que se debe usar para descifrar tokens entrantes. Debe especificar el `type` atributo. El tipo especificado puede ser <xref:System.IdentityModel.Selectors.SecurityTokenResolver> o un tipo personalizado que deriva de la <xref:System.IdentityModel.Selectors.SecurityTokenResolver> clase.  
  
 Algunos controladores de tokens permiten especificar la configuración de la resolución del token de servicio en la configuración. La configuración en los controladores de tokens individuales invalida los especificados en la colección de controlador de token de seguridad.  
  
> [!NOTE]
>  Especificar el `<serviceTokenResolver>` elemento como un elemento secundario de la [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento está en desuso, pero todavía se admite por compatibilidad con versiones anteriores. Configuración de la `<securityTokenHandlerConfiguration>` elemento reemplazan a las que en el `<identityConfiguration>` elemento.  
  
## <a name="example"></a>Ejemplo  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```

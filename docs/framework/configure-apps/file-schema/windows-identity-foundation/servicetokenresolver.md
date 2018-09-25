---
title: '&lt;serviceTokenResolver&gt;'
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: d4b64e2c88e153834b7cf5a83bd6258b6dfd471f
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47075315"
---
# <a name="ltservicetokenresolvergt"></a>&lt;serviceTokenResolver&gt;
Registra a la resolución de tokens de servicio que se usa los controladores en la colección de controladores de token. La resolución del servicio de token se usa para resolver el token cifrado en los mensajes y los tokens entrantes.  
  
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
|type|Especifica el tipo de la resolución de tokens de servicio. Ya sea el <xref:System.IdentityModel.Selectors.SecurityTokenResolver> tipo o un tipo que se deriva el <xref:System.IdentityModel.Selectors.SecurityTokenResolver> clase. Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipos personalizado]. Requerido.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Proporciona la configuración para una colección de seguridad controladores de token.|  
  
## <a name="remarks"></a>Comentarios  
 La resolución del servicio de token puede usarse para resolver el token cifrado en los mensajes y los tokens entrantes. Sirve para recuperar la clave que debe usarse para descifrar tokens entrantes. Debe especificar el `type` atributo. El tipo especificado puede ser <xref:System.IdentityModel.Selectors.SecurityTokenResolver> o un tipo personalizado que deriva la <xref:System.IdentityModel.Selectors.SecurityTokenResolver> clase.  
  
 Algunos controladores de tokens permiten especificar la configuración de resolución de tokens del servicio en la configuración. La configuración en los controladores de token individuales invalida los especificados en la colección de controladores de token de seguridad.  
  
> [!NOTE]
>  Especificar el `<serviceTokenResolver>` como un elemento secundario de la [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento en desuso, pero todavía se admite por compatibilidad con versiones anteriores. Configuración de la `<securityTokenHandlerConfiguration>` elemento invalidan aquellas establecidas en el `<identityConfiguration>` elemento.  
  
## <a name="example"></a>Ejemplo  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```

---
title: '&lt;audienceUris&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 69c96698b309a789b4527c76e1fe8b8b99811a19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltaudienceurisgt"></a>&lt;audienceUris&gt;
Especifica el conjunto de URI que son aceptables identificadores de usuario de confianza (RP). No se aceptarán tokens a menos que tengan el ámbito de uno de lo URI de público permitido.  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<securityTokenHandlers >  
\<securityTokenHandlerConfiguration >  
\<audienceUris >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <audienceUris mode=xs:string>  
          <add value=xs:string />  
          <clear />  
          <remove value=xs:string />  
        </audienceUris>  
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
|modo|Un <xref:System.IdentityModel.Selectors.AudienceUriMode> valor que especifica si se debe aplicar la restricción de audiencia para un token entrante. Los valores posibles son "Siempre", "Nunca" y "BearerKeyOnly". El valor predeterminado es "Siempre". Opcional.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`<add value=xs:string>`|Agrega el URI especificado por el `value` de atributo a la colección audienceUris. El atributo `value` es necesario. El URI distingue mayúsculas de minúsculas.|  
|`<clear>`|Borra la colección de audienceUris. Se quitan todos los identificadores de la colección.|  
|`<remove value=xs:string>`|Quita el URI especificado por el `value` atributo de la colección de audienceUris. El atributo `value` es necesario. El URI distingue mayúsculas de minúsculas.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Proporciona la configuración para una colección de seguridad controladores de tokens.|  
  
## <a name="remarks"></a>Comentarios  
 De forma predeterminada, la colección está vacía; usar `<add>`, `<clear>`, y `<remove>` elementos que se va a modificar la colección. <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>y <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> por los objetos de los valores de la colección de URI de audiencia para configurar cualquiera permiten audiencia restricciones de URI en <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objetos.  
  
 El `<audienceUris>` elemento representado por la <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> clase. Un URI individual que se agrega a la colección se representa mediante la <xref:System.IdentityModel.Configuration.AudienceUriElement> clase.  
  
> [!NOTE]
>  El uso de la `<audienceUris>` elemento como un elemento secundario de la [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento está en desuso, pero todavía se admite por compatibilidad con versiones anteriores. Configuración de la `<securityTokenHandlerConfiguration>` elemento reemplazan a las que en el `<identityConfiguration>` elemento.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código XML muestra cómo configurar el URI de audiencia aceptables para una aplicación. Este ejemplo configura un URI único. Se aceptarán tokens en el ámbito de este URI, se rechazarán todas las demás.  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```

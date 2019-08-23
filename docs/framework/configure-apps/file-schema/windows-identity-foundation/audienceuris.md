---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: 003221ed4dc7f4ccf72d2e0d3a91265e13172813
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941953"
---
# <a name="audienceuris"></a>\<audienceUris>
Especifica el conjunto de URI que son identificadores aceptables del usuario de confianza (RP). No se aceptarán tokens a menos que estén en el ámbito de uno de los URI de audiencia permitidos.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
\<securityTokenHandlerConfiguration>  
\<audienceUris>  
  
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
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|modo|<xref:System.IdentityModel.Selectors.AudienceUriMode> Valor que especifica si la restricción de audiencia debe aplicarse a un token de entrada. Los valores posibles son "always", "Never" y "BearerKeyOnly". El valor predeterminado es "always". Opcional.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|`<add value=xs:string>`|Agrega el URI especificado por el `value` atributo a la colección audienceUris. El atributo `value` es necesario. El URI distingue entre mayúsculas y minúsculas.|  
|`<clear>`|Borra la colección audienceUris. Todos los identificadores se quitan de la colección.|  
|`<remove value=xs:string>`|Quita el URI especificado por el `value` atributo de la colección audienceUris. El atributo `value` es necesario. El URI distingue entre mayúsculas y minúsculas.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Proporciona la configuración para una colección de controladores de tokens de seguridad.|  
  
## <a name="remarks"></a>Comentarios  
 De forma predeterminada, la colección está vacía; Use `<add>`los `<clear>`elementos, `<remove>` y para modificar la colección. <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>los <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objetos y usan los valores de la colección de URI de audiencia para configurar las restricciones de <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> URI de audiencia permitidas en los objetos.  
  
 El elemento se representa mediante la <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> clase. `<audienceUris>` Una dirección URI individual agregada a la colección se representa <xref:System.IdentityModel.Configuration.AudienceUriElement> mediante la clase.  
  
> [!NOTE]
> El uso del `<audienceUris>` elemento como elemento secundario [ \<del elemento > identityConfiguration](identityconfiguration.md) está en desuso, pero todavía se admite por compatibilidad con versiones anteriores. La `<securityTokenHandlerConfiguration>` configuración del elemento invalida la `<identityConfiguration>` del elemento.  
  
## <a name="example"></a>Ejemplo  
 El siguiente XML muestra cómo configurar los URI de audiencia aceptables para una aplicación. En este ejemplo se configura un URI único. Se aceptarán los tokens con ámbito para este URI; se rechazarán todos los demás.  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```

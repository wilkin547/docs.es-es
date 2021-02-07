---
description: 'Más información acerca de: <audienceUris>'
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: 98b411e73d4b9941e65daaf5d1d63285cdc90fd0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681856"
---
# \<audienceUris>

Especifica el conjunto de URI que son identificadores aceptables del usuario de confianza (RP). Los tokens no se aceptarán a menos que se definan sus ámbitos para uno de los URI de público permitido.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<audienceUris>**  
  
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
|mode|<xref:System.IdentityModel.Selectors.AudienceUriMode>Valor que especifica si la restricción de audiencia debe aplicarse a un token de entrada. Los valores posibles son "always", "Never" y "BearerKeyOnly". El valor predeterminado es "always". Opcional.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`<add value=xs:string>`|Agrega el URI especificado por el `value` atributo a la colección audienceUris. El atributo `value` es necesario. El URI distingue entre mayúsculas y minúsculas.|  
|`<clear>`|Borra la colección audienceUris. Todos los identificadores se quitan de la colección.|  
|`<remove value=xs:string>`|Quita el URI especificado por el `value` atributo de la colección audienceUris. El atributo `value` es necesario. El URI distingue entre mayúsculas y minúsculas.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Proporciona la configuración para una colección de controladores de tokens de seguridad.|  
  
## <a name="remarks"></a>Observaciones  

 De forma predeterminada, la colección está vacía; Use `<add>` `<clear>` `<remove>` los elementos, y para modificar la colección. <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> los <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objetos y usan los valores de la colección de URI de audiencia para configurar las restricciones de URI de audiencia permitidas en los <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objetos.  
  
 El `<audienceUris>` elemento se representa mediante la <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> clase. Una dirección URI individual agregada a la colección se representa mediante la <xref:System.IdentityModel.Configuration.AudienceUriElement> clase.  
  
> [!NOTE]
> El uso del `<audienceUris>` elemento como elemento secundario del elemento está en [\<identityConfiguration>](identityconfiguration.md) desuso, pero todavía se admite por compatibilidad con versiones anteriores. La configuración del `<securityTokenHandlerConfiguration>` elemento invalida la del `<identityConfiguration>` elemento.  
  
## <a name="example"></a>Ejemplo  

 El siguiente XML muestra cómo configurar los URI de audiencia aceptables para una aplicación. En este ejemplo se configura un URI único. Se aceptarán los tokens con ámbito para este URI; se rechazarán todos los demás.  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```

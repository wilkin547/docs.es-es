---
title: '&lt;securityTokenHandlers&gt;'
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: e63f02add81495e474b59b6c5cc090bd69add3d2
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47082994"
---
# <a name="ltsecuritytokenhandlersgt"></a>&lt;securityTokenHandlers&gt;
Especifica una colección de controladores de token de seguridad que están registrados con el punto de conexión.  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<securityTokenHandlers>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|name|Especifica el nombre de una colección de controladores de token. Los únicos valores reconocidos por el marco de trabajo son "ActAs" y "OnBehalfOf". Si se especifican las colecciones de controlador de token con cualquiera de estos nombres, la colección se usará al procesar ActAs u OnBehalfOf tokens, respectivamente.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|Agrega un controlador de token de seguridad a la colección de controladores de token.|  
|[\<clear>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md)|Borra todos los controladores de token de seguridad de la colección de controladores de token.|  
|[\<remove>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md)|Quita un controlador de token de seguridad de la colección de controladores de token.|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Proporciona la configuración de la colección de controladores de token.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Especifica los valores de identidad de nivel de servicio.|  
  
## <a name="remarks"></a>Comentarios  
 Puede especificar una o varias colecciones con nombre de los controladores de token de seguridad en una configuración de servicio. Puede especificar un nombre para una colección mediante el `name` atributo. Los únicos nombres que controla el marco de trabajo son "ActAs" y "OnBehalfOf". Si existen controladores de estas recopilaciones, se utilizaron un servicio de token de seguridad (STS) en lugar de los controladores predeterminados al procesar `ActAs` y `OnBehalfOf` tokens.  
  
 De forma predeterminada, la colección se rellena con los siguientes tipos de controlador: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, y <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>. Puede modificar la colección mediante el `<add>`, `<remove>`, y `<clear>` elementos. Debe asegurarse de que solo un único controlador de ningún tipo concreto existe en la colección. Por ejemplo, si se deriva de un controlador de la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase, ya sea el controlador o la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> puede configurarse en una sola colección, pero no ambos.  
  
 Use el `<securityTokenHandlerConfiguration>` elemento para especificar opciones de configuración para los controladores en la colección. Configuración especificada a través de este elemento invalida las especificadas en el servicio a través de la [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento. Algunos controladores (incluidos algunos de los tipos de controlador integrados) pueden admitir una configuración adicional a través de un elemento secundario de la `<add>` elemento. Configuración especificada en un controlador de invalida la configuración equivalente especificada en la colección o el servicio.

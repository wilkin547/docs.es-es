---
title: <securityTokenHandlers>
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: 017309436660991c69da569e9cc4219e842ecaa3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251872"
---
# <a name="securitytokenhandlers"></a>\<securityTokenHandlers>
Especifica una colección de controladores de tokens de seguridad que se registran con el punto de conexión.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> securityTokenHandlers**  
  
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
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|name|Especifica el nombre de una colección de controladores de token. Los únicos valores que reconoce el marco son "ActAs" y "Onbehalfof". Si se especifican colecciones de controladores de token con cualquiera de estos nombres, la colección se usará al procesar los tokens ActAs o Onbehalfof, respectivamente.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<add>](add.md)|Agrega un controlador de tokens de seguridad a la colección de controladores de tokens.|  
|[\<clear>](clear.md)|Borra todos los controladores de token de seguridad de la colección de controladores de tokens.|  
|[\<remove>](remove.md)|Quita un controlador de tokens de seguridad de la colección de controladores de tokens.|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Proporciona la configuración para la colección de controladores de token.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Especifica la configuración de identidad de nivel de servicio.|  
  
## <a name="remarks"></a>Comentarios  
 Puede especificar una o varias colecciones con nombre de controladores de token de seguridad en una configuración de servicio. Puede especificar un nombre para una colección mediante el `name` atributo. Los únicos nombres que controla el marco de trabajo son "ActAs" y "Onbehalfof". Si existen controladores en estas colecciones, un servicio de token de seguridad (STS) los usa en lugar de los controladores predeterminados al procesar `ActAs` los `OnBehalfOf` tokens y.  
  
 De forma predeterminada, la colección se rellena con los siguientes tipos de <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>controlador <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>: <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>,, <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>y. Puede modificar la colección mediante los `<add>`elementos, `<remove>`y `<clear>` . Debe asegurarse de que solo existe en la colección un único controlador de un tipo determinado. Por ejemplo, si se deriva un controlador de la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase, el controlador <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> o se puede configurar en una colección única, pero no en ambos.  
  
 Use el `<securityTokenHandlerConfiguration>` elemento para especificar los valores de configuración de los controladores de la colección. Los valores especificados a través de este elemento reemplazan a los [ \<](identityconfiguration.md) especificados en el servicio a través del elemento > de identityConfiguration. Algunos controladores (incluidos algunos de los tipos de controlador integrados) pueden admitir la configuración adicional a través de un elemento secundario del `<add>` elemento. La configuración especificada en un controlador invalida la configuración equivalente especificada en la colección o el servicio.

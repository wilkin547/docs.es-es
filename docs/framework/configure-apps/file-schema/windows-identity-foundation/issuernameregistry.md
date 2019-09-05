---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: 209e702da80f2569f2b6c068f50f1af4489157f6
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251966"
---
# <a name="issuernameregistry"></a>\<issuerNameRegistry>
Configura el registro de nombres de emisores que usan los controladores de la colección de controladores de tokens.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlerConfiguration**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> issuerNameRegistry**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry type=xs:string>  
          <optionalCustomConfigurationElements />  
        </issuerNameRegistry>  
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
|type|Tipo que se deriva de la <xref:System.IdentityModel.Tokens.IssuerNameRegistry> clase. Para obtener más información sobre cómo especificar un personalizado `type`, vea [referencias de tipo personalizado].|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<trustedIssuers>](trustedissuers.md)|Cuando el `type` atributo especifica el registro del nombre del emisor basado en la configuración <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> (la clase) [ \<](trustedissuers.md) , se debe especificar el elemento > de trustedIssuers. El `<add>` `<clear>` [ \<elemento > trustedIssuers](trustedissuers.md) puede tomar los elementos, `<remove>` o como elementos secundarios.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Proporciona la configuración para una colección de controladores de tokens de seguridad.|  
  
## <a name="remarks"></a>Comentarios  
 Todos los tokens de emisor se validan mediante un registro de nombres de emisor. Se trata de un objeto que se deriva de <xref:System.IdentityModel.Tokens.IssuerNameRegistry> la clase. El registro de nombres de emisores se usa para asociar un nombre de tecla de cifrado al material criptográfico necesario para comprobar las firmas de los tokens generados por el emisor correspondiente. El registro del nombre del emisor mantiene una lista de emisores de confianza para la aplicación de usuario de confianza (RP). El tipo de registro del nombre del emisor se especifica mediante el `type` atributo. El `<issuerNameRegistry>` elemento puede tener uno o más elementos secundarios que proporcionan la configuración para el tipo especificado. Proporcione la lógica que procesa estos elementos secundarios invalidando el <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> método.  
  
 WIF proporciona un tipo de registro de nombre de emisor único fuera del cuadro, <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> la clase. Esta clase usa un conjunto de certificados de emisor de confianza que se especifican en la configuración. Requiere un elemento de configuración secundario, `<trustedIssuers>`, en el que se configura la colección de certificados de emisor de confianza. Los certificados de confianza se especifican mediante la forma codificada ASN. 1 de la huella digital del certificado y se agregan o quitan `<clear>`de la `<remove>` colección `<add>`mediante los elementos, o.  
  
 El elemento se representa mediante la <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> clase. `<issuerNameRegistry>`  
  
> [!NOTE]
> Especificar el `<issuerNameRegistry>` elemento como elemento secundario [ \<](identityconfiguration.md) del elemento de > identityConfiguration está en desuso, pero todavía se admite por compatibilidad con versiones anteriores. La `<securityTokenHandlerConfiguration>` configuración del elemento invalida la `<identityConfiguration>` del elemento.  
  
## <a name="example"></a>Ejemplo  
 El siguiente XML muestra cómo especificar el registro de nombres de emisor basado en la configuración.  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>

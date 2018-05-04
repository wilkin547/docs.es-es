---
title: '&lt;issuerNameRegistry&gt;'
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: b695cc6d66e5b9e45bb6a5fd22d594bc22ea3cba
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltissuernameregistrygt"></a>&lt;issuerNameRegistry&gt;
Configura el registro de nombre de emisor que se usa por los controladores de la colección de controlador de token.  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<securityTokenHandlers>  
\<securityTokenHandlerConfiguration >  
\<issuerNameRegistry >  
  
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
  
|Atributo|Descripción|  
|---------------|-----------------|  
|type|Un tipo que deriva de la <xref:System.IdentityModel.Tokens.IssuerNameRegistry> clase. Para obtener más información acerca de cómo especificar un personalizado `type`, consulte la sección [referencias de tipo personalizado].|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)|Cuando el `type` atributo especifica el registro de nombre de emisor basadas en configuración (la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> clase), el [ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) se debe especificar el elemento. El [ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) puede tardar elemento `<add>`, `<clear>`, o `<remove>` elementos como elementos secundarios.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Proporciona la configuración para una colección de seguridad controladores de tokens.|  
  
## <a name="remarks"></a>Comentarios  
 Todos los tokens de emisor se validan mediante un registro de nombre de emisor. Se trata de un objeto que se deriva de la <xref:System.IdentityModel.Tokens.IssuerNameRegistry> clase. El registro de nombre de emisor se usa para asociar un nombre de tecla de acceso para el material criptográfico que se necesita para comprobar las firmas de tokens generados por el emisor correspondiente. El registro de nombre de emisor mantiene una lista de emisores de confianza para la aplicación del usuario (RP) autenticado. El tipo del registro de nombre de emisor se especifica utilizando el `type` atributo. El `<issuerNameRegistry>` elemento puede tener uno o varios elementos secundarios que proporcionan la configuración para el tipo especificado. Proporcionar la lógica que procesa estos elementos secundarios invalidando el <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> método.  
  
 WIF ofrece un emisor único nombre de tipo de registro de fábrica, el <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> clase. Esta clase utiliza un conjunto de certificados de emisor de confianza que se especifican en la configuración. Requiere un elemento de configuración secundario, `<trustedIssuers>`, en la que se configura la colección de certificados de emisor de confianza. Confianza de certificados se especifican utilizando el ASN.1 codificado de formulario de la huella digital del certificado y se agregan o quitan de la colección mediante el uso de `<add>`, `<clear>`, o `<remove>` elementos.  
  
 El `<issuerNameRegistry>` elemento representado por la <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> clase.  
  
> [!NOTE]
>  Especificar el `<issuerNameRegistry>` elemento como un elemento secundario de la [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento está en desuso, pero todavía se admite por compatibilidad con versiones anteriores. Configuración de la `<securityTokenHandlerConfiguration>` elemento reemplazan a las que en el `<identityConfiguration>` elemento.  
  
## <a name="example"></a>Ejemplo  
 El siguiente XML muestra cómo especificar al emisor de la configuración basada en el registro de nombres.  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>  
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>

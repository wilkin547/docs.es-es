---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: ae263a4590cc523c64306ff5d53e54b5190ca510
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59202526"
---
# <a name="issuernameregistry"></a>\<issuerNameRegistry>
Configura el registro de nombre del emisor que se usa los controladores en la colección de controladores de token.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
\<securityTokenHandlerConfiguration>  
\<issuerNameRegistry>  
  
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
|type|Un tipo que deriva la <xref:System.IdentityModel.Tokens.IssuerNameRegistry> clase. Para obtener más información acerca de cómo especificar un personalizado `type`, consulte la sección [referencias de tipo personalizado].|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<trustedIssuers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)|Cuando el `type` atributo especifica el registro de nombres de emisores basada en la configuración (el <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> clase), el [ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) debe especificarse el elemento. El [ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) puede tomar el elemento `<add>`, `<clear>`, o `<remove>` elementos como elementos secundarios.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Proporciona la configuración para una colección de seguridad controladores de token.|  
  
## <a name="remarks"></a>Comentarios  
 Todos los tokens de emisor se validan mediante un registro de nombre del emisor. Se trata de un objeto que se deriva el <xref:System.IdentityModel.Tokens.IssuerNameRegistry> clase. El registro de nombre del emisor se utiliza para asociar un nombre mnemotécnico al material criptográfico que se necesita para comprobar las firmas de los tokens generados por el emisor correspondiente. El registro de nombre del emisor mantiene una lista de emisores de confianza para la aplicación de confianza (RP) de usuario de confianza. El tipo de registro de nombres de emisor se especifica utilizando el `type` atributo. El `<issuerNameRegistry>` elemento puede tener uno o varios elementos secundarios que proporcionan la configuración para el tipo especificado. Proporcionar la lógica que procesa estos elementos secundarios invalidando el <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> método.  
  
 WIF proporciona un emisor único nombre de tipo de registro de fábrica, el <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> clase. Esta clase usa un conjunto de certificados de emisor de confianza que se especifican en la configuración. Requiere un elemento de configuración secundario, `<trustedIssuers>`, en la que está configurada la colección de certificados de emisor de confianza. Los certificados se especifican utilizando el ASN.1 codificado de formulario de la huella digital del certificado y se agregan o quitan de la colección mediante el uso de confianza `<add>`, `<clear>`, o `<remove>` elementos.  
  
 El `<issuerNameRegistry>` elemento representado por la <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> clase.  
  
> [!NOTE]
>  Especificar el `<issuerNameRegistry>` como un elemento secundario de la [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento en desuso, pero todavía se admite por compatibilidad con versiones anteriores. Configuración de la `<securityTokenHandlerConfiguration>` elemento invalidan aquellas establecidas en el `<identityConfiguration>` elemento.  
  
## <a name="example"></a>Ejemplo  
 El siguiente XML muestra cómo especificar al emisor de la configuración en función de registro de nombres.  
  
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

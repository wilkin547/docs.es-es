---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: bb4cb5178885b90ef25ee827c2f11593ead6e73d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55276684"
---
# <a name="trustedissuers"></a>\<trustedIssuers>
Configura la lista de certificados de emisor de confianza utilizado por el registro de nombres de emisores basada en la configuración (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
\<securityTokenHandlerConfiguration>  
\<issuerNameRegistry>  
\<trustedIssuers>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry>  
          <trustedIssuers>  
            <add thumbprint=xs:string name=xs:string>  
            <clear>  
            <remove thumbprint=xs:string>  
          </trustedIssuers>  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguna  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|Agrega un certificado a la colección de emisores de confianza. El certificado se especifica con el `thumbprint` atributo. Este atributo es necesario y debe contener el formulario ASN.1 codificado la huella digital del certificado. El `name` atributo es opcional y puede utilizarse para especificar un nombre descriptivo para el certificado.|  
|`<clear>`|Borra todos los certificados de la colección de emisores de confianza.|  
|`<remove thumbprint=xs:string>`|Quita un certificado de la colección de emisores de confianza. El certificado se especifica con el `thumbprint` atributo. Este atributo es necesario.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<issuerNameRegistry>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|Configura el registro de nombre del emisor. **Importante:**  El `type` atributo de la `<issuerNameRegistry>` elemento debe hacer referencia a la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> de clases para el `<trustedIssuers>` elemento sea válido.|  
  
## <a name="remarks"></a>Comentarios  
 Windows Identity Foundation (WIF) proporciona una implementación única de la <xref:System.IdentityModel.Tokens.IssuerNameRegistry> clase de fábrica, el <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> clase. El registro de nombre de configuración del emisor mantiene una lista de emisores de confianza que se carga desde la configuración. La lista asocia cada nombre de emisor del certificado X.509 que se necesita para comprobar la firma de tokens generados por el emisor. La lista de certificados de emisor de confianza se especifica en el `<trustedIssuers>` elemento. Cada elemento de la lista asocia un nombre de emisor de tecla de acceso con el certificado X.509 que se necesita para comprobar la firma de tokens generados por ese emisor. Certificados de confianza se especifican utilizando el ASN.1 formato codificado de la huella digital del certificado y se agregan a la colección mediante `<add>` elemento. Puede borrar o quitar de la lista de emisores (certificados) con el `<clear>` y `<remove>` elementos.  
  
 El `type` atributo de la `<issuerNameRegistry>` elemento debe hacer referencia a la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> de clases para el `<trustedIssuers>` elemento sea válido.  
  
## <a name="example"></a>Ejemplo  
 El siguiente XML muestra cómo especificar al emisor de la configuración en función de registro de nombres.  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a>Vea también
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>

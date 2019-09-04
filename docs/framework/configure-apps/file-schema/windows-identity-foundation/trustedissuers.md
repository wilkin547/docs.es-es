---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: 50fc7194823fb0c5c426fb54ffd50b17c3714ed9
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251754"
---
# <a name="trustedissuers"></a>\<trustedIssuers>
Configura la lista de certificados de emisor de confianza utilizados por el registro de nombres de emisores basados en la<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>configuración ().  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlerConfiguration**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> issuerNameRegistry**](issuernameregistry.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> trustedIssuers**  
  
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
 None  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|Agrega un certificado a la colección de emisores de confianza. El certificado se especifica con el `thumbprint` atributo. Este atributo es necesario y debe contener la forma de codificación ASN. 1 de la huella digital del certificado. El `name` atributo es opcional y se puede usar para especificar un nombre descriptivo para el certificado.|  
|`<clear>`|Borra todos los certificados de la colección de emisores de confianza.|  
|`<remove thumbprint=xs:string>`|Quita un certificado de la colección de emisores de confianza. El certificado se especifica con el `thumbprint` atributo. Este atributo es necesario.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<issuerNameRegistry>](issuernameregistry.md)|Configura el registro de nombres de emisores. **Importante:**  El `type` atributo <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> `<trustedIssuers>` del elemento debe hacer referencia a la clase para que el elemento sea válido. `<issuerNameRegistry>`|  
  
## <a name="remarks"></a>Comentarios  
 Windows Identity Foundation (WIF) proporciona una implementación única de la <xref:System.IdentityModel.Tokens.IssuerNameRegistry> clase desde el cuadro, la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> clase. El registro de nombres de emisores de configuración mantiene una lista de emisores de confianza que se cargan desde la configuración. La lista asocia cada nombre de emisor con el certificado X. 509 necesario para comprobar la firma de los tokens generados por el emisor. La lista de certificados de emisor de confianza se especifica en `<trustedIssuers>` el elemento. Cada elemento de la lista asocia un nombre de emisor de mnemotécnico con el certificado X. 509 necesario para comprobar la firma de los tokens generados por dicho emisor. Los certificados de confianza se especifican con el formato ASN. 1 codificado de la huella digital del certificado y se agregan a la colección mediante `<add>` el elemento. Puede borrar o quitar emisores (certificados) de la lista mediante los `<clear>` elementos y. `<remove>`  
  
 El `type` atributo <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> `<trustedIssuers>` del elemento debe hacer referencia a la clase para que el elemento sea válido. `<issuerNameRegistry>`  
  
## <a name="example"></a>Ejemplo  
 El siguiente XML muestra cómo especificar el registro de nombres de emisor basado en la configuración.  
  
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

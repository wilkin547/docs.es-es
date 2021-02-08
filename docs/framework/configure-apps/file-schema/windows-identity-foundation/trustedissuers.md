---
description: 'Más información acerca de: <trustedIssuers>'
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: 8789eaa38666e22f6a58b3178103aef4408677b7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786517"
---
# \<trustedIssuers>

Configura la lista de certificados de emisor de confianza utilizados por el registro de nombres de emisores basados en la configuración ( <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> ).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerNameRegistry>**](issuernameregistry.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<trustedIssuers>**  
  
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
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|Agrega un certificado a la colección de emisores de confianza. El certificado se especifica con el `thumbprint` atributo. Este atributo es necesario y debe contener la forma de codificación ASN. 1 de la huella digital del certificado. El `name` atributo es opcional y se puede usar para especificar un nombre descriptivo para el certificado.|  
|`<clear>`|Borra todos los certificados de la colección de emisores de confianza.|  
|`<remove thumbprint=xs:string>`|Quita un certificado de la colección de emisores de confianza. El certificado se especifica con el `thumbprint` atributo. Este atributo es necesario.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<issuerNameRegistry>](issuernameregistry.md)|Configura el registro de nombres de emisores. **Importante:**  El `type` atributo del `<issuerNameRegistry>` elemento debe hacer referencia <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> a la clase para `<trustedIssuers>` que el elemento sea válido.|  
  
## <a name="remarks"></a>Observaciones  

 Windows Identity Foundation (WIF) proporciona una implementación única de la <xref:System.IdentityModel.Tokens.IssuerNameRegistry> clase desde el cuadro, la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> clase. El registro de nombres de emisores de configuración mantiene una lista de emisores de confianza que se cargan desde la configuración. La lista asocia cada nombre de emisor con el certificado X. 509 necesario para comprobar la firma de los tokens generados por el emisor. La lista de certificados de emisor de confianza se especifica en el `<trustedIssuers>` elemento. Cada elemento de la lista asocia un nombre de emisor de mnemotécnico con el certificado X. 509 necesario para comprobar la firma de los tokens generados por dicho emisor. Los certificados de confianza se especifican con el formato ASN. 1 codificado de la huella digital del certificado y se agregan a la colección mediante el `<add>` elemento. Puede borrar o quitar emisores (certificados) de la lista mediante los `<clear>` `<remove>` elementos y.  
  
 El `type` atributo del `<issuerNameRegistry>` elemento debe hacer referencia <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> a la clase para `<trustedIssuers>` que el elemento sea válido.  
  
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

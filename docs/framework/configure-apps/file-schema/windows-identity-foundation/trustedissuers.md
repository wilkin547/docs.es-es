---
title: "&lt;trustedIssuers&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;trustedIssuers&gt;
Configura la lista de certificados de emisor de confianza utilizados por el registro de nombre de emisor en función de configuración \(<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>\).  
  
## Sintaxis  
  
```  
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
  
## Atributos y elementos  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 None  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|Elemento  Descripción  Este atributo es necesario y debe contener el formulario ASN.1 codificado de huella digital del certificado.  El `name` atributo es opcional y puede utilizarse para especificar un nombre descriptivo para el certificado.|  
|`<clear>`|Borra todos los certificados de la colección de emisores de confianza.|  
|`<remove thumbprint=xs:string>`|Quita un certificado de la colección de emisores de confianza.  El certificado se especifica con la `thumbprint` atributo.  Esta información es necesaria.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<issuerNameRegistry\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|Configura el registro de nombre de emisor. **Important:**  El `type` atributo de la `<issuerNameRegistry>` elementos deben hacer referencia a la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> de clases para el `<trustedIssuers>` elemento para que sea válido.|  
  
## Comentarios  
 Fundación de la identidad de Windows \(WIF\) proporciona una única implementación de la <xref:System.IdentityModel.Tokens.IssuerNameRegistry> clase fuera de la caja, el <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> clase.  El registro de nombre de emisor de configuración mantiene una lista de emisores de confianza que se carga desde la configuración.  La lista asocia cada nombre del emisor del certificado X.509 que es necesaria para verificar la firma de tokens producida por el emisor.  La lista de certificados de emisor de confianza se especifica en el `<trustedIssuers>` elemento.  Cada elemento en la lista asocia un nombre de emisor de tecla de acceso con el certificado X.509 que es necesaria para verificar la firma de tokens producido por dicho emisor.  Certificados de confianza se especifican utilizando el ASN.1 codificado de forma de la huella digital del certificado y se agregan a la colección mediante el uso de `<add>` elemento.  Puede borrar o quitar los emisores \(certificados\) de la lista mediante el uso de la `<clear>` y `<remove>` elementos.  
  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
## Ejemplo  
 None  
  
```  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
  
```  
  
## Vea también  
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>   
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
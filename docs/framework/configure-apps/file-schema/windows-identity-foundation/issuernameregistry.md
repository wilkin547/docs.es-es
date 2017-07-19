---
title: "&lt;issuerNameRegistry&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
caps.latest.revision: 13
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 12
---
# &lt;issuerNameRegistry&gt;
Descripción  
  
## Sintaxis  
  
```  
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
  
## Atributos y elementos  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|type|Un tipo que se deriva de la <xref:System.IdentityModel.Tokens.IssuerNameRegistry> clase.  Para obtener más información acerca de cómo especificar una personalizada `type`, consulte [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferences).|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<trustedIssuers\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)|Cuando el `type` atributo especifica el registro de nombre de emisor en función de configuración \(el <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> clase\), el [\<trustedIssuers\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) debe especificarse el elemento.  El [\<trustedIssuers\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) puede tener el elemento `<add>`, `<clear>`, o `<remove>` elementos como elementos secundarios.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Proporciona la configuración de una colección de seguridad de los controladores de símbolo \(token\).|  
  
## Comentarios  
 Todos los tokens de emisor se validan mediante un registro de nombre de emisor.  Se trata de un objeto que se deriva de la <xref:System.IdentityModel.Tokens.IssuerNameRegistry> clase.  El registro de nombre de emisor se utiliza para asociar un nombre de tecla de acceso para el material criptográfico que se necesita para comprobar las firmas de símbolos \(tokens\) producidos por el emisor correspondiente.  El registro de nombre de emisor mantiene una lista de emisores de confianza para la aplicación de terceros \(RP\) confía.  Todas los demás valores se omiten.  Para obtener más información, vea el elemento `<issuerNameRegistry>`.  Proporcionan la lógica que procesa estos elementos secundarios mediante el reemplazo de la <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> método.  
  
 WIF proporciona un único emisor nombre, escriba del registro de la caja, el <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> clase.  Esta clase utiliza un conjunto de certificados de emisor de confianza que se especifican en la configuración.  Requiere un elemento de configuración secundarios, `<trustedIssuers>`, en la que esté configurada de la colección de certificados de emisor de confianza.  Confianza de certificados se especifican utilizando el ASN.1 codificado de forma de la huella digital del certificado y se agregan o quitan de la colección mediante el uso de `<add>`, `<clear>`, o `<remove>` elementos.  
  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
> [!NOTE]
>  Atributo  Descripción  
  
## Ejemplo  
 name  
  
```  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
  
```  
  
## Vea también  
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>   
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
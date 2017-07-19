---
title: "&lt;x509SecurityTokenHandlerRequirement&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
caps.latest.revision: 3
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 3
---
# &lt;x509SecurityTokenHandlerRequirement&gt;
Proporciona la configuración opcional para la clase o clases derivadas de <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> .  
  
## Sintaxis  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
        <x509SecurityTokenHandlerRequirement>  
          mapToWindows=xs:boolean  
          certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
          certificateValidator="Namespace.Class, Assembly"  
          revocationMode="NoCheck||Offline||Online"  
          trustedStoreLocation="CurrentUser||LocalMachine"  
        </x509SecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Atributos y elementos  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|certificateValidationMode|Un valor de <xref:System.ServiceModel.Security.X509CertificateValidationMode> que especifica el modo de validación para utilizar para el certificado X.509.  El valor predeterminado es “PeerOrChainTrust”.|  
|mapToWindows|Especifica si el controlador del token debe asignar el token que valida una cuenta de Windows mediante la petición de entrada de UPN.  El valor predeterminado es “false”.|  
|revocationMode|Un valor de <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> que especifica el modo de inversión para utilizar para el certificado X.509.  El valor predeterminado es “conectado”.|  
|trustedStoreLocation|Un valor de <xref:System.Security.Cryptography.X509Certificates.StoreLocation> que especifica el almacén de certificados X.509.  El valor predeterminado es “LocalMachine”.|  
|certificateValidator|Un tipo personalizado que deriva de <xref:System.IdentityModel.Selectors.X509CertificateValidator>.  Si el atributo de `certificateValidationMode` es “custom”, una instancia de este tipo se utiliza para la validación del certificado del emisor.|  
  
### Elementos secundarios  
 None  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|Agrega el controlador especificado de token de seguridad a la colección de controlador de token.|  
  
## Ejemplo  
  
```  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
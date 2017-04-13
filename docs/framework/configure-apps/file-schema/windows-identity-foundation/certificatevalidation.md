---
title: "&lt;certificateValidation&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# &lt;certificateValidation&gt;
Controla los valores que los controladores de utilizan para validar los certificados.  Estos valores se reemplazan si se configura un controlador específico con su propio validador.  
  
## Sintaxis  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation  
      certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
      revocationMode="NoCheck||Offline||Online"  
      trustedStoreLocation="CurrentLocation||LocalMachine" >  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Atributos y elementos  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|certificateValidationMode|Un valor de <xref:System.ServiceModel.Security.X509CertificateValidationMode> que especifica el modo de validación para utilizar para el certificado X.509.  el valor predeterminado es “PeerOrChainTrust”.  Para especificar un validador personalizado, establezca este atributo en “custom” y especifique el validador mediante [\<certificateValidator\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) el elemento.  Opcional.|  
|revocationMode|Un valor de <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> que especifica el modo de inversión para utilizar para el certificado X.509.  el valor predeterminado es “conectado”.  Opcional.|  
|trustedStoreLocation|Un valor de <xref:System.Security.Cryptography.X509Certificates.StoreLocation> que especifica el almacén de certificados X.509.  el valor predeterminado es “LocalMachine”.  Opcional.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<certificateValidator\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)|Especifica un tipo personalizado para la validación de certificados.  Utilizan este tipo sólo si el atributo de `certificateValidationMode` [\<certificateValidation\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) de elemento está establecida en “custom”.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Especifica valores de identidad de nivel de servicio.|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Proporciona la configuración para una colección de controladores de token de seguridad.|  
  
## Comentarios  
 Un elemento de `<certificateValidation>` se puede especificar en el nivel de servicio bajo el elemento de `<identityConfiguration>` o en la colección de controlador de token de seguridad nivel bajo el elemento de `<securityTokenHandlerConfiguration>` .  Los valores de una colección simbólica de controlador reemplazan a los especificados en el servicio.  Algunos controladores token permiten especificar valores de validación de certificado en configuración.  Los valores en los controladores de token individuales reemplazan a los especificados en el nivel de servicio y de la colección de controlador de token de seguridad.  
  
## Ejemplo  
  
```  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
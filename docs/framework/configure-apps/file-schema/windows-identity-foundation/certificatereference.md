---
title: "&lt;certificateReference&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# &lt;certificateReference&gt;
Especifica la configuración que se utiliza para buscar y validar un certificado X.509 en un almacén de certificados.  
  
## Sintaxis  
  
```  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
      <certificateReference   
        storeName=”AddressBook||AuthRoot||CertificateAuthority||Disallowed||My||Root||TrustedPeople||TrustedPublisher”  
        storeLocation=”CurrentUser||LocalMachine”  
        x509FindType="FindByThumbprint||FindBySubjectName||FindBySubjectDistinguishedName||FindByIssuerName||FindByIssuerDistinguishedName||FindBySerialNumber||FindByTimeValid||FindByTimeNotYetValid||FindByTimeExpired||FindByTemplateName||FindByApplicationPolicy||FindByCertificatePolicy||FindByExtension||FindByKeyUsage||FindBySubjectKeyIdentifier"  
        findValue=xs:String  
        isChainIncluded=xs:Boolean >  
      </certificateReference>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## Atributos y elementos  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|storeName|El nombre del almacén de certificados X.509.  El valor predeterminado es "My".  Opcional.|  
|storeLocation|Opcional.  None  Opcional.|  
|x509FindType|Elemento  Descripción  Opcional.|  
|findValue|El valor que se va a utilizar para buscar en el almacén de certificados X.509.  Opcional.|  
|isChainIncluded|Especifica si la validación debe realizarse mediante el uso de la cadena de certificados.  El valor predeterminado es "true"; se realiza la validación mediante el uso de la cadena de certificados.  Opcional.|  
  
### Elementos secundarios  
 None  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<serviceCertificate\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|Configura el certificado que se utiliza para cifrar y descifrar los símbolos \(tokens\).|  
  
## Comentarios  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  Atributo  Descripción
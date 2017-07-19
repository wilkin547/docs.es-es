---
title: "&lt;serviceCertificate&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
caps.latest.revision: 5
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;serviceCertificate&gt;
Configura el certificado X.509 que se utiliza para cifrar y descifrar los símbolos \(tokens\).  
  
## Sintaxis  
  
```  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## Atributos y elementos  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 None  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<certificateReference\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatereference.md)|Especifica la configuración que se utiliza para buscar y validar un certificado X.509 en un almacén de certificados.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Contiene las opciones que configurar el <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> \(WSFAM\) y el <xref:System.IdentityModel.Services.SessionAuthenticationModule> \(SAM\).|  
  
## Ejemplo  
 El XML siguiente muestra el uso de \<serviceCertificate\> elemento.  El código XML se toma de la `CustomToken` ejemplo.  
  
```  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
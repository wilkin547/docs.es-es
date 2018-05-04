---
title: '&lt;serviceCertificate&gt;'
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: af59562dbf6c13970526f1665a9ba2c57c4f32ee
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltservicecertificategt"></a>&lt;serviceCertificate&gt;
Configura el certificado X.509 que se utiliza para cifrar y descifrar los tokens.  
  
 \<system.identityModel.services >  
\<federationConfiguration >  
\<serviceCertificate >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguna  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<certificateReference >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatereference.md)|Especifica valores que se usan para encontrar y validar un certificado X.509 en un almacén de certificados.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Contiene los valores que configuran la <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) y <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).|  
  
## <a name="example"></a>Ejemplo  
 El siguiente XML muestra el uso de la \<serviceCertificate > elemento. El XML procede de la `CustomToken` ejemplo.  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```

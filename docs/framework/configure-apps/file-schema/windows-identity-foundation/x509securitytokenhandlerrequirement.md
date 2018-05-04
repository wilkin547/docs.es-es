---
title: '&lt;x509SecurityTokenHandlerRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 8af4a718fc9f4ba7f674d98e13424bb443693c6c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltx509securitytokenhandlerrequirementgt"></a>&lt;x509SecurityTokenHandlerRequirement&gt;
Proporciona una configuración opcional para la <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> clase o clases derivadas.  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<securityTokenHandlers>  
\<add>  
\<x509SecurityTokenHandlerRequirement >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
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
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|certificateValidationMode|Un <xref:System.ServiceModel.Security.X509CertificateValidationMode> valor que especifica el modo de validación que se utilizará para el certificado X.509. El valor predeterminado es "PeerOrChainTrust".|  
|mapToWindows|Especifica si el controlador de token debe asignar el token de validación a una cuenta de Windows mediante la notificación UPN entrante. El valor predeterminado es "false".|  
|revocationMode|Un <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> valor que especifica el modo de revocación que se usará para el certificado X.509. El valor predeterminado es "Online".|  
|trustedStoreLocation|Un <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valor que especifica el almacén de certificados X.509. El valor predeterminado es "LocalMachine".|  
|certificateValidator|Un tipo personalizado que deriva de <xref:System.IdentityModel.Selectors.X509CertificateValidator>. Si el `certificateValidationMode` atributo es "Custom", se utiliza una instancia de este tipo de validación de certificados de emisor.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|Agrega el controlador de token de seguridad especificado a la colección de controlador de token.|  
  
## <a name="example"></a>Ejemplo  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```

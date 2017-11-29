---
title: '&lt;certificateValidation&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 778088f2e0508f5a80c29ae027b2442a80286795
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltcertificatevalidationgt"></a>&lt;certificateValidation&gt;
Controla la configuración que usan los controladores de tokens para validar certificados. Estos valores se sustituyen si se configura un controlador específico con su propio validador.  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<certificateValidation >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
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
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|certificateValidationMode|Un <xref:System.ServiceModel.Security.X509CertificateValidationMode> valor que especifica el modo de validación que se utilizará para el certificado X.509. El valor predeterminado es "PeerOrChainTrust". Para especificar un validador personalizado, establezca este atributo en "Custom" y especifique el validador mediante el [ \<certificateValidator >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) elemento. Opcional.|  
|revocationMode|Un <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> valor que especifica el modo de revocación que se usará para el certificado X.509. El valor predeterminado es "Online". Opcional.|  
|trustedStoreLocation|Un <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valor que especifica el almacén de certificados X.509. El valor predeterminado es "LocalMachine". Opcional.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<certificateValidator >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)|Especifica un tipo personalizado para la validación del certificado. Este tipo se usa únicamente si la `certificateValidationMode` atributo de la [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) elemento está establecido en "Custom".|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Especifica los valores de identidad de nivel de servicio.|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Proporciona la configuración para una colección de seguridad controladores de tokens.|  
  
## <a name="remarks"></a>Comentarios  
 A `<certificateValidation>` elemento puede especificarse en el nivel de servicio en la `<identityConfiguration>` elemento o en el nivel de colección de controlador de token de seguridad en el `<securityTokenHandlerConfiguration>` elemento. La configuración en una colección de controlador de token invalida las especificadas en el servicio. Algunos controladores de tokens permiten especificar la configuración de la validación de certificado en la configuración. Configuración de controladores de tokens individuales invalida los especificados en el nivel de servicio y en la colección de controlador de token de seguridad.  
  
## <a name="example"></a>Ejemplo  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```

---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: c2d1a5d36cb5616ef06eedc093dd70a68a164a81
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252131"
---
# <a name="certificatevalidation"></a>\<certificateValidation>
Controla la configuración que usan los controladores de token para validar certificados. Esta configuración se invalida si un controlador concreto se configura con su propio validador.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> certificateValidation**  
  
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
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|certificateValidationMode|<xref:System.ServiceModel.Security.X509CertificateValidationMode> Valor que especifica el modo de validación que se va a usar para el certificado X. 509. El valor predeterminado es "PeerOrChainTrust". Para especificar un validador personalizado, establezca este atributo en "Custom" y especifique el validador mediante el elemento [ \<> de certificateValidator](certificatevalidator.md) . Opcional.|  
|revocationMode|<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Valor que especifica el modo de revocación que se va a usar para el certificado X. 509. El valor predeterminado es "online". Opcional.|  
|trustedStoreLocation|<xref:System.Security.Cryptography.X509Certificates.StoreLocation> Valor que especifica el almacén de certificados X. 509. El valor predeterminado es "LocalMachine". Opcional.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<certificateValidator>](certificatevalidator.md)|Especifica un tipo personalizado para la validación del certificado. Este tipo solo se utiliza si el `certificateValidationMode` atributo [ \<del elemento > certificateValidation](certificatevalidation.md) se establece en "Custom".|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Especifica la configuración de identidad de nivel de servicio.|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Proporciona la configuración para una colección de controladores de tokens de seguridad.|  
  
## <a name="remarks"></a>Comentarios  
 Un `<certificateValidation>` elemento se puede especificar en el nivel de servicio bajo `<identityConfiguration>` el elemento o en el nivel de colección de controladores de `<securityTokenHandlerConfiguration>` tokens de seguridad bajo el elemento. La configuración de una colección de controladores de tokens invalida las especificadas en el servicio. Algunos controladores de token permiten especificar la configuración de validación de certificados en la configuración. La configuración de los controladores de token individuales invalida los especificados tanto en el nivel de servicio como en la colección de controladores de tokens de seguridad.  
  
## <a name="example"></a>Ejemplo  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```

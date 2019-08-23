---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: c25f183679f41f51ffee4f482bfe7a64763647d9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941900"
---
# <a name="certificatevalidator"></a>\<certificateValidator>
Especifica un tipo personalizado para la validación del certificado. Este tipo solo se utiliza si el `certificateValidationMode` atributo [ \<del elemento > certificateValidation](certificatevalidation.md) se establece en "Custom".  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<certificateValidation>  
\<certificateValidator>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation>  
      <certificateValidator type=xs:string>  
      </certificateValidator>  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|type|Especifica un tipo personalizado que deriva de la <xref:System.IdentityModel.Selectors.X509CertificateValidator> clase. Establezca el `certificateValidationMode` atributo [ \<](certificatevalidation.md) del elemento > de certificateValidation en "Custom" para usar este tipo. Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado](../windows-workflow-foundation/index.md). Opcional.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 None  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<certificateValidation>](certificatevalidation.md)|Controla la configuración que usan los controladores de token para validar certificados.|  
  
## <a name="example"></a>Ejemplo  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```

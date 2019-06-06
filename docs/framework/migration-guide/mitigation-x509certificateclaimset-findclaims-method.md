---
title: 'Mitigación: Método X509CertificateClaimSet.FindClaims'
ms.date: 03/30/2017
ms.assetid: ee356e3b-f932-48f5-875a-5e42340bee63
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f7fb1eb0c502584caac11ca3dde6e7e646b29cfe
ms.sourcegitcommit: 26f4a7697c32978f6a328c89dc4ea87034065989
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2019
ms.locfileid: "66251087"
---
# <a name="mitigation-x509certificateclaimsetfindclaims-method"></a>Mitigación: Método X509CertificateClaimSet.FindClaims
A partir de las aplicaciones que tienen como destino .NET Framework 4.6.1, el método <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> intentará hacer coincidir el argumento `claimType` con todas las entradas DNS de su campo de SAN.  
  
## <a name="impact"></a>Impacto  
 Este cambio solo afecta a aplicaciones que tienen como destino versiones de .NET Framework a partir de .NET Framework 4.6.1.  
  
 Para aquellas aplicaciones destinadas a versiones anteriores de .NET Framework, el método <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> intenta hacer coincidir el argumento `claimType` solo con la última entrada DNS.  
  
## <a name="mitigation"></a>Mitigación  
 Si no quiere este cambio, las aplicaciones que tienen como destino versiones de .NET Framework a partir de .NET Framework 4.6.1 pueden optar por no recibir agregando la siguiente opción de configuración en la sección [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=true" />   
</runtime>  
```  
  
 Además, las aplicaciones que tienen como destino versiones anteriores de .NET Framework, pero que se ejecutan en .NET Framework 4.6.1 y versiones posteriores, pueden optar por recibir en este comportamiento agregando el siguiente ajuste de configuración a la sección [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=false" />   
</runtime>  
```  
  
## <a name="see-also"></a>Vea también

- [Cambios de redestinación](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)

---
title: "Mitigación: Método X509CertificateClaimSet.FindClaims"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ee356e3b-f932-48f5-875a-5e42340bee63
caps.latest.revision: 7
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d19bf73e36061729c0c57439f4e4144669787d1a
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-x509certificateclaimsetfindclaims-method"></a>Mitigación: Método X509CertificateClaimSet.FindClaims
A partir de las aplicaciones que tienen como destino [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], el método <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName> intentará hacer coincidir el argumento `claimType` con todas las entradas DNS de su campo de SAN.  
  
## <a name="impact"></a>Impacto  
 Este cambio solo afecta a aplicaciones que tienen como destino versiones de .NET Framework a partir de [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].  
  
 Para aquellas aplicaciones destinadas a versiones anteriores de .NET Framework, el método <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName> intenta hacer coincidir el argumento `claimType` solo con la última entrada DNS.  
  
## <a name="mitigation"></a>Mitigación  
 Si no desea este cambio, las aplicaciones que tienen como destino versiones de .NET Framework a partir de [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] pueden excluirse al agregar la siguiente opción de configuración en la sección [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=true" />   
</runtime>  
```  
  
 Además, las aplicaciones que tienen como destino versiones anteriores de .NET Framework pero que se ejecutan en [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] y versiones posteriores pueden incluirse en este comportamiento si agregan el siguiente ajuste de configuración a la sección [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=false" />   
</runtime>  
```  
  
## <a name="see-also"></a>Vea también  
 [Cambios de redestinación](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)


---
title: "Mitigaci&#243;n: X509CertificiateClaimSet.FindClaims (m&#233;todo) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ee356e3b-f932-48f5-875a-5e42340bee63
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 3
---
# Mitigaci&#243;n: X509CertificiateClaimSet.FindClaims (m&#233;todo)
A partir de las aplicaciones que tienen como destino [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], el método <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName> intentará hacer coincidir el argumento `claimType` con todas las entradas DNS de su campo de SAN.  
  
## Impacto  
 Este cambio solo afecta a aplicaciones destinadas a [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].  
  
 Para aquellas aplicaciones destinadas a versiones anteriores de .NET Framework, el método <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName> intenta hacer coincidir el argumento `claimType` solo con la última entrada DNS.  
  
## Mitigación  
 Si no desea que este cambio, las aplicaciones que se destinan a [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] pueden excluirse al agregar la siguiente opción de configuración para la sección [\<runtime\>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:  
  
```xml  
  
<runtime> <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=true" /> </runtime>  
  
```  
  
 Además, las aplicaciones destinadas a las versiones anteriores de .NET Framework pero se ejecutan en [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] pueden incluirse en este comportamiento si se agrega la opción de configuración siguiente para la sección [\<runtime\>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:  
  
```xml  
  
<runtime> <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=false" /> </runtime>  
  
```  
  
## Vea también  
 [Cambios de redestinación](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)
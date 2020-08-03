---
title: 'Mitigación: Método X509CertificateClaimSet.FindClaims'
description: Obtenga información sobre cómo ha cambiado el método X509CertificateClaimSet.FindClaims para las aplicaciones que tienen como destino .NET Framework 4.6.1.
ms.date: 03/30/2017
ms.assetid: ee356e3b-f932-48f5-875a-5e42340bee63
ms.openlocfilehash: 304d8fb5adc27b33f2410faaaf8662e0ff9be66d
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475325"
---
# <a name="mitigation-x509certificateclaimsetfindclaims-method"></a><span data-ttu-id="32275-103">Mitigación: Método X509CertificateClaimSet.FindClaims</span><span class="sxs-lookup"><span data-stu-id="32275-103">Mitigation: X509CertificateClaimSet.FindClaims Method</span></span>

<span data-ttu-id="32275-104">A partir de las aplicaciones que tienen como destino .NET Framework 4.6.1, el método <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> intentará hacer coincidir el argumento `claimType` con todas las entradas DNS de su campo de SAN.</span><span class="sxs-lookup"><span data-stu-id="32275-104">Starting with apps that target .NET Framework 4.6.1, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> method will attempt to match the `claimType` argument with all the DNS entries in its SAN field.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="32275-105">Impacto</span><span class="sxs-lookup"><span data-stu-id="32275-105">Impact</span></span>  
 <span data-ttu-id="32275-106">Este cambio solo afecta a aplicaciones que tienen como destino versiones de .NET Framework a partir de .NET Framework 4.6.1.</span><span class="sxs-lookup"><span data-stu-id="32275-106">This change only affects apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1.</span></span>  
  
 <span data-ttu-id="32275-107">Para aquellas aplicaciones destinadas a versiones anteriores de .NET Framework, el método <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> intenta hacer coincidir el argumento `claimType` solo con la última entrada DNS.</span><span class="sxs-lookup"><span data-stu-id="32275-107">For apps that target previous versions of the .NET Framework, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> method attempts to match the `claimType` argument only with the last  DNS entry.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="32275-108">Mitigación</span><span class="sxs-lookup"><span data-stu-id="32275-108">Mitigation</span></span>  
 <span data-ttu-id="32275-109">Si no quiere este cambio, las aplicaciones que tienen como destino versiones de .NET Framework a partir de .NET Framework 4.6.1 pueden rechazarlo si se agrega la siguiente opción de configuración en la sección [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="32275-109">If this change is undesirable, apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1 can opt out of it by adding the following configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=true" />
</runtime>  
```  
  
 <span data-ttu-id="32275-110">Además, las aplicaciones que tienen como destino versiones anteriores de .NET Framework, pero que se ejecutan en .NET Framework 4.6.1 y versiones posteriores, pueden optar por recibir este comportamiento si se agrega el siguiente ajuste de configuración en la sección [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="32275-110">In addition, apps that target previous versions of the .NET Framework but are running under the .NET Framework 4.6.1 and later versions can opt in to this behavior by adding the following configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=false" />
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="32275-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="32275-111">See also</span></span>

- [<span data-ttu-id="32275-112">Compatibilidad de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="32275-112">Application compatibility</span></span>](application-compatibility.md)

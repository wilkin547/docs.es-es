---
description: 'Más información sobre: creación de notificaciones y valores de recursos'
title: Creación de notificaciones y valores de recursos
ms.date: 03/30/2017
helpviewer_keywords:
- claims [WCF], creation and resource values
ms.assetid: 30431f76-cbe7-4bad-bad7-8e43e23a82d4
ms.openlocfilehash: 20763c683c5bf5734a21a4315576a8f9f354ff35
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99734989"
---
# <a name="claim-creation-and-resource-values"></a><span data-ttu-id="9bc8e-103">Creación de notificaciones y valores de recursos</span><span class="sxs-lookup"><span data-stu-id="9bc8e-103">Claim Creation and Resource Values</span></span>

<span data-ttu-id="9bc8e-104">La clase <xref:System.IdentityModel.Claims.Claim> proporciona varios métodos para crear instancias de tipos de demandas integradas.</span><span class="sxs-lookup"><span data-stu-id="9bc8e-104">The <xref:System.IdentityModel.Claims.Claim> class provides several methods for creating instances of built-in claims types.</span></span> <span data-ttu-id="9bc8e-105">De estos métodos, los siguientes no realizan ninguna comprobación semántica ni de formato en el recurso proporcionado:</span><span class="sxs-lookup"><span data-stu-id="9bc8e-105">Of these methods, the following perform no semantic or format checking on the supplied resource:</span></span>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateDnsClaim%2A>  
  
- <span data-ttu-id="9bc8e-106"><xref:System.IdentityModel.Claims.Claim.CreateHashClaim%2A> (no compruebe la longitud o contenido de la matriz de bytes)</span><span class="sxs-lookup"><span data-stu-id="9bc8e-106"><xref:System.IdentityModel.Claims.Claim.CreateHashClaim%2A> (does not check the length or content of the byte array)</span></span>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateNameClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateSpnClaim%2A>  
  
- <span data-ttu-id="9bc8e-107"><xref:System.IdentityModel.Claims.Claim.CreateThumbprintClaim%2A> (no compruebe la longitud o contenido de la matriz de bytes)</span><span class="sxs-lookup"><span data-stu-id="9bc8e-107"><xref:System.IdentityModel.Claims.Claim.CreateThumbprintClaim%2A> (does not check the length or content of the byte array)</span></span>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateUpnClaim%2A>  
  
 <span data-ttu-id="9bc8e-108">Se debería tener cuidado al llamar a los métodos anteriores para asegurarse de que los valores de recurso pasados son del formato correcto o contienen el tipo de información correcto (o ambos).</span><span class="sxs-lookup"><span data-stu-id="9bc8e-108">Care should be taken when calling the above methods to ensure that the resource values passed in are of the correct format or contain the correct kind of information (or both).</span></span>  
  
 <span data-ttu-id="9bc8e-109">Los métodos siguientes toman tipos específicos:</span><span class="sxs-lookup"><span data-stu-id="9bc8e-109">The following methods take specific types:</span></span>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateDenyOnlyWindowsSidClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateMailAddressClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateRsaClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateUriClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateWindowsSidClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateX500DistinguishedNameClaim%2A>  
  
## <a name="see-also"></a><span data-ttu-id="9bc8e-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="9bc8e-110">See also</span></span>

- <xref:System.IdentityModel.Claims.Claim>
- <xref:System.IdentityModel.Claims.ClaimSet>
- [<span data-ttu-id="9bc8e-111">Administración de notificaciones y autorización con el modelo de identidad</span><span class="sxs-lookup"><span data-stu-id="9bc8e-111">Managing Claims and Authorization with the Identity Model</span></span>](managing-claims-and-authorization-with-the-identity-model.md)

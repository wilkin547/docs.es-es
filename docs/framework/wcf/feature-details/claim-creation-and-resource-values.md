---
title: Creación de notificaciones y valores de recursos
ms.date: 03/30/2017
helpviewer_keywords:
- claims [WCF], creation and resource values
ms.assetid: 30431f76-cbe7-4bad-bad7-8e43e23a82d4
ms.openlocfilehash: ca1bb8ccbc77e2b026a65a9cef56118e8b86dbb3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54704074"
---
# <a name="claim-creation-and-resource-values"></a><span data-ttu-id="463ec-102">Creación de notificaciones y valores de recursos</span><span class="sxs-lookup"><span data-stu-id="463ec-102">Claim Creation and Resource Values</span></span>
<span data-ttu-id="463ec-103">La clase <xref:System.IdentityModel.Claims.Claim> proporciona varios métodos para crear instancias de tipos de demandas integradas.</span><span class="sxs-lookup"><span data-stu-id="463ec-103">The <xref:System.IdentityModel.Claims.Claim> class provides several methods for creating instances of built-in claims types.</span></span> <span data-ttu-id="463ec-104">De estos métodos, los siguientes no realizan ninguna comprobación semántica ni de formato en el recurso proporcionado:</span><span class="sxs-lookup"><span data-stu-id="463ec-104">Of these methods, the following perform no semantic or format checking on the supplied resource:</span></span>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateDnsClaim%2A>  
  
-   <span data-ttu-id="463ec-105"><xref:System.IdentityModel.Claims.Claim.CreateHashClaim%2A> (no compruebe la longitud o contenido de la matriz de bytes)</span><span class="sxs-lookup"><span data-stu-id="463ec-105"><xref:System.IdentityModel.Claims.Claim.CreateHashClaim%2A> (does not check the length or content of the byte array)</span></span>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateNameClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateSpnClaim%2A>  
  
-   <span data-ttu-id="463ec-106"><xref:System.IdentityModel.Claims.Claim.CreateThumbprintClaim%2A> (no compruebe la longitud o contenido de la matriz de bytes)</span><span class="sxs-lookup"><span data-stu-id="463ec-106"><xref:System.IdentityModel.Claims.Claim.CreateThumbprintClaim%2A> (does not check the length or content of the byte array)</span></span>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateUpnClaim%2A>  
  
 <span data-ttu-id="463ec-107">Se debería tener cuidado al llamar a los métodos anteriores para asegurarse de que los valores de recurso pasados son del formato correcto o contienen el tipo de información correcto (o ambos).</span><span class="sxs-lookup"><span data-stu-id="463ec-107">Care should be taken when calling the above methods to ensure that the resource values passed in are of the correct format or contain the correct kind of information (or both).</span></span>  
  
 <span data-ttu-id="463ec-108">Los métodos siguientes toman tipos específicos:</span><span class="sxs-lookup"><span data-stu-id="463ec-108">The following methods take specific types:</span></span>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateDenyOnlyWindowsSidClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateMailAddressClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateRsaClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateUriClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateWindowsSidClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateX500DistinguishedNameClaim%2A>  
  
## <a name="see-also"></a><span data-ttu-id="463ec-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="463ec-109">See also</span></span>
- <xref:System.IdentityModel.Claims.Claim>
- <xref:System.IdentityModel.Claims.ClaimSet>
- [<span data-ttu-id="463ec-110">Administración de notificaciones y autorización con el modelo de identidad</span><span class="sxs-lookup"><span data-stu-id="463ec-110">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)

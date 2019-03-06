---
title: <claimTypeRequirements> para <message>
ms.date: 03/30/2017
ms.assetid: f95c5ecd-abb6-4b77-a6d7-a38727f4a142
ms.openlocfilehash: 9cf77f6c026df5f78cc8ae6e6783e91f1c86e282
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367458"
---
# <a name="claimtyperequirements-for-message"></a><span data-ttu-id="09e8a-102">\<claimTypeRequirements > para \<mensaje ></span><span class="sxs-lookup"><span data-stu-id="09e8a-102">\<claimTypeRequirements> for \<message></span></span>
<span data-ttu-id="09e8a-103">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="09e8a-103">Specifies a collection of required claim types.</span></span>  
  
 <span data-ttu-id="09e8a-104">El servicio usa la colección para especificar cualquier notificación necesaria y opcional que debe estar en el token emitido que el cliente utiliza para tener acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="09e8a-104">The collection is used by the service to specify any required and optional claims which must be in the issued token the client uses to access the service.</span></span> <span data-ttu-id="09e8a-105">El servicio expone los tipos de notificación necesarios en metadatos si se habilita la publicación de WSDL pero WCF no requiere que el token emitido contenga los tipos de notificación especificados.</span><span class="sxs-lookup"><span data-stu-id="09e8a-105">The service exposes the required claim types in metadata if WSDL publishing is enabled but WCF does not require the issued token contain the specified claim types.</span></span> <span data-ttu-id="09e8a-106">Los servicios que desean exigir tipos de notificación necesarios están presentes y deberían hacerlo con la directiva de autorización.</span><span class="sxs-lookup"><span data-stu-id="09e8a-106">Services wishing to enforce required claim types are present should do using authorization policy.</span></span>  
  
 <span data-ttu-id="09e8a-107">En los clientes federados, esta colección contiene la lista de notificaciones necesarias y opcionales que se envían al servicio del token de seguridad en la solicitud del cliente para un token emitido.</span><span class="sxs-lookup"><span data-stu-id="09e8a-107">On federated clients, this collection contains the list of required and optional claims which is sent to the security token service in the client’s request for an issued token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09e8a-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="09e8a-108">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>

---
title: "Búsqueda de notificaciones en ClaimSet"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- claims [WCF], finding in a claimset
- claims [WCF]
ms.assetid: a76ce107-aeb3-47d0-bfa9-134c53664e20
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ca3f296f46f2a1603f275a92b25ffb09c3025230
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="finding-claims-in-a-claimset"></a><span data-ttu-id="474df-102">Búsqueda de notificaciones en ClaimSet</span><span class="sxs-lookup"><span data-stu-id="474df-102">Finding Claims in a ClaimSet</span></span>
<span data-ttu-id="474df-103">Examinar el contenido de <xref:System.IdentityModel.Claims.ClaimSet> para los tipos determinados de notificaciones es una tarea común al utilizar la autorización basada en notificaciones.</span><span class="sxs-lookup"><span data-stu-id="474df-103">Examining the content of a <xref:System.IdentityModel.Claims.ClaimSet> for particular types of claims is a common task when using claim-based authorization.</span></span> <span data-ttu-id="474df-104">Para examinar <xref:System.IdentityModel.Claims.ClaimSet> para la presencia de notificaciones determinadas, utilice el método <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A>.</span><span class="sxs-lookup"><span data-stu-id="474df-104">To examine a <xref:System.IdentityModel.Claims.ClaimSet> for the presence of particular claims, use the <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A> method.</span></span> <span data-ttu-id="474df-105">Este método proporciona un mejor rendimiento que ejecutar una iteración directamente sobre <xref:System.IdentityModel.Claims.ClaimSet>.</span><span class="sxs-lookup"><span data-stu-id="474df-105">This method provides better performance than iterating directly over the <xref:System.IdentityModel.Claims.ClaimSet>.</span></span> <span data-ttu-id="474df-106">En el siguiente ejemplo se muestra este uso.</span><span class="sxs-lookup"><span data-stu-id="474df-106">The following example demonstrates this usage.</span></span> <span data-ttu-id="474df-107">Tenga en cuenta que los parámetros `claimType` y `claimRight` pueden ser `null`.</span><span class="sxs-lookup"><span data-stu-id="474df-107">Note that the `claimType` and `claimRight` parameters can be `null`.</span></span> <span data-ttu-id="474df-108">En ese caso, los parámetros coincidirán con todos los tipos de notificaciones y derechos de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="474df-108">In that case, the parameters will match all claim types and claim rights.</span></span>  
  
## <a name="example"></a><span data-ttu-id="474df-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="474df-109">Example</span></span>  
 [!code-csharp[c_FindClaimsPerf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_findclaimsperf/cs/c_findclaimsperf.cs#2)]
 [!code-vb[c_FindClaimsPerf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_findclaimsperf/vb/c_findclaimsperf.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="474df-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="474df-110">See Also</span></span>  
 [<span data-ttu-id="474df-111">Administración de notificaciones y autorización con el modelo de identidad</span><span class="sxs-lookup"><span data-stu-id="474df-111">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)

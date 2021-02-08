---
description: Más información acerca de cómo buscar notificaciones en un ClaimSet
title: Búsqueda de notificaciones en ClaimSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- claims [WCF], finding in a claimset
- claims [WCF]
ms.assetid: a76ce107-aeb3-47d0-bfa9-134c53664e20
ms.openlocfilehash: 3ac4553e50f98f54e0a23aa9d759d7ae2f7caa8c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802936"
---
# <a name="finding-claims-in-a-claimset"></a><span data-ttu-id="05a2f-103">Búsqueda de notificaciones en ClaimSet</span><span class="sxs-lookup"><span data-stu-id="05a2f-103">Finding Claims in a ClaimSet</span></span>

<span data-ttu-id="05a2f-104">Examinar el contenido de <xref:System.IdentityModel.Claims.ClaimSet> para los tipos determinados de notificaciones es una tarea común al utilizar la autorización basada en notificaciones.</span><span class="sxs-lookup"><span data-stu-id="05a2f-104">Examining the content of a <xref:System.IdentityModel.Claims.ClaimSet> for particular types of claims is a common task when using claim-based authorization.</span></span> <span data-ttu-id="05a2f-105">Para examinar <xref:System.IdentityModel.Claims.ClaimSet> para la presencia de notificaciones determinadas, utilice el método <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A>.</span><span class="sxs-lookup"><span data-stu-id="05a2f-105">To examine a <xref:System.IdentityModel.Claims.ClaimSet> for the presence of particular claims, use the <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A> method.</span></span> <span data-ttu-id="05a2f-106">Este método proporciona un mejor rendimiento que ejecutar una iteración directamente sobre <xref:System.IdentityModel.Claims.ClaimSet>.</span><span class="sxs-lookup"><span data-stu-id="05a2f-106">This method provides better performance than iterating directly over the <xref:System.IdentityModel.Claims.ClaimSet>.</span></span> <span data-ttu-id="05a2f-107">En el siguiente ejemplo se muestra este uso.</span><span class="sxs-lookup"><span data-stu-id="05a2f-107">The following example demonstrates this usage.</span></span> <span data-ttu-id="05a2f-108">Tenga en cuenta que los parámetros `claimType` y `claimRight` pueden ser `null`.</span><span class="sxs-lookup"><span data-stu-id="05a2f-108">Note that the `claimType` and `claimRight` parameters can be `null`.</span></span> <span data-ttu-id="05a2f-109">En ese caso, los parámetros coincidirán con todos los tipos de notificaciones y derechos de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="05a2f-109">In that case, the parameters will match all claim types and claim rights.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05a2f-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="05a2f-110">Example</span></span>  

 [!code-csharp[c_FindClaimsPerf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_findclaimsperf/cs/c_findclaimsperf.cs#2)]
 [!code-vb[c_FindClaimsPerf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_findclaimsperf/vb/c_findclaimsperf.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="05a2f-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="05a2f-111">See also</span></span>

- [<span data-ttu-id="05a2f-112">Administración de notificaciones y autorización con el modelo de identidad</span><span class="sxs-lookup"><span data-stu-id="05a2f-112">Managing Claims and Authorization with the Identity Model</span></span>](managing-claims-and-authorization-with-the-identity-model.md)

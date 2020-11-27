---
title: Búsqueda de notificaciones en ClaimSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- claims [WCF], finding in a claimset
- claims [WCF]
ms.assetid: a76ce107-aeb3-47d0-bfa9-134c53664e20
ms.openlocfilehash: c43a47b32a2a3c15d1a51b8b6931ebb021722a64
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96268461"
---
# <a name="finding-claims-in-a-claimset"></a>Búsqueda de notificaciones en ClaimSet

Examinar el contenido de <xref:System.IdentityModel.Claims.ClaimSet> para los tipos determinados de notificaciones es una tarea común al utilizar la autorización basada en notificaciones. Para examinar <xref:System.IdentityModel.Claims.ClaimSet> para la presencia de notificaciones determinadas, utilice el método <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A>. Este método proporciona un mejor rendimiento que ejecutar una iteración directamente sobre <xref:System.IdentityModel.Claims.ClaimSet>. En el siguiente ejemplo se muestra este uso. Tenga en cuenta que los parámetros `claimType` y `claimRight` pueden ser `null`. En ese caso, los parámetros coincidirán con todos los tipos de notificaciones y derechos de notificaciones.  
  
## <a name="example"></a>Ejemplo  

 [!code-csharp[c_FindClaimsPerf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_findclaimsperf/cs/c_findclaimsperf.cs#2)]
 [!code-vb[c_FindClaimsPerf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_findclaimsperf/vb/c_findclaimsperf.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [Administración de notificaciones y autorización con el modelo de identidad](managing-claims-and-authorization-with-the-identity-model.md)

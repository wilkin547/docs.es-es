---
title: Creación de notificaciones y valores de recursos
ms.date: 03/30/2017
helpviewer_keywords:
- claims [WCF], creation and resource values
ms.assetid: 30431f76-cbe7-4bad-bad7-8e43e23a82d4
ms.openlocfilehash: bd9a8b7faf3cd7a648ff6b2a50ac68f21561497c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766914"
---
# <a name="claim-creation-and-resource-values"></a>Creación de notificaciones y valores de recursos
La clase <xref:System.IdentityModel.Claims.Claim> proporciona varios métodos para crear instancias de tipos de demandas integradas. De estos métodos, los siguientes no realizan ninguna comprobación semántica ni de formato en el recurso proporcionado:  
  
- <xref:System.IdentityModel.Claims.Claim.CreateDnsClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateHashClaim%2A> (no compruebe la longitud o contenido de la matriz de bytes)  
  
- <xref:System.IdentityModel.Claims.Claim.CreateNameClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateSpnClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateThumbprintClaim%2A> (no compruebe la longitud o contenido de la matriz de bytes)  
  
- <xref:System.IdentityModel.Claims.Claim.CreateUpnClaim%2A>  
  
 Se debería tener cuidado al llamar a los métodos anteriores para asegurarse de que los valores de recurso pasados son del formato correcto o contienen el tipo de información correcto (o ambos).  
  
 Los métodos siguientes toman tipos específicos:  
  
- <xref:System.IdentityModel.Claims.Claim.CreateDenyOnlyWindowsSidClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateMailAddressClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateRsaClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateUriClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateWindowsSidClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateX500DistinguishedNameClaim%2A>  
  
## <a name="see-also"></a>Vea también

- <xref:System.IdentityModel.Claims.Claim>
- <xref:System.IdentityModel.Claims.ClaimSet>
- [Administración de notificaciones y autorización con el modelo de identidad](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)

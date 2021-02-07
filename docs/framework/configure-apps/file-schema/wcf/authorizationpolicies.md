---
description: 'Más información acerca de: <authorizationPolicies>'
title: <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 5b367489-54d7-408b-8f56-cb157dd68eaf
ms.openlocfilehash: 4b0f341a1bb6ebb4918a5d71aba82270c31ba863
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749836"
---
# \<authorizationPolicies>

Esta sección de configuración contiene una colección de tipos de directiva de autorización, que se pueden agregar utilizando la palabra clave `add`. Cada directiva de autorización contiene un atributo `policyType` necesario único que es una cadena. El atributo especifica una directiva de autorización que permite la transformación de un conjunto de demandas de entrada en otro conjunto de demandas. Se puede permitir o denegar el acceso en base a eso. Para obtener más información sobre cómo funciona una directiva de autorización, vea <xref:System.IdentityModel.Policy.IAuthorizationPolicy> y [Directiva de autorización](../../../wcf/samples/authorization-policy.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [Autorización de acceso a operaciones de servicio](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [Procedimiento para crear un administrador de autorización personalizado para un servicio](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [\<add>](add-of-authorizationpolicies.md)
- [Directiva de autorización](../../../wcf/samples/authorization-policy.md)

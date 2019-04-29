---
title: <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 5b367489-54d7-408b-8f56-cb157dd68eaf
ms.openlocfilehash: 2910f47b85ee67694cae0c3a725c3c7c7b3803c0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701728"
---
# <a name="authorizationpolicies"></a><span data-ttu-id="b7837-101">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="b7837-101">\<authorizationPolicies></span></span>
<span data-ttu-id="b7837-102">Esta sección de configuración contiene una colección de tipos de directiva de autorización, que se pueden agregar utilizando la palabra clave `add`.</span><span class="sxs-lookup"><span data-stu-id="b7837-102">This configuration section contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="b7837-103">Cada directiva de autorización contiene un atributo `policyType` necesario único que es una cadena.</span><span class="sxs-lookup"><span data-stu-id="b7837-103">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="b7837-104">El atributo especifica una directiva de autorización que permite la transformación de un conjunto de demandas de entrada en otro conjunto de demandas.</span><span class="sxs-lookup"><span data-stu-id="b7837-104">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="b7837-105">Se puede permitir o denegar el acceso en base a eso.</span><span class="sxs-lookup"><span data-stu-id="b7837-105">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="b7837-106">Para obtener más información sobre el funcionamiento de una directiva de autorización, consulte <xref:System.IdentityModel.Policy.IAuthorizationPolicy> y [directiva de autorización](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="b7837-106">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7837-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7837-107">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="b7837-108">Autorización de acceso a operaciones de servicio</span><span class="sxs-lookup"><span data-stu-id="b7837-108">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="b7837-109">Cómo: Crear un administrador de autorización personalizado para un servicio</span><span class="sxs-lookup"><span data-stu-id="b7837-109">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="b7837-110">\<add></span><span class="sxs-lookup"><span data-stu-id="b7837-110">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)
- [<span data-ttu-id="b7837-111">Directiva de autorización</span><span class="sxs-lookup"><span data-stu-id="b7837-111">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)

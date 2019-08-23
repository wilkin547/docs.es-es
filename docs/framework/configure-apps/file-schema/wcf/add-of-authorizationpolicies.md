---
title: <add> de <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
ms.openlocfilehash: 65398c5afa9750f215c95899bb6004cae671123a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920270"
---
# <a name="add-of-authorizationpolicies"></a><span data-ttu-id="40f76-102">\<Agregar > de \<authorizationPolicies ></span><span class="sxs-lookup"><span data-stu-id="40f76-102">\<add> of \<authorizationPolicies></span></span>
<span data-ttu-id="40f76-103">Especifica una directiva de autorización para la transformación de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="40f76-103">Specifies an authorization policy for claim transformation.</span></span>  
  
 <span data-ttu-id="40f76-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="40f76-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="40f76-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="40f76-105">\<behaviors></span></span>  
<span data-ttu-id="40f76-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="40f76-106">\<behavior></span></span>  
<span data-ttu-id="40f76-107">\<serviceAuthorization></span><span class="sxs-lookup"><span data-stu-id="40f76-107">\<serviceAuthorization></span></span>  
<span data-ttu-id="40f76-108">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="40f76-108">\<authorizationPolicies></span></span>  
<span data-ttu-id="40f76-109">\<add></span><span class="sxs-lookup"><span data-stu-id="40f76-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40f76-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40f76-110">Syntax</span></span>  
  
```xml  
<authorizationPolicies>
  <add policyType="String" />
</authorizationPolicies>
```  
  
## <a name="type"></a><span data-ttu-id="40f76-111">Type</span><span class="sxs-lookup"><span data-stu-id="40f76-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40f76-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="40f76-112">Attributes and Elements</span></span>  
 <span data-ttu-id="40f76-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="40f76-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40f76-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="40f76-114">Attributes</span></span>  
  
|<span data-ttu-id="40f76-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="40f76-115">Attribute</span></span>|<span data-ttu-id="40f76-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="40f76-116">Description</span></span>|  
|---------------|-----------------|  
|`policyType`|<span data-ttu-id="40f76-117">Atributo de cadena requerido.</span><span class="sxs-lookup"><span data-stu-id="40f76-117">A required String attribute.</span></span><br /><br /> <span data-ttu-id="40f76-118">El modelo de control de acceso de Windows Communication Foundation (WCF) admite el aprovisionamiento de un conjunto de directivas de autorización como tipos.</span><span class="sxs-lookup"><span data-stu-id="40f76-118">The Windows Communication Foundation (WCF) access control model supports provisioning a set of authorization policies as types.</span></span> <span data-ttu-id="40f76-119">Este atributo especifica una directiva de autorización que permite la transformación de un conjunto de notificaciones de entrada en otro conjunto de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="40f76-119">This attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="40f76-120">Se puede permitir o denegar el acceso en base a eso.</span><span class="sxs-lookup"><span data-stu-id="40f76-120">Access control can be granted or denied based on that.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40f76-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="40f76-121">Child Elements</span></span>  
 <span data-ttu-id="40f76-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="40f76-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="40f76-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="40f76-123">Parent Elements</span></span>  
  
|<span data-ttu-id="40f76-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="40f76-124">Element</span></span>|<span data-ttu-id="40f76-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="40f76-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40f76-126">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="40f76-126">\<authorizationPolicies></span></span>](authorizationpolicies.md)|<span data-ttu-id="40f76-127">Especifica una colección de tipos de directiva de autorización.</span><span class="sxs-lookup"><span data-stu-id="40f76-127">Specifies a collection of authorization policy types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40f76-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="40f76-128">Remarks</span></span>  
 <span data-ttu-id="40f76-129">Cada directiva de autorización contiene un atributo `policyType` necesario único que es una cadena.</span><span class="sxs-lookup"><span data-stu-id="40f76-129">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="40f76-130">El atributo especifica una directiva de autorización que permite la transformación de un conjunto de demandas de entrada en otro conjunto de demandas.</span><span class="sxs-lookup"><span data-stu-id="40f76-130">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="40f76-131">Se puede permitir o denegar el acceso en base a eso.</span><span class="sxs-lookup"><span data-stu-id="40f76-131">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="40f76-132">Para obtener más información sobre cómo funciona una directiva de autorización <xref:System.IdentityModel.Policy.IAuthorizationPolicy> , vea y [Directiva de autorización](../../../wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="40f76-132">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40f76-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="40f76-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="40f76-134">Autorización de acceso a operaciones de servicio</span><span class="sxs-lookup"><span data-stu-id="40f76-134">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="40f76-135">Cómo: Crear un administrador de autorización personalizado para un servicio</span><span class="sxs-lookup"><span data-stu-id="40f76-135">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="40f76-136">\<add></span><span class="sxs-lookup"><span data-stu-id="40f76-136">\<add></span></span>](add-of-authorizationpolicies.md)
- [<span data-ttu-id="40f76-137">Directiva de autorización</span><span class="sxs-lookup"><span data-stu-id="40f76-137">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)

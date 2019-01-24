---
title: '&lt;add&gt; de &lt;authorizationPolicies&gt;'
ms.date: 03/30/2017
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
ms.openlocfilehash: c283f99bedc16352ffca4c41c3d4628271200695
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577530"
---
# <a name="ltaddgt-of-ltauthorizationpoliciesgt"></a><span data-ttu-id="85a4b-102">&lt;add&gt; de &lt;authorizationPolicies&gt;</span><span class="sxs-lookup"><span data-stu-id="85a4b-102">&lt;add&gt; of &lt;authorizationPolicies&gt;</span></span>
<span data-ttu-id="85a4b-103">Especifica una directiva de autorización para la transformación de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="85a4b-103">Specifies an authorization policy for claim transformation.</span></span>  
  
 <span data-ttu-id="85a4b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="85a4b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="85a4b-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="85a4b-105">\<behaviors></span></span>  
<span data-ttu-id="85a4b-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="85a4b-106">\<behavior></span></span>  
<span data-ttu-id="85a4b-107">\<serviceAuthorization></span><span class="sxs-lookup"><span data-stu-id="85a4b-107">\<serviceAuthorization></span></span>  
<span data-ttu-id="85a4b-108">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="85a4b-108">\<authorizationPolicies></span></span>  
<span data-ttu-id="85a4b-109">\<add></span><span class="sxs-lookup"><span data-stu-id="85a4b-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85a4b-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85a4b-110">Syntax</span></span>  
  
```xml  
<authorizationPolicies>
  <add policyType="String" />
</authorizationPolicies>
```  
  
## <a name="type"></a><span data-ttu-id="85a4b-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="85a4b-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85a4b-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="85a4b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="85a4b-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="85a4b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85a4b-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="85a4b-114">Attributes</span></span>  
  
|<span data-ttu-id="85a4b-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="85a4b-115">Attribute</span></span>|<span data-ttu-id="85a4b-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="85a4b-116">Description</span></span>|  
|---------------|-----------------|  
|`policyType`|<span data-ttu-id="85a4b-117">Atributo de cadena requerido.</span><span class="sxs-lookup"><span data-stu-id="85a4b-117">A required String attribute.</span></span><br /><br /> <span data-ttu-id="85a4b-118">El modelo de control de acceso de Windows Communication Foundation (WCF) admite el aprovisionamiento de un conjunto de directivas de autorización como tipos.</span><span class="sxs-lookup"><span data-stu-id="85a4b-118">The Windows Communication Foundation (WCF) access control model supports provisioning a set of authorization policies as types.</span></span> <span data-ttu-id="85a4b-119">Este atributo especifica una directiva de autorización que permite la transformación de un conjunto de notificaciones de entrada en otro conjunto de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="85a4b-119">This attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="85a4b-120">Se puede permitir o denegar el acceso en base a eso.</span><span class="sxs-lookup"><span data-stu-id="85a4b-120">Access control can be granted or denied based on that.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85a4b-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="85a4b-121">Child Elements</span></span>  
 <span data-ttu-id="85a4b-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="85a4b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="85a4b-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="85a4b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="85a4b-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="85a4b-124">Element</span></span>|<span data-ttu-id="85a4b-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="85a4b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="85a4b-126">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="85a4b-126">\<authorizationPolicies></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authorizationpolicies.md)|<span data-ttu-id="85a4b-127">Especifica una colección de tipos de directiva de autorización.</span><span class="sxs-lookup"><span data-stu-id="85a4b-127">Specifies a collection of authorization policy types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85a4b-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="85a4b-128">Remarks</span></span>  
 <span data-ttu-id="85a4b-129">Cada directiva de autorización contiene un atributo `policyType` necesario único que es una cadena.</span><span class="sxs-lookup"><span data-stu-id="85a4b-129">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="85a4b-130">El atributo especifica una directiva de autorización que permite la transformación de un conjunto de demandas de entrada en otro conjunto de demandas.</span><span class="sxs-lookup"><span data-stu-id="85a4b-130">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="85a4b-131">Se puede permitir o denegar el acceso en base a eso.</span><span class="sxs-lookup"><span data-stu-id="85a4b-131">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="85a4b-132">Para obtener más información sobre el funcionamiento de una directiva de autorización, consulte <xref:System.IdentityModel.Policy.IAuthorizationPolicy> y [directiva de autorización](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="85a4b-132">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85a4b-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="85a4b-133">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="85a4b-134">Autorización de acceso a operaciones de servicio</span><span class="sxs-lookup"><span data-stu-id="85a4b-134">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="85a4b-135">Cómo: Crear un administrador de autorización personalizado para un servicio</span><span class="sxs-lookup"><span data-stu-id="85a4b-135">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="85a4b-136">\<add></span><span class="sxs-lookup"><span data-stu-id="85a4b-136">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)
- [<span data-ttu-id="85a4b-137">Directiva de autorización</span><span class="sxs-lookup"><span data-stu-id="85a4b-137">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)

---
title: '&lt;add&gt; de &lt;authorizationPolicies&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7a039500281f02aa6ae891065255174c2353ba33
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltauthorizationpoliciesgt"></a><span data-ttu-id="c863d-102">&lt;add&gt; de &lt;authorizationPolicies&gt;</span><span class="sxs-lookup"><span data-stu-id="c863d-102">&lt;add&gt; of &lt;authorizationPolicies&gt;</span></span>
<span data-ttu-id="c863d-103">Especifica una directiva de autorización para la transformación de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="c863d-103">Specifies an authorization policy for claim transformation.</span></span>  
  
 <span data-ttu-id="c863d-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c863d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c863d-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="c863d-105">\<behaviors></span></span>  
<span data-ttu-id="c863d-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="c863d-106">\<behavior></span></span>  
<span data-ttu-id="c863d-107">\<serviceAuthorization ></span><span class="sxs-lookup"><span data-stu-id="c863d-107">\<serviceAuthorization></span></span>  
<span data-ttu-id="c863d-108">\<authorizationPolicies ></span><span class="sxs-lookup"><span data-stu-id="c863d-108">\<authorizationPolicies></span></span>  
<span data-ttu-id="c863d-109">\<add></span><span class="sxs-lookup"><span data-stu-id="c863d-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c863d-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c863d-110">Syntax</span></span>  
  
```xml  
<authorizationPolicies>  
   <add policyType="String" />  
</authorizationPolicies>  
```  
  
## <a name="type"></a><span data-ttu-id="c863d-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="c863d-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c863d-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c863d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c863d-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c863d-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c863d-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="c863d-114">Attributes</span></span>  
  
|<span data-ttu-id="c863d-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="c863d-115">Attribute</span></span>|<span data-ttu-id="c863d-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="c863d-116">Description</span></span>|  
|---------------|-----------------|  
|`policyType`|<span data-ttu-id="c863d-117">Atributo de cadena requerido.</span><span class="sxs-lookup"><span data-stu-id="c863d-117">A required String attribute.</span></span><br /><br /> <span data-ttu-id="c863d-118">El modelo de control de acceso de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] admite el aprovisionamiento de un conjunto de directivas de autorización como tipos.</span><span class="sxs-lookup"><span data-stu-id="c863d-118">The [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] access control model supports provisioning a set of authorization policies as types.</span></span> <span data-ttu-id="c863d-119">Este atributo especifica una directiva de autorización que permite la transformación de un conjunto de notificaciones de entrada en otro conjunto de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="c863d-119">This attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="c863d-120">Se puede permitir o denegar el acceso en base a eso.</span><span class="sxs-lookup"><span data-stu-id="c863d-120">Access control can be granted or denied based on that.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c863d-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c863d-121">Child Elements</span></span>  
 <span data-ttu-id="c863d-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c863d-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c863d-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c863d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c863d-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="c863d-124">Element</span></span>|<span data-ttu-id="c863d-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="c863d-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c863d-126">\<authorizationPolicies ></span><span class="sxs-lookup"><span data-stu-id="c863d-126">\<authorizationPolicies></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authorizationpolicies.md)|<span data-ttu-id="c863d-127">Especifica una colección de tipos de directiva de autorización.</span><span class="sxs-lookup"><span data-stu-id="c863d-127">Specifies a collection of authorization policy types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c863d-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c863d-128">Remarks</span></span>  
 <span data-ttu-id="c863d-129">Cada directiva de autorización contiene un atributo `policyType` necesario único que es una cadena.</span><span class="sxs-lookup"><span data-stu-id="c863d-129">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="c863d-130">El atributo especifica una directiva de autorización que permite la transformación de un conjunto de demandas de entrada en otro conjunto de demandas.</span><span class="sxs-lookup"><span data-stu-id="c863d-130">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="c863d-131">Se puede permitir o denegar el acceso en base a eso.</span><span class="sxs-lookup"><span data-stu-id="c863d-131">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="c863d-132">Para obtener más información sobre el funcionamiento de una directiva de autorización, consulte <xref:System.IdentityModel.Policy.IAuthorizationPolicy> y [directiva de autorización](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="c863d-132">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c863d-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="c863d-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>  
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>  
 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>  
 [<span data-ttu-id="c863d-134">Autorizar el acceso a las operaciones de servicio</span><span class="sxs-lookup"><span data-stu-id="c863d-134">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 [<span data-ttu-id="c863d-135">Cómo: crear un administrador de autorización personalizado para un servicio</span><span class="sxs-lookup"><span data-stu-id="c863d-135">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)  
 [<span data-ttu-id="c863d-136">\<add></span><span class="sxs-lookup"><span data-stu-id="c863d-136">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)  
 [<span data-ttu-id="c863d-137">Directiva de autorización</span><span class="sxs-lookup"><span data-stu-id="c863d-137">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)

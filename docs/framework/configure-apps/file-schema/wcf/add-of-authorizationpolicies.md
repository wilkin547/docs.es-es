---
title: <add> de <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
ms.openlocfilehash: e2597bc51e788c919bfe3ce3422ae2911cc6b33b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400697"
---
# <a name="add-of-authorizationpolicies"></a><span data-ttu-id="c3cf6-102">\<Agregar > de \<authorizationPolicies ></span><span class="sxs-lookup"><span data-stu-id="c3cf6-102">\<add> of \<authorizationPolicies></span></span>
<span data-ttu-id="c3cf6-103">Especifica una directiva de autorización para la transformación de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="c3cf6-103">Specifies an authorization policy for claim transformation.</span></span>  
  
<span data-ttu-id="c3cf6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c3cf6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c3cf6-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c3cf6-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c3cf6-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c3cf6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="c3cf6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c3cf6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="c3cf6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c3cf6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="c3cf6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceAuthorization**](serviceauthorization-element.md)</span><span class="sxs-lookup"><span data-stu-id="c3cf6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceAuthorization>**](serviceauthorization-element.md)</span></span>\
<span data-ttu-id="c3cf6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> authorizationPolicies**](authorizationpolicies.md)</span><span class="sxs-lookup"><span data-stu-id="c3cf6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<authorizationPolicies>**](authorizationpolicies.md)</span></span>\
<span data-ttu-id="c3cf6-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Agregar >**</span><span class="sxs-lookup"><span data-stu-id="c3cf6-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3cf6-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c3cf6-112">Syntax</span></span>  
  
```xml  
<authorizationPolicies>
  <add policyType="String" />
</authorizationPolicies>
```  
  
## <a name="type"></a><span data-ttu-id="c3cf6-113">Type</span><span class="sxs-lookup"><span data-stu-id="c3cf6-113">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c3cf6-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c3cf6-114">Attributes and Elements</span></span>  
 <span data-ttu-id="c3cf6-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c3cf6-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c3cf6-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="c3cf6-116">Attributes</span></span>  
  
|<span data-ttu-id="c3cf6-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="c3cf6-117">Attribute</span></span>|<span data-ttu-id="c3cf6-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c3cf6-118">Description</span></span>|  
|---------------|-----------------|  
|`policyType`|<span data-ttu-id="c3cf6-119">Atributo de cadena requerido.</span><span class="sxs-lookup"><span data-stu-id="c3cf6-119">A required String attribute.</span></span><br /><br /> <span data-ttu-id="c3cf6-120">El modelo de control de acceso de Windows Communication Foundation (WCF) admite el aprovisionamiento de un conjunto de directivas de autorización como tipos.</span><span class="sxs-lookup"><span data-stu-id="c3cf6-120">The Windows Communication Foundation (WCF) access control model supports provisioning a set of authorization policies as types.</span></span> <span data-ttu-id="c3cf6-121">Este atributo especifica una directiva de autorización que permite la transformación de un conjunto de notificaciones de entrada en otro conjunto de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="c3cf6-121">This attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="c3cf6-122">Se puede permitir o denegar el acceso en base a eso.</span><span class="sxs-lookup"><span data-stu-id="c3cf6-122">Access control can be granted or denied based on that.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c3cf6-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c3cf6-123">Child Elements</span></span>  
 <span data-ttu-id="c3cf6-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c3cf6-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c3cf6-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c3cf6-125">Parent Elements</span></span>  
  
|<span data-ttu-id="c3cf6-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="c3cf6-126">Element</span></span>|<span data-ttu-id="c3cf6-127">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c3cf6-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c3cf6-128">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="c3cf6-128">\<authorizationPolicies></span></span>](authorizationpolicies.md)|<span data-ttu-id="c3cf6-129">Especifica una colección de tipos de directiva de autorización.</span><span class="sxs-lookup"><span data-stu-id="c3cf6-129">Specifies a collection of authorization policy types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3cf6-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c3cf6-130">Remarks</span></span>  
 <span data-ttu-id="c3cf6-131">Cada directiva de autorización contiene un atributo `policyType` necesario único que es una cadena.</span><span class="sxs-lookup"><span data-stu-id="c3cf6-131">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="c3cf6-132">El atributo especifica una directiva de autorización que permite la transformación de un conjunto de demandas de entrada en otro conjunto de demandas.</span><span class="sxs-lookup"><span data-stu-id="c3cf6-132">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="c3cf6-133">Se puede permitir o denegar el acceso en base a eso.</span><span class="sxs-lookup"><span data-stu-id="c3cf6-133">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="c3cf6-134">Para obtener más información sobre cómo funciona una directiva de autorización <xref:System.IdentityModel.Policy.IAuthorizationPolicy> , vea y [Directiva de autorización](../../../wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="c3cf6-134">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3cf6-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3cf6-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="c3cf6-136">Autorización de acceso a operaciones de servicio</span><span class="sxs-lookup"><span data-stu-id="c3cf6-136">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="c3cf6-137">Procedimientos: Crear un administrador de autorización personalizado para un servicio</span><span class="sxs-lookup"><span data-stu-id="c3cf6-137">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="c3cf6-138">\<add></span><span class="sxs-lookup"><span data-stu-id="c3cf6-138">\<add></span></span>](add-of-authorizationpolicies.md)
- [<span data-ttu-id="c3cf6-139">Directiva de autorización</span><span class="sxs-lookup"><span data-stu-id="c3cf6-139">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)

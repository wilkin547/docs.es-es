---
description: 'Más información sobre: <add> de <authorizationPolicies>'
title: <add> de <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
ms.openlocfilehash: 616f09abfad51f41348b0ffa8557a4fd54492437
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99804106"
---
# <a name="add-of-authorizationpolicies"></a><span data-ttu-id="fb985-103">\<add> de \<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="fb985-103">\<add> of \<authorizationPolicies></span></span>

<span data-ttu-id="fb985-104">Especifica una directiva de autorización para la transformación de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="fb985-104">Specifies an authorization policy for claim transformation.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceAuthorization>**](serviceauthorization-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<authorizationPolicies>**](authorizationpolicies.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="fb985-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fb985-105">Syntax</span></span>  
  
```xml  
<authorizationPolicies>
  <add policyType="String" />
</authorizationPolicies>
```  
  
## <a name="type"></a><span data-ttu-id="fb985-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="fb985-106">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fb985-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fb985-107">Attributes and Elements</span></span>  

 <span data-ttu-id="fb985-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fb985-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fb985-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="fb985-109">Attributes</span></span>  
  
|<span data-ttu-id="fb985-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="fb985-110">Attribute</span></span>|<span data-ttu-id="fb985-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb985-111">Description</span></span>|  
|---------------|-----------------|  
|`policyType`|<span data-ttu-id="fb985-112">Atributo de cadena requerido.</span><span class="sxs-lookup"><span data-stu-id="fb985-112">A required String attribute.</span></span><br /><br /> <span data-ttu-id="fb985-113">El modelo de control de acceso de Windows Communication Foundation (WCF) admite el aprovisionamiento de un conjunto de directivas de autorización como tipos.</span><span class="sxs-lookup"><span data-stu-id="fb985-113">The Windows Communication Foundation (WCF) access control model supports provisioning a set of authorization policies as types.</span></span> <span data-ttu-id="fb985-114">Este atributo especifica una directiva de autorización que permite la transformación de un conjunto de notificaciones de entrada en otro conjunto de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="fb985-114">This attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="fb985-115">Se puede permitir o denegar el acceso en base a eso.</span><span class="sxs-lookup"><span data-stu-id="fb985-115">Access control can be granted or denied based on that.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fb985-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fb985-116">Child Elements</span></span>  

 <span data-ttu-id="fb985-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fb985-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fb985-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fb985-118">Parent Elements</span></span>  
  
|<span data-ttu-id="fb985-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="fb985-119">Element</span></span>|<span data-ttu-id="fb985-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb985-120">Description</span></span>|  
|-------------|-----------------|  
|[\<authorizationPolicies>](authorizationpolicies.md)|<span data-ttu-id="fb985-121">Especifica una colección de tipos de directiva de autorización.</span><span class="sxs-lookup"><span data-stu-id="fb985-121">Specifies a collection of authorization policy types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb985-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fb985-122">Remarks</span></span>  

 <span data-ttu-id="fb985-123">Cada directiva de autorización contiene un atributo `policyType` necesario único que es una cadena.</span><span class="sxs-lookup"><span data-stu-id="fb985-123">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="fb985-124">El atributo especifica una directiva de autorización que permite la transformación de un conjunto de demandas de entrada en otro conjunto de demandas.</span><span class="sxs-lookup"><span data-stu-id="fb985-124">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="fb985-125">Se puede permitir o denegar el acceso en base a eso.</span><span class="sxs-lookup"><span data-stu-id="fb985-125">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="fb985-126">Para obtener más información sobre cómo funciona una directiva de autorización, vea <xref:System.IdentityModel.Policy.IAuthorizationPolicy> y [Directiva de autorización](../../../wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="fb985-126">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb985-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb985-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="fb985-128">Autorización de acceso a operaciones de servicio</span><span class="sxs-lookup"><span data-stu-id="fb985-128">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="fb985-129">Procedimiento para crear un administrador de autorización personalizado para un servicio</span><span class="sxs-lookup"><span data-stu-id="fb985-129">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [\<add>](add-of-authorizationpolicies.md)
- [<span data-ttu-id="fb985-130">Directiva de autorización</span><span class="sxs-lookup"><span data-stu-id="fb985-130">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)

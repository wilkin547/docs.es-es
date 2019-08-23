---
title: <remove>del <claimTypeRequirements> elemento
ms.date: 03/30/2017
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
ms.openlocfilehash: 7238c253bfbc3224c8bbd31265e197dd35e56514
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934238"
---
# <a name="remove-of-claimtyperequirements-element"></a><span data-ttu-id="b0ca7-102">\<quitar > del \<elemento de > claimTypeRequirements</span><span class="sxs-lookup"><span data-stu-id="b0ca7-102">\<remove> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="b0ca7-103">Especifica los tipos de notificaciones que se van a quitar en la credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="b0ca7-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
 <span data-ttu-id="b0ca7-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b0ca7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b0ca7-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="b0ca7-105">\<bindings></span></span>  
<span data-ttu-id="b0ca7-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="b0ca7-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="b0ca7-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="b0ca7-107">\<binding></span></span>  
<span data-ttu-id="b0ca7-108">\<> de seguridad</span><span class="sxs-lookup"><span data-stu-id="b0ca7-108">\<security></span></span>  
<span data-ttu-id="b0ca7-109">\<message></span><span class="sxs-lookup"><span data-stu-id="b0ca7-109">\<message></span></span>  
<span data-ttu-id="b0ca7-110">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="b0ca7-110">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0ca7-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0ca7-111">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <remove claimType="URI" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0ca7-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b0ca7-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b0ca7-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b0ca7-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0ca7-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="b0ca7-114">Attributes</span></span>  
  
|<span data-ttu-id="b0ca7-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="b0ca7-115">Attribute</span></span>|<span data-ttu-id="b0ca7-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b0ca7-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b0ca7-117">claimType</span><span class="sxs-lookup"><span data-stu-id="b0ca7-117">claimType</span></span>|<span data-ttu-id="b0ca7-118">URI que define el tipo de una notificación que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="b0ca7-118">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0ca7-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b0ca7-119">Child Elements</span></span>  
 <span data-ttu-id="b0ca7-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b0ca7-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b0ca7-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b0ca7-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b0ca7-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="b0ca7-122">Element</span></span>|<span data-ttu-id="b0ca7-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b0ca7-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0ca7-124">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="b0ca7-124">\<claimTypeRequirements></span></span>](claimtyperequirements-for-message.md)|<span data-ttu-id="b0ca7-125">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="b0ca7-125">Specifies a collection of required claim types.</span></span> <span data-ttu-id="b0ca7-126">Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="b0ca7-126">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="b0ca7-127">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="b0ca7-127">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="b0ca7-128">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="b0ca7-128">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="b0ca7-129">Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="b0ca7-129">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0ca7-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0ca7-130">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>

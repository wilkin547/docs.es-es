---
title: <clear> de <claimTypeRequirements> elemento
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: b20d5c1808bf41d1ecd6b3e3a61606ae45b0fbdd
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270347"
---
# <a name="clear-of-claimtyperequirements-element"></a><span data-ttu-id="7050c-102">\<Borrar > de \<claimTypeRequirements > elemento</span><span class="sxs-lookup"><span data-stu-id="7050c-102">\<clear> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="7050c-103">Especifica que se quiten todos los tipos de notificaciones en la credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="7050c-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="7050c-104">Esto asegura que la colección se inicia vacía.</span><span class="sxs-lookup"><span data-stu-id="7050c-104">This ensures that the collection starts empty.</span></span>  
  
 <span data-ttu-id="7050c-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7050c-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="7050c-106">\<bindings></span><span class="sxs-lookup"><span data-stu-id="7050c-106">\<bindings></span></span>  
<span data-ttu-id="7050c-107">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="7050c-107">\<wsFederatedBinding></span></span>  
<span data-ttu-id="7050c-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="7050c-108">\<binding></span></span>  
<span data-ttu-id="7050c-109">\<security></span><span class="sxs-lookup"><span data-stu-id="7050c-109">\<security></span></span>  
<span data-ttu-id="7050c-110">\<message></span><span class="sxs-lookup"><span data-stu-id="7050c-110">\<message></span></span>  
<span data-ttu-id="7050c-111">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="7050c-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7050c-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7050c-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7050c-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7050c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="7050c-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7050c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7050c-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="7050c-115">Attributes</span></span>  
 <span data-ttu-id="7050c-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7050c-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7050c-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7050c-117">Child Elements</span></span>  
 <span data-ttu-id="7050c-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7050c-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7050c-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7050c-119">Parent Elements</span></span>  
  
|<span data-ttu-id="7050c-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="7050c-120">Element</span></span>|<span data-ttu-id="7050c-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="7050c-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7050c-122">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="7050c-122">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="7050c-123">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="7050c-123">Specifies a collection of required claim types.</span></span> <span data-ttu-id="7050c-124">Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="7050c-124">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="7050c-125">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="7050c-125">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="7050c-126">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="7050c-126">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="7050c-127">Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="7050c-127">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7050c-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="7050c-128">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>

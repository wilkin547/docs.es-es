---
title: '&lt;clear&gt; del elemento &lt;claimTypeRequirements&gt;'
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: c64e5450e01fdb011eb726f3bef1a85a5698d0d2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568340"
---
# <a name="ltcleargt-of-ltclaimtyperequirementsgt-element"></a><span data-ttu-id="1938d-102">&lt;clear&gt; del elemento &lt;claimTypeRequirements&gt;</span><span class="sxs-lookup"><span data-stu-id="1938d-102">&lt;clear&gt; of &lt;claimTypeRequirements&gt; element</span></span>
<span data-ttu-id="1938d-103">Especifica que se quiten todos los tipos de notificaciones en la credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="1938d-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="1938d-104">Esto asegura que la colección se inicia vacía.</span><span class="sxs-lookup"><span data-stu-id="1938d-104">This ensures that the collection starts empty.</span></span>  
  
 <span data-ttu-id="1938d-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1938d-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="1938d-106">\<bindings></span><span class="sxs-lookup"><span data-stu-id="1938d-106">\<bindings></span></span>  
<span data-ttu-id="1938d-107">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="1938d-107">\<wsFederatedBinding></span></span>  
<span data-ttu-id="1938d-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="1938d-108">\<binding></span></span>  
<span data-ttu-id="1938d-109">\<security></span><span class="sxs-lookup"><span data-stu-id="1938d-109">\<security></span></span>  
<span data-ttu-id="1938d-110">\<message></span><span class="sxs-lookup"><span data-stu-id="1938d-110">\<message></span></span>  
<span data-ttu-id="1938d-111">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="1938d-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1938d-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1938d-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1938d-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1938d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="1938d-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1938d-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1938d-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="1938d-115">Attributes</span></span>  
 <span data-ttu-id="1938d-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1938d-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1938d-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1938d-117">Child Elements</span></span>  
 <span data-ttu-id="1938d-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1938d-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1938d-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1938d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1938d-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="1938d-120">Element</span></span>|<span data-ttu-id="1938d-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="1938d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1938d-122">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="1938d-122">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="1938d-123">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="1938d-123">Specifies a collection of required claim types.</span></span> <span data-ttu-id="1938d-124">Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="1938d-124">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="1938d-125">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="1938d-125">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="1938d-126">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="1938d-126">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="1938d-127">Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="1938d-127">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1938d-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="1938d-128">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>

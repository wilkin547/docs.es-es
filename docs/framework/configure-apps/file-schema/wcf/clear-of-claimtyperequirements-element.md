---
title: '&lt;clear&gt; del elemento &lt;claimTypeRequirements&gt;'
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: ca8ea91f5806a6cedc98729de1c45ab6b5de6afb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747130"
---
# <a name="ltcleargt-of-ltclaimtyperequirementsgt-element"></a><span data-ttu-id="80d77-102">&lt;clear&gt; del elemento &lt;claimTypeRequirements&gt;</span><span class="sxs-lookup"><span data-stu-id="80d77-102">&lt;clear&gt; of &lt;claimTypeRequirements&gt; element</span></span>
<span data-ttu-id="80d77-103">Especifica que se quiten todos los tipos de notificaciones en la credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="80d77-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="80d77-104">Esto asegura que la colección se inicia vacía.</span><span class="sxs-lookup"><span data-stu-id="80d77-104">This ensures that the collection starts empty.</span></span>  
  
 <span data-ttu-id="80d77-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="80d77-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="80d77-106">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="80d77-106">\<bindings></span></span>  
<span data-ttu-id="80d77-107">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="80d77-107">\<wsFederatedBinding></span></span>  
<span data-ttu-id="80d77-108">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="80d77-108">\<binding></span></span>  
<span data-ttu-id="80d77-109">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="80d77-109">\<security></span></span>  
<span data-ttu-id="80d77-110">\<mensaje ></span><span class="sxs-lookup"><span data-stu-id="80d77-110">\<message></span></span>  
<span data-ttu-id="80d77-111">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="80d77-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80d77-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80d77-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>  
      <clear />  
</claimTypeRequirements>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80d77-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="80d77-113">Attributes and Elements</span></span>  
 <span data-ttu-id="80d77-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="80d77-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80d77-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="80d77-115">Attributes</span></span>  
 <span data-ttu-id="80d77-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="80d77-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="80d77-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="80d77-117">Child Elements</span></span>  
 <span data-ttu-id="80d77-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="80d77-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="80d77-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="80d77-119">Parent Elements</span></span>  
  
|<span data-ttu-id="80d77-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="80d77-120">Element</span></span>|<span data-ttu-id="80d77-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="80d77-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80d77-122">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="80d77-122">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="80d77-123">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="80d77-123">Specifies a collection of required claim types.</span></span> <span data-ttu-id="80d77-124">Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="80d77-124">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="80d77-125">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="80d77-125">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="80d77-126">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="80d77-126">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="80d77-127">Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="80d77-127">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="80d77-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="80d77-128">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>

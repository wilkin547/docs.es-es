---
title: '&lt;clear&gt; del elemento &lt;claimTypeRequirements&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9a5c3b101c51bcba1c1a579dcf99001c4b8dbab2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltcleargt-of-ltclaimtyperequirementsgt-element"></a><span data-ttu-id="7b43c-102">&lt;clear&gt; del elemento &lt;claimTypeRequirements&gt;</span><span class="sxs-lookup"><span data-stu-id="7b43c-102">&lt;clear&gt; of &lt;claimTypeRequirements&gt; element</span></span>
<span data-ttu-id="7b43c-103">Especifica que se quiten todos los tipos de notificaciones en la credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="7b43c-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="7b43c-104">Esto asegura que la colección se inicia vacía.</span><span class="sxs-lookup"><span data-stu-id="7b43c-104">This ensures that the collection starts empty.</span></span>  
  
 <span data-ttu-id="7b43c-105">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7b43c-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="7b43c-106">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="7b43c-106">\<bindings></span></span>  
<span data-ttu-id="7b43c-107">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="7b43c-107">\<wsFederatedBinding></span></span>  
<span data-ttu-id="7b43c-108">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="7b43c-108">\<binding></span></span>  
<span data-ttu-id="7b43c-109">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="7b43c-109">\<security></span></span>  
<span data-ttu-id="7b43c-110">\<mensaje ></span><span class="sxs-lookup"><span data-stu-id="7b43c-110">\<message></span></span>  
<span data-ttu-id="7b43c-111">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="7b43c-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b43c-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b43c-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>  
      <clear />  
</claimTypeRequirements>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b43c-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7b43c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="7b43c-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7b43c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b43c-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="7b43c-115">Attributes</span></span>  
 <span data-ttu-id="7b43c-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7b43c-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7b43c-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7b43c-117">Child Elements</span></span>  
 <span data-ttu-id="7b43c-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7b43c-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7b43c-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7b43c-119">Parent Elements</span></span>  
  
|<span data-ttu-id="7b43c-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="7b43c-120">Element</span></span>|<span data-ttu-id="7b43c-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="7b43c-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7b43c-122">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="7b43c-122">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="7b43c-123">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="7b43c-123">Specifies a collection of required claim types.</span></span> <span data-ttu-id="7b43c-124">Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="7b43c-124">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="7b43c-125">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="7b43c-125">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="7b43c-126">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="7b43c-126">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="7b43c-127">Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="7b43c-127">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7b43c-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b43c-128">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>

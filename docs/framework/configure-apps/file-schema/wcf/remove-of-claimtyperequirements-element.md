---
title: '&lt;remove&gt; del elemento &lt;claimTypeRequirements&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 49009cb7e988c27ccc426e29c6ac973e553a0f73
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltremovegt-of-ltclaimtyperequirementsgt-element"></a><span data-ttu-id="96a72-102">&lt;remove&gt; del elemento &lt;claimTypeRequirements&gt;</span><span class="sxs-lookup"><span data-stu-id="96a72-102">&lt;remove&gt; of &lt;claimTypeRequirements&gt; element</span></span>
<span data-ttu-id="96a72-103">Especifica los tipos de notificaciones que se van a quitar en la credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="96a72-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
 <span data-ttu-id="96a72-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="96a72-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="96a72-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="96a72-105">\<bindings></span></span>  
<span data-ttu-id="96a72-106">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="96a72-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="96a72-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="96a72-107">\<binding></span></span>  
<span data-ttu-id="96a72-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="96a72-108">\<security></span></span>  
<span data-ttu-id="96a72-109">\<mensaje ></span><span class="sxs-lookup"><span data-stu-id="96a72-109">\<message></span></span>  
<span data-ttu-id="96a72-110">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="96a72-110">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96a72-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="96a72-111">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>  
      <remove claimType="URI" />  
</claimTypeRequirements>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="96a72-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="96a72-112">Attributes and Elements</span></span>  
 <span data-ttu-id="96a72-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="96a72-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="96a72-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="96a72-114">Attributes</span></span>  
  
|<span data-ttu-id="96a72-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="96a72-115">Attribute</span></span>|<span data-ttu-id="96a72-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="96a72-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="96a72-117">claimType</span><span class="sxs-lookup"><span data-stu-id="96a72-117">claimType</span></span>|<span data-ttu-id="96a72-118">URI que define el tipo de una notificación que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="96a72-118">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="96a72-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="96a72-119">Child Elements</span></span>  
 <span data-ttu-id="96a72-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="96a72-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="96a72-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="96a72-121">Parent Elements</span></span>  
  
|<span data-ttu-id="96a72-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="96a72-122">Element</span></span>|<span data-ttu-id="96a72-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="96a72-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="96a72-124">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="96a72-124">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="96a72-125">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="96a72-125">Specifies a collection of required claim types.</span></span> <span data-ttu-id="96a72-126">Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="96a72-126">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="96a72-127">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="96a72-127">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="96a72-128">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="96a72-128">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="96a72-129">Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="96a72-129">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="96a72-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="96a72-130">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>

---
title: '&lt;serviceTimeouts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f6d2940a4c4615a922efcc74802a82adbe10267c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltservicetimeoutsgt"></a><span data-ttu-id="97ec5-102">&lt;serviceTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="97ec5-102">&lt;serviceTimeouts&gt;</span></span>
<span data-ttu-id="97ec5-103">Especifica el tiempo de espera para un servicio.</span><span class="sxs-lookup"><span data-stu-id="97ec5-103">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="97ec5-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="97ec5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="97ec5-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="97ec5-105">\<behaviors></span></span>  
<span data-ttu-id="97ec5-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="97ec5-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="97ec5-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="97ec5-107">\<behavior></span></span>  
<span data-ttu-id="97ec5-108">\<serviceTimeouts ></span><span class="sxs-lookup"><span data-stu-id="97ec5-108">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97ec5-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="97ec5-109">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />  
```  
  
## <a name="type"></a><span data-ttu-id="97ec5-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="97ec5-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97ec5-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="97ec5-111">Attributes and Elements</span></span>  
 <span data-ttu-id="97ec5-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="97ec5-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97ec5-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="97ec5-113">Attributes</span></span>  
  
|<span data-ttu-id="97ec5-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="97ec5-114">Attribute</span></span>|<span data-ttu-id="97ec5-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="97ec5-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="97ec5-116">Valor <xref:System.TimeSpan> que especifica el intervalo de tiempo que una transacción debe fluir del cliente al servidor.</span><span class="sxs-lookup"><span data-stu-id="97ec5-116">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="97ec5-117">El valor predeterminado es "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="97ec5-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="97ec5-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="97ec5-118">Child Elements</span></span>  
 <span data-ttu-id="97ec5-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="97ec5-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="97ec5-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="97ec5-120">Parent Elements</span></span>  
  
|<span data-ttu-id="97ec5-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="97ec5-121">Element</span></span>|<span data-ttu-id="97ec5-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="97ec5-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97ec5-123">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="97ec5-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="97ec5-124">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="97ec5-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="97ec5-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="97ec5-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>

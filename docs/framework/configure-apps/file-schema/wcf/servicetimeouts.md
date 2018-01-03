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
ms.workload: dotnet
ms.openlocfilehash: 0d8bfde535eb417614eee4ec6a2db7985152be33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltservicetimeoutsgt"></a><span data-ttu-id="238b6-102">&lt;serviceTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="238b6-102">&lt;serviceTimeouts&gt;</span></span>
<span data-ttu-id="238b6-103">Especifica el tiempo de espera para un servicio.</span><span class="sxs-lookup"><span data-stu-id="238b6-103">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="238b6-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="238b6-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="238b6-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="238b6-105">\<behaviors></span></span>  
<span data-ttu-id="238b6-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="238b6-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="238b6-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="238b6-107">\<behavior></span></span>  
<span data-ttu-id="238b6-108">\<serviceTimeouts ></span><span class="sxs-lookup"><span data-stu-id="238b6-108">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="238b6-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="238b6-109">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />  
```  
  
## <a name="type"></a><span data-ttu-id="238b6-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="238b6-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="238b6-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="238b6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="238b6-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="238b6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="238b6-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="238b6-113">Attributes</span></span>  
  
|<span data-ttu-id="238b6-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="238b6-114">Attribute</span></span>|<span data-ttu-id="238b6-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="238b6-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="238b6-116">Valor <xref:System.TimeSpan> que especifica el intervalo de tiempo que una transacción debe fluir del cliente al servidor.</span><span class="sxs-lookup"><span data-stu-id="238b6-116">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="238b6-117">El valor predeterminado es "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="238b6-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="238b6-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="238b6-118">Child Elements</span></span>  
 <span data-ttu-id="238b6-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="238b6-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="238b6-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="238b6-120">Parent Elements</span></span>  
  
|<span data-ttu-id="238b6-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="238b6-121">Element</span></span>|<span data-ttu-id="238b6-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="238b6-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="238b6-123">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="238b6-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="238b6-124">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="238b6-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="238b6-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="238b6-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>

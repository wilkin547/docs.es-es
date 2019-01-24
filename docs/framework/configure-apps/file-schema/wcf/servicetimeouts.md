---
title: '&lt;serviceTimeouts&gt;'
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: f7aa623ee387f67f3bbff32249d3695049359cde
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54524473"
---
# <a name="ltservicetimeoutsgt"></a><span data-ttu-id="71a7a-102">&lt;serviceTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="71a7a-102">&lt;serviceTimeouts&gt;</span></span>
<span data-ttu-id="71a7a-103">Especifica el tiempo de espera para un servicio.</span><span class="sxs-lookup"><span data-stu-id="71a7a-103">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="71a7a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="71a7a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="71a7a-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="71a7a-105">\<behaviors></span></span>  
<span data-ttu-id="71a7a-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="71a7a-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="71a7a-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="71a7a-107">\<behavior></span></span>  
<span data-ttu-id="71a7a-108">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="71a7a-108">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71a7a-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="71a7a-109">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="71a7a-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="71a7a-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71a7a-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="71a7a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="71a7a-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="71a7a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71a7a-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="71a7a-113">Attributes</span></span>  
  
|<span data-ttu-id="71a7a-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="71a7a-114">Attribute</span></span>|<span data-ttu-id="71a7a-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="71a7a-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="71a7a-116">Valor <xref:System.TimeSpan> que especifica el intervalo de tiempo que una transacción debe fluir del cliente al servidor.</span><span class="sxs-lookup"><span data-stu-id="71a7a-116">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="71a7a-117">El valor predeterminado es "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="71a7a-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71a7a-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="71a7a-118">Child Elements</span></span>  
 <span data-ttu-id="71a7a-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="71a7a-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="71a7a-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="71a7a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="71a7a-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="71a7a-121">Element</span></span>|<span data-ttu-id="71a7a-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="71a7a-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71a7a-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="71a7a-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="71a7a-124">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="71a7a-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="71a7a-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="71a7a-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>

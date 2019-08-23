---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: a1792fec4f86c9ac31107c043b976cfafcfa4c13
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937092"
---
# <a name="servicetimeouts"></a><span data-ttu-id="49977-101">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="49977-101">\<serviceTimeouts></span></span>
<span data-ttu-id="49977-102">Especifica el tiempo de espera para un servicio.</span><span class="sxs-lookup"><span data-stu-id="49977-102">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="49977-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="49977-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="49977-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="49977-104">\<behaviors></span></span>  
<span data-ttu-id="49977-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="49977-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="49977-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="49977-106">\<behavior></span></span>  
<span data-ttu-id="49977-107">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="49977-107">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49977-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="49977-108">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="49977-109">Type</span><span class="sxs-lookup"><span data-stu-id="49977-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="49977-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="49977-110">Attributes and Elements</span></span>  
 <span data-ttu-id="49977-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="49977-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="49977-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="49977-112">Attributes</span></span>  
  
|<span data-ttu-id="49977-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="49977-113">Attribute</span></span>|<span data-ttu-id="49977-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="49977-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="49977-115">Valor <xref:System.TimeSpan> que especifica el intervalo de tiempo que una transacción debe fluir del cliente al servidor.</span><span class="sxs-lookup"><span data-stu-id="49977-115">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="49977-116">El valor predeterminado es "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="49977-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="49977-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="49977-117">Child Elements</span></span>  
 <span data-ttu-id="49977-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="49977-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="49977-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="49977-119">Parent Elements</span></span>  
  
|<span data-ttu-id="49977-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="49977-120">Element</span></span>|<span data-ttu-id="49977-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="49977-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="49977-122">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="49977-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="49977-123">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="49977-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="49977-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="49977-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>

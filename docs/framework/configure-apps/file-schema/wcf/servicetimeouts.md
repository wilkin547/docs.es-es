---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 5c2f0ef7ad509eb5d6c686802c3fe5a75ea1a258
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075527"
---
# <a name="servicetimeouts"></a><span data-ttu-id="e5b15-101">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="e5b15-101">\<serviceTimeouts></span></span>
<span data-ttu-id="e5b15-102">Especifica el tiempo de espera para un servicio.</span><span class="sxs-lookup"><span data-stu-id="e5b15-102">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="e5b15-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e5b15-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="e5b15-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="e5b15-104">\<behaviors></span></span>  
<span data-ttu-id="e5b15-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="e5b15-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="e5b15-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="e5b15-106">\<behavior></span></span>  
<span data-ttu-id="e5b15-107">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="e5b15-107">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5b15-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5b15-108">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="e5b15-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="e5b15-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5b15-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e5b15-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e5b15-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e5b15-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5b15-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="e5b15-112">Attributes</span></span>  
  
|<span data-ttu-id="e5b15-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="e5b15-113">Attribute</span></span>|<span data-ttu-id="e5b15-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5b15-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="e5b15-115">Valor <xref:System.TimeSpan> que especifica el intervalo de tiempo que una transacción debe fluir del cliente al servidor.</span><span class="sxs-lookup"><span data-stu-id="e5b15-115">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="e5b15-116">El valor predeterminado es "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="e5b15-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e5b15-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e5b15-117">Child Elements</span></span>  
 <span data-ttu-id="e5b15-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e5b15-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e5b15-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e5b15-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e5b15-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="e5b15-120">Element</span></span>|<span data-ttu-id="e5b15-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5b15-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5b15-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e5b15-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="e5b15-123">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="e5b15-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e5b15-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5b15-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>

---
title: '&lt;serviceTimeouts&gt;'
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 4cb4b4ae6fe01430989d9ee5f3d94b16778595aa
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148479"
---
# <a name="ltservicetimeoutsgt"></a><span data-ttu-id="54d16-102">&lt;serviceTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="54d16-102">&lt;serviceTimeouts&gt;</span></span>
<span data-ttu-id="54d16-103">Especifica el tiempo de espera para un servicio.</span><span class="sxs-lookup"><span data-stu-id="54d16-103">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="54d16-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="54d16-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="54d16-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="54d16-105">\<behaviors></span></span>  
<span data-ttu-id="54d16-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="54d16-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="54d16-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="54d16-107">\<behavior></span></span>  
<span data-ttu-id="54d16-108">\<serviceTimeouts ></span><span class="sxs-lookup"><span data-stu-id="54d16-108">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54d16-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54d16-109">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="54d16-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="54d16-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="54d16-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="54d16-111">Attributes and Elements</span></span>  
 <span data-ttu-id="54d16-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="54d16-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="54d16-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="54d16-113">Attributes</span></span>  
  
|<span data-ttu-id="54d16-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="54d16-114">Attribute</span></span>|<span data-ttu-id="54d16-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="54d16-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="54d16-116">Valor <xref:System.TimeSpan> que especifica el intervalo de tiempo que una transacción debe fluir del cliente al servidor.</span><span class="sxs-lookup"><span data-stu-id="54d16-116">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="54d16-117">El valor predeterminado es "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="54d16-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="54d16-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="54d16-118">Child Elements</span></span>  
 <span data-ttu-id="54d16-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="54d16-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="54d16-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="54d16-120">Parent Elements</span></span>  
  
|<span data-ttu-id="54d16-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="54d16-121">Element</span></span>|<span data-ttu-id="54d16-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="54d16-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54d16-123">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="54d16-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="54d16-124">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="54d16-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="54d16-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="54d16-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>

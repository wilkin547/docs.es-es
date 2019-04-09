---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 5c2f0ef7ad509eb5d6c686802c3fe5a75ea1a258
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075527"
---
# <a name="servicetimeouts"></a><span data-ttu-id="97ab9-101">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="97ab9-101">\<serviceTimeouts></span></span>
<span data-ttu-id="97ab9-102">Especifica el tiempo de espera para un servicio.</span><span class="sxs-lookup"><span data-stu-id="97ab9-102">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="97ab9-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="97ab9-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="97ab9-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="97ab9-104">\<behaviors></span></span>  
<span data-ttu-id="97ab9-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="97ab9-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="97ab9-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="97ab9-106">\<behavior></span></span>  
<span data-ttu-id="97ab9-107">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="97ab9-107">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97ab9-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="97ab9-108">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="97ab9-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="97ab9-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97ab9-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="97ab9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="97ab9-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="97ab9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97ab9-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="97ab9-112">Attributes</span></span>  
  
|<span data-ttu-id="97ab9-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="97ab9-113">Attribute</span></span>|<span data-ttu-id="97ab9-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="97ab9-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="97ab9-115">Valor <xref:System.TimeSpan> que especifica el intervalo de tiempo que una transacción debe fluir del cliente al servidor.</span><span class="sxs-lookup"><span data-stu-id="97ab9-115">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="97ab9-116">El valor predeterminado es "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="97ab9-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="97ab9-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="97ab9-117">Child Elements</span></span>  
 <span data-ttu-id="97ab9-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="97ab9-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="97ab9-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="97ab9-119">Parent Elements</span></span>  
  
|<span data-ttu-id="97ab9-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="97ab9-120">Element</span></span>|<span data-ttu-id="97ab9-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="97ab9-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97ab9-122">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="97ab9-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="97ab9-123">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="97ab9-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="97ab9-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="97ab9-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>

---
title: '&lt;callbackTimeouts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e86b69b7d633fd99728936070e94da964e16de58
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltcallbacktimeoutsgt"></a><span data-ttu-id="4ee81-102">&lt;callbackTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="4ee81-102">&lt;callbackTimeouts&gt;</span></span>
<span data-ttu-id="4ee81-103">Especifica el valor de tiempo de espera cuando fluyen transacciones desde servidor al cliente en un escenario delcontrato de devolución de llamada dúplex.</span><span class="sxs-lookup"><span data-stu-id="4ee81-103">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="4ee81-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4ee81-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4ee81-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="4ee81-105">\<behaviors></span></span>  
<span data-ttu-id="4ee81-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="4ee81-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="4ee81-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="4ee81-107">\<behavior></span></span>  
<span data-ttu-id="4ee81-108">\<callbackTimeOuts ></span><span class="sxs-lookup"><span data-stu-id="4ee81-108">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ee81-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ee81-109">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />  
```  
  
## <a name="type"></a><span data-ttu-id="4ee81-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="4ee81-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ee81-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4ee81-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4ee81-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4ee81-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ee81-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="4ee81-113">Attributes</span></span>  
  
|<span data-ttu-id="4ee81-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="4ee81-114">Attribute</span></span>|<span data-ttu-id="4ee81-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="4ee81-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="4ee81-116">Un valor <xref:System.TimeSpan> que especifica el intervalo de hora dentro del cual las transacciones deben completarse o finalizarse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4ee81-116">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="4ee81-117">El valor predeterminado es "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="4ee81-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ee81-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4ee81-118">Child Elements</span></span>  
 <span data-ttu-id="4ee81-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4ee81-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ee81-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4ee81-120">Parent Elements</span></span>  
  
|<span data-ttu-id="4ee81-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="4ee81-121">Element</span></span>|<span data-ttu-id="4ee81-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="4ee81-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ee81-123">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="4ee81-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="4ee81-124">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="4ee81-124">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4ee81-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ee81-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>

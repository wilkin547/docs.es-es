---
title: '&lt;synchronousReceive&gt; (elemento)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b630f5ad2fbf5e3f20667e0bd1b7ae711992dc18
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltsynchronousreceivegt-element"></a><span data-ttu-id="7adda-102">&lt;synchronousReceive&gt; (elemento)</span><span class="sxs-lookup"><span data-stu-id="7adda-102">&lt;synchronousReceive&gt; element</span></span>
<span data-ttu-id="7adda-103">Este elemento de configuración se usa para especificar el comportamiento del tiempo de ejecución para recibir mensajes en una aplicación de cliente o de servicio.</span><span class="sxs-lookup"><span data-stu-id="7adda-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="7adda-104">No tiene ningún atributo o elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="7adda-104">It does not have any attributes or child elements.</span></span>  
  
 <span data-ttu-id="7adda-105">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7adda-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="7adda-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="7adda-106">\<behaviors></span></span>  
<span data-ttu-id="7adda-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="7adda-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="7adda-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="7adda-108">\<behavior></span></span>  
<span data-ttu-id="7adda-109">\<synchronousReceive ></span><span class="sxs-lookup"><span data-stu-id="7adda-109">\<synchronousReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7adda-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7adda-110">Syntax</span></span>  
  
```xml  
<synchronousReceive />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7adda-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7adda-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7adda-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7adda-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7adda-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="7adda-113">Attributes</span></span>  
 <span data-ttu-id="7adda-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7adda-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7adda-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7adda-115">Child Elements</span></span>  
 <span data-ttu-id="7adda-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7adda-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7adda-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7adda-117">Parent Elements</span></span>  
  
|<span data-ttu-id="7adda-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="7adda-118">Element</span></span>|<span data-ttu-id="7adda-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="7adda-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7adda-120">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="7adda-120">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="7adda-121">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="7adda-121">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7adda-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7adda-122">Remarks</span></span>  
 <span data-ttu-id="7adda-123">Utilice este comportamiento para indicar a la escucha del canal que utilice un receptor sincrónico en lugar del valor predeterminado, asincrónico.</span><span class="sxs-lookup"><span data-stu-id="7adda-123">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="7adda-124"> emite un nuevo subproceso para bombear para cada canal aceptado.</span><span class="sxs-lookup"><span data-stu-id="7adda-124"> issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="7adda-125">Si hay muchos canales, cabe la posibilidad de quedarse sin subprocesos.</span><span class="sxs-lookup"><span data-stu-id="7adda-125">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7adda-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="7adda-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>  
 <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>

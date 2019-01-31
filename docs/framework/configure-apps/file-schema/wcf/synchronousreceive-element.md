---
title: <synchronousReceive> (elemento)
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: f4a8868304ebae9a7ed5e6afbfb14fb2116afc49
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278484"
---
# <a name="synchronousreceive-element"></a><span data-ttu-id="6ddf1-102">\<synchronousReceive > elemento</span><span class="sxs-lookup"><span data-stu-id="6ddf1-102">\<synchronousReceive> element</span></span>
<span data-ttu-id="6ddf1-103">Este elemento de configuración se usa para especificar el comportamiento del tiempo de ejecución para recibir mensajes en una aplicación de cliente o de servicio.</span><span class="sxs-lookup"><span data-stu-id="6ddf1-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="6ddf1-104">No tiene ningún atributo o elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="6ddf1-104">It does not have any attributes or child elements.</span></span>  
  
 <span data-ttu-id="6ddf1-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6ddf1-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="6ddf1-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="6ddf1-106">\<behaviors></span></span>  
<span data-ttu-id="6ddf1-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="6ddf1-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="6ddf1-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="6ddf1-108">\<behavior></span></span>  
<span data-ttu-id="6ddf1-109">\<synchronousReceive></span><span class="sxs-lookup"><span data-stu-id="6ddf1-109">\<synchronousReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ddf1-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ddf1-110">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6ddf1-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6ddf1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6ddf1-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6ddf1-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6ddf1-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="6ddf1-113">Attributes</span></span>  
 <span data-ttu-id="6ddf1-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6ddf1-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6ddf1-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6ddf1-115">Child Elements</span></span>  
 <span data-ttu-id="6ddf1-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6ddf1-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6ddf1-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6ddf1-117">Parent Elements</span></span>  
  
|<span data-ttu-id="6ddf1-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="6ddf1-118">Element</span></span>|<span data-ttu-id="6ddf1-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="6ddf1-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6ddf1-120">\<behavior></span><span class="sxs-lookup"><span data-stu-id="6ddf1-120">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="6ddf1-121">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="6ddf1-121">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ddf1-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6ddf1-122">Remarks</span></span>  
 <span data-ttu-id="6ddf1-123">Utilice este comportamiento para indicar a la escucha del canal que utilice un receptor sincrónico en lugar del valor predeterminado, asincrónico.</span><span class="sxs-lookup"><span data-stu-id="6ddf1-123">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="6ddf1-124">Windows Communication Foundation (WCF) emite un nuevo subproceso para bombear para cada canal aceptado.</span><span class="sxs-lookup"><span data-stu-id="6ddf1-124">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="6ddf1-125">Si hay muchos canales, cabe la posibilidad de quedarse sin subprocesos.</span><span class="sxs-lookup"><span data-stu-id="6ddf1-125">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ddf1-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ddf1-126">See also</span></span>
- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>

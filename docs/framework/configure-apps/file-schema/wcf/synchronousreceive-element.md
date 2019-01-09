---
title: '&lt;synchronousReceive&gt; (elemento)'
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: bc89470900e50e4d3e522682b39b20e21a66b284
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147387"
---
# <a name="ltsynchronousreceivegt-element"></a><span data-ttu-id="f9a4a-102">&lt;synchronousReceive&gt; (elemento)</span><span class="sxs-lookup"><span data-stu-id="f9a4a-102">&lt;synchronousReceive&gt; element</span></span>
<span data-ttu-id="f9a4a-103">Este elemento de configuración se usa para especificar el comportamiento del tiempo de ejecución para recibir mensajes en una aplicación de cliente o de servicio.</span><span class="sxs-lookup"><span data-stu-id="f9a4a-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="f9a4a-104">No tiene ningún atributo o elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="f9a4a-104">It does not have any attributes or child elements.</span></span>  
  
 <span data-ttu-id="f9a4a-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f9a4a-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="f9a4a-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="f9a4a-106">\<behaviors></span></span>  
<span data-ttu-id="f9a4a-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="f9a4a-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="f9a4a-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="f9a4a-108">\<behavior></span></span>  
<span data-ttu-id="f9a4a-109">\<synchronousReceive ></span><span class="sxs-lookup"><span data-stu-id="f9a4a-109">\<synchronousReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9a4a-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f9a4a-110">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9a4a-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f9a4a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f9a4a-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f9a4a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9a4a-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="f9a4a-113">Attributes</span></span>  
 <span data-ttu-id="f9a4a-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f9a4a-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f9a4a-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f9a4a-115">Child Elements</span></span>  
 <span data-ttu-id="f9a4a-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f9a4a-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f9a4a-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f9a4a-117">Parent Elements</span></span>  
  
|<span data-ttu-id="f9a4a-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="f9a4a-118">Element</span></span>|<span data-ttu-id="f9a4a-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="f9a4a-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9a4a-120">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="f9a4a-120">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="f9a4a-121">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="f9a4a-121">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9a4a-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f9a4a-122">Remarks</span></span>  
 <span data-ttu-id="f9a4a-123">Utilice este comportamiento para indicar a la escucha del canal que utilice un receptor sincrónico en lugar del valor predeterminado, asincrónico.</span><span class="sxs-lookup"><span data-stu-id="f9a4a-123">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="f9a4a-124">Windows Communication Foundation (WCF) emite un nuevo subproceso para bombear para cada canal aceptado.</span><span class="sxs-lookup"><span data-stu-id="f9a4a-124">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="f9a4a-125">Si hay muchos canales, cabe la posibilidad de quedarse sin subprocesos.</span><span class="sxs-lookup"><span data-stu-id="f9a4a-125">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9a4a-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9a4a-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>  
 <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>

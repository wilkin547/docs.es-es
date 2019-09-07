---
title: Elemento <synchronousReceive>
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: b3f4860be6b7edac776a1c30611271b2eb36968e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399497"
---
# <a name="synchronousreceive-element"></a><span data-ttu-id="e5a72-102">\<synchronousReceive >, elemento</span><span class="sxs-lookup"><span data-stu-id="e5a72-102">\<synchronousReceive> element</span></span>
<span data-ttu-id="e5a72-103">Este elemento de configuración se usa para especificar el comportamiento del tiempo de ejecución para recibir mensajes en una aplicación de cliente o de servicio.</span><span class="sxs-lookup"><span data-stu-id="e5a72-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="e5a72-104">No tiene ningún atributo o elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="e5a72-104">It does not have any attributes or child elements.</span></span>  
  
<span data-ttu-id="e5a72-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e5a72-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e5a72-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e5a72-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e5a72-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e5a72-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="e5a72-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e5a72-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="e5a72-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e5a72-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="e5a72-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> synchronousReceive**</span><span class="sxs-lookup"><span data-stu-id="e5a72-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<synchronousReceive>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5a72-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5a72-111">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5a72-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e5a72-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e5a72-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e5a72-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5a72-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="e5a72-114">Attributes</span></span>  
 <span data-ttu-id="e5a72-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e5a72-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e5a72-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e5a72-116">Child Elements</span></span>  
 <span data-ttu-id="e5a72-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e5a72-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e5a72-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e5a72-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e5a72-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="e5a72-119">Element</span></span>|<span data-ttu-id="e5a72-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e5a72-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5a72-121">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="e5a72-121">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="e5a72-122">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="e5a72-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5a72-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e5a72-123">Remarks</span></span>  
 <span data-ttu-id="e5a72-124">Utilice este comportamiento para indicar a la escucha del canal que utilice un receptor sincrónico en lugar del valor predeterminado, asincrónico.</span><span class="sxs-lookup"><span data-stu-id="e5a72-124">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="e5a72-125">Windows Communication Foundation (WCF) emite un nuevo subproceso para bombear cada canal aceptado.</span><span class="sxs-lookup"><span data-stu-id="e5a72-125">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="e5a72-126">Si hay muchos canales, cabe la posibilidad de quedarse sin subprocesos.</span><span class="sxs-lookup"><span data-stu-id="e5a72-126">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5a72-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5a72-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>

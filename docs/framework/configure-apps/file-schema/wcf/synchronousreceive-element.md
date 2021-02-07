---
description: 'Más información acerca de: <synchronousReceive> elemento'
title: <synchronousReceive> (elemento)
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: afcd10b4ad41bd6ff12dbf246f66ef7fac4e759a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682623"
---
# <a name="synchronousreceive-element"></a><span data-ttu-id="4cdd4-103">Elemento \<synchronousReceive></span><span class="sxs-lookup"><span data-stu-id="4cdd4-103">\<synchronousReceive> element</span></span>

<span data-ttu-id="4cdd4-104">Este elemento de configuración se usa para especificar el comportamiento del tiempo de ejecución para recibir mensajes en una aplicación de cliente o de servicio.</span><span class="sxs-lookup"><span data-stu-id="4cdd4-104">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="4cdd4-105">No tiene ningún atributo o elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="4cdd4-105">It does not have any attributes or child elements.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<synchronousReceive>**  
  
## <a name="syntax"></a><span data-ttu-id="4cdd4-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4cdd4-106">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4cdd4-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4cdd4-107">Attributes and Elements</span></span>  

 <span data-ttu-id="4cdd4-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4cdd4-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4cdd4-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="4cdd4-109">Attributes</span></span>  

 <span data-ttu-id="4cdd4-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4cdd4-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4cdd4-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4cdd4-111">Child Elements</span></span>  

 <span data-ttu-id="4cdd4-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4cdd4-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4cdd4-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4cdd4-113">Parent Elements</span></span>  
  
|<span data-ttu-id="4cdd4-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="4cdd4-114">Element</span></span>|<span data-ttu-id="4cdd4-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="4cdd4-115">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="4cdd4-116">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="4cdd4-116">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4cdd4-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4cdd4-117">Remarks</span></span>  

 <span data-ttu-id="4cdd4-118">Utilice este comportamiento para indicar a la escucha del canal que utilice un receptor sincrónico en lugar del valor predeterminado, asincrónico.</span><span class="sxs-lookup"><span data-stu-id="4cdd4-118">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="4cdd4-119">Windows Communication Foundation (WCF) emite un nuevo subproceso para bombear cada canal aceptado.</span><span class="sxs-lookup"><span data-stu-id="4cdd4-119">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="4cdd4-120">Si hay muchos canales, cabe la posibilidad de quedarse sin subprocesos.</span><span class="sxs-lookup"><span data-stu-id="4cdd4-120">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cdd4-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="4cdd4-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>

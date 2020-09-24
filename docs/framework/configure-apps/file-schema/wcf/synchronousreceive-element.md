---
title: <synchronousReceive> (elemento)
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: 2073d115dd87d513a6e48b8b585fed4b49d5bb32
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157179"
---
# <a name="synchronousreceive-element"></a><span data-ttu-id="593da-102">Elemento \<synchronousReceive></span><span class="sxs-lookup"><span data-stu-id="593da-102">\<synchronousReceive> element</span></span>

<span data-ttu-id="593da-103">Este elemento de configuración se usa para especificar el comportamiento del tiempo de ejecución para recibir mensajes en una aplicación de cliente o de servicio.</span><span class="sxs-lookup"><span data-stu-id="593da-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="593da-104">No tiene ningún atributo o elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="593da-104">It does not have any attributes or child elements.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<synchronousReceive>**  
  
## <a name="syntax"></a><span data-ttu-id="593da-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="593da-105">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="593da-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="593da-106">Attributes and Elements</span></span>  

 <span data-ttu-id="593da-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="593da-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="593da-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="593da-108">Attributes</span></span>  

 <span data-ttu-id="593da-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="593da-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="593da-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="593da-110">Child Elements</span></span>  

 <span data-ttu-id="593da-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="593da-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="593da-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="593da-112">Parent Elements</span></span>  
  
|<span data-ttu-id="593da-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="593da-113">Element</span></span>|<span data-ttu-id="593da-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="593da-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="593da-115">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="593da-115">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="593da-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="593da-116">Remarks</span></span>  

 <span data-ttu-id="593da-117">Utilice este comportamiento para indicar a la escucha del canal que utilice un receptor sincrónico en lugar del valor predeterminado, asincrónico.</span><span class="sxs-lookup"><span data-stu-id="593da-117">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="593da-118">Windows Communication Foundation (WCF) emite un nuevo subproceso para bombear cada canal aceptado.</span><span class="sxs-lookup"><span data-stu-id="593da-118">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="593da-119">Si hay muchos canales, cabe la posibilidad de quedarse sin subprocesos.</span><span class="sxs-lookup"><span data-stu-id="593da-119">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="593da-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="593da-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>

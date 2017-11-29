---
title: '&lt;bufferReceive&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 623ff924e171282c399bddcdc212a0606a3416d6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltbufferreceivegt"></a><span data-ttu-id="68c51-102">&lt;bufferReceive&gt;</span><span class="sxs-lookup"><span data-stu-id="68c51-102">&lt;bufferReceive&gt;</span></span>
<span data-ttu-id="68c51-103">Un comportamiento del servicio que permite a un servicio usar procesamiento de recepción almacenado en búfer, lo que permite que un servicio de flujo de trabajo procese mensajes desordenados.</span><span class="sxs-lookup"><span data-stu-id="68c51-103">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="68c51-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="68c51-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="68c51-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="68c51-105">\<behaviors></span></span>  
<span data-ttu-id="68c51-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="68c51-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="68c51-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="68c51-107">\<behavior></span></span>  
<span data-ttu-id="68c51-108">\<bufferReceive ></span><span class="sxs-lookup"><span data-stu-id="68c51-108">\<bufferReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68c51-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="68c51-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="68c51-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="68c51-110">Attributes and Elements</span></span>  
 <span data-ttu-id="68c51-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="68c51-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="68c51-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="68c51-112">Attributes</span></span>  
  
|<span data-ttu-id="68c51-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="68c51-113">Attribute</span></span>|<span data-ttu-id="68c51-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="68c51-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="68c51-115">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="68c51-115">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="68c51-116">Un entero que especifica el número máximo de mensajes pendientes permitido en cada canal.</span><span class="sxs-lookup"><span data-stu-id="68c51-116">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="68c51-117">El valor predeterminado es 512.</span><span class="sxs-lookup"><span data-stu-id="68c51-117">The default value is 512.</span></span> <span data-ttu-id="68c51-118">Esta propiedad limita el número de mensajes desordenados que pueden recibirse en un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="68c51-118">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="68c51-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="68c51-119">Child Elements</span></span>  
 <span data-ttu-id="68c51-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="68c51-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="68c51-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="68c51-121">Parent Elements</span></span>  
  
|<span data-ttu-id="68c51-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="68c51-122">Element</span></span>|<span data-ttu-id="68c51-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="68c51-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68c51-124">\<comportamiento > de \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="68c51-124">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="68c51-125">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="68c51-125">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="68c51-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="68c51-126">See Also</span></span>  
<!-- <xref:System.ServiceModel.Activities.Description.BufferReceiveServiceBehavior>  -->
 <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>

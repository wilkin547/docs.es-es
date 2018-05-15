---
title: '&lt;bufferReceive&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: 07d5b66b14d9495808f972734cdce4476efaefde
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltbufferreceivegt"></a><span data-ttu-id="2ad24-102">&lt;bufferReceive&gt;</span><span class="sxs-lookup"><span data-stu-id="2ad24-102">&lt;bufferReceive&gt;</span></span>
<span data-ttu-id="2ad24-103">Un comportamiento del servicio que permite a un servicio usar procesamiento de recepción almacenado en búfer, lo que permite que un servicio de flujo de trabajo procese mensajes desordenados.</span><span class="sxs-lookup"><span data-stu-id="2ad24-103">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="2ad24-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2ad24-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2ad24-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="2ad24-105">\<behaviors></span></span>  
<span data-ttu-id="2ad24-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="2ad24-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="2ad24-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="2ad24-107">\<behavior></span></span>  
<span data-ttu-id="2ad24-108">\<bufferReceive ></span><span class="sxs-lookup"><span data-stu-id="2ad24-108">\<bufferReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ad24-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ad24-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ad24-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2ad24-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2ad24-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2ad24-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ad24-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="2ad24-112">Attributes</span></span>  
  
|<span data-ttu-id="2ad24-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="2ad24-113">Attribute</span></span>|<span data-ttu-id="2ad24-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="2ad24-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2ad24-115">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="2ad24-115">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="2ad24-116">Un entero que especifica el número máximo de mensajes pendientes permitido en cada canal.</span><span class="sxs-lookup"><span data-stu-id="2ad24-116">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="2ad24-117">El valor predeterminado es 512.</span><span class="sxs-lookup"><span data-stu-id="2ad24-117">The default value is 512.</span></span> <span data-ttu-id="2ad24-118">Esta propiedad limita el número de mensajes desordenados que pueden recibirse en un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2ad24-118">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ad24-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2ad24-119">Child Elements</span></span>  
 <span data-ttu-id="2ad24-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2ad24-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2ad24-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2ad24-121">Parent Elements</span></span>  
  
|<span data-ttu-id="2ad24-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="2ad24-122">Element</span></span>|<span data-ttu-id="2ad24-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="2ad24-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ad24-124">\<comportamiento > de \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="2ad24-124">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="2ad24-125">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="2ad24-125">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2ad24-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ad24-126">See Also</span></span>  
<!-- <xref:System.ServiceModel.Activities.Description.BufferReceiveServiceBehavior>  -->
 <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>

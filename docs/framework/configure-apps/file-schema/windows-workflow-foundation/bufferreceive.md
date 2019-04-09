---
title: <bufferReceive>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: 360d26fda964fa33640e833ad22dab7e06e153f6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203163"
---
# <a name="bufferreceive"></a><span data-ttu-id="37fbe-101">\<bufferReceive></span><span class="sxs-lookup"><span data-stu-id="37fbe-101">\<bufferReceive></span></span>
<span data-ttu-id="37fbe-102">Un comportamiento del servicio que permite a un servicio usar procesamiento de recepción almacenado en búfer, lo que permite que un servicio de flujo de trabajo procese mensajes desordenados.</span><span class="sxs-lookup"><span data-stu-id="37fbe-102">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="37fbe-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="37fbe-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="37fbe-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="37fbe-104">\<behaviors></span></span>  
<span data-ttu-id="37fbe-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="37fbe-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="37fbe-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="37fbe-106">\<behavior></span></span>  
<span data-ttu-id="37fbe-107">\<bufferReceive></span><span class="sxs-lookup"><span data-stu-id="37fbe-107">\<bufferReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37fbe-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37fbe-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="37fbe-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="37fbe-109">Attributes and Elements</span></span>  
 <span data-ttu-id="37fbe-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="37fbe-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="37fbe-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="37fbe-111">Attributes</span></span>  
  
|<span data-ttu-id="37fbe-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="37fbe-112">Attribute</span></span>|<span data-ttu-id="37fbe-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="37fbe-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="37fbe-114">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="37fbe-114">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="37fbe-115">Un entero que especifica el número máximo de mensajes pendientes permitido en cada canal.</span><span class="sxs-lookup"><span data-stu-id="37fbe-115">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="37fbe-116">El valor predeterminado es 512.</span><span class="sxs-lookup"><span data-stu-id="37fbe-116">The default value is 512.</span></span> <span data-ttu-id="37fbe-117">Esta propiedad limita el número de mensajes desordenados que pueden recibirse en un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="37fbe-117">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="37fbe-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="37fbe-118">Child Elements</span></span>  
 <span data-ttu-id="37fbe-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="37fbe-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="37fbe-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="37fbe-120">Parent Elements</span></span>  
  
|<span data-ttu-id="37fbe-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="37fbe-121">Element</span></span>|<span data-ttu-id="37fbe-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="37fbe-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="37fbe-123">\<comportamiento > de \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="37fbe-123">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="37fbe-124">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="37fbe-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="37fbe-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="37fbe-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.BufferedReceiveServiceBehavior>
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>

---
title: '&lt;bufferReceive&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: 507d58f852544c0eadcefaf997b2345d5e123cfa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607519"
---
# <a name="ltbufferreceivegt"></a><span data-ttu-id="9cddb-102">&lt;bufferReceive&gt;</span><span class="sxs-lookup"><span data-stu-id="9cddb-102">&lt;bufferReceive&gt;</span></span>
<span data-ttu-id="9cddb-103">Un comportamiento del servicio que permite a un servicio usar procesamiento de recepción almacenado en búfer, lo que permite que un servicio de flujo de trabajo procese mensajes desordenados.</span><span class="sxs-lookup"><span data-stu-id="9cddb-103">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="9cddb-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9cddb-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9cddb-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="9cddb-105">\<behaviors></span></span>  
<span data-ttu-id="9cddb-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="9cddb-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="9cddb-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="9cddb-107">\<behavior></span></span>  
<span data-ttu-id="9cddb-108">\<bufferReceive></span><span class="sxs-lookup"><span data-stu-id="9cddb-108">\<bufferReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cddb-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9cddb-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9cddb-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9cddb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9cddb-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9cddb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9cddb-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="9cddb-112">Attributes</span></span>  
  
|<span data-ttu-id="9cddb-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="9cddb-113">Attribute</span></span>|<span data-ttu-id="9cddb-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="9cddb-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9cddb-115">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="9cddb-115">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="9cddb-116">Un entero que especifica el número máximo de mensajes pendientes permitido en cada canal.</span><span class="sxs-lookup"><span data-stu-id="9cddb-116">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="9cddb-117">El valor predeterminado es 512.</span><span class="sxs-lookup"><span data-stu-id="9cddb-117">The default value is 512.</span></span> <span data-ttu-id="9cddb-118">Esta propiedad limita el número de mensajes desordenados que pueden recibirse en un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9cddb-118">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9cddb-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9cddb-119">Child Elements</span></span>  
 <span data-ttu-id="9cddb-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9cddb-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9cddb-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9cddb-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9cddb-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="9cddb-122">Element</span></span>|<span data-ttu-id="9cddb-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="9cddb-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9cddb-124">\<comportamiento > de \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="9cddb-124">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="9cddb-125">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="9cddb-125">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9cddb-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="9cddb-126">See also</span></span>
<!-- <xref:System.ServiceModel.Activities.Description.BufferReceiveServiceBehavior>  -->
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>

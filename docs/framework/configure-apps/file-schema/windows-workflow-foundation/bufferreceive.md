---
title: <bufferReceive>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: be5173ea43c6f7fca7180a311885a26c889b12db
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398835"
---
# <a name="bufferreceive"></a><span data-ttu-id="260ac-101">\<bufferReceive></span><span class="sxs-lookup"><span data-stu-id="260ac-101">\<bufferReceive></span></span>
<span data-ttu-id="260ac-102">Un comportamiento del servicio que permite a un servicio usar procesamiento de recepción almacenado en búfer, lo que permite que un servicio de flujo de trabajo procese mensajes desordenados.</span><span class="sxs-lookup"><span data-stu-id="260ac-102">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="260ac-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="260ac-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="260ac-104">&nbsp;&nbsp;[ **\<integrado. > De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="260ac-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="260ac-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="260ac-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="260ac-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="260ac-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="260ac-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="260ac-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="260ac-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> bufferReceive**</span><span class="sxs-lookup"><span data-stu-id="260ac-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bufferReceive>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="260ac-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="260ac-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="260ac-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="260ac-110">Attributes and Elements</span></span>  
 <span data-ttu-id="260ac-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="260ac-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="260ac-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="260ac-112">Attributes</span></span>  
  
|<span data-ttu-id="260ac-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="260ac-113">Attribute</span></span>|<span data-ttu-id="260ac-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="260ac-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="260ac-115">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="260ac-115">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="260ac-116">Un entero que especifica el número máximo de mensajes pendientes permitido en cada canal.</span><span class="sxs-lookup"><span data-stu-id="260ac-116">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="260ac-117">El valor predeterminado es 512.</span><span class="sxs-lookup"><span data-stu-id="260ac-117">The default value is 512.</span></span> <span data-ttu-id="260ac-118">Esta propiedad limita el número de mensajes desordenados que pueden recibirse en un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="260ac-118">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="260ac-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="260ac-119">Child Elements</span></span>  
 <span data-ttu-id="260ac-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="260ac-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="260ac-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="260ac-121">Parent Elements</span></span>  
  
|<span data-ttu-id="260ac-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="260ac-122">Element</span></span>|<span data-ttu-id="260ac-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="260ac-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="260ac-124">\<comportamiento > de \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="260ac-124">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="260ac-125">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="260ac-125">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="260ac-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="260ac-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.BufferedReceiveServiceBehavior>
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>

---
description: 'Más información acerca de: <bufferReceive>'
title: <bufferReceive>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: 8f5e58e0e72a81d8b3a20a68e0890be907c20d2b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698094"
---
# \<bufferReceive>

<span data-ttu-id="366b1-102">Un comportamiento del servicio que permite a un servicio usar procesamiento de recepción almacenado en búfer, lo que permite que un servicio de flujo de trabajo procese mensajes desordenados.</span><span class="sxs-lookup"><span data-stu-id="366b1-102">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bufferReceive>**  
  
## <a name="syntax"></a><span data-ttu-id="366b1-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="366b1-103">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="366b1-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="366b1-104">Attributes and Elements</span></span>  

 <span data-ttu-id="366b1-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="366b1-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="366b1-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="366b1-106">Attributes</span></span>  
  
|<span data-ttu-id="366b1-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="366b1-107">Attribute</span></span>|<span data-ttu-id="366b1-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="366b1-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="366b1-109">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="366b1-109">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="366b1-110">Un entero que especifica el número máximo de mensajes pendientes permitido en cada canal.</span><span class="sxs-lookup"><span data-stu-id="366b1-110">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="366b1-111">El valor predeterminado es 512.</span><span class="sxs-lookup"><span data-stu-id="366b1-111">The default value is 512.</span></span> <span data-ttu-id="366b1-112">Esta propiedad limita el número de mensajes desordenados que pueden recibirse en un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="366b1-112">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="366b1-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="366b1-113">Child Elements</span></span>  

 <span data-ttu-id="366b1-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="366b1-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="366b1-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="366b1-115">Parent Elements</span></span>  
  
|<span data-ttu-id="366b1-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="366b1-116">Element</span></span>|<span data-ttu-id="366b1-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="366b1-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="366b1-118">\<behavior> de \<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="366b1-118">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="366b1-119">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="366b1-119">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="366b1-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="366b1-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.BufferedReceiveServiceBehavior>
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>

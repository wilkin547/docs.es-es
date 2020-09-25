---
title: <bufferReceive>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: 16d4546bce461b55695e0deed093396ce1c2b0b6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189570"
---
# \<bufferReceive>

<span data-ttu-id="66db1-101">Un comportamiento del servicio que permite a un servicio usar procesamiento de recepción almacenado en búfer, lo que permite que un servicio de flujo de trabajo procese mensajes desordenados.</span><span class="sxs-lookup"><span data-stu-id="66db1-101">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bufferReceive>**  
  
## <a name="syntax"></a><span data-ttu-id="66db1-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66db1-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="66db1-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="66db1-103">Attributes and Elements</span></span>  

 <span data-ttu-id="66db1-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="66db1-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="66db1-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="66db1-105">Attributes</span></span>  
  
|<span data-ttu-id="66db1-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="66db1-106">Attribute</span></span>|<span data-ttu-id="66db1-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="66db1-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="66db1-108">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="66db1-108">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="66db1-109">Un entero que especifica el número máximo de mensajes pendientes permitido en cada canal.</span><span class="sxs-lookup"><span data-stu-id="66db1-109">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="66db1-110">El valor predeterminado es 512.</span><span class="sxs-lookup"><span data-stu-id="66db1-110">The default value is 512.</span></span> <span data-ttu-id="66db1-111">Esta propiedad limita el número de mensajes desordenados que pueden recibirse en un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="66db1-111">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="66db1-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="66db1-112">Child Elements</span></span>  

 <span data-ttu-id="66db1-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="66db1-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="66db1-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="66db1-114">Parent Elements</span></span>  
  
|<span data-ttu-id="66db1-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="66db1-115">Element</span></span>|<span data-ttu-id="66db1-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="66db1-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="66db1-117">\<behavior> de \<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="66db1-117">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="66db1-118">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="66db1-118">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="66db1-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="66db1-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.BufferedReceiveServiceBehavior>
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>

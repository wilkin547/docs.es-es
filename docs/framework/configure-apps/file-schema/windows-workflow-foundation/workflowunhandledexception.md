---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: c46d1fb9eb853e57c7ad1b97eb9a22556cdfb7d8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913096"
---
# <a name="workflowunhandledexception"></a><span data-ttu-id="bd37e-101">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="bd37e-101">\<workflowUnhandledException></span></span>
<span data-ttu-id="bd37e-102">Un comportamiento del servicio que permite especificar la acción que debe emprenderse cuando se produce una excepción no controlada dentro de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bd37e-102">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="bd37e-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="bd37e-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="bd37e-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="bd37e-104">\<behaviors></span></span>  
<span data-ttu-id="bd37e-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="bd37e-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="bd37e-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="bd37e-106">\<behavior></span></span>  
<span data-ttu-id="bd37e-107">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="bd37e-107">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd37e-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd37e-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd37e-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bd37e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="bd37e-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bd37e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bd37e-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="bd37e-111">Attributes</span></span>  
  
|<span data-ttu-id="bd37e-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="bd37e-112">Attribute</span></span>|<span data-ttu-id="bd37e-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bd37e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bd37e-114">action</span><span class="sxs-lookup"><span data-stu-id="bd37e-114">action</span></span>|<span data-ttu-id="bd37e-115">Una cadena que especifica la acción que debe emprenderse cuando se produce una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="bd37e-115">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="bd37e-116">Este atributo es del tipo <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="bd37e-116">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bd37e-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bd37e-117">Child Elements</span></span>  
 <span data-ttu-id="bd37e-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bd37e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bd37e-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bd37e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="bd37e-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="bd37e-120">Element</span></span>|<span data-ttu-id="bd37e-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bd37e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd37e-122">\<comportamiento > de \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="bd37e-122">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="bd37e-123">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="bd37e-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd37e-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd37e-124">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>

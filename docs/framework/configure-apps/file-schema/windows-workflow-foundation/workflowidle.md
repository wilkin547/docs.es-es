---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: d9eb182ef9c35d2e4c6f5d434e6b200ae2e7ca26
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151850"
---
# <a name="workflowidle"></a><span data-ttu-id="fd899-101">\<workflowIdle></span><span class="sxs-lookup"><span data-stu-id="fd899-101">\<workflowIdle></span></span>
<span data-ttu-id="fd899-102">Un comportamiento del servicio que controla cuando las instancias de flujo de trabajo inactivas se descargan y conservan.</span><span class="sxs-lookup"><span data-stu-id="fd899-102">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="fd899-103">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fd899-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fd899-104">&nbsp;&nbsp;[**\<Sistema.>De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="fd899-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="fd899-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<comportamientos>**](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="fd899-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="fd899-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="fd899-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="fd899-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comportamiento>**](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="fd899-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="fd899-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowIdle>**</span><span class="sxs-lookup"><span data-stu-id="fd899-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowIdle>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd899-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd899-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowIdle timeToPersist="TimeSpan"
                    timeToUnload="TimeSpan" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd899-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fd899-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fd899-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fd899-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd899-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="fd899-112">Attributes</span></span>  
  
|<span data-ttu-id="fd899-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="fd899-113">Attribute</span></span>|<span data-ttu-id="fd899-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="fd899-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fd899-115">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="fd899-115">timeToPersist</span></span>|<span data-ttu-id="fd899-116">Un valor Timespan que especifica el tiempo que transcurre entre el momento en que el flujo de trabajo se vuelve inactivo y se conserva.</span><span class="sxs-lookup"><span data-stu-id="fd899-116">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="fd899-117">El valor predeterminado es TimeSpan.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="fd899-117">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="fd899-118">La duración comienza a transcurrir cuando la instancia de flujo de trabajo se vuelve inactiva.</span><span class="sxs-lookup"><span data-stu-id="fd899-118">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="fd899-119">Este atributo es útil si desea conservar de forma más agresiva una instancia de flujo de trabajo mientras se mantiene la instancia en memoria durante el máximo tiempo posible.</span><span class="sxs-lookup"><span data-stu-id="fd899-119">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="fd899-120">Este atributo solo es válido si su valor es menor que el atributo **timeToUnload.**</span><span class="sxs-lookup"><span data-stu-id="fd899-120">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="fd899-121">Si es mayor, se omite.</span><span class="sxs-lookup"><span data-stu-id="fd899-121">If it is greater, it is ignored.</span></span> <span data-ttu-id="fd899-122">Si este atributo transcurre antes del valor especificado por el atributo **timeToUnload,** la persistencia debe completarse antes de descargar el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fd899-122">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="fd899-123">Esto implica que se puede retrasar la operación de descarga hasta que se conserve el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fd899-123">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="fd899-124">El nivel de conservación es responsable de administrar todos los reintentos de errores transitorios y solo produce excepciones con errores no recuperables.</span><span class="sxs-lookup"><span data-stu-id="fd899-124">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="fd899-125">Por consiguiente, cualquier excepción producida durante la conservación se trata como grave y se anula la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fd899-125">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="fd899-126">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="fd899-126">timeToUnload</span></span>|<span data-ttu-id="fd899-127">Un valor Timespan que especifica el tiempo que transcurre entre el momento en que el flujo de trabajo se vuelve inactivo y descarga.</span><span class="sxs-lookup"><span data-stu-id="fd899-127">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="fd899-128">El valor predeterminado es 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="fd899-128">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="fd899-129">Descargar un flujo de trabajo implica que también se conserva.</span><span class="sxs-lookup"><span data-stu-id="fd899-129">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="fd899-130">Si este atributo se pone a cero, la instancia de flujo de trabajo se conserva y se descarga de inmediato en cuanto el flujo de trabajo se vuelve inactivo.</span><span class="sxs-lookup"><span data-stu-id="fd899-130">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="fd899-131">Al establecer este atributo en TimeSpan.MaxValue, se deshabilita de forma eficaz la operación de descarga.</span><span class="sxs-lookup"><span data-stu-id="fd899-131">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="fd899-132">Las instancias de flujo de trabajo inactivas nunca se descargan.</span><span class="sxs-lookup"><span data-stu-id="fd899-132">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fd899-133">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fd899-133">Child Elements</span></span>  
 <span data-ttu-id="fd899-134">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fd899-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fd899-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fd899-135">Parent Elements</span></span>  
  
|<span data-ttu-id="fd899-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="fd899-136">Element</span></span>|<span data-ttu-id="fd899-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="fd899-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fd899-138">\<comportamiento> \<de serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="fd899-138">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="fd899-139">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="fd899-139">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fd899-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fd899-140">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>

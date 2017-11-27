---
title: '&lt;workflowIdle&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5f9b4989de57204d9ec97d69475121c30ae82644
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltworkflowidlegt"></a><span data-ttu-id="57adc-102">&lt;workflowIdle&gt;</span><span class="sxs-lookup"><span data-stu-id="57adc-102">&lt;workflowIdle&gt;</span></span>
<span data-ttu-id="57adc-103">Un comportamiento del servicio que controla cuando las instancias de flujo de trabajo inactivas se descargan y conservan.</span><span class="sxs-lookup"><span data-stu-id="57adc-103">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="57adc-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="57adc-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="57adc-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="57adc-105">\<behaviors></span></span>  
<span data-ttu-id="57adc-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="57adc-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="57adc-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="57adc-107">\<behavior></span></span>  
<span data-ttu-id="57adc-108">\<workflowIdle ></span><span class="sxs-lookup"><span data-stu-id="57adc-108">\<workflowIdle></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57adc-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57adc-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="57adc-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="57adc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="57adc-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="57adc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="57adc-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="57adc-112">Attributes</span></span>  
  
|<span data-ttu-id="57adc-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="57adc-113">Attribute</span></span>|<span data-ttu-id="57adc-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="57adc-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="57adc-115">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="57adc-115">timeToPersist</span></span>|<span data-ttu-id="57adc-116">Un valor Timespan que especifica la duración entre el momento en el flujo de trabajo se vuelve inactivo y se conserva.</span><span class="sxs-lookup"><span data-stu-id="57adc-116">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="57adc-117">El valor predeterminado es TimeSpan.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="57adc-117">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="57adc-118">La duración comienza a transcurrir cuando la instancia de flujo de trabajo se vuelve inactiva.</span><span class="sxs-lookup"><span data-stu-id="57adc-118">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="57adc-119">Este atributo es útil si desea conservar una instancia de flujo de trabajo de una forma más agresiva mientras mantiene la instancia en memoria mientras sea posible.</span><span class="sxs-lookup"><span data-stu-id="57adc-119">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="57adc-120">Este atributo solo es válido si su valor es menor que el **timeToUnload** atributo.</span><span class="sxs-lookup"><span data-stu-id="57adc-120">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="57adc-121">Si es mayor, se omite.</span><span class="sxs-lookup"><span data-stu-id="57adc-121">If it is greater, it is ignored.</span></span> <span data-ttu-id="57adc-122">Si este atributo transcurre antes de que el valor especificado por el **timeToUnload** atributo, la persistencia deberá completarse antes de que se descarga el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="57adc-122">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="57adc-123">Esto implica que se puede retrasar la operación de descarga hasta que se conserve el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="57adc-123">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="57adc-124">El nivel de conservación es responsable de administrar todos los reintentos de errores transitorios y solo produce excepciones con errores no recuperables.</span><span class="sxs-lookup"><span data-stu-id="57adc-124">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="57adc-125">Por consiguiente, cualquier excepción producida durante la conservación se trata como grave y se anula la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="57adc-125">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="57adc-126">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="57adc-126">timeToUnload</span></span>|<span data-ttu-id="57adc-127">Un valor Timespan que especifica el tiempo que transcurre entre el momento en que el flujo de trabajo se vuelve inactivo y descarga.</span><span class="sxs-lookup"><span data-stu-id="57adc-127">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="57adc-128">El valor predeterminado es 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="57adc-128">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="57adc-129">Descargar un flujo de trabajo implica que también se conserva.</span><span class="sxs-lookup"><span data-stu-id="57adc-129">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="57adc-130">Si este atributo se establece en cero se conservan y se descargan inmediatamente después de la instancia de flujo de trabajo del flujo de trabajo se vuelve inactivo.</span><span class="sxs-lookup"><span data-stu-id="57adc-130">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="57adc-131">Establecer este atributo en TimeSpan.MaxValue eficazmente, deshabilita la operación de descarga.</span><span class="sxs-lookup"><span data-stu-id="57adc-131">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="57adc-132">Las instancias de flujo de trabajo inactivas nunca se descargan.</span><span class="sxs-lookup"><span data-stu-id="57adc-132">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="57adc-133">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="57adc-133">Child Elements</span></span>  
 <span data-ttu-id="57adc-134">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="57adc-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="57adc-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="57adc-135">Parent Elements</span></span>  
  
|<span data-ttu-id="57adc-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="57adc-136">Element</span></span>|<span data-ttu-id="57adc-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="57adc-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="57adc-138">\<comportamiento > de \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="57adc-138">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="57adc-139">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="57adc-139">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="57adc-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="57adc-140">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>

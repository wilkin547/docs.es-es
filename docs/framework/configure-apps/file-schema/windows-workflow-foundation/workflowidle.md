---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: 16a485b6d0ba2584cccd08a36506582fd3930f71
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947164"
---
# <a name="workflowidle"></a><span data-ttu-id="c21da-101">\<workflowIdle></span><span class="sxs-lookup"><span data-stu-id="c21da-101">\<workflowIdle></span></span>
<span data-ttu-id="c21da-102">Un comportamiento del servicio que controla cuando las instancias de flujo de trabajo inactivas se descargan y conservan.</span><span class="sxs-lookup"><span data-stu-id="c21da-102">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="c21da-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c21da-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="c21da-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="c21da-104">\<behaviors></span></span>  
<span data-ttu-id="c21da-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="c21da-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="c21da-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="c21da-106">\<behavior></span></span>  
<span data-ttu-id="c21da-107">\<workflowIdle></span><span class="sxs-lookup"><span data-stu-id="c21da-107">\<workflowIdle></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c21da-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c21da-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c21da-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c21da-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c21da-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c21da-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c21da-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="c21da-111">Attributes</span></span>  
  
|<span data-ttu-id="c21da-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="c21da-112">Attribute</span></span>|<span data-ttu-id="c21da-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c21da-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c21da-114">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="c21da-114">timeToPersist</span></span>|<span data-ttu-id="c21da-115">Valor TimeSpan que especifica la duración entre el momento en que el flujo de trabajo se vuelve inactivo y se conserva.</span><span class="sxs-lookup"><span data-stu-id="c21da-115">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="c21da-116">El valor predeterminado es TimeSpan. MaxValue.</span><span class="sxs-lookup"><span data-stu-id="c21da-116">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="c21da-117">La duración comienza a transcurrir cuando la instancia de flujo de trabajo se vuelve inactiva.</span><span class="sxs-lookup"><span data-stu-id="c21da-117">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="c21da-118">Este atributo es útil si desea conservar una instancia de flujo de trabajo más agresiva mientras mantiene la instancia en memoria durante el tiempo que sea posible.</span><span class="sxs-lookup"><span data-stu-id="c21da-118">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="c21da-119">Este atributo solo es válido si su valor es menor que el atributo **timeToUnload** .</span><span class="sxs-lookup"><span data-stu-id="c21da-119">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="c21da-120">Si es mayor, se omite.</span><span class="sxs-lookup"><span data-stu-id="c21da-120">If it is greater, it is ignored.</span></span> <span data-ttu-id="c21da-121">Si este atributo transcurre antes del valor especificado por el atributo **timeToUnload** , la persistencia debe completarse antes de que se descargue el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c21da-121">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="c21da-122">Esto implica que se puede retrasar la operación de descarga hasta que se conserve el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c21da-122">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="c21da-123">El nivel de conservación es responsable de administrar todos los reintentos de errores transitorios y solo produce excepciones con errores no recuperables.</span><span class="sxs-lookup"><span data-stu-id="c21da-123">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="c21da-124">Por consiguiente, cualquier excepción producida durante la conservación se trata como grave y se anula la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c21da-124">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="c21da-125">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="c21da-125">timeToUnload</span></span>|<span data-ttu-id="c21da-126">Un valor Timespan que especifica el tiempo que transcurre entre el momento en que el flujo de trabajo se vuelve inactivo y descarga.</span><span class="sxs-lookup"><span data-stu-id="c21da-126">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="c21da-127">El valor predeterminado es 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="c21da-127">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="c21da-128">Descargar un flujo de trabajo implica que también se conserva.</span><span class="sxs-lookup"><span data-stu-id="c21da-128">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="c21da-129">Si este atributo se establece en cero, la instancia de flujo de trabajo se conserva y se descarga inmediatamente después de que el flujo de trabajo se vuelva inactivo.</span><span class="sxs-lookup"><span data-stu-id="c21da-129">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="c21da-130">Si se establece este atributo en TimeSpan. MaxValue, se deshabilita la operación de descarga.</span><span class="sxs-lookup"><span data-stu-id="c21da-130">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="c21da-131">Las instancias de flujo de trabajo inactivas nunca se descargan.</span><span class="sxs-lookup"><span data-stu-id="c21da-131">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c21da-132">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c21da-132">Child Elements</span></span>  
 <span data-ttu-id="c21da-133">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c21da-133">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c21da-134">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c21da-134">Parent Elements</span></span>  
  
|<span data-ttu-id="c21da-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="c21da-135">Element</span></span>|<span data-ttu-id="c21da-136">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c21da-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c21da-137">\<comportamiento > de \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="c21da-137">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="c21da-138">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="c21da-138">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c21da-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="c21da-139">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>

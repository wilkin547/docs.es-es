---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: 1d8ddaf5d69d87ff6112b5cbb285f0ccfda724e2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397533"
---
# <a name="workflowidle"></a><span data-ttu-id="c1495-101">\<workflowIdle></span><span class="sxs-lookup"><span data-stu-id="c1495-101">\<workflowIdle></span></span>
<span data-ttu-id="c1495-102">Un comportamiento del servicio que controla cuando las instancias de flujo de trabajo inactivas se descargan y conservan.</span><span class="sxs-lookup"><span data-stu-id="c1495-102">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="c1495-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c1495-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c1495-104">&nbsp;&nbsp;[ **\<integrado. > De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="c1495-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="c1495-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="c1495-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="c1495-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="c1495-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="c1495-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="c1495-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="c1495-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> workflowIdle**</span><span class="sxs-lookup"><span data-stu-id="c1495-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowIdle>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1495-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1495-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1495-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c1495-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c1495-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c1495-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1495-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="c1495-112">Attributes</span></span>  
  
|<span data-ttu-id="c1495-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="c1495-113">Attribute</span></span>|<span data-ttu-id="c1495-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c1495-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c1495-115">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="c1495-115">timeToPersist</span></span>|<span data-ttu-id="c1495-116">Valor TimeSpan que especifica la duración entre el momento en que el flujo de trabajo se vuelve inactivo y se conserva.</span><span class="sxs-lookup"><span data-stu-id="c1495-116">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="c1495-117">El valor predeterminado es TimeSpan. MaxValue.</span><span class="sxs-lookup"><span data-stu-id="c1495-117">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="c1495-118">La duración comienza a transcurrir cuando la instancia de flujo de trabajo se vuelve inactiva.</span><span class="sxs-lookup"><span data-stu-id="c1495-118">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="c1495-119">Este atributo es útil si desea conservar una instancia de flujo de trabajo más agresiva mientras mantiene la instancia en memoria durante el tiempo que sea posible.</span><span class="sxs-lookup"><span data-stu-id="c1495-119">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="c1495-120">Este atributo solo es válido si su valor es menor que el atributo **timeToUnload** .</span><span class="sxs-lookup"><span data-stu-id="c1495-120">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="c1495-121">Si es mayor, se omite.</span><span class="sxs-lookup"><span data-stu-id="c1495-121">If it is greater, it is ignored.</span></span> <span data-ttu-id="c1495-122">Si este atributo transcurre antes del valor especificado por el atributo **timeToUnload** , la persistencia debe completarse antes de que se descargue el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c1495-122">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="c1495-123">Esto implica que se puede retrasar la operación de descarga hasta que se conserve el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c1495-123">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="c1495-124">El nivel de conservación es responsable de administrar todos los reintentos de errores transitorios y solo produce excepciones con errores no recuperables.</span><span class="sxs-lookup"><span data-stu-id="c1495-124">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="c1495-125">Por consiguiente, cualquier excepción producida durante la conservación se trata como grave y se anula la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c1495-125">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="c1495-126">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="c1495-126">timeToUnload</span></span>|<span data-ttu-id="c1495-127">Un valor Timespan que especifica el tiempo que transcurre entre el momento en que el flujo de trabajo se vuelve inactivo y descarga.</span><span class="sxs-lookup"><span data-stu-id="c1495-127">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="c1495-128">El valor predeterminado es 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="c1495-128">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="c1495-129">Descargar un flujo de trabajo implica que también se conserva.</span><span class="sxs-lookup"><span data-stu-id="c1495-129">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="c1495-130">Si este atributo se establece en cero, la instancia de flujo de trabajo se conserva y se descarga inmediatamente después de que el flujo de trabajo se vuelva inactivo.</span><span class="sxs-lookup"><span data-stu-id="c1495-130">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="c1495-131">Si se establece este atributo en TimeSpan. MaxValue, se deshabilita la operación de descarga.</span><span class="sxs-lookup"><span data-stu-id="c1495-131">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="c1495-132">Las instancias de flujo de trabajo inactivas nunca se descargan.</span><span class="sxs-lookup"><span data-stu-id="c1495-132">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c1495-133">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c1495-133">Child Elements</span></span>  
 <span data-ttu-id="c1495-134">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c1495-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c1495-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c1495-135">Parent Elements</span></span>  
  
|<span data-ttu-id="c1495-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="c1495-136">Element</span></span>|<span data-ttu-id="c1495-137">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c1495-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1495-138">\<comportamiento > de \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="c1495-138">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="c1495-139">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="c1495-139">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c1495-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1495-140">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>

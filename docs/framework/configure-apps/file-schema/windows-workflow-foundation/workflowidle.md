---
description: 'Más información acerca de: <workflowIdle>'
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: c1707ab5c633a358846a8ddf529bbfab90d3012d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697964"
---
# \<workflowIdle>

<span data-ttu-id="2400c-102">Un comportamiento del servicio que controla cuando las instancias de flujo de trabajo inactivas se descargan y conservan.</span><span class="sxs-lookup"><span data-stu-id="2400c-102">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowIdle>**  
  
## <a name="syntax"></a><span data-ttu-id="2400c-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2400c-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2400c-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2400c-104">Attributes and Elements</span></span>  

 <span data-ttu-id="2400c-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2400c-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2400c-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="2400c-106">Attributes</span></span>  
  
|<span data-ttu-id="2400c-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="2400c-107">Attribute</span></span>|<span data-ttu-id="2400c-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="2400c-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2400c-109">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="2400c-109">timeToPersist</span></span>|<span data-ttu-id="2400c-110">Un valor Timespan que especifica el tiempo que transcurre entre el momento en que el flujo de trabajo se vuelve inactivo y se conserva.</span><span class="sxs-lookup"><span data-stu-id="2400c-110">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="2400c-111">El valor predeterminado es TimeSpan.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="2400c-111">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="2400c-112">La duración comienza a transcurrir cuando la instancia de flujo de trabajo se vuelve inactiva.</span><span class="sxs-lookup"><span data-stu-id="2400c-112">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="2400c-113">Este atributo es útil si desea conservar de forma más agresiva una instancia de flujo de trabajo mientras se mantiene la instancia en memoria durante el máximo tiempo posible.</span><span class="sxs-lookup"><span data-stu-id="2400c-113">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="2400c-114">Este atributo solo es válido si su valor es menor que el atributo **timeToUnload** .</span><span class="sxs-lookup"><span data-stu-id="2400c-114">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="2400c-115">Si es mayor, se omite.</span><span class="sxs-lookup"><span data-stu-id="2400c-115">If it is greater, it is ignored.</span></span> <span data-ttu-id="2400c-116">Si este atributo transcurre antes del valor especificado por el atributo **timeToUnload** , la persistencia debe completarse antes de que se descargue el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2400c-116">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="2400c-117">Esto implica que se puede retrasar la operación de descarga hasta que se conserve el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2400c-117">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="2400c-118">El nivel de conservación es responsable de administrar todos los reintentos de errores transitorios y solo produce excepciones con errores no recuperables.</span><span class="sxs-lookup"><span data-stu-id="2400c-118">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="2400c-119">Por consiguiente, cualquier excepción producida durante la conservación se trata como grave y se anula la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2400c-119">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="2400c-120">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="2400c-120">timeToUnload</span></span>|<span data-ttu-id="2400c-121">Un valor Timespan que especifica el tiempo que transcurre entre el momento en que el flujo de trabajo se vuelve inactivo y descarga.</span><span class="sxs-lookup"><span data-stu-id="2400c-121">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="2400c-122">El valor predeterminado es 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="2400c-122">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="2400c-123">Descargar un flujo de trabajo implica que también se conserva.</span><span class="sxs-lookup"><span data-stu-id="2400c-123">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="2400c-124">Si este atributo se pone a cero, la instancia de flujo de trabajo se conserva y se descarga de inmediato en cuanto el flujo de trabajo se vuelve inactivo.</span><span class="sxs-lookup"><span data-stu-id="2400c-124">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="2400c-125">Al establecer este atributo en TimeSpan.MaxValue, se deshabilita de forma eficaz la operación de descarga.</span><span class="sxs-lookup"><span data-stu-id="2400c-125">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="2400c-126">Las instancias de flujo de trabajo inactivas nunca se descargan.</span><span class="sxs-lookup"><span data-stu-id="2400c-126">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2400c-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2400c-127">Child Elements</span></span>  

 <span data-ttu-id="2400c-128">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2400c-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2400c-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2400c-129">Parent Elements</span></span>  
  
|<span data-ttu-id="2400c-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="2400c-130">Element</span></span>|<span data-ttu-id="2400c-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="2400c-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2400c-132">\<behavior> de \<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="2400c-132">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="2400c-133">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="2400c-133">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2400c-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="2400c-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>

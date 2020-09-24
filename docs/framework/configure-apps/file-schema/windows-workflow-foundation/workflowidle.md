---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: 790e852eb515e19afc324f6e1c25db81ed22999c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148677"
---
# \<workflowIdle>

<span data-ttu-id="49cee-101">Un comportamiento del servicio que controla cuando las instancias de flujo de trabajo inactivas se descargan y conservan.</span><span class="sxs-lookup"><span data-stu-id="49cee-101">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowIdle>**  
  
## <a name="syntax"></a><span data-ttu-id="49cee-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="49cee-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="49cee-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="49cee-103">Attributes and Elements</span></span>  

 <span data-ttu-id="49cee-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="49cee-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="49cee-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="49cee-105">Attributes</span></span>  
  
|<span data-ttu-id="49cee-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="49cee-106">Attribute</span></span>|<span data-ttu-id="49cee-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="49cee-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="49cee-108">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="49cee-108">timeToPersist</span></span>|<span data-ttu-id="49cee-109">Un valor Timespan que especifica el tiempo que transcurre entre el momento en que el flujo de trabajo se vuelve inactivo y se conserva.</span><span class="sxs-lookup"><span data-stu-id="49cee-109">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="49cee-110">El valor predeterminado es TimeSpan.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="49cee-110">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="49cee-111">La duración comienza a transcurrir cuando la instancia de flujo de trabajo se vuelve inactiva.</span><span class="sxs-lookup"><span data-stu-id="49cee-111">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="49cee-112">Este atributo es útil si desea conservar de forma más agresiva una instancia de flujo de trabajo mientras se mantiene la instancia en memoria durante el máximo tiempo posible.</span><span class="sxs-lookup"><span data-stu-id="49cee-112">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="49cee-113">Este atributo solo es válido si su valor es menor que el atributo **timeToUnload** .</span><span class="sxs-lookup"><span data-stu-id="49cee-113">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="49cee-114">Si es mayor, se omite.</span><span class="sxs-lookup"><span data-stu-id="49cee-114">If it is greater, it is ignored.</span></span> <span data-ttu-id="49cee-115">Si este atributo transcurre antes del valor especificado por el atributo **timeToUnload** , la persistencia debe completarse antes de que se descargue el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="49cee-115">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="49cee-116">Esto implica que se puede retrasar la operación de descarga hasta que se conserve el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="49cee-116">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="49cee-117">El nivel de conservación es responsable de administrar todos los reintentos de errores transitorios y solo produce excepciones con errores no recuperables.</span><span class="sxs-lookup"><span data-stu-id="49cee-117">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="49cee-118">Por consiguiente, cualquier excepción producida durante la conservación se trata como grave y se anula la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="49cee-118">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="49cee-119">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="49cee-119">timeToUnload</span></span>|<span data-ttu-id="49cee-120">Un valor Timespan que especifica el tiempo que transcurre entre el momento en que el flujo de trabajo se vuelve inactivo y descarga.</span><span class="sxs-lookup"><span data-stu-id="49cee-120">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="49cee-121">El valor predeterminado es 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="49cee-121">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="49cee-122">Descargar un flujo de trabajo implica que también se conserva.</span><span class="sxs-lookup"><span data-stu-id="49cee-122">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="49cee-123">Si este atributo se pone a cero, la instancia de flujo de trabajo se conserva y se descarga de inmediato en cuanto el flujo de trabajo se vuelve inactivo.</span><span class="sxs-lookup"><span data-stu-id="49cee-123">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="49cee-124">Al establecer este atributo en TimeSpan.MaxValue, se deshabilita de forma eficaz la operación de descarga.</span><span class="sxs-lookup"><span data-stu-id="49cee-124">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="49cee-125">Las instancias de flujo de trabajo inactivas nunca se descargan.</span><span class="sxs-lookup"><span data-stu-id="49cee-125">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="49cee-126">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="49cee-126">Child Elements</span></span>  

 <span data-ttu-id="49cee-127">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="49cee-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="49cee-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="49cee-128">Parent Elements</span></span>  
  
|<span data-ttu-id="49cee-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="49cee-129">Element</span></span>|<span data-ttu-id="49cee-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="49cee-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="49cee-131">\<behavior> de \<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="49cee-131">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="49cee-132">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="49cee-132">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="49cee-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="49cee-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>

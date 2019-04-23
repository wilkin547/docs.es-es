---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: cfe3350ac42d1e0e837b79f25753f62dc2051dd2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096256"
---
# <a name="workflowunhandledexception"></a><span data-ttu-id="1ff7c-101">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="1ff7c-101">\<workflowUnhandledException></span></span>
<span data-ttu-id="1ff7c-102">Un comportamiento del servicio que permite especificar la acción que debe emprenderse cuando se produce una excepción no controlada dentro de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1ff7c-102">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="1ff7c-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1ff7c-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="1ff7c-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="1ff7c-104">\<behaviors></span></span>  
<span data-ttu-id="1ff7c-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="1ff7c-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="1ff7c-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="1ff7c-106">\<behavior></span></span>  
<span data-ttu-id="1ff7c-107">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="1ff7c-107">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ff7c-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ff7c-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ff7c-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1ff7c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1ff7c-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1ff7c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ff7c-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="1ff7c-111">Attributes</span></span>  
  
|<span data-ttu-id="1ff7c-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="1ff7c-112">Attribute</span></span>|<span data-ttu-id="1ff7c-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ff7c-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1ff7c-114">predeterminada</span><span class="sxs-lookup"><span data-stu-id="1ff7c-114">action</span></span>|<span data-ttu-id="1ff7c-115">Una cadena que especifica la acción que debe emprenderse cuando se produce una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="1ff7c-115">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="1ff7c-116">Este atributo es del tipo <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="1ff7c-116">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1ff7c-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1ff7c-117">Child Elements</span></span>  
 <span data-ttu-id="1ff7c-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1ff7c-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1ff7c-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1ff7c-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1ff7c-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="1ff7c-120">Element</span></span>|<span data-ttu-id="1ff7c-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ff7c-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ff7c-122">\<comportamiento > de \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1ff7c-122">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="1ff7c-123">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="1ff7c-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1ff7c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ff7c-124">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>

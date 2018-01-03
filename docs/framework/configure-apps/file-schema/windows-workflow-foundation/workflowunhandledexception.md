---
title: '&lt;workflowUnhandledException&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4266eb6480c98c7ea1b96f2325a018b0fdcba041
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltworkflowunhandledexceptiongt"></a><span data-ttu-id="12b9e-102">&lt;workflowUnhandledException&gt;</span><span class="sxs-lookup"><span data-stu-id="12b9e-102">&lt;workflowUnhandledException&gt;</span></span>
<span data-ttu-id="12b9e-103">Un comportamiento del servicio que permite especificar la acción que debe emprenderse cuando se produce una excepción no controlada dentro de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="12b9e-103">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="12b9e-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="12b9e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="12b9e-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="12b9e-105">\<behaviors></span></span>  
<span data-ttu-id="12b9e-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="12b9e-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="12b9e-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="12b9e-107">\<behavior></span></span>  
<span data-ttu-id="12b9e-108">\<workflowUnhandledException ></span><span class="sxs-lookup"><span data-stu-id="12b9e-108">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12b9e-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="12b9e-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="12b9e-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="12b9e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="12b9e-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="12b9e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="12b9e-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="12b9e-112">Attributes</span></span>  
  
|<span data-ttu-id="12b9e-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="12b9e-113">Attribute</span></span>|<span data-ttu-id="12b9e-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="12b9e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="12b9e-115">predeterminada</span><span class="sxs-lookup"><span data-stu-id="12b9e-115">action</span></span>|<span data-ttu-id="12b9e-116">Una cadena que especifica la acción que debe emprenderse cuando se produce una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="12b9e-116">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="12b9e-117">Este atributo es del tipo <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="12b9e-117">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="12b9e-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="12b9e-118">Child Elements</span></span>  
 <span data-ttu-id="12b9e-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="12b9e-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="12b9e-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="12b9e-120">Parent Elements</span></span>  
  
|<span data-ttu-id="12b9e-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="12b9e-121">Element</span></span>|<span data-ttu-id="12b9e-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="12b9e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12b9e-123">\<comportamiento > de \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="12b9e-123">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="12b9e-124">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="12b9e-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="12b9e-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="12b9e-125">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>

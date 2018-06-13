---
title: '&lt;workflowUnhandledException&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: d9db6ecc2e95e0d1ec5738f1d2f4a09a89c57f21
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755141"
---
# <a name="ltworkflowunhandledexceptiongt"></a><span data-ttu-id="ddc78-102">&lt;workflowUnhandledException&gt;</span><span class="sxs-lookup"><span data-stu-id="ddc78-102">&lt;workflowUnhandledException&gt;</span></span>
<span data-ttu-id="ddc78-103">Un comportamiento del servicio que permite especificar la acción que debe emprenderse cuando se produce una excepción no controlada dentro de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ddc78-103">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="ddc78-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ddc78-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ddc78-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="ddc78-105">\<behaviors></span></span>  
<span data-ttu-id="ddc78-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="ddc78-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="ddc78-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="ddc78-107">\<behavior></span></span>  
<span data-ttu-id="ddc78-108">\<workflowUnhandledException ></span><span class="sxs-lookup"><span data-stu-id="ddc78-108">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddc78-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ddc78-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ddc78-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ddc78-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ddc78-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ddc78-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ddc78-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="ddc78-112">Attributes</span></span>  
  
|<span data-ttu-id="ddc78-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="ddc78-113">Attribute</span></span>|<span data-ttu-id="ddc78-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="ddc78-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ddc78-115">predeterminada</span><span class="sxs-lookup"><span data-stu-id="ddc78-115">action</span></span>|<span data-ttu-id="ddc78-116">Una cadena que especifica la acción que debe emprenderse cuando se produce una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="ddc78-116">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="ddc78-117">Este atributo es del tipo <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="ddc78-117">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ddc78-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ddc78-118">Child Elements</span></span>  
 <span data-ttu-id="ddc78-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ddc78-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ddc78-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ddc78-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ddc78-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="ddc78-121">Element</span></span>|<span data-ttu-id="ddc78-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="ddc78-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ddc78-123">\<comportamiento > de \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="ddc78-123">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="ddc78-124">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="ddc78-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ddc78-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="ddc78-125">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>

---
title: '&lt;add&gt; de &lt;services&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 60a717513689aeba1bfbd6229d4eef28024df8c9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-of-ltservicesgt"></a><span data-ttu-id="bdf32-102">&lt;add&gt; de &lt;services&gt;</span><span class="sxs-lookup"><span data-stu-id="bdf32-102">&lt;add&gt; of &lt;services&gt;</span></span>
<span data-ttu-id="bdf32-103">Especifica los valores de una instancia de <xref:System.Workflow.Runtime.WorkflowRuntime> para hospedar los servicios [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] basados en flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bdf32-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services.</span></span> <span data-ttu-id="bdf32-104">Este elemento es del tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="bdf32-104">This element is of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  
  
 <span data-ttu-id="bdf32-105">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="bdf32-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="bdf32-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="bdf32-106">\<behaviors></span></span>  
<span data-ttu-id="bdf32-107">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="bdf32-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="bdf32-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="bdf32-108">\<behavior></span></span>  
<span data-ttu-id="bdf32-109">\<Servicios ></span><span class="sxs-lookup"><span data-stu-id="bdf32-109">\<services></span></span>  
<span data-ttu-id="bdf32-110">\<add></span><span class="sxs-lookup"><span data-stu-id="bdf32-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdf32-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bdf32-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>  
   <services>  
      <add type="String"/>  
   </services>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bdf32-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bdf32-112">Attributes and Elements</span></span>  
 <span data-ttu-id="bdf32-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bdf32-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bdf32-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="bdf32-114">Attributes</span></span>  
  
|<span data-ttu-id="bdf32-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="bdf32-115">Attribute</span></span>|<span data-ttu-id="bdf32-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="bdf32-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bdf32-117">tipo</span><span class="sxs-lookup"><span data-stu-id="bdf32-117">type</span></span>|<span data-ttu-id="bdf32-118">Una cadena que especifica el nombre de tipo calificado con el nombre de ensamblado del servicio que se va a inicializar.</span><span class="sxs-lookup"><span data-stu-id="bdf32-118">A string that specifies the assembly-qualified type name of the service to be initialized.</span></span> <span data-ttu-id="bdf32-119">El servicio especificado debe seguir ciertas reglas sobre las firmas de sus constructores.</span><span class="sxs-lookup"><span data-stu-id="bdf32-119">The service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="bdf32-120">Vea <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="bdf32-120">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bdf32-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bdf32-121">Child Elements</span></span>  
 <span data-ttu-id="bdf32-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bdf32-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bdf32-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bdf32-123">Parent Elements</span></span>  
  
|<span data-ttu-id="bdf32-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="bdf32-124">Element</span></span>|<span data-ttu-id="bdf32-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="bdf32-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bdf32-126">\<Servicios ></span><span class="sxs-lookup"><span data-stu-id="bdf32-126">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services-of-workflowruntime.md)|<span data-ttu-id="bdf32-127">Una  colección de servicios que se agregará al motor <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="bdf32-127">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="bdf32-128">Los elementos son de tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="bdf32-128">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="bdf32-129">El motor en tiempo de ejecución del flujo de trabajo inicializará y agregará los servicios especificados en la colección a sus servicios cuando se llame al constructor <xref:System.Workflow.Runtime.WorkflowRuntime> adecuado.</span><span class="sxs-lookup"><span data-stu-id="bdf32-129">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="bdf32-130">Por consiguiente los servicios especificados en la colección deben seguir ciertas reglas sobre las firmas de sus constructores.</span><span class="sxs-lookup"><span data-stu-id="bdf32-130">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="bdf32-131">Vea <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="bdf32-131">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bdf32-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bdf32-132">Remarks</span></span>  
 <span data-ttu-id="bdf32-133">El motor en tiempo de ejecución del flujo de trabajo inicializará y agregará el servicio especificado a sus servicios cuando se llame al constructor <xref:System.Workflow.Runtime.WorkflowRuntime> adecuado.</span><span class="sxs-lookup"><span data-stu-id="bdf32-133">The service specified in this element will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="bdf32-134">Por consiguiente, el servicio especificado debe seguir ciertas reglas sobre las firmas de sus constructores.</span><span class="sxs-lookup"><span data-stu-id="bdf32-134">Therefore, the service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="bdf32-135">Vea <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="bdf32-135">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bdf32-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bdf32-136">Example</span></span>  
  
```xml  
<serviceBehaviors>  
   <behavior name="ServiceBehavior">  
      <workflowRuntime name="WorkflowServiceHostRuntime"  
                       validateOnCreate="true"  
                       enablePerformanceCounters="true">  
         <services>  
             <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common"/>  
         </services>  
      </workflowRuntime>  
   </behavior>  
</serviceBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bdf32-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="bdf32-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 [<span data-ttu-id="bdf32-138">Archivos de configuración de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="bdf32-138">Workflow Configuration Files</span></span>](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)

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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 040db3b350ebacfc3aff76d90e87e65206701069
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="ltaddgt-of-ltservicesgt"></a><span data-ttu-id="74560-102">&lt;add&gt; de &lt;services&gt;</span><span class="sxs-lookup"><span data-stu-id="74560-102">&lt;add&gt; of &lt;services&gt;</span></span>
<span data-ttu-id="74560-103">Especifica los valores de una instancia de <xref:System.Workflow.Runtime.WorkflowRuntime> para hospedar los servicios [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] basados en flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="74560-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services.</span></span> <span data-ttu-id="74560-104">Este elemento es del tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="74560-104">This element is of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  
  
 <span data-ttu-id="74560-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="74560-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="74560-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="74560-106">\<behaviors></span></span>  
<span data-ttu-id="74560-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="74560-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="74560-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="74560-108">\<behavior></span></span>  
<span data-ttu-id="74560-109">\<services></span><span class="sxs-lookup"><span data-stu-id="74560-109">\<services></span></span>  
<span data-ttu-id="74560-110">\<add></span><span class="sxs-lookup"><span data-stu-id="74560-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74560-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74560-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>  
   <services>  
      <add type="String"/>  
   </services>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74560-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="74560-112">Attributes and Elements</span></span>  
 <span data-ttu-id="74560-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="74560-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74560-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="74560-114">Attributes</span></span>  
  
|<span data-ttu-id="74560-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="74560-115">Attribute</span></span>|<span data-ttu-id="74560-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="74560-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="74560-117">tipo</span><span class="sxs-lookup"><span data-stu-id="74560-117">type</span></span>|<span data-ttu-id="74560-118">Una cadena que especifica el nombre de tipo calificado con el nombre de ensamblado del servicio que se va a inicializar.</span><span class="sxs-lookup"><span data-stu-id="74560-118">A string that specifies the assembly-qualified type name of the service to be initialized.</span></span> <span data-ttu-id="74560-119">El servicio especificado debe seguir ciertas reglas sobre las firmas de sus constructores.</span><span class="sxs-lookup"><span data-stu-id="74560-119">The service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="74560-120">Vea <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="74560-120">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="74560-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="74560-121">Child Elements</span></span>  
 <span data-ttu-id="74560-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="74560-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="74560-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="74560-123">Parent Elements</span></span>  
  
|<span data-ttu-id="74560-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="74560-124">Element</span></span>|<span data-ttu-id="74560-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="74560-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74560-126">\<services></span><span class="sxs-lookup"><span data-stu-id="74560-126">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services-of-workflowruntime.md)|<span data-ttu-id="74560-127">Una  colección de servicios que se agregará al motor <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="74560-127">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="74560-128">Los elementos son de tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="74560-128">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="74560-129">El motor en tiempo de ejecución del flujo de trabajo inicializará y agregará los servicios especificados en la colección a sus servicios cuando se llame al constructor <xref:System.Workflow.Runtime.WorkflowRuntime> adecuado.</span><span class="sxs-lookup"><span data-stu-id="74560-129">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="74560-130">Por consiguiente los servicios especificados en la colección deben seguir ciertas reglas sobre las firmas de sus constructores.</span><span class="sxs-lookup"><span data-stu-id="74560-130">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="74560-131">Vea <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="74560-131">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74560-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="74560-132">Remarks</span></span>  
 <span data-ttu-id="74560-133">El motor en tiempo de ejecución del flujo de trabajo inicializará y agregará el servicio especificado a sus servicios cuando se llame al constructor <xref:System.Workflow.Runtime.WorkflowRuntime> adecuado.</span><span class="sxs-lookup"><span data-stu-id="74560-133">The service specified in this element will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="74560-134">Por consiguiente, el servicio especificado debe seguir ciertas reglas sobre las firmas de sus constructores.</span><span class="sxs-lookup"><span data-stu-id="74560-134">Therefore, the service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="74560-135">Vea <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="74560-135">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74560-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="74560-136">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="74560-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="74560-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 [<span data-ttu-id="74560-138">Archivos de configuración de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="74560-138">Workflow Configuration Files</span></span>](http://msdn.microsoft.com/library/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)

---
title: '&lt;add&gt; de &lt;services&gt;'
ms.date: 03/30/2017
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
ms.openlocfilehash: 9a86b7549e0efef10cbeb16dcc427d04065e43d3
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145541"
---
# <a name="ltaddgt-of-ltservicesgt"></a><span data-ttu-id="50061-102">&lt;add&gt; de &lt;services&gt;</span><span class="sxs-lookup"><span data-stu-id="50061-102">&lt;add&gt; of &lt;services&gt;</span></span>
<span data-ttu-id="50061-103">Especifica la configuración de una instancia de <xref:System.Workflow.Runtime.WorkflowRuntime> para hospedar servicios de Windows Communication Foundation (WCF) basados en flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="50061-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="50061-104">Este elemento es del tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="50061-104">This element is of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  
  
 <span data-ttu-id="50061-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="50061-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="50061-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="50061-106">\<behaviors></span></span>  
<span data-ttu-id="50061-107">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="50061-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="50061-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="50061-108">\<behavior></span></span>  
<span data-ttu-id="50061-109">\<Services ></span><span class="sxs-lookup"><span data-stu-id="50061-109">\<services></span></span>  
<span data-ttu-id="50061-110">\<add></span><span class="sxs-lookup"><span data-stu-id="50061-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50061-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="50061-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <services>
    <add type="String" />
  </services>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50061-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="50061-112">Attributes and Elements</span></span>  
 <span data-ttu-id="50061-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="50061-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="50061-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="50061-114">Attributes</span></span>  
  
|<span data-ttu-id="50061-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="50061-115">Attribute</span></span>|<span data-ttu-id="50061-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="50061-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="50061-117">tipo</span><span class="sxs-lookup"><span data-stu-id="50061-117">type</span></span>|<span data-ttu-id="50061-118">Una cadena que especifica el nombre de tipo calificado con el nombre de ensamblado del servicio que se va a inicializar.</span><span class="sxs-lookup"><span data-stu-id="50061-118">A string that specifies the assembly-qualified type name of the service to be initialized.</span></span> <span data-ttu-id="50061-119">El servicio especificado debe seguir ciertas reglas sobre las firmas de sus constructores.</span><span class="sxs-lookup"><span data-stu-id="50061-119">The service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="50061-120">Vea <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="50061-120">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="50061-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="50061-121">Child Elements</span></span>  
 <span data-ttu-id="50061-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="50061-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="50061-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="50061-123">Parent Elements</span></span>  
  
|<span data-ttu-id="50061-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="50061-124">Element</span></span>|<span data-ttu-id="50061-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="50061-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="50061-126">\<Services ></span><span class="sxs-lookup"><span data-stu-id="50061-126">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services-of-workflowruntime.md)|<span data-ttu-id="50061-127">Una colección de servicios que se agregará al motor <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="50061-127">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="50061-128">Los elementos son de tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="50061-128">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="50061-129">El motor en tiempo de ejecución del flujo de trabajo inicializará y agregará los servicios especificados en la colección a sus servicios cuando se llame al constructor <xref:System.Workflow.Runtime.WorkflowRuntime> adecuado.</span><span class="sxs-lookup"><span data-stu-id="50061-129">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="50061-130">Por consiguiente los servicios especificados en la colección deben seguir ciertas reglas sobre las firmas de sus constructores.</span><span class="sxs-lookup"><span data-stu-id="50061-130">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="50061-131">Vea <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="50061-131">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50061-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="50061-132">Remarks</span></span>  
 <span data-ttu-id="50061-133">El motor en tiempo de ejecución del flujo de trabajo inicializará y agregará el servicio especificado a sus servicios cuando se llame al constructor <xref:System.Workflow.Runtime.WorkflowRuntime> adecuado.</span><span class="sxs-lookup"><span data-stu-id="50061-133">The service specified in this element will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="50061-134">Por consiguiente, el servicio especificado debe seguir ciertas reglas sobre las firmas de sus constructores.</span><span class="sxs-lookup"><span data-stu-id="50061-134">Therefore, the service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="50061-135">Vea <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="50061-135">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50061-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="50061-136">Example</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="ServiceBehavior">
    <workflowRuntime name="WorkflowServiceHostRuntime"
                     validateOnCreate="true"
                     enablePerformanceCounters="true">
      <services>
        <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common" />
      </services>
    </workflowRuntime>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="50061-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="50061-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <span data-ttu-id="50061-138">[Archivos de configuración de flujo de trabajo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="50061-138">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>

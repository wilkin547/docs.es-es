---
title: <add> de <services>
ms.date: 03/30/2017
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
ms.openlocfilehash: c07b3377db4f5b434fd021b09de510c1d43ec832
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673581"
---
# <a name="add-of-services"></a><span data-ttu-id="b6a23-102">\<Agregar > de \<services ></span><span class="sxs-lookup"><span data-stu-id="b6a23-102">\<add> of \<services></span></span>
<span data-ttu-id="b6a23-103">Especifica la configuración de una instancia de <xref:System.Workflow.Runtime.WorkflowRuntime> para hospedar servicios de Windows Communication Foundation (WCF) basados en flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b6a23-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="b6a23-104">Este elemento es del tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="b6a23-104">This element is of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  
  
 <span data-ttu-id="b6a23-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b6a23-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="b6a23-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="b6a23-106">\<behaviors></span></span>  
<span data-ttu-id="b6a23-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="b6a23-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="b6a23-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="b6a23-108">\<behavior></span></span>  
<span data-ttu-id="b6a23-109">\<services></span><span class="sxs-lookup"><span data-stu-id="b6a23-109">\<services></span></span>  
<span data-ttu-id="b6a23-110">\<add></span><span class="sxs-lookup"><span data-stu-id="b6a23-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6a23-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b6a23-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <services>
    <add type="String" />
  </services>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6a23-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b6a23-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b6a23-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b6a23-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6a23-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="b6a23-114">Attributes</span></span>  
  
|<span data-ttu-id="b6a23-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="b6a23-115">Attribute</span></span>|<span data-ttu-id="b6a23-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="b6a23-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b6a23-117">type</span><span class="sxs-lookup"><span data-stu-id="b6a23-117">type</span></span>|<span data-ttu-id="b6a23-118">Una cadena que especifica el nombre de tipo calificado con el nombre de ensamblado del servicio que se va a inicializar.</span><span class="sxs-lookup"><span data-stu-id="b6a23-118">A string that specifies the assembly-qualified type name of the service to be initialized.</span></span> <span data-ttu-id="b6a23-119">El servicio especificado debe seguir ciertas reglas sobre las firmas de sus constructores.</span><span class="sxs-lookup"><span data-stu-id="b6a23-119">The service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="b6a23-120">Vea <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b6a23-120">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b6a23-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b6a23-121">Child Elements</span></span>  
 <span data-ttu-id="b6a23-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b6a23-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b6a23-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b6a23-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b6a23-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="b6a23-124">Element</span></span>|<span data-ttu-id="b6a23-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="b6a23-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6a23-126">\<services></span><span class="sxs-lookup"><span data-stu-id="b6a23-126">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services-of-workflowruntime.md)|<span data-ttu-id="b6a23-127">Una colección de servicios que se agregará al motor <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="b6a23-127">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="b6a23-128">Los elementos son de tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="b6a23-128">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="b6a23-129">El motor en tiempo de ejecución del flujo de trabajo inicializará y agregará los servicios especificados en la colección a sus servicios cuando se llame al constructor <xref:System.Workflow.Runtime.WorkflowRuntime> adecuado.</span><span class="sxs-lookup"><span data-stu-id="b6a23-129">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="b6a23-130">Por consiguiente los servicios especificados en la colección deben seguir ciertas reglas sobre las firmas de sus constructores.</span><span class="sxs-lookup"><span data-stu-id="b6a23-130">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="b6a23-131">Vea <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b6a23-131">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6a23-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b6a23-132">Remarks</span></span>  
 <span data-ttu-id="b6a23-133">El motor en tiempo de ejecución del flujo de trabajo inicializará y agregará el servicio especificado a sus servicios cuando se llame al constructor <xref:System.Workflow.Runtime.WorkflowRuntime> adecuado.</span><span class="sxs-lookup"><span data-stu-id="b6a23-133">The service specified in this element will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="b6a23-134">Por consiguiente, el servicio especificado debe seguir ciertas reglas sobre las firmas de sus constructores.</span><span class="sxs-lookup"><span data-stu-id="b6a23-134">Therefore, the service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="b6a23-135">Vea <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b6a23-135">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6a23-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b6a23-136">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b6a23-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6a23-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <span data-ttu-id="b6a23-138">[Archivos de configuración de flujo de trabajo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="b6a23-138">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>

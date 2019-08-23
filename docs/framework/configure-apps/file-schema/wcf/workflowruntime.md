---
title: <workflowRuntime>
ms.date: 03/30/2017
ms.assetid: 304c70fa-78d1-4d0f-b89f-0ca23d734c6f
ms.openlocfilehash: 0cd04f66cc4b73eb5f1c43bd6c8dc9189dfceff1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915215"
---
# <a name="workflowruntime"></a><span data-ttu-id="06324-101">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="06324-101">\<workflowRuntime></span></span>
<span data-ttu-id="06324-102">Especifica la configuración de una instancia <xref:System.Workflow.Runtime.WorkflowRuntime> de para hospedar servicios de Windows Communication Foundation basados en el flujo de trabajo (WCF).</span><span class="sxs-lookup"><span data-stu-id="06324-102">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>  
  
 <span data-ttu-id="06324-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="06324-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="06324-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="06324-104">\<behaviors></span></span>  
<span data-ttu-id="06324-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="06324-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="06324-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="06324-106">\<behavior></span></span>  
<span data-ttu-id="06324-107">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="06324-107">\<workflowRuntime></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06324-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06324-108">Syntax</span></span>  
  
```xml  
<workflowRuntime cachedInstanceExpiration="TimeSpan"
                 enablePerformanceCounters="Boolean"
                 name="String"
                 validateOnCreate="Boolean">
  <commonParameters>
    <add name="String"
         value="String" />
  </commonParameters>
  <services>
    <add type="String" />
  </services>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06324-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="06324-109">Attributes and Elements</span></span>  
 <span data-ttu-id="06324-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="06324-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06324-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="06324-111">Attributes</span></span>  
  
|<span data-ttu-id="06324-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="06324-112">Attribute</span></span>|<span data-ttu-id="06324-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="06324-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="06324-114">cachedInstanceExpiration</span><span class="sxs-lookup"><span data-stu-id="06324-114">cachedInstanceExpiration</span></span>|<span data-ttu-id="06324-115">Un valor <xref:System.TimeSpan> opcional que especifica la duración máxima que una instancia de flujo de trabajo puede quedarse en memoria en estado inactivo antes de descargarse o cancelarse de forma obligatoria.</span><span class="sxs-lookup"><span data-stu-id="06324-115">An optional <xref:System.TimeSpan> value that specifies the maximum duration a workflow instance can stay in-memory in idle state before it is forcefully unloaded or aborted.</span></span> <span data-ttu-id="06324-116">Si workflowruntime tiene `PersistenceService` que realiza unloadOnIdle, se omite este atributo.</span><span class="sxs-lookup"><span data-stu-id="06324-116">If the workflowruntime has `PersistenceService` which performs unloadOnIdle, this attribute is ignored.</span></span>|  
|<span data-ttu-id="06324-117">enablePerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="06324-117">enablePerformanceCounters</span></span>|<span data-ttu-id="06324-118">Un valor booleano opcional que especifica si los contadores de rendimiento están habilitados.</span><span class="sxs-lookup"><span data-stu-id="06324-118">An optional Boolean value that specifies whether performance counters are enabled.</span></span> <span data-ttu-id="06324-119">Los contadores de rendimiento proporcionan información sobre varias estadísticas relacionadas con el flujo de trabajo, pero producen una reducción del rendimiento al iniciar el motor en tiempo de ejecución del flujo de trabajo, y durante la ejecución de las instancias del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="06324-119">Performance counters provide information on various workflow-related statistics, but they cause a performance penalty when the workflow runtime engine starts, and when workflow instances are running.</span></span> <span data-ttu-id="06324-120">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="06324-120">The default value is `true`.</span></span>|  
|<span data-ttu-id="06324-121">Nombre</span><span class="sxs-lookup"><span data-stu-id="06324-121">name</span></span>|<span data-ttu-id="06324-122">Una cadena que contiene el nombre del motor en tiempo de ejecución del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="06324-122">A string containing the name of the workflow runtime engine.</span></span> <span data-ttu-id="06324-123">El nombre se usa en resultado para distinguir este tiempo de ejecución de otros tiempo de ejecución que se pueden estar ejecutando en el sistema, por ejemplo, en contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="06324-123">The name is used in output to distinguish this runtime from other runtimes that may be running on the system, for example, in performance counters.</span></span><br /><br /> <span data-ttu-id="06324-124">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="06324-124">The default is an empty string.</span></span>|  
|<span data-ttu-id="06324-125">validateOnCreate</span><span class="sxs-lookup"><span data-stu-id="06324-125">validateOnCreate</span></span>|<span data-ttu-id="06324-126">Un valor booleano opcional que especifica si se producirá la validación de definición de flujo de trabajo cuando se abra WorkflowServiceHost.</span><span class="sxs-lookup"><span data-stu-id="06324-126">An optional Boolean value that specifies whether validation of workflow definition will occur when the WorkflowServiceHost is opened.</span></span>  <span data-ttu-id="06324-127">Cuando este atributo se establece en `true`, se ejecuta la validación del flujo de trabajo cada vez que se llama a `WorkflowServiceHost.Open`.</span><span class="sxs-lookup"><span data-stu-id="06324-127">When this attribute is set to `true`, the workflow validation is executed every time `WorkflowServiceHost.Open` is called.</span></span> <span data-ttu-id="06324-128">Si se encuentran errores de validación, se inicia un error <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException>.</span><span class="sxs-lookup"><span data-stu-id="06324-128">If validation errors are found, a <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException> error is thrown.</span></span><br /><br /> <span data-ttu-id="06324-129">Cuando esta propiedad se establece en `false`, no pasará ninguna validación de definición de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="06324-129">When this property is set to `false`, no Workflow definition validation will happen.</span></span><br /><br /> <span data-ttu-id="06324-130">El valor predeterminado de esta propiedad es `true`.</span><span class="sxs-lookup"><span data-stu-id="06324-130">The default value for this property is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="06324-131">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="06324-131">Child Elements</span></span>  
  
|<span data-ttu-id="06324-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="06324-132">Element</span></span>|<span data-ttu-id="06324-133">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="06324-133">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="06324-134">commonParameters</span><span class="sxs-lookup"><span data-stu-id="06324-134">commonParameters</span></span>|<span data-ttu-id="06324-135">Una colección de parámetros comunes usada por los servicios.</span><span class="sxs-lookup"><span data-stu-id="06324-135">A collection of common parameters used by services.</span></span> <span data-ttu-id="06324-136">Esta colección incluirá, normalmente, la cadena de conexión de la base de datos que podrían compartir los servicios duraderos.</span><span class="sxs-lookup"><span data-stu-id="06324-136">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
|<span data-ttu-id="06324-137">servicios</span><span class="sxs-lookup"><span data-stu-id="06324-137">services</span></span>|<span data-ttu-id="06324-138">Una colección de servicios que se agregará al motor <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="06324-138">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="06324-139">Los elementos son de tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="06324-139">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="06324-140">El motor en tiempo de ejecución del flujo de trabajo inicializará y agregará los servicios especificados en la colección a sus servicios cuando se llame al constructor <xref:System.Workflow.Runtime.WorkflowRuntime> adecuado.</span><span class="sxs-lookup"><span data-stu-id="06324-140">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="06324-141">Por consiguiente los servicios especificados en la colección deben seguir ciertas reglas sobre las firmas de sus constructores.</span><span class="sxs-lookup"><span data-stu-id="06324-141">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="06324-142">Vea <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="06324-142">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="06324-143">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="06324-143">Parent Elements</span></span>  
  
|<span data-ttu-id="06324-144">Elemento</span><span class="sxs-lookup"><span data-stu-id="06324-144">Element</span></span>|<span data-ttu-id="06324-145">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="06324-145">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06324-146">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="06324-146">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="06324-147">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="06324-147">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06324-148">Comentarios</span><span class="sxs-lookup"><span data-stu-id="06324-148">Remarks</span></span>  
 <span data-ttu-id="06324-149">Para obtener más información sobre el uso de un archivo de configuración para controlar <xref:System.Workflow.Runtime.WorkflowRuntime> el comportamiento de un objeto de una aplicación host de Windows Workflow Foundation, consulte [archivos de configuración de flujo de trabajo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="06324-149">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="06324-150">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="06324-150">Example</span></span>  
  
```xml  
<serviceBehaviors>
   <behavior name="ServiceBehavior">
      <workflowRuntime name="WorkflowServiceHostRuntime"
                       validateOnCreate="true"
                       enablePerformanceCounters="true">
         <commonParameters>
            <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
            <add name="EnableRetries" value="True" />
         </commonParameters>
         <services>
             <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common"/>
         </services>
      </workflowRuntime>
   </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="06324-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="06324-151">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <span data-ttu-id="06324-152">[Archivos de configuración de flujo de trabajo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="06324-152">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>

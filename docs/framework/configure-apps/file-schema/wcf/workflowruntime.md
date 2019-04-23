---
title: <workflowRuntime>
ms.date: 03/30/2017
ms.assetid: 304c70fa-78d1-4d0f-b89f-0ca23d734c6f
ms.openlocfilehash: db5e1083c07d4e204eb19eaae9257ed44439132e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206569"
---
# <a name="workflowruntime"></a><span data-ttu-id="5b439-101">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="5b439-101">\<workflowRuntime></span></span>
<span data-ttu-id="5b439-102">Especifica la configuración de una instancia de <xref:System.Workflow.Runtime.WorkflowRuntime> para hospedar servicios de Windows Communication Foundation (WCF) basados en flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5b439-102">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>  
  
 <span data-ttu-id="5b439-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5b439-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="5b439-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="5b439-104">\<behaviors></span></span>  
<span data-ttu-id="5b439-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="5b439-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="5b439-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="5b439-106">\<behavior></span></span>  
<span data-ttu-id="5b439-107">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="5b439-107">\<workflowRuntime></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b439-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5b439-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b439-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5b439-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5b439-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5b439-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b439-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="5b439-111">Attributes</span></span>  
  
|<span data-ttu-id="5b439-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="5b439-112">Attribute</span></span>|<span data-ttu-id="5b439-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b439-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5b439-114">cachedInstanceExpiration</span><span class="sxs-lookup"><span data-stu-id="5b439-114">cachedInstanceExpiration</span></span>|<span data-ttu-id="5b439-115">Un valor <xref:System.TimeSpan> opcional que especifica la duración máxima que una instancia de flujo de trabajo puede quedarse en memoria en estado inactivo antes de descargarse o cancelarse de forma obligatoria.</span><span class="sxs-lookup"><span data-stu-id="5b439-115">An optional <xref:System.TimeSpan> value that specifies the maximum duration a workflow instance can stay in-memory in idle state before it is forcefully unloaded or aborted.</span></span> <span data-ttu-id="5b439-116">Si workflowruntime tiene `PersistenceService` que realiza unloadOnIdle, se omite este atributo.</span><span class="sxs-lookup"><span data-stu-id="5b439-116">If the workflowruntime has `PersistenceService` which performs unloadOnIdle, this attribute is ignored.</span></span>|  
|<span data-ttu-id="5b439-117">enablePerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="5b439-117">enablePerformanceCounters</span></span>|<span data-ttu-id="5b439-118">Un valor booleano opcional que especifica si los contadores de rendimiento están habilitados.</span><span class="sxs-lookup"><span data-stu-id="5b439-118">An optional Boolean value that specifies whether performance counters are enabled.</span></span> <span data-ttu-id="5b439-119">Los contadores de rendimiento proporcionan información sobre varias estadísticas relacionadas con el flujo de trabajo, pero producen una reducción del rendimiento al iniciar el motor en tiempo de ejecución del flujo de trabajo, y durante la ejecución de las instancias del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5b439-119">Performance counters provide information on various workflow-related statistics, but they cause a performance penalty when the workflow runtime engine starts, and when workflow instances are running.</span></span> <span data-ttu-id="5b439-120">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="5b439-120">The default value is `true`.</span></span>|  
|<span data-ttu-id="5b439-121">name</span><span class="sxs-lookup"><span data-stu-id="5b439-121">name</span></span>|<span data-ttu-id="5b439-122">Una cadena que contiene el nombre del motor en tiempo de ejecución del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5b439-122">A string containing the name of the workflow runtime engine.</span></span> <span data-ttu-id="5b439-123">El nombre se usa en resultado para distinguir este tiempo de ejecución de otros tiempo de ejecución que se pueden estar ejecutando en el sistema, por ejemplo, en contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="5b439-123">The name is used in output to distinguish this runtime from other runtimes that may be running on the system, for example, in performance counters.</span></span><br /><br /> <span data-ttu-id="5b439-124">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="5b439-124">The default is an empty string.</span></span>|  
|<span data-ttu-id="5b439-125">validateOnCreate</span><span class="sxs-lookup"><span data-stu-id="5b439-125">validateOnCreate</span></span>|<span data-ttu-id="5b439-126">Un valor booleano opcional que especifica si se producirá la validación de definición de flujo de trabajo cuando se abra WorkflowServiceHost.</span><span class="sxs-lookup"><span data-stu-id="5b439-126">An optional Boolean value that specifies whether validation of workflow definition will occur when the WorkflowServiceHost is opened.</span></span>  <span data-ttu-id="5b439-127">Cuando este atributo se establece en `true`, se ejecuta la validación del flujo de trabajo cada vez que se llama a `WorkflowServiceHost.Open`.</span><span class="sxs-lookup"><span data-stu-id="5b439-127">When this attribute is set to `true`, the workflow validation is executed every time `WorkflowServiceHost.Open` is called.</span></span> <span data-ttu-id="5b439-128">Si se encuentran errores de validación, se inicia un error <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException>.</span><span class="sxs-lookup"><span data-stu-id="5b439-128">If validation errors are found, a <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException> error is thrown.</span></span><br /><br /> <span data-ttu-id="5b439-129">Cuando esta propiedad se establece en `false`, no pasará ninguna validación de definición de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5b439-129">When this property is set to `false`, no Workflow definition validation will happen.</span></span><br /><br /> <span data-ttu-id="5b439-130">El valor predeterminado de esta propiedad es `true`.</span><span class="sxs-lookup"><span data-stu-id="5b439-130">The default value for this property is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5b439-131">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5b439-131">Child Elements</span></span>  
  
|<span data-ttu-id="5b439-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="5b439-132">Element</span></span>|<span data-ttu-id="5b439-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b439-133">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5b439-134">commonParameters</span><span class="sxs-lookup"><span data-stu-id="5b439-134">commonParameters</span></span>|<span data-ttu-id="5b439-135">Una colección de parámetros comunes usada por los servicios.</span><span class="sxs-lookup"><span data-stu-id="5b439-135">A collection of common parameters used by services.</span></span> <span data-ttu-id="5b439-136">Esta colección incluirá, normalmente, la cadena de conexión de la base de datos que podrían compartir los servicios duraderos.</span><span class="sxs-lookup"><span data-stu-id="5b439-136">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
|<span data-ttu-id="5b439-137">servicios</span><span class="sxs-lookup"><span data-stu-id="5b439-137">services</span></span>|<span data-ttu-id="5b439-138">Una colección de servicios que se agregará al motor <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="5b439-138">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="5b439-139">Los elementos son de tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="5b439-139">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="5b439-140">El motor en tiempo de ejecución del flujo de trabajo inicializará y agregará los servicios especificados en la colección a sus servicios cuando se llame al constructor <xref:System.Workflow.Runtime.WorkflowRuntime> adecuado.</span><span class="sxs-lookup"><span data-stu-id="5b439-140">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="5b439-141">Por consiguiente los servicios especificados en la colección deben seguir ciertas reglas sobre las firmas de sus constructores.</span><span class="sxs-lookup"><span data-stu-id="5b439-141">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="5b439-142">Vea <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="5b439-142">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5b439-143">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5b439-143">Parent Elements</span></span>  
  
|<span data-ttu-id="5b439-144">Elemento</span><span class="sxs-lookup"><span data-stu-id="5b439-144">Element</span></span>|<span data-ttu-id="5b439-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b439-145">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5b439-146">\<behavior></span><span class="sxs-lookup"><span data-stu-id="5b439-146">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="5b439-147">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="5b439-147">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b439-148">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5b439-148">Remarks</span></span>  
 <span data-ttu-id="5b439-149">Para obtener más información sobre el uso de un archivo de configuración para controlar el comportamiento de un <xref:System.Workflow.Runtime.WorkflowRuntime> objeto de una aplicación de host de Windows Workflow Foundation, vea [archivos de configuración de flujo de trabajo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="5b439-149">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b439-150">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5b439-150">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5b439-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b439-151">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <span data-ttu-id="5b439-152">[Archivos de configuración de flujo de trabajo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="5b439-152">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>

---
title: '&lt;WorkflowRuntime&gt;'
ms.date: 03/30/2017
ms.assetid: 304c70fa-78d1-4d0f-b89f-0ca23d734c6f
ms.openlocfilehash: 7c2bd4e2a8c1ddbdb98878d1d97c7acc41856310
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755853"
---
# <a name="ltworkflowruntimegt"></a><span data-ttu-id="2d139-102">&lt;WorkflowRuntime&gt;</span><span class="sxs-lookup"><span data-stu-id="2d139-102">&lt;workflowRuntime&gt;</span></span>
<span data-ttu-id="2d139-103">Especifica valores para una instancia de <xref:System.Workflow.Runtime.WorkflowRuntime> para hospedar servicios de Windows Communication Foundation (WCF) basados en flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2d139-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>  
  
 <span data-ttu-id="2d139-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2d139-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2d139-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="2d139-105">\<behaviors></span></span>  
<span data-ttu-id="2d139-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="2d139-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="2d139-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="2d139-107">\<behavior></span></span>  
<span data-ttu-id="2d139-108">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="2d139-108">\<workflowRuntime></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d139-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d139-109">Syntax</span></span>  
  
```xml  
<workflowRuntime cachedInstanceExpiration="TimeSpan"  
                                  enablePerformanceCounters="Boolean"  
                                  name="String"  
                                  validateOnCreate="Boolean">  
                 <commonParameters>  
                    <add name="String" value="String" />  
                 </commonParameters>  
                 <services>  
                    <add type="String"/>  
                 </services>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d139-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2d139-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2d139-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2d139-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d139-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="2d139-112">Attributes</span></span>  
  
|<span data-ttu-id="2d139-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="2d139-113">Attribute</span></span>|<span data-ttu-id="2d139-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d139-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2d139-115">cachedInstanceExpiration</span><span class="sxs-lookup"><span data-stu-id="2d139-115">cachedInstanceExpiration</span></span>|<span data-ttu-id="2d139-116">Un valor <xref:System.TimeSpan> opcional que especifica la duración máxima que una instancia de flujo de trabajo puede quedarse en memoria en estado inactivo antes de descargarse o cancelarse de forma obligatoria.</span><span class="sxs-lookup"><span data-stu-id="2d139-116">An optional <xref:System.TimeSpan> value that specifies the maximum duration a workflow instance can stay in-memory in idle state before it is forcefully unloaded or aborted.</span></span> <span data-ttu-id="2d139-117">Si workflowruntime tiene `PersistenceService` que realiza unloadOnIdle, se omite este atributo.</span><span class="sxs-lookup"><span data-stu-id="2d139-117">If the workflowruntime has `PersistenceService` which performs unloadOnIdle, this attribute is ignored.</span></span>|  
|<span data-ttu-id="2d139-118">enablePerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="2d139-118">enablePerformanceCounters</span></span>|<span data-ttu-id="2d139-119">Un valor booleano opcional que especifica si los contadores de rendimiento están habilitados.</span><span class="sxs-lookup"><span data-stu-id="2d139-119">An optional Boolean value that specifies whether performance counters are enabled.</span></span> <span data-ttu-id="2d139-120">Los contadores de rendimiento proporcionan información sobre varias estadísticas relacionadas con el flujo de trabajo, pero producen una reducción del rendimiento al iniciar el motor en tiempo de ejecución del flujo de trabajo, y durante la ejecución de las instancias del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2d139-120">Performance counters provide information on various workflow-related statistics, but they cause a performance penalty when the workflow runtime engine starts, and when workflow instances are running.</span></span> <span data-ttu-id="2d139-121">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="2d139-121">The default value is `true`.</span></span>|  
|<span data-ttu-id="2d139-122">name</span><span class="sxs-lookup"><span data-stu-id="2d139-122">name</span></span>|<span data-ttu-id="2d139-123">Una cadena que contiene el nombre del motor en tiempo de ejecución del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2d139-123">A string containing the name of the workflow runtime engine.</span></span> <span data-ttu-id="2d139-124">El nombre se usa en resultado para distinguir este tiempo de ejecución de otros tiempo de ejecución que se pueden estar ejecutando en el sistema, por ejemplo, en contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="2d139-124">The name is used in output to distinguish this runtime from other runtimes that may be running on the system, for example, in performance counters.</span></span><br /><br /> <span data-ttu-id="2d139-125">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="2d139-125">The default is an empty string.</span></span>|  
|<span data-ttu-id="2d139-126">validateOnCreate</span><span class="sxs-lookup"><span data-stu-id="2d139-126">validateOnCreate</span></span>|<span data-ttu-id="2d139-127">Un valor booleano opcional que especifica si se producirá la validación de definición de flujo de trabajo cuando se abra WorkflowServiceHost.</span><span class="sxs-lookup"><span data-stu-id="2d139-127">An optional Boolean value that specifies whether validation of workflow definition will occur when the WorkflowServiceHost is opened.</span></span>  <span data-ttu-id="2d139-128">Cuando este atributo se establece en `true`, se ejecuta la validación del flujo de trabajo cada vez que se llama a `WorkflowServiceHost.Open`.</span><span class="sxs-lookup"><span data-stu-id="2d139-128">When this attribute is set to `true`, the workflow validation is executed every time `WorkflowServiceHost.Open` is called.</span></span> <span data-ttu-id="2d139-129">Si se encuentran errores de validación, se inicia un error <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException>.</span><span class="sxs-lookup"><span data-stu-id="2d139-129">If validation errors are found, a <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException> error is thrown.</span></span><br /><br /> <span data-ttu-id="2d139-130">Cuando esta propiedad se establece en `false`, no pasará ninguna validación de definición de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2d139-130">When this property is set to `false`, no Workflow definition validation will happen.</span></span><br /><br /> <span data-ttu-id="2d139-131">El valor predeterminado de esta propiedad es `true`.</span><span class="sxs-lookup"><span data-stu-id="2d139-131">The default value for this property is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2d139-132">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2d139-132">Child Elements</span></span>  
  
|<span data-ttu-id="2d139-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="2d139-133">Element</span></span>|<span data-ttu-id="2d139-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d139-134">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2d139-135">commonParameters</span><span class="sxs-lookup"><span data-stu-id="2d139-135">commonParameters</span></span>|<span data-ttu-id="2d139-136">Una colección de parámetros comunes usada por los servicios.</span><span class="sxs-lookup"><span data-stu-id="2d139-136">A collection of common parameters used by services.</span></span> <span data-ttu-id="2d139-137">Esta colección incluirá, normalmente, la cadena de conexión de la base de datos que podrían compartir los servicios duraderos.</span><span class="sxs-lookup"><span data-stu-id="2d139-137">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
|<span data-ttu-id="2d139-138">servicios</span><span class="sxs-lookup"><span data-stu-id="2d139-138">services</span></span>|<span data-ttu-id="2d139-139">Una  colección de servicios que se agregará al motor <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="2d139-139">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="2d139-140">Los elementos son de tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="2d139-140">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="2d139-141">El motor en tiempo de ejecución del flujo de trabajo inicializará y agregará los servicios especificados en la colección a sus servicios cuando se llame al constructor <xref:System.Workflow.Runtime.WorkflowRuntime> adecuado.</span><span class="sxs-lookup"><span data-stu-id="2d139-141">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="2d139-142">Por consiguiente los servicios especificados en la colección deben seguir ciertas reglas sobre las firmas de sus constructores.</span><span class="sxs-lookup"><span data-stu-id="2d139-142">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="2d139-143">Vea <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2d139-143">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2d139-144">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2d139-144">Parent Elements</span></span>  
  
|<span data-ttu-id="2d139-145">Elemento</span><span class="sxs-lookup"><span data-stu-id="2d139-145">Element</span></span>|<span data-ttu-id="2d139-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d139-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d139-147">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="2d139-147">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="2d139-148">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="2d139-148">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d139-149">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2d139-149">Remarks</span></span>  
 <span data-ttu-id="2d139-150">Para obtener más información sobre el uso de un archivo de configuración para controlar el comportamiento de un <xref:System.Workflow.Runtime.WorkflowRuntime> objeto de una aplicación de host de Windows Workflow Foundation, consulte [archivos de configuración de flujo de trabajo](http://msdn.microsoft.com/library/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909).</span><span class="sxs-lookup"><span data-stu-id="2d139-150">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](http://msdn.microsoft.com/library/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d139-151">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2d139-151">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2d139-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d139-152">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 [<span data-ttu-id="2d139-153">Archivos de configuración de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="2d139-153">Workflow Configuration Files</span></span>](http://msdn.microsoft.com/library/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)

---
title: '&lt;commonParameters&gt;'
ms.date: 03/30/2017
ms.assetid: ffc20832-34d6-4622-8174-81924fd53514
ms.openlocfilehash: 5e4c19c48709ffd81cb00e9820e6c3cdb297ec7e
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2018
ms.locfileid: "47027151"
---
# <a name="ltcommonparametersgt"></a><span data-ttu-id="4f6f2-102">&lt;commonParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="4f6f2-102">&lt;commonParameters&gt;</span></span>
<span data-ttu-id="4f6f2-103">Representa una colección de parámetros que se utilizan globalmente en varios servicios.</span><span class="sxs-lookup"><span data-stu-id="4f6f2-103">Represents a collection of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="4f6f2-104">Esta colección incluirá, normalmente, la cadena de conexión de la base de datos que podrían compartir los servicios duraderos.</span><span class="sxs-lookup"><span data-stu-id="4f6f2-104">This collection will typically include the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="4f6f2-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4f6f2-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="4f6f2-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="4f6f2-106">\<behaviors></span></span>  
<span data-ttu-id="4f6f2-107">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="4f6f2-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="4f6f2-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="4f6f2-108">\<behavior></span></span>  
<span data-ttu-id="4f6f2-109">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="4f6f2-109">\<workflowRuntime></span></span>  
<span data-ttu-id="4f6f2-110">\<commonParameters ></span><span class="sxs-lookup"><span data-stu-id="4f6f2-110">\<commonParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f6f2-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f6f2-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>  
   <commonParameters>  
      <add name="String" value="String" />  
   </commonParameters>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f6f2-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4f6f2-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4f6f2-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4f6f2-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f6f2-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="4f6f2-114">Attributes</span></span>  
 <span data-ttu-id="4f6f2-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4f6f2-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4f6f2-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4f6f2-116">Child Elements</span></span>  
  
|<span data-ttu-id="4f6f2-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="4f6f2-117">Element</span></span>|<span data-ttu-id="4f6f2-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f6f2-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f6f2-119">\<add></span><span class="sxs-lookup"><span data-stu-id="4f6f2-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)|<span data-ttu-id="4f6f2-120">Agrega un par de nombre y valor de parámetros comunes utilizados por los servicios para la colección.</span><span class="sxs-lookup"><span data-stu-id="4f6f2-120">Adds a name-value pair of common parameters used by services to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4f6f2-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4f6f2-121">Parent Elements</span></span>  
  
|<span data-ttu-id="4f6f2-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="4f6f2-122">Element</span></span>|<span data-ttu-id="4f6f2-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f6f2-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f6f2-124">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="4f6f2-124">\<workflowRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowruntime.md)|<span data-ttu-id="4f6f2-125">Especifica la configuración de una instancia de <xref:System.Workflow.Runtime.WorkflowRuntime> para hospedar servicios de Windows Communication Foundation (WCF) basados en flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4f6f2-125">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f6f2-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4f6f2-126">Remarks</span></span>  
 <span data-ttu-id="4f6f2-127">El elemento `<commonParameters>` define cualquier parámetro que se usa globalmente en varios servicios, por ejemplo `ConnectionString` al usar <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span><span class="sxs-lookup"><span data-stu-id="4f6f2-127">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f6f2-128">El servicio de seguimiento de SQL no utiliza de forma consistente el valor `ConnectionString` si se especifica en la sección `<commonParameters>`.</span><span class="sxs-lookup"><span data-stu-id="4f6f2-128">SQL Tracking service does not consistently use the `ConnectionString` value if it is specified in the `<commonParameters>` section.</span></span> <span data-ttu-id="4f6f2-129">Es posible que se produzca un error en alguna de sus operaciones, como al recuperar la propiedad `StateMachineWorkflowInstance.StateHistory`.</span><span class="sxs-lookup"><span data-stu-id="4f6f2-129">Some of its operations such as retrieving the `StateMachineWorkflowInstance.StateHistory` property may fail.</span></span> <span data-ttu-id="4f6f2-130">Para solucionar este problema, especifique el atributo `ConnectionString` en la sección de configuración del proveedor de seguimiento, tal y como se indica en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="4f6f2-130">To workaround this, specify the `ConnectionString` attribute in the configuration section for tracking provider, as indicated in the following example.</span></span>  
  
 `<add`  
  
 `type="System.Workflow.Runtime.Tracking.SqlTrackingService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"`  
  
 `ConnectionString="Data Source=localhost;Initial Catalog=Partner20WFTP;Integrated Security=True;" />`  
  
 <span data-ttu-id="4f6f2-131">Puede habilitar los servicios que confirman los lotes de trabajo en los almacenes de persistencia, como <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> y <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, para reintentar su transacción utilizando el parámetro `EnableRetries` como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4f6f2-131">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
```xml  
<WorkflowRuntime Name="SampleApplication" UnloadOnIdle="false">  
    <commonParameters>  
        <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />  
        <add name="EnableRetries" value="True" />  
    </commonParameters>  
    <Services>  
        <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" EnableRetries="False" />   
     </Services>  
</WorkflowRuntime>  
```  
  
 <span data-ttu-id="4f6f2-132">Tenga en cuenta que el `EnableRetries` parámetro puede establecerse en un nivel global (como se muestra en el *CommonParameters* sección) o para servicios individuales que admiten `EnableRetries` (como se muestra en el *servicios*sección).</span><span class="sxs-lookup"><span data-stu-id="4f6f2-132">Notice that the `EnableRetries` parameter can be set either at a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="4f6f2-133">El siguiente código de ejemplo muestra cómo cambiar los parámetros comunes mediante programación.</span><span class="sxs-lookup"><span data-stu-id="4f6f2-133">The following sample code shows how to change the common parameters programmatically.</span></span>  
  
```  
Configuration config=WebConfigurationManager.OpenWebConfiguration("/Workflow", "Default Web Site", null, "localhost");  
WorkflowRuntimeSection wfruntime=config.GetSection("WorkflowRuntime") as WorkflowRuntimeSection;  
NameValueConfigurationCollection commonParameters=wfruntime.CommonParameters;  
commonParameters["ConnectionString"].Value="another connection string";  
config.Save();  
```  
  
 <span data-ttu-id="4f6f2-134">Para obtener más información sobre el uso de un archivo de configuración para controlar el comportamiento de un <xref:System.Workflow.Runtime.WorkflowRuntime> objeto de una aplicación de host de Windows Workflow Foundation, vea [archivos de configuración de flujo de trabajo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="4f6f2-134">For more information about using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f6f2-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4f6f2-135">Example</span></span>  
  
```xml  
<commonParameters>  
   <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;"/>  
   <add name="EnableRetries" value="true"/>  
</commonParameters>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4f6f2-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f6f2-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>  
 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>  
 <span data-ttu-id="4f6f2-137">[Archivos de configuración de flujo de trabajo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="4f6f2-137">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>  
 [<span data-ttu-id="4f6f2-138">\<add></span><span class="sxs-lookup"><span data-stu-id="4f6f2-138">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)

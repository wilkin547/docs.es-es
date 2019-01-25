---
title: '&lt;add&gt; de &lt;commonParameters&gt;'
ms.date: 03/30/2017
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
ms.openlocfilehash: a5de8104b23de37144cb99ef2b90a4161a0396b4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670217"
---
# <a name="ltaddgt-of-ltcommonparametersgt"></a><span data-ttu-id="fc176-102">&lt;add&gt; de &lt;commonParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="fc176-102">&lt;add&gt; of &lt;commonParameters&gt;</span></span>
<span data-ttu-id="fc176-103">Especifica un par de nombre y valor de parámetros que se utilizan globalmente en varios servicios.</span><span class="sxs-lookup"><span data-stu-id="fc176-103">Specifies a name-value pair of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="fc176-104">Normalmente este parámetro incluye la cadena de conexión a la base de datos que podría ser compartida por servicios duraderos.</span><span class="sxs-lookup"><span data-stu-id="fc176-104">Typically this parameter includes the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="fc176-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fc176-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="fc176-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="fc176-106">\<behaviors></span></span>  
<span data-ttu-id="fc176-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="fc176-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="fc176-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="fc176-108">\<behavior></span></span>  
<span data-ttu-id="fc176-109">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="fc176-109">\<workflowRuntime></span></span>  
<span data-ttu-id="fc176-110">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="fc176-110">\<commonParameters></span></span>  
<span data-ttu-id="fc176-111">\<add></span><span class="sxs-lookup"><span data-stu-id="fc176-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc176-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc176-112">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String" value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc176-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fc176-113">Attributes and Elements</span></span>  
 <span data-ttu-id="fc176-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fc176-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc176-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="fc176-115">Attributes</span></span>  
  
|<span data-ttu-id="fc176-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="fc176-116">Attribute</span></span>|<span data-ttu-id="fc176-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc176-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fc176-118">name</span><span class="sxs-lookup"><span data-stu-id="fc176-118">name</span></span>|<span data-ttu-id="fc176-119">El nombre del parámetro especificado para un servicio.</span><span class="sxs-lookup"><span data-stu-id="fc176-119">The name of the parameter specified for a service.</span></span>|  
|<span data-ttu-id="fc176-120">value</span><span class="sxs-lookup"><span data-stu-id="fc176-120">value</span></span>|<span data-ttu-id="fc176-121">El valor del parámetro especificado para un servicio.</span><span class="sxs-lookup"><span data-stu-id="fc176-121">The value of the parameter specified for a service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc176-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fc176-122">Child Elements</span></span>  
 <span data-ttu-id="fc176-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fc176-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fc176-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fc176-124">Parent Elements</span></span>  
  
|<span data-ttu-id="fc176-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="fc176-125">Element</span></span>|<span data-ttu-id="fc176-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc176-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc176-127">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="fc176-127">\<commonParameters></span></span>](https://msdn.microsoft.com/library/d0e1e6fc-985a-4713-b7da-194e30dfab4c)|<span data-ttu-id="fc176-128">Una colección de parámetros comunes usada por los servicios.</span><span class="sxs-lookup"><span data-stu-id="fc176-128">A collection of common parameters used by services.</span></span> <span data-ttu-id="fc176-129">Esta colección incluirá, normalmente, la cadena de conexión de la base de datos que podrían compartir los servicios duraderos.</span><span class="sxs-lookup"><span data-stu-id="fc176-129">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc176-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fc176-130">Remarks</span></span>  
 <span data-ttu-id="fc176-131">El elemento `<commonParameters>` define cualquier parámetro que se usa globalmente en varios servicios, por ejemplo `ConnectionString` al usar <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span><span class="sxs-lookup"><span data-stu-id="fc176-131">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
 <span data-ttu-id="fc176-132">Puede habilitar los servicios que confirman los lotes de trabajo en los almacenes de persistencia, como <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> y <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, para reintentar su transacción utilizando el parámetro `EnableRetries` como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fc176-132">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
```xml  
<workflowRuntime name="SampleApplication"
                 unloadOnIdle="false">
  <commonParameters>
    <add name="ConnectionString"
         value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
    <add name="EnableRetries"
         value="True" />
  </commonParameters>
  <services>
    <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
         enableRetries="False" />
  </services>
</workflowRuntime>
```  
  
 <span data-ttu-id="fc176-133">Tenga en cuenta que el `EnableRetries` parámetro puede establecerse en uno nivel global (como se muestra en el *CommonParameters* sección) o para servicios individuales que admiten `EnableRetries` (como se muestra en el *servicios*sección).</span><span class="sxs-lookup"><span data-stu-id="fc176-133">Notice that the `EnableRetries` parameter can be set at either a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="fc176-134">Para obtener más información sobre el uso de un archivo de configuración para controlar el comportamiento de un <xref:System.Workflow.Runtime.WorkflowRuntime> objeto de una aplicación de host de Windows Workflow Foundation, vea [archivos de configuración de flujo de trabajo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="fc176-134">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc176-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fc176-135">Example</span></span>  
  
```xml  
<commonParameters>
  <add name="ConnectionString"
       value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
  <add name="EnableRetries"
       value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="fc176-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc176-136">See also</span></span>
- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- <span data-ttu-id="fc176-137">[Archivos de configuración de flujo de trabajo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="fc176-137">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
- [<span data-ttu-id="fc176-138">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="fc176-138">\<commonParameters></span></span>](https://msdn.microsoft.com/library/d0e1e6fc-985a-4713-b7da-194e30dfab4c)

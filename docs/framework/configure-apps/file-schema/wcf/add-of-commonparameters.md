---
title: '&lt;add&gt; de &lt;commonParameters&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cdb11f83ed2b7d3d371d7dc5475f4ce3672bb8c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltcommonparametersgt"></a><span data-ttu-id="e06b1-102">&lt;add&gt; de &lt;commonParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="e06b1-102">&lt;add&gt; of &lt;commonParameters&gt;</span></span>
<span data-ttu-id="e06b1-103">Especifica un par de nombre y valor de parámetros que se utilizan globalmente en varios servicios.</span><span class="sxs-lookup"><span data-stu-id="e06b1-103">Specifies a name-value pair of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="e06b1-104">Normalmente este parámetro incluye la cadena de conexión a la base de datos que podría ser compartida por servicios duraderos.</span><span class="sxs-lookup"><span data-stu-id="e06b1-104">Typically this parameter includes the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="e06b1-105">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e06b1-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="e06b1-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="e06b1-106">\<behaviors></span></span>  
<span data-ttu-id="e06b1-107">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e06b1-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="e06b1-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="e06b1-108">\<behavior></span></span>  
<span data-ttu-id="e06b1-109">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="e06b1-109">\<workflowRuntime></span></span>  
<span data-ttu-id="e06b1-110">\<commonParameters ></span><span class="sxs-lookup"><span data-stu-id="e06b1-110">\<commonParameters></span></span>  
<span data-ttu-id="e06b1-111">\<add></span><span class="sxs-lookup"><span data-stu-id="e06b1-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e06b1-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e06b1-112">Syntax</span></span>  
  
```xml  
<workflowRuntime>  
   <commonParameters>  
      <add name="String" value="String" />  
   </commonParameters>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e06b1-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e06b1-113">Attributes and Elements</span></span>  
 <span data-ttu-id="e06b1-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e06b1-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e06b1-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="e06b1-115">Attributes</span></span>  
  
|<span data-ttu-id="e06b1-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="e06b1-116">Attribute</span></span>|<span data-ttu-id="e06b1-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="e06b1-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e06b1-118">name</span><span class="sxs-lookup"><span data-stu-id="e06b1-118">name</span></span>|<span data-ttu-id="e06b1-119">El nombre del parámetro especificado para un servicio.</span><span class="sxs-lookup"><span data-stu-id="e06b1-119">The name of the parameter specified for a service.</span></span>|  
|<span data-ttu-id="e06b1-120">value</span><span class="sxs-lookup"><span data-stu-id="e06b1-120">value</span></span>|<span data-ttu-id="e06b1-121">El valor del parámetro especificado para un servicio.</span><span class="sxs-lookup"><span data-stu-id="e06b1-121">The value of the parameter specified for a service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e06b1-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e06b1-122">Child Elements</span></span>  
 <span data-ttu-id="e06b1-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e06b1-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e06b1-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e06b1-124">Parent Elements</span></span>  
  
|<span data-ttu-id="e06b1-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="e06b1-125">Element</span></span>|<span data-ttu-id="e06b1-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="e06b1-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e06b1-127">\<commonParameters ></span><span class="sxs-lookup"><span data-stu-id="e06b1-127">\<commonParameters></span></span>](http://msdn.microsoft.com/en-us/d0e1e6fc-985a-4713-b7da-194e30dfab4c)|<span data-ttu-id="e06b1-128">Una colección de parámetros comunes usada por los servicios.</span><span class="sxs-lookup"><span data-stu-id="e06b1-128">A collection of common parameters used by services.</span></span> <span data-ttu-id="e06b1-129">Esta colección incluirá, normalmente, la cadena de conexión de la base de datos que podrían compartir los servicios duraderos.</span><span class="sxs-lookup"><span data-stu-id="e06b1-129">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e06b1-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e06b1-130">Remarks</span></span>  
 <span data-ttu-id="e06b1-131">El elemento `<commonParameters>` define cualquier parámetro que se usa globalmente en varios servicios, por ejemplo `ConnectionString` al usar <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span><span class="sxs-lookup"><span data-stu-id="e06b1-131">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
 <span data-ttu-id="e06b1-132">Puede habilitar los servicios que confirman los lotes de trabajo en los almacenes de persistencia, como <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> y <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, para reintentar su transacción utilizando el parámetro `EnableRetries` como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e06b1-132">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
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
  
 <span data-ttu-id="e06b1-133">Tenga en cuenta que la `EnableRetries` parámetro se puede establecer en ninguna globalmente (como se muestra en el *CommonParameters* sección) o para servicios individuales que admiten `EnableRetries` (como se muestra en el *servicios*sección).</span><span class="sxs-lookup"><span data-stu-id="e06b1-133">Notice that the `EnableRetries` parameter can be set at either a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="e06b1-134">Para obtener más información sobre el uso de un archivo de configuración para controlar el comportamiento de un <xref:System.Workflow.Runtime.WorkflowRuntime> objeto de una aplicación de host de Windows Workflow Foundation, consulte [archivos de configuración de flujo de trabajo](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909).</span><span class="sxs-lookup"><span data-stu-id="e06b1-134">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e06b1-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e06b1-135">Example</span></span>  
  
```xml  
<commonParameters>  
   <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;"/>  
   <add name="EnableRetries" value="true"/>  
</commonParameters>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e06b1-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="e06b1-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>  
 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>  
 [<span data-ttu-id="e06b1-137">Archivos de configuración de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="e06b1-137">Workflow Configuration Files</span></span>](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)  
 [<span data-ttu-id="e06b1-138">\<commonParameters ></span><span class="sxs-lookup"><span data-stu-id="e06b1-138">\<commonParameters></span></span>](http://msdn.microsoft.com/en-us/d0e1e6fc-985a-4713-b7da-194e30dfab4c)

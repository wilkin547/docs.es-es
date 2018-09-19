---
title: '&lt;add&gt; de &lt;commonParameters&gt;'
ms.date: 03/30/2017
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
ms.openlocfilehash: 93e82aa3bd44a747d1e85986c51c21522d709bd0
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46287269"
---
# <a name="ltaddgt-of-ltcommonparametersgt"></a><span data-ttu-id="44bca-102">&lt;add&gt; de &lt;commonParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="44bca-102">&lt;add&gt; of &lt;commonParameters&gt;</span></span>
<span data-ttu-id="44bca-103">Especifica un par de nombre y valor de parámetros que se utilizan globalmente en varios servicios.</span><span class="sxs-lookup"><span data-stu-id="44bca-103">Specifies a name-value pair of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="44bca-104">Normalmente este parámetro incluye la cadena de conexión a la base de datos que podría ser compartida por servicios duraderos.</span><span class="sxs-lookup"><span data-stu-id="44bca-104">Typically this parameter includes the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="44bca-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="44bca-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="44bca-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="44bca-106">\<behaviors></span></span>  
<span data-ttu-id="44bca-107">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="44bca-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="44bca-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="44bca-108">\<behavior></span></span>  
<span data-ttu-id="44bca-109">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="44bca-109">\<workflowRuntime></span></span>  
<span data-ttu-id="44bca-110">\<commonParameters ></span><span class="sxs-lookup"><span data-stu-id="44bca-110">\<commonParameters></span></span>  
<span data-ttu-id="44bca-111">\<add></span><span class="sxs-lookup"><span data-stu-id="44bca-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44bca-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44bca-112">Syntax</span></span>  
  
```xml  
<workflowRuntime>  
   <commonParameters>  
      <add name="String" value="String" />  
   </commonParameters>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44bca-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="44bca-113">Attributes and Elements</span></span>  
 <span data-ttu-id="44bca-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="44bca-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44bca-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="44bca-115">Attributes</span></span>  
  
|<span data-ttu-id="44bca-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="44bca-116">Attribute</span></span>|<span data-ttu-id="44bca-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="44bca-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="44bca-118">name</span><span class="sxs-lookup"><span data-stu-id="44bca-118">name</span></span>|<span data-ttu-id="44bca-119">El nombre del parámetro especificado para un servicio.</span><span class="sxs-lookup"><span data-stu-id="44bca-119">The name of the parameter specified for a service.</span></span>|  
|<span data-ttu-id="44bca-120">value</span><span class="sxs-lookup"><span data-stu-id="44bca-120">value</span></span>|<span data-ttu-id="44bca-121">El valor del parámetro especificado para un servicio.</span><span class="sxs-lookup"><span data-stu-id="44bca-121">The value of the parameter specified for a service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44bca-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="44bca-122">Child Elements</span></span>  
 <span data-ttu-id="44bca-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="44bca-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="44bca-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="44bca-124">Parent Elements</span></span>  
  
|<span data-ttu-id="44bca-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="44bca-125">Element</span></span>|<span data-ttu-id="44bca-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="44bca-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44bca-127">\<commonParameters ></span><span class="sxs-lookup"><span data-stu-id="44bca-127">\<commonParameters></span></span>](https://msdn.microsoft.com/library/d0e1e6fc-985a-4713-b7da-194e30dfab4c)|<span data-ttu-id="44bca-128">Una colección de parámetros comunes usada por los servicios.</span><span class="sxs-lookup"><span data-stu-id="44bca-128">A collection of common parameters used by services.</span></span> <span data-ttu-id="44bca-129">Esta colección incluirá, normalmente, la cadena de conexión de la base de datos que podrían compartir los servicios duraderos.</span><span class="sxs-lookup"><span data-stu-id="44bca-129">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44bca-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="44bca-130">Remarks</span></span>  
 <span data-ttu-id="44bca-131">El elemento `<commonParameters>` define cualquier parámetro que se usa globalmente en varios servicios, por ejemplo `ConnectionString` al usar <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span><span class="sxs-lookup"><span data-stu-id="44bca-131">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
 <span data-ttu-id="44bca-132">Puede habilitar los servicios que confirman los lotes de trabajo en los almacenes de persistencia, como <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> y <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, para reintentar su transacción utilizando el parámetro `EnableRetries` como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="44bca-132">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
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
  
 <span data-ttu-id="44bca-133">Tenga en cuenta que el `EnableRetries` parámetro puede establecerse en uno nivel global (como se muestra en el *CommonParameters* sección) o para servicios individuales que admiten `EnableRetries` (como se muestra en el *servicios*sección).</span><span class="sxs-lookup"><span data-stu-id="44bca-133">Notice that the `EnableRetries` parameter can be set at either a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="44bca-134">Para obtener más información sobre el uso de un archivo de configuración para controlar el comportamiento de un <xref:System.Workflow.Runtime.WorkflowRuntime> objeto de una aplicación de host de Windows Workflow Foundation, vea [archivos de configuración de flujo de trabajo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="44bca-134">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="44bca-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="44bca-135">Example</span></span>  
  
```xml  
<commonParameters>  
   <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;"/>  
   <add name="EnableRetries" value="true"/>  
</commonParameters>  
```  
  
## <a name="see-also"></a><span data-ttu-id="44bca-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="44bca-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>  
 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>  
 <span data-ttu-id="44bca-137">[Archivos de configuración de flujo de trabajo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="44bca-137">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>  
 [<span data-ttu-id="44bca-138">\<commonParameters ></span><span class="sxs-lookup"><span data-stu-id="44bca-138">\<commonParameters></span></span>](https://msdn.microsoft.com/library/d0e1e6fc-985a-4713-b7da-194e30dfab4c)

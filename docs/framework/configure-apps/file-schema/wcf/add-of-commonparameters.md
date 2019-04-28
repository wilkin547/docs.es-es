---
title: <add> de <commonParameters>
ms.date: 03/30/2017
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
ms.openlocfilehash: 6aaba3f82966ad4496e6edaae06b5d7a8aef3863
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673659"
---
# <a name="add-of-commonparameters"></a><span data-ttu-id="10fc9-102">\<Agregar > de \<commonParameters ></span><span class="sxs-lookup"><span data-stu-id="10fc9-102">\<add> of \<commonParameters></span></span>
<span data-ttu-id="10fc9-103">Especifica un par de nombre y valor de parámetros que se utilizan globalmente en varios servicios.</span><span class="sxs-lookup"><span data-stu-id="10fc9-103">Specifies a name-value pair of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="10fc9-104">Normalmente este parámetro incluye la cadena de conexión a la base de datos que podría ser compartida por servicios duraderos.</span><span class="sxs-lookup"><span data-stu-id="10fc9-104">Typically this parameter includes the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="10fc9-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="10fc9-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="10fc9-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="10fc9-106">\<behaviors></span></span>  
<span data-ttu-id="10fc9-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="10fc9-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="10fc9-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="10fc9-108">\<behavior></span></span>  
<span data-ttu-id="10fc9-109">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="10fc9-109">\<workflowRuntime></span></span>  
<span data-ttu-id="10fc9-110">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="10fc9-110">\<commonParameters></span></span>  
<span data-ttu-id="10fc9-111">\<add></span><span class="sxs-lookup"><span data-stu-id="10fc9-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10fc9-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="10fc9-112">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String" value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10fc9-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="10fc9-113">Attributes and Elements</span></span>  
 <span data-ttu-id="10fc9-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="10fc9-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10fc9-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="10fc9-115">Attributes</span></span>  
  
|<span data-ttu-id="10fc9-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="10fc9-116">Attribute</span></span>|<span data-ttu-id="10fc9-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="10fc9-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="10fc9-118">name</span><span class="sxs-lookup"><span data-stu-id="10fc9-118">name</span></span>|<span data-ttu-id="10fc9-119">El nombre del parámetro especificado para un servicio.</span><span class="sxs-lookup"><span data-stu-id="10fc9-119">The name of the parameter specified for a service.</span></span>|  
|<span data-ttu-id="10fc9-120">value</span><span class="sxs-lookup"><span data-stu-id="10fc9-120">value</span></span>|<span data-ttu-id="10fc9-121">El valor del parámetro especificado para un servicio.</span><span class="sxs-lookup"><span data-stu-id="10fc9-121">The value of the parameter specified for a service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="10fc9-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="10fc9-122">Child Elements</span></span>  
 <span data-ttu-id="10fc9-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="10fc9-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="10fc9-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="10fc9-124">Parent Elements</span></span>  
  
|<span data-ttu-id="10fc9-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="10fc9-125">Element</span></span>|<span data-ttu-id="10fc9-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="10fc9-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="10fc9-127">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="10fc9-127">\<commonParameters></span></span>](commonparameters.md)|<span data-ttu-id="10fc9-128">Una colección de parámetros comunes usada por los servicios.</span><span class="sxs-lookup"><span data-stu-id="10fc9-128">A collection of common parameters used by services.</span></span> <span data-ttu-id="10fc9-129">Esta colección incluirá, normalmente, la cadena de conexión de la base de datos que podrían compartir los servicios duraderos.</span><span class="sxs-lookup"><span data-stu-id="10fc9-129">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10fc9-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="10fc9-130">Remarks</span></span>  
 <span data-ttu-id="10fc9-131">El elemento `<commonParameters>` define cualquier parámetro que se usa globalmente en varios servicios, por ejemplo `ConnectionString` al usar <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span><span class="sxs-lookup"><span data-stu-id="10fc9-131">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
 <span data-ttu-id="10fc9-132">Puede habilitar los servicios que confirman los lotes de trabajo en los almacenes de persistencia, como <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> y <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, para reintentar su transacción utilizando el parámetro `EnableRetries` como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="10fc9-132">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
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
  
 <span data-ttu-id="10fc9-133">Tenga en cuenta que el `EnableRetries` parámetro puede establecerse en uno nivel global (como se muestra en el *CommonParameters* sección) o para servicios individuales que admiten `EnableRetries` (como se muestra en el *servicios*sección).</span><span class="sxs-lookup"><span data-stu-id="10fc9-133">Notice that the `EnableRetries` parameter can be set at either a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="10fc9-134">Para obtener más información sobre el uso de un archivo de configuración para controlar el comportamiento de un <xref:System.Workflow.Runtime.WorkflowRuntime> objeto de una aplicación de host de Windows Workflow Foundation, vea [archivos de configuración de flujo de trabajo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="10fc9-134">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="10fc9-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="10fc9-135">Example</span></span>  
  
```xml  
<commonParameters>
  <add name="ConnectionString"
       value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
  <add name="EnableRetries"
       value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="10fc9-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="10fc9-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- <span data-ttu-id="10fc9-137">[Archivos de configuración de flujo de trabajo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="10fc9-137">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
- [<span data-ttu-id="10fc9-138">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="10fc9-138">\<commonParameters></span></span>](commonparameters.md)

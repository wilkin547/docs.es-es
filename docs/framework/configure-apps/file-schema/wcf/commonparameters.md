---
title: <commonParameters>
ms.date: 03/30/2017
ms.assetid: ffc20832-34d6-4622-8174-81924fd53514
ms.openlocfilehash: 73d8549f68e8ca77115619431c857c4a2aac3fdf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153027"
---
# <a name="commonparameters"></a><span data-ttu-id="c55a2-101">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="c55a2-101">\<commonParameters></span></span>
<span data-ttu-id="c55a2-102">Representa una colección de parámetros que se utilizan globalmente en varios servicios.</span><span class="sxs-lookup"><span data-stu-id="c55a2-102">Represents a collection of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="c55a2-103">Esta colección incluirá, normalmente, la cadena de conexión de la base de datos que podrían compartir los servicios duraderos.</span><span class="sxs-lookup"><span data-stu-id="c55a2-103">This collection will typically include the database connection string that might be shared by durable services.</span></span>  
  
<span data-ttu-id="c55a2-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c55a2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c55a2-105">&nbsp;&nbsp;[**\<>system.serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c55a2-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c55a2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<comportamientos>**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c55a2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="c55a2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c55a2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="c55a2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comportamiento>**](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c55a2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="c55a2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowRuntime>**](workflowruntime.md)</span><span class="sxs-lookup"><span data-stu-id="c55a2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowRuntime>**](workflowruntime.md)</span></span>\
<span data-ttu-id="c55a2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<commonParameters>**</span><span class="sxs-lookup"><span data-stu-id="c55a2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<commonParameters>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c55a2-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c55a2-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String"
         value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c55a2-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c55a2-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c55a2-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c55a2-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c55a2-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="c55a2-114">Attributes</span></span>  
 <span data-ttu-id="c55a2-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c55a2-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c55a2-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c55a2-116">Child Elements</span></span>  
  
|<span data-ttu-id="c55a2-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="c55a2-117">Element</span></span>|<span data-ttu-id="c55a2-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="c55a2-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c55a2-119">\<añadir></span><span class="sxs-lookup"><span data-stu-id="c55a2-119">\<add></span></span>](add-of-commonparameters.md)|<span data-ttu-id="c55a2-120">Agrega un par de nombre y valor de parámetros comunes utilizados por los servicios para la colección.</span><span class="sxs-lookup"><span data-stu-id="c55a2-120">Adds a name-value pair of common parameters used by services to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c55a2-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c55a2-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c55a2-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="c55a2-122">Element</span></span>|<span data-ttu-id="c55a2-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="c55a2-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c55a2-124">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="c55a2-124">\<workflowRuntime></span></span>](workflowruntime.md)|<span data-ttu-id="c55a2-125">Especifica la configuración de <xref:System.Workflow.Runtime.WorkflowRuntime> una instancia de hospedar servicios de Windows Communication Foundation (WCF) basados en flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c55a2-125">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c55a2-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c55a2-126">Remarks</span></span>  
 <span data-ttu-id="c55a2-127">El elemento `<commonParameters>` define cualquier parámetro que se usa globalmente en varios servicios, por ejemplo `ConnectionString` al usar <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span><span class="sxs-lookup"><span data-stu-id="c55a2-127">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c55a2-128">El servicio de seguimiento de SQL no utiliza de forma consistente el valor `ConnectionString` si se especifica en la sección `<commonParameters>`.</span><span class="sxs-lookup"><span data-stu-id="c55a2-128">SQL Tracking service does not consistently use the `ConnectionString` value if it is specified in the `<commonParameters>` section.</span></span> <span data-ttu-id="c55a2-129">Es posible que se produzca un error en alguna de sus operaciones, como al recuperar la propiedad `StateMachineWorkflowInstance.StateHistory`.</span><span class="sxs-lookup"><span data-stu-id="c55a2-129">Some of its operations such as retrieving the `StateMachineWorkflowInstance.StateHistory` property may fail.</span></span> <span data-ttu-id="c55a2-130">Para solucionar este problema, especifique el atributo `ConnectionString` en la sección de configuración del proveedor de seguimiento, tal y como se indica en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c55a2-130">To workaround this, specify the `ConnectionString` attribute in the configuration section for tracking provider, as indicated in the following example.</span></span>  

```xml  
<add
type="System.Workflow.Runtime.Tracking.SqlTrackingService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
ConnectionString="Data Source=localhost;Initial Catalog=Partner20WFTP;Integrated Security=True;" />
```  
  
 <span data-ttu-id="c55a2-131">Puede habilitar los servicios que confirman los lotes de trabajo en los almacenes de persistencia, como <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> y <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, para reintentar su transacción utilizando el parámetro `EnableRetries` como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c55a2-131">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
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
    <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime,
               Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
         enableRetries="False" />
  </services>
</workflowRuntime>
```  
  
 <span data-ttu-id="c55a2-132">Observe que `EnableRetries` el parámetro se puede establecer a nivel global (como se muestra `EnableRetries` en la sección *CommonParameters)* o para servicios individuales que admiten (como se muestra en la sección *Servicios).*</span><span class="sxs-lookup"><span data-stu-id="c55a2-132">Notice that the `EnableRetries` parameter can be set either at a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="c55a2-133">El siguiente código de ejemplo muestra cómo cambiar los parámetros comunes mediante programación:</span><span class="sxs-lookup"><span data-stu-id="c55a2-133">The following sample code shows how to change the common parameters programmatically:</span></span>
  
```csharp  
Configuration config = WebConfigurationManager.OpenWebConfiguration("/Workflow", "Default Web Site", null, "localhost");
var wfruntime = config.GetSection("WorkflowRuntime") as WorkflowRuntimeSection;  
NameValueConfigurationCollection commonParameters = wfruntime.CommonParameters;
commonParameters["ConnectionString"].Value="another connection string";  
config.Save();  
```  
  
 <span data-ttu-id="c55a2-134">Para obtener más información sobre el uso <xref:System.Workflow.Runtime.WorkflowRuntime> de un archivo de configuración para controlar el comportamiento de un objeto de una aplicación host de Windows Workflow Foundation, vea Archivos de [configuración](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))de flujo de trabajo .</span><span class="sxs-lookup"><span data-stu-id="c55a2-134">For more information about using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c55a2-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c55a2-135">Example</span></span>  
  
```xml  
<commonParameters>
   <add name="ConnectionString"
        value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
   <add name="EnableRetries"
        value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="c55a2-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c55a2-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- <span data-ttu-id="c55a2-137">[Archivos de configuración del flujo de trabajo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="c55a2-137">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
- [<span data-ttu-id="c55a2-138">\<añadir></span><span class="sxs-lookup"><span data-stu-id="c55a2-138">\<add></span></span>](add-of-commonparameters.md)

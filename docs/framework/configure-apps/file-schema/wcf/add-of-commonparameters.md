---
title: <add> de <commonParameters>
ms.date: 03/30/2017
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
ms.openlocfilehash: d682acd7fff6bab2c66660a028f8a75b780e21d2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400666"
---
# <a name="add-of-commonparameters"></a><span data-ttu-id="ff700-102">\<Agregar > de \<commonParameters ></span><span class="sxs-lookup"><span data-stu-id="ff700-102">\<add> of \<commonParameters></span></span>
<span data-ttu-id="ff700-103">Especifica un par de nombre y valor de parámetros que se utilizan globalmente en varios servicios.</span><span class="sxs-lookup"><span data-stu-id="ff700-103">Specifies a name-value pair of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="ff700-104">Normalmente este parámetro incluye la cadena de conexión a la base de datos que podría ser compartida por servicios duraderos.</span><span class="sxs-lookup"><span data-stu-id="ff700-104">Typically this parameter includes the database connection string that might be shared by durable services.</span></span>  
  
<span data-ttu-id="ff700-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ff700-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ff700-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ff700-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ff700-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ff700-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="ff700-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ff700-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="ff700-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ff700-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="ff700-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> workflowRuntime**](workflowruntime.md)</span><span class="sxs-lookup"><span data-stu-id="ff700-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowRuntime>**](workflowruntime.md)</span></span>\
<span data-ttu-id="ff700-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> commonParameters**](commonparameters.md)</span><span class="sxs-lookup"><span data-stu-id="ff700-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<commonParameters>**](commonparameters.md)</span></span>\
<span data-ttu-id="ff700-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Agregar >**</span><span class="sxs-lookup"><span data-stu-id="ff700-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff700-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff700-113">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String" value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff700-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ff700-114">Attributes and Elements</span></span>  
 <span data-ttu-id="ff700-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ff700-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff700-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="ff700-116">Attributes</span></span>  
  
|<span data-ttu-id="ff700-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="ff700-117">Attribute</span></span>|<span data-ttu-id="ff700-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ff700-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ff700-119">Nombre</span><span class="sxs-lookup"><span data-stu-id="ff700-119">name</span></span>|<span data-ttu-id="ff700-120">El nombre del parámetro especificado para un servicio.</span><span class="sxs-lookup"><span data-stu-id="ff700-120">The name of the parameter specified for a service.</span></span>|  
|<span data-ttu-id="ff700-121">valor</span><span class="sxs-lookup"><span data-stu-id="ff700-121">value</span></span>|<span data-ttu-id="ff700-122">El valor del parámetro especificado para un servicio.</span><span class="sxs-lookup"><span data-stu-id="ff700-122">The value of the parameter specified for a service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ff700-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ff700-123">Child Elements</span></span>  
 <span data-ttu-id="ff700-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ff700-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ff700-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ff700-125">Parent Elements</span></span>  
  
|<span data-ttu-id="ff700-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="ff700-126">Element</span></span>|<span data-ttu-id="ff700-127">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ff700-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff700-128">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="ff700-128">\<commonParameters></span></span>](commonparameters.md)|<span data-ttu-id="ff700-129">Una colección de parámetros comunes usada por los servicios.</span><span class="sxs-lookup"><span data-stu-id="ff700-129">A collection of common parameters used by services.</span></span> <span data-ttu-id="ff700-130">Esta colección incluirá, normalmente, la cadena de conexión de la base de datos que podrían compartir los servicios duraderos.</span><span class="sxs-lookup"><span data-stu-id="ff700-130">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff700-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ff700-131">Remarks</span></span>  
 <span data-ttu-id="ff700-132">El elemento `<commonParameters>` define cualquier parámetro que se usa globalmente en varios servicios, por ejemplo `ConnectionString` al usar <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span><span class="sxs-lookup"><span data-stu-id="ff700-132">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
 <span data-ttu-id="ff700-133">Puede habilitar los servicios que confirman los lotes de trabajo en los almacenes de persistencia, como <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> y <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, para reintentar su transacción utilizando el parámetro `EnableRetries` como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff700-133">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
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
  
 <span data-ttu-id="ff700-134">Observe que el `EnableRetries` parámetro se puede establecer en un nivel global (como se muestra en la sección *CommonParameters* ) o para servicios individuales que admiten `EnableRetries` (como se muestra en la sección *servicios* ).</span><span class="sxs-lookup"><span data-stu-id="ff700-134">Notice that the `EnableRetries` parameter can be set at either a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="ff700-135">Para obtener más información sobre el uso de un archivo de configuración para controlar <xref:System.Workflow.Runtime.WorkflowRuntime> el comportamiento de un objeto de una aplicación host de Windows Workflow Foundation, consulte [archivos de configuración de flujo de trabajo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="ff700-135">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff700-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ff700-136">Example</span></span>  
  
```xml  
<commonParameters>
  <add name="ConnectionString"
       value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
  <add name="EnableRetries"
       value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="ff700-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff700-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- <span data-ttu-id="ff700-138">[Archivos de configuración de flujo de trabajo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="ff700-138">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
- [<span data-ttu-id="ff700-139">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="ff700-139">\<commonParameters></span></span>](commonparameters.md)

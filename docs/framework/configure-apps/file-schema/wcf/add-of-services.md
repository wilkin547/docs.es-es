---
title: <add> de <services>
ms.date: 03/30/2017
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
ms.openlocfilehash: 31a4d2a5a3baf3d53cf18ab6e37edfaf7acb8540
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204988"
---
# <a name="add-of-services"></a><span data-ttu-id="54fea-102">\<add> de \<services></span><span class="sxs-lookup"><span data-stu-id="54fea-102">\<add> of \<services></span></span>

<span data-ttu-id="54fea-103">Especifica la configuración de una instancia de <xref:System.Workflow.Runtime.WorkflowRuntime> para hospedar servicios de Windows Communication Foundation basados en el flujo de trabajo (WCF).</span><span class="sxs-lookup"><span data-stu-id="54fea-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="54fea-104">Este elemento es del tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="54fea-104">This element is of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowRuntime>**](workflowruntime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services-of-workflowruntime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="54fea-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54fea-105">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <services>
    <add type="String" />
  </services>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="54fea-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="54fea-106">Attributes and Elements</span></span>  

 <span data-ttu-id="54fea-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="54fea-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="54fea-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="54fea-108">Attributes</span></span>  
  
|<span data-ttu-id="54fea-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="54fea-109">Attribute</span></span>|<span data-ttu-id="54fea-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="54fea-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="54fea-111">type</span><span class="sxs-lookup"><span data-stu-id="54fea-111">type</span></span>|<span data-ttu-id="54fea-112">Una cadena que especifica el nombre de tipo calificado con el nombre de ensamblado del servicio que se va a inicializar.</span><span class="sxs-lookup"><span data-stu-id="54fea-112">A string that specifies the assembly-qualified type name of the service to be initialized.</span></span> <span data-ttu-id="54fea-113">El servicio especificado debe seguir ciertas reglas sobre las firmas de sus constructores.</span><span class="sxs-lookup"><span data-stu-id="54fea-113">The service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="54fea-114">Vea <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="54fea-114">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="54fea-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="54fea-115">Child Elements</span></span>  

 <span data-ttu-id="54fea-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="54fea-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="54fea-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="54fea-117">Parent Elements</span></span>  
  
|<span data-ttu-id="54fea-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="54fea-118">Element</span></span>|<span data-ttu-id="54fea-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="54fea-119">Description</span></span>|  
|-------------|-----------------|  
|[\<services>](services-of-workflowruntime.md)|<span data-ttu-id="54fea-120">Una colección de servicios que se agregará al motor <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="54fea-120">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="54fea-121">Los elementos son de tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="54fea-121">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="54fea-122">El motor en tiempo de ejecución del flujo de trabajo inicializará y agregará los servicios especificados en la colección a sus servicios cuando se llame al constructor <xref:System.Workflow.Runtime.WorkflowRuntime> adecuado.</span><span class="sxs-lookup"><span data-stu-id="54fea-122">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="54fea-123">Por consiguiente los servicios especificados en la colección deben seguir ciertas reglas sobre las firmas de sus constructores.</span><span class="sxs-lookup"><span data-stu-id="54fea-123">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="54fea-124">Vea <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="54fea-124">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54fea-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="54fea-125">Remarks</span></span>  

 <span data-ttu-id="54fea-126">El motor en tiempo de ejecución del flujo de trabajo inicializará y agregará el servicio especificado a sus servicios cuando se llame al constructor <xref:System.Workflow.Runtime.WorkflowRuntime> adecuado.</span><span class="sxs-lookup"><span data-stu-id="54fea-126">The service specified in this element will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="54fea-127">Por consiguiente, el servicio especificado debe seguir ciertas reglas sobre las firmas de sus constructores.</span><span class="sxs-lookup"><span data-stu-id="54fea-127">Therefore, the service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="54fea-128">Vea <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="54fea-128">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54fea-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="54fea-129">Example</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="ServiceBehavior">
    <workflowRuntime name="WorkflowServiceHostRuntime"
                     validateOnCreate="true"
                     enablePerformanceCounters="true">
      <services>
        <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common" />
      </services>
    </workflowRuntime>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="54fea-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="54fea-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <span data-ttu-id="54fea-131">[Archivos de configuración del flujo de trabajo](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="54fea-131">[Workflow Configuration Files](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>

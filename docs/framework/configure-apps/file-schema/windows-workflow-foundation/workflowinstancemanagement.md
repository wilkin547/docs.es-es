---
title: '&lt;workflowInstanceManagement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3be696133bff5c1fc8858ab31093866ed05c98a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltworkflowinstancemanagementgt"></a><span data-ttu-id="79ad5-102">&lt;workflowInstanceManagement&gt;</span><span class="sxs-lookup"><span data-stu-id="79ad5-102">&lt;workflowInstanceManagement&gt;</span></span>
<span data-ttu-id="79ad5-103">Un comportamiento del servicio que permite especificar valores que controlan cómo se ejecutan las instancias de flujo de trabajo, incluida la conservación, el comportamiento de la excepción no controlada y el comportamiento inactivo.</span><span class="sxs-lookup"><span data-stu-id="79ad5-103">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="79ad5-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="79ad5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="79ad5-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="79ad5-105">\<behaviors></span></span>  
<span data-ttu-id="79ad5-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="79ad5-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="79ad5-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="79ad5-107">\<behavior></span></span>  
<span data-ttu-id="79ad5-108">\<workflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="79ad5-108">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79ad5-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="79ad5-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79ad5-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="79ad5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="79ad5-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="79ad5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79ad5-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="79ad5-112">Attributes</span></span>  
  
|<span data-ttu-id="79ad5-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="79ad5-113">Attribute</span></span>|<span data-ttu-id="79ad5-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="79ad5-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="79ad5-115">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="79ad5-115">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="79ad5-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="79ad5-116">Child Elements</span></span>  
 <span data-ttu-id="79ad5-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="79ad5-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="79ad5-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="79ad5-118">Parent Elements</span></span>  
  
|<span data-ttu-id="79ad5-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="79ad5-119">Element</span></span>|<span data-ttu-id="79ad5-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="79ad5-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="79ad5-121">\<comportamiento > de \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="79ad5-121">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="79ad5-122">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="79ad5-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="79ad5-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="79ad5-123">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>

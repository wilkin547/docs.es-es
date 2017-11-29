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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9883cedbbe3657eb82c25abbad66487e39ce2579
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltworkflowinstancemanagementgt"></a><span data-ttu-id="bcaf7-102">&lt;workflowInstanceManagement&gt;</span><span class="sxs-lookup"><span data-stu-id="bcaf7-102">&lt;workflowInstanceManagement&gt;</span></span>
<span data-ttu-id="bcaf7-103">Un comportamiento del servicio que permite especificar valores que controlan cómo se ejecutan las instancias de flujo de trabajo, incluida la conservación, el comportamiento de la excepción no controlada y el comportamiento inactivo.</span><span class="sxs-lookup"><span data-stu-id="bcaf7-103">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="bcaf7-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="bcaf7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="bcaf7-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="bcaf7-105">\<behaviors></span></span>  
<span data-ttu-id="bcaf7-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="bcaf7-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="bcaf7-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="bcaf7-107">\<behavior></span></span>  
<span data-ttu-id="bcaf7-108">\<workflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="bcaf7-108">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcaf7-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bcaf7-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bcaf7-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bcaf7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bcaf7-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bcaf7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bcaf7-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="bcaf7-112">Attributes</span></span>  
  
|<span data-ttu-id="bcaf7-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="bcaf7-113">Attribute</span></span>|<span data-ttu-id="bcaf7-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="bcaf7-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bcaf7-115">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="bcaf7-115">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="bcaf7-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bcaf7-116">Child Elements</span></span>  
 <span data-ttu-id="bcaf7-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bcaf7-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bcaf7-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bcaf7-118">Parent Elements</span></span>  
  
|<span data-ttu-id="bcaf7-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="bcaf7-119">Element</span></span>|<span data-ttu-id="bcaf7-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="bcaf7-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bcaf7-121">\<comportamiento > de \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="bcaf7-121">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="bcaf7-122">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="bcaf7-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bcaf7-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="bcaf7-123">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>

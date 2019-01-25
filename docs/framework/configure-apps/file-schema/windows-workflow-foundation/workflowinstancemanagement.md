---
title: '&lt;workflowInstanceManagement&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: ba3d9415efc21012b470fd2e9a7f426ca8f3aad1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662067"
---
# <a name="ltworkflowinstancemanagementgt"></a><span data-ttu-id="b8dc4-102">&lt;workflowInstanceManagement&gt;</span><span class="sxs-lookup"><span data-stu-id="b8dc4-102">&lt;workflowInstanceManagement&gt;</span></span>
<span data-ttu-id="b8dc4-103">Un comportamiento del servicio que permite especificar valores que controlan cómo se ejecutan las instancias de flujo de trabajo, incluida la conservación, el comportamiento de la excepción no controlada y el comportamiento inactivo.</span><span class="sxs-lookup"><span data-stu-id="b8dc4-103">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="b8dc4-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b8dc4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b8dc4-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="b8dc4-105">\<behaviors></span></span>  
<span data-ttu-id="b8dc4-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="b8dc4-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="b8dc4-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="b8dc4-107">\<behavior></span></span>  
<span data-ttu-id="b8dc4-108">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="b8dc4-108">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8dc4-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8dc4-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8dc4-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b8dc4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b8dc4-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b8dc4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8dc4-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="b8dc4-112">Attributes</span></span>  
  
|<span data-ttu-id="b8dc4-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="b8dc4-113">Attribute</span></span>|<span data-ttu-id="b8dc4-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8dc4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b8dc4-115">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="b8dc4-115">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="b8dc4-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b8dc4-116">Child Elements</span></span>  
 <span data-ttu-id="b8dc4-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b8dc4-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b8dc4-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b8dc4-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b8dc4-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="b8dc4-119">Element</span></span>|<span data-ttu-id="b8dc4-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8dc4-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8dc4-121">\<comportamiento > de \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="b8dc4-121">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="b8dc4-122">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="b8dc4-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b8dc4-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8dc4-123">See also</span></span>
- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>

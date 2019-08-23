---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: a22c72b7a683e3ecab4344c92e7d835a184a58d5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947161"
---
# <a name="workflowinstancemanagement"></a><span data-ttu-id="6aec3-101">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="6aec3-101">\<workflowInstanceManagement></span></span>
<span data-ttu-id="6aec3-102">Un comportamiento del servicio que permite especificar valores que controlan cómo se ejecutan las instancias de flujo de trabajo, incluida la conservación, el comportamiento de la excepción no controlada y el comportamiento inactivo.</span><span class="sxs-lookup"><span data-stu-id="6aec3-102">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="6aec3-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6aec3-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="6aec3-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="6aec3-104">\<behaviors></span></span>  
<span data-ttu-id="6aec3-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="6aec3-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="6aec3-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="6aec3-106">\<behavior></span></span>  
<span data-ttu-id="6aec3-107">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="6aec3-107">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6aec3-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6aec3-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6aec3-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6aec3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6aec3-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6aec3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6aec3-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="6aec3-111">Attributes</span></span>  
  
|<span data-ttu-id="6aec3-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="6aec3-112">Attribute</span></span>|<span data-ttu-id="6aec3-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6aec3-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6aec3-114">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="6aec3-114">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="6aec3-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6aec3-115">Child Elements</span></span>  
 <span data-ttu-id="6aec3-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6aec3-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6aec3-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6aec3-117">Parent Elements</span></span>  
  
|<span data-ttu-id="6aec3-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="6aec3-118">Element</span></span>|<span data-ttu-id="6aec3-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6aec3-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6aec3-120">\<comportamiento > de \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="6aec3-120">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="6aec3-121">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="6aec3-121">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6aec3-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="6aec3-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>

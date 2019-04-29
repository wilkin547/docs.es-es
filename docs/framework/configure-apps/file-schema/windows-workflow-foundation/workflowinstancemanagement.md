---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: 98bc1b24da6e65a11a39d133057c1bb55b003a58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61613468"
---
# <a name="workflowinstancemanagement"></a><span data-ttu-id="275c6-101">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="275c6-101">\<workflowInstanceManagement></span></span>
<span data-ttu-id="275c6-102">Un comportamiento del servicio que permite especificar valores que controlan cómo se ejecutan las instancias de flujo de trabajo, incluida la conservación, el comportamiento de la excepción no controlada y el comportamiento inactivo.</span><span class="sxs-lookup"><span data-stu-id="275c6-102">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="275c6-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="275c6-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="275c6-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="275c6-104">\<behaviors></span></span>  
<span data-ttu-id="275c6-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="275c6-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="275c6-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="275c6-106">\<behavior></span></span>  
<span data-ttu-id="275c6-107">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="275c6-107">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="275c6-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="275c6-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="275c6-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="275c6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="275c6-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="275c6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="275c6-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="275c6-111">Attributes</span></span>  
  
|<span data-ttu-id="275c6-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="275c6-112">Attribute</span></span>|<span data-ttu-id="275c6-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="275c6-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="275c6-114">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="275c6-114">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="275c6-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="275c6-115">Child Elements</span></span>  
 <span data-ttu-id="275c6-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="275c6-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="275c6-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="275c6-117">Parent Elements</span></span>  
  
|<span data-ttu-id="275c6-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="275c6-118">Element</span></span>|<span data-ttu-id="275c6-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="275c6-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="275c6-120">\<comportamiento > de \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="275c6-120">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="275c6-121">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="275c6-121">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="275c6-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="275c6-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>

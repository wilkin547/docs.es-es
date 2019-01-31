---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: baa1ccbe0accd2db701fac9ef53cdc6357713c5d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257426"
---
# <a name="workflowinstancemanagement"></a><span data-ttu-id="fb9be-101">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="fb9be-101">\<workflowInstanceManagement></span></span>
<span data-ttu-id="fb9be-102">Un comportamiento del servicio que permite especificar valores que controlan cómo se ejecutan las instancias de flujo de trabajo, incluida la conservación, el comportamiento de la excepción no controlada y el comportamiento inactivo.</span><span class="sxs-lookup"><span data-stu-id="fb9be-102">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="fb9be-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fb9be-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="fb9be-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="fb9be-104">\<behaviors></span></span>  
<span data-ttu-id="fb9be-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="fb9be-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="fb9be-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="fb9be-106">\<behavior></span></span>  
<span data-ttu-id="fb9be-107">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="fb9be-107">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb9be-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fb9be-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fb9be-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fb9be-109">Attributes and Elements</span></span>  
 <span data-ttu-id="fb9be-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fb9be-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fb9be-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="fb9be-111">Attributes</span></span>  
  
|<span data-ttu-id="fb9be-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="fb9be-112">Attribute</span></span>|<span data-ttu-id="fb9be-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb9be-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fb9be-114">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="fb9be-114">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="fb9be-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fb9be-115">Child Elements</span></span>  
 <span data-ttu-id="fb9be-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fb9be-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fb9be-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fb9be-117">Parent Elements</span></span>  
  
|<span data-ttu-id="fb9be-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="fb9be-118">Element</span></span>|<span data-ttu-id="fb9be-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb9be-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fb9be-120">\<comportamiento > de \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="fb9be-120">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="fb9be-121">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="fb9be-121">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fb9be-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb9be-122">See also</span></span>
- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>

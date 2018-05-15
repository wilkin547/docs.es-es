---
title: '&lt;comportamientos&gt; de flujo de trabajo'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 762fd1ff0de7980848ac3921706f406932c7f35d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltbehaviorsgt-of-workflow"></a><span data-ttu-id="9943e-102">&lt;comportamientos&gt; de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="9943e-102">&lt;behaviors&gt; of workflow</span></span>
<span data-ttu-id="9943e-103">Este elemento contiene el **serviceBehaviors** colección.</span><span class="sxs-lookup"><span data-stu-id="9943e-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="9943e-104">Cada elemento de la colección define elementos de comportamiento utilizados por servicios del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9943e-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="9943e-105">Su único identifica cada elemento de comportamiento **nombre** atributo.</span><span class="sxs-lookup"><span data-stu-id="9943e-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
 <span data-ttu-id="9943e-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9943e-106">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9943e-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9943e-107">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9943e-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9943e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9943e-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9943e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9943e-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="9943e-110">Attributes</span></span>  
 <span data-ttu-id="9943e-111">Ninguna</span><span class="sxs-lookup"><span data-stu-id="9943e-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9943e-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9943e-112">Child Elements</span></span>  
  
|<span data-ttu-id="9943e-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="9943e-113">Element</span></span>|<span data-ttu-id="9943e-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="9943e-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9943e-115">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="9943e-115">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|<span data-ttu-id="9943e-116">Esta sección de configuración representa todos los comportamientos definidos para un servicio de flujo de trabajo concreto.</span><span class="sxs-lookup"><span data-stu-id="9943e-116">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9943e-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9943e-117">Parent Elements</span></span>  
  
|<span data-ttu-id="9943e-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="9943e-118">Element</span></span>|<span data-ttu-id="9943e-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="9943e-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9943e-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9943e-120">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="9943e-121">El elemento raíz de todos los elementos de configuración de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9943e-121">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9943e-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="9943e-122">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BehaviorsSection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>  
 [<span data-ttu-id="9943e-123">Configuración y extensión del tiempo de ejecución con comportamientos</span><span class="sxs-lookup"><span data-stu-id="9943e-123">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)

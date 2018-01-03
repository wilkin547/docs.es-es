---
title: '&lt;comportamientos&gt; de flujo de trabajo'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 83c1bf4beb244b72d2fe3d82d749ff6ae6723baf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltbehaviorsgt-of-workflow"></a><span data-ttu-id="a07e6-102">&lt;comportamientos&gt; de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a07e6-102">&lt;behaviors&gt; of workflow</span></span>
<span data-ttu-id="a07e6-103">Este elemento contiene el **serviceBehaviors** colección.</span><span class="sxs-lookup"><span data-stu-id="a07e6-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="a07e6-104">Cada elemento de la colección define elementos de comportamiento utilizados por servicios del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a07e6-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="a07e6-105">Su único identifica cada elemento de comportamiento **nombre** atributo.</span><span class="sxs-lookup"><span data-stu-id="a07e6-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
 <span data-ttu-id="a07e6-106">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a07e6-106">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a07e6-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a07e6-107">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a07e6-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a07e6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a07e6-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a07e6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a07e6-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="a07e6-110">Attributes</span></span>  
 <span data-ttu-id="a07e6-111">Ninguna</span><span class="sxs-lookup"><span data-stu-id="a07e6-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a07e6-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a07e6-112">Child Elements</span></span>  
  
|<span data-ttu-id="a07e6-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="a07e6-113">Element</span></span>|<span data-ttu-id="a07e6-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="a07e6-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a07e6-115">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="a07e6-115">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|<span data-ttu-id="a07e6-116">Esta sección de configuración representa todos los comportamientos definidos para un servicio de flujo de trabajo concreto.</span><span class="sxs-lookup"><span data-stu-id="a07e6-116">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a07e6-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a07e6-117">Parent Elements</span></span>  
  
|<span data-ttu-id="a07e6-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="a07e6-118">Element</span></span>|<span data-ttu-id="a07e6-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="a07e6-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a07e6-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a07e6-120">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="a07e6-121">El elemento raíz de todos los elementos de configuración de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a07e6-121">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a07e6-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="a07e6-122">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BehaviorsSection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>  
 [<span data-ttu-id="a07e6-123">Configuración y extensión del tiempo de ejecución con comportamientos</span><span class="sxs-lookup"><span data-stu-id="a07e6-123">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)

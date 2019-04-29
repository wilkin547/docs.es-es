---
title: <behaviors> de flujo de trabajo
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: b7c5cf93a82ac88c25f9c478ad52cf41eb6f6d65
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790304"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="a61ba-102">\<comportamientos > de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a61ba-102">\<behaviors> of workflow</span></span>
<span data-ttu-id="a61ba-103">Este elemento contiene el **serviceBehaviors** colección.</span><span class="sxs-lookup"><span data-stu-id="a61ba-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="a61ba-104">Cada elemento de la colección define elementos de comportamiento utilizados por servicios del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a61ba-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="a61ba-105">Su único identifica cada elemento de comportamiento **nombre** atributo.</span><span class="sxs-lookup"><span data-stu-id="a61ba-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
 <span data-ttu-id="a61ba-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a61ba-106">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a61ba-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a61ba-107">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a61ba-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a61ba-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a61ba-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a61ba-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a61ba-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="a61ba-110">Attributes</span></span>  
 <span data-ttu-id="a61ba-111">Ninguna</span><span class="sxs-lookup"><span data-stu-id="a61ba-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a61ba-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a61ba-112">Child Elements</span></span>  
  
|<span data-ttu-id="a61ba-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="a61ba-113">Element</span></span>|<span data-ttu-id="a61ba-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="a61ba-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a61ba-115">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="a61ba-115">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|<span data-ttu-id="a61ba-116">Esta sección de configuración representa todos los comportamientos definidos para un servicio de flujo de trabajo concreto.</span><span class="sxs-lookup"><span data-stu-id="a61ba-116">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a61ba-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a61ba-117">Parent Elements</span></span>  
  
|<span data-ttu-id="a61ba-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="a61ba-118">Element</span></span>|<span data-ttu-id="a61ba-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="a61ba-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a61ba-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a61ba-120">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="a61ba-121">El elemento raíz de todos los elementos de configuración de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a61ba-121">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a61ba-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="a61ba-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="a61ba-123">Configuración y extensión del tiempo de ejecución con comportamientos</span><span class="sxs-lookup"><span data-stu-id="a61ba-123">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)

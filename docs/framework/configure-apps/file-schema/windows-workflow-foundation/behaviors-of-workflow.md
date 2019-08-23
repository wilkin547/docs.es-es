---
title: <behaviors>del flujo de trabajo
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 7dd3b0b20c9d7accd80a85b3693e67ffc9b729e5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946004"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="ef7b4-102">\<comportamientos > del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="ef7b4-102">\<behaviors> of workflow</span></span>
<span data-ttu-id="ef7b4-103">Este elemento contiene la colección **serviceBehaviors** .</span><span class="sxs-lookup"><span data-stu-id="ef7b4-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="ef7b4-104">Cada elemento de la colección define elementos de comportamiento utilizados por servicios del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ef7b4-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="ef7b4-105">Cada elemento de comportamiento se identifica mediante su atributo de **nombre** único.</span><span class="sxs-lookup"><span data-stu-id="ef7b4-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
 <span data-ttu-id="ef7b4-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ef7b4-106">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef7b4-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef7b4-107">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef7b4-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ef7b4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ef7b4-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ef7b4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef7b4-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="ef7b4-110">Attributes</span></span>  
 <span data-ttu-id="ef7b4-111">None</span><span class="sxs-lookup"><span data-stu-id="ef7b4-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ef7b4-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ef7b4-112">Child Elements</span></span>  
  
|<span data-ttu-id="ef7b4-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef7b4-113">Element</span></span>|<span data-ttu-id="ef7b4-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ef7b4-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef7b4-115">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="ef7b4-115">\<serviceBehaviors></span></span>](servicebehaviors-of-workflow.md)|<span data-ttu-id="ef7b4-116">Esta sección de configuración representa todos los comportamientos definidos para un servicio de flujo de trabajo concreto.</span><span class="sxs-lookup"><span data-stu-id="ef7b4-116">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ef7b4-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ef7b4-117">Parent Elements</span></span>  
  
|<span data-ttu-id="ef7b4-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef7b4-118">Element</span></span>|<span data-ttu-id="ef7b4-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ef7b4-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef7b4-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ef7b4-120">\<system.serviceModel></span></span>](../wcf/system-servicemodel.md)|<span data-ttu-id="ef7b4-121">El elemento raíz de todos los elementos de configuración de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ef7b4-121">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ef7b4-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef7b4-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="ef7b4-123">Configuración y extensión del tiempo de ejecución con comportamientos</span><span class="sxs-lookup"><span data-stu-id="ef7b4-123">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)

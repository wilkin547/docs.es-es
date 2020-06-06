---
title: <behaviors>del flujo de trabajo
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 05a15cdf5c043eb5d94b36028324310d2b7a8413
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398877"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="03e57-102">\<behaviors>del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="03e57-102">\<behaviors> of workflow</span></span>
<span data-ttu-id="03e57-103">Este elemento contiene la colección **serviceBehaviors** .</span><span class="sxs-lookup"><span data-stu-id="03e57-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="03e57-104">Cada elemento de la colección define elementos de comportamiento utilizados por servicios del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="03e57-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="03e57-105">Cada elemento de comportamiento se identifica mediante su atributo de **nombre** único.</span><span class="sxs-lookup"><span data-stu-id="03e57-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**  
  
## <a name="syntax"></a><span data-ttu-id="03e57-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03e57-106">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03e57-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="03e57-107">Attributes and Elements</span></span>  
 <span data-ttu-id="03e57-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="03e57-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03e57-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="03e57-109">Attributes</span></span>  
 <span data-ttu-id="03e57-110">None</span><span class="sxs-lookup"><span data-stu-id="03e57-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="03e57-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="03e57-111">Child Elements</span></span>  
  
|<span data-ttu-id="03e57-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="03e57-112">Element</span></span>|<span data-ttu-id="03e57-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="03e57-113">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors-of-workflow.md)|<span data-ttu-id="03e57-114">Esta sección de configuración representa todos los comportamientos definidos para un servicio de flujo de trabajo concreto.</span><span class="sxs-lookup"><span data-stu-id="03e57-114">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="03e57-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="03e57-115">Parent Elements</span></span>  
  
|<span data-ttu-id="03e57-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="03e57-116">Element</span></span>|<span data-ttu-id="03e57-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="03e57-117">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](../wcf/system-servicemodel.md)|<span data-ttu-id="03e57-118">El elemento raíz de todos los elementos de configuración de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="03e57-118">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="03e57-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="03e57-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="03e57-120">Configuración y extensión del tiempo de ejecución con comportamientos</span><span class="sxs-lookup"><span data-stu-id="03e57-120">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)

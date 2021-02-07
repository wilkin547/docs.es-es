---
description: 'Más información sobre: <behaviors> del flujo de trabajo'
title: <behaviors> del flujo de trabajo
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 5154a389aded34065cc7bdb11d1c73d71ca9f9f5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698198"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="95f42-103">\<behaviors> del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="95f42-103">\<behaviors> of workflow</span></span>

<span data-ttu-id="95f42-104">Este elemento contiene la colección **serviceBehaviors** .</span><span class="sxs-lookup"><span data-stu-id="95f42-104">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="95f42-105">Cada elemento de la colección define elementos de comportamiento utilizados por servicios del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="95f42-105">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="95f42-106">Cada elemento de comportamiento se identifica mediante su atributo de **nombre** único.</span><span class="sxs-lookup"><span data-stu-id="95f42-106">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**  
  
## <a name="syntax"></a><span data-ttu-id="95f42-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="95f42-107">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95f42-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="95f42-108">Attributes and Elements</span></span>  

 <span data-ttu-id="95f42-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="95f42-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95f42-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="95f42-110">Attributes</span></span>  

 <span data-ttu-id="95f42-111">None</span><span class="sxs-lookup"><span data-stu-id="95f42-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="95f42-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="95f42-112">Child Elements</span></span>  
  
|<span data-ttu-id="95f42-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="95f42-113">Element</span></span>|<span data-ttu-id="95f42-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="95f42-114">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors-of-workflow.md)|<span data-ttu-id="95f42-115">Esta sección de configuración representa todos los comportamientos definidos para un servicio de flujo de trabajo concreto.</span><span class="sxs-lookup"><span data-stu-id="95f42-115">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="95f42-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="95f42-116">Parent Elements</span></span>  
  
|<span data-ttu-id="95f42-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="95f42-117">Element</span></span>|<span data-ttu-id="95f42-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="95f42-118">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](../wcf/system-servicemodel.md)|<span data-ttu-id="95f42-119">El elemento raíz de todos los elementos de configuración de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="95f42-119">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="95f42-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="95f42-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="95f42-121">Configuración y extensión del tiempo de ejecución con comportamientos</span><span class="sxs-lookup"><span data-stu-id="95f42-121">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)

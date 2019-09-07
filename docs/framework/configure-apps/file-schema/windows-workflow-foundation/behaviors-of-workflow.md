---
title: <behaviors>del flujo de trabajo
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 05a15cdf5c043eb5d94b36028324310d2b7a8413
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398877"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="543a5-102">\<comportamientos > del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="543a5-102">\<behaviors> of workflow</span></span>
<span data-ttu-id="543a5-103">Este elemento contiene la colección **serviceBehaviors** .</span><span class="sxs-lookup"><span data-stu-id="543a5-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="543a5-104">Cada elemento de la colección define elementos de comportamiento utilizados por servicios del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="543a5-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="543a5-105">Cada elemento de comportamiento se identifica mediante su atributo de **nombre** único.</span><span class="sxs-lookup"><span data-stu-id="543a5-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
<span data-ttu-id="543a5-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="543a5-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="543a5-107">&nbsp;&nbsp;[ **\<integrado. > De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="543a5-107">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="543a5-108">&nbsp;&nbsp;&nbsp;&nbsp; **\<comportamientos >**</span><span class="sxs-lookup"><span data-stu-id="543a5-108">&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="543a5-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="543a5-109">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="543a5-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="543a5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="543a5-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="543a5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="543a5-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="543a5-112">Attributes</span></span>  
 <span data-ttu-id="543a5-113">None</span><span class="sxs-lookup"><span data-stu-id="543a5-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="543a5-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="543a5-114">Child Elements</span></span>  
  
|<span data-ttu-id="543a5-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="543a5-115">Element</span></span>|<span data-ttu-id="543a5-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="543a5-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="543a5-117">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="543a5-117">\<serviceBehaviors></span></span>](servicebehaviors-of-workflow.md)|<span data-ttu-id="543a5-118">Esta sección de configuración representa todos los comportamientos definidos para un servicio de flujo de trabajo concreto.</span><span class="sxs-lookup"><span data-stu-id="543a5-118">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="543a5-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="543a5-119">Parent Elements</span></span>  
  
|<span data-ttu-id="543a5-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="543a5-120">Element</span></span>|<span data-ttu-id="543a5-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="543a5-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="543a5-122">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="543a5-122">\<system.serviceModel></span></span>](../wcf/system-servicemodel.md)|<span data-ttu-id="543a5-123">El elemento raíz de todos los elementos de configuración de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="543a5-123">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="543a5-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="543a5-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="543a5-125">Configuración y extensión del tiempo de ejecución con comportamientos</span><span class="sxs-lookup"><span data-stu-id="543a5-125">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)

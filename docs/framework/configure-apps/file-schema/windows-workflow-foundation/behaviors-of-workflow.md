---
title: <behaviors> del flujo de trabajo
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 21974f77526f55a47c014a285efd3bbac6fc1f7b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189609"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="c4654-102">\<behaviors> del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="c4654-102">\<behaviors> of workflow</span></span>

<span data-ttu-id="c4654-103">Este elemento contiene la colección **serviceBehaviors** .</span><span class="sxs-lookup"><span data-stu-id="c4654-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="c4654-104">Cada elemento de la colección define elementos de comportamiento utilizados por servicios del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c4654-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="c4654-105">Cada elemento de comportamiento se identifica mediante su atributo de **nombre** único.</span><span class="sxs-lookup"><span data-stu-id="c4654-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**  
  
## <a name="syntax"></a><span data-ttu-id="c4654-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c4654-106">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4654-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c4654-107">Attributes and Elements</span></span>  

 <span data-ttu-id="c4654-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c4654-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4654-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="c4654-109">Attributes</span></span>  

 <span data-ttu-id="c4654-110">None</span><span class="sxs-lookup"><span data-stu-id="c4654-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c4654-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c4654-111">Child Elements</span></span>  
  
|<span data-ttu-id="c4654-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="c4654-112">Element</span></span>|<span data-ttu-id="c4654-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="c4654-113">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors-of-workflow.md)|<span data-ttu-id="c4654-114">Esta sección de configuración representa todos los comportamientos definidos para un servicio de flujo de trabajo concreto.</span><span class="sxs-lookup"><span data-stu-id="c4654-114">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c4654-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c4654-115">Parent Elements</span></span>  
  
|<span data-ttu-id="c4654-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="c4654-116">Element</span></span>|<span data-ttu-id="c4654-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="c4654-117">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](../wcf/system-servicemodel.md)|<span data-ttu-id="c4654-118">El elemento raíz de todos los elementos de configuración de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c4654-118">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c4654-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c4654-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="c4654-120">Configuración y extensión del tiempo de ejecución con comportamientos</span><span class="sxs-lookup"><span data-stu-id="c4654-120">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)

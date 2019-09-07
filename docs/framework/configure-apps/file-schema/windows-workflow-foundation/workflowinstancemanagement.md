---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: aa2edafd9adc0317ed0023ad46688025dcecad67
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397520"
---
# <a name="workflowinstancemanagement"></a><span data-ttu-id="a32f4-101">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="a32f4-101">\<workflowInstanceManagement></span></span>
<span data-ttu-id="a32f4-102">Un comportamiento del servicio que permite especificar valores que controlan cómo se ejecutan las instancias de flujo de trabajo, incluida la conservación, el comportamiento de la excepción no controlada y el comportamiento inactivo.</span><span class="sxs-lookup"><span data-stu-id="a32f4-102">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="a32f4-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a32f4-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a32f4-104">&nbsp;&nbsp;[ **\<integrado. > De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="a32f4-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="a32f4-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="a32f4-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="a32f4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="a32f4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="a32f4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="a32f4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="a32f4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> workflowInstanceManagement**</span><span class="sxs-lookup"><span data-stu-id="a32f4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceManagement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a32f4-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a32f4-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a32f4-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a32f4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a32f4-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a32f4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a32f4-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="a32f4-112">Attributes</span></span>  
  
|<span data-ttu-id="a32f4-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="a32f4-113">Attribute</span></span>|<span data-ttu-id="a32f4-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a32f4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a32f4-115">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="a32f4-115">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="a32f4-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a32f4-116">Child Elements</span></span>  
 <span data-ttu-id="a32f4-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a32f4-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a32f4-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a32f4-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a32f4-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="a32f4-119">Element</span></span>|<span data-ttu-id="a32f4-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a32f4-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a32f4-121">\<comportamiento > de \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="a32f4-121">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="a32f4-122">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="a32f4-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a32f4-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="a32f4-123">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>

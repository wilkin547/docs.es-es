---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: 29b6d8982e712a0fa595b3103803f1795adea892
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398567"
---
# <a name="workflowunhandledexception"></a><span data-ttu-id="b0064-101">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="b0064-101">\<workflowUnhandledException></span></span>
<span data-ttu-id="b0064-102">Un comportamiento del servicio que permite especificar la acción que debe emprenderse cuando se produce una excepción no controlada dentro de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b0064-102">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="b0064-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b0064-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b0064-104">&nbsp;&nbsp;[ **\<integrado. > De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="b0064-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="b0064-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="b0064-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="b0064-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="b0064-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="b0064-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="b0064-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="b0064-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> workflowUnhandledException**</span><span class="sxs-lookup"><span data-stu-id="b0064-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowUnhandledException>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0064-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0064-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0064-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b0064-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b0064-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b0064-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0064-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="b0064-112">Attributes</span></span>  
  
|<span data-ttu-id="b0064-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="b0064-113">Attribute</span></span>|<span data-ttu-id="b0064-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b0064-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b0064-115">action</span><span class="sxs-lookup"><span data-stu-id="b0064-115">action</span></span>|<span data-ttu-id="b0064-116">Una cadena que especifica la acción que debe emprenderse cuando se produce una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="b0064-116">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="b0064-117">Este atributo es del tipo <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="b0064-117">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0064-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b0064-118">Child Elements</span></span>  
 <span data-ttu-id="b0064-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b0064-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b0064-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b0064-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b0064-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="b0064-121">Element</span></span>|<span data-ttu-id="b0064-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b0064-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0064-123">\<comportamiento > de \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="b0064-123">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="b0064-124">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="b0064-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0064-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0064-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>

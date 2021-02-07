---
description: 'Más información acerca de: <workflowUnhandledException>'
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: b9258c986ffa154e490f80bead1dc53d8f7ef44d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697782"
---
# \<workflowUnhandledException>

<span data-ttu-id="a6ac5-102">Un comportamiento del servicio que permite especificar la acción que debe emprenderse cuando se produce una excepción no controlada dentro de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a6ac5-102">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowUnhandledException>**  
  
## <a name="syntax"></a><span data-ttu-id="a6ac5-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6ac5-103">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6ac5-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a6ac5-104">Attributes and Elements</span></span>  

 <span data-ttu-id="a6ac5-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a6ac5-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6ac5-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="a6ac5-106">Attributes</span></span>  
  
|<span data-ttu-id="a6ac5-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="a6ac5-107">Attribute</span></span>|<span data-ttu-id="a6ac5-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6ac5-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a6ac5-109">action</span><span class="sxs-lookup"><span data-stu-id="a6ac5-109">action</span></span>|<span data-ttu-id="a6ac5-110">Una cadena que especifica la acción que debe emprenderse cuando se produce una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="a6ac5-110">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="a6ac5-111">Este atributo es del tipo <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="a6ac5-111">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a6ac5-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a6ac5-112">Child Elements</span></span>  

 <span data-ttu-id="a6ac5-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a6ac5-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a6ac5-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a6ac5-114">Parent Elements</span></span>  
  
|<span data-ttu-id="a6ac5-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="a6ac5-115">Element</span></span>|<span data-ttu-id="a6ac5-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6ac5-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a6ac5-117">\<behavior> de \<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="a6ac5-117">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="a6ac5-118">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="a6ac5-118">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a6ac5-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6ac5-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>

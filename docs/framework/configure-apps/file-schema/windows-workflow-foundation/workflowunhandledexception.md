---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: 6e3993e43aac746f380a30341fe4ebffcd257c5f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148521"
---
# \<workflowUnhandledException>

<span data-ttu-id="d5a72-101">Un comportamiento del servicio que permite especificar la acción que debe emprenderse cuando se produce una excepción no controlada dentro de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d5a72-101">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowUnhandledException>**  
  
## <a name="syntax"></a><span data-ttu-id="d5a72-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5a72-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5a72-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d5a72-103">Attributes and Elements</span></span>  

 <span data-ttu-id="d5a72-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d5a72-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5a72-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="d5a72-105">Attributes</span></span>  
  
|<span data-ttu-id="d5a72-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="d5a72-106">Attribute</span></span>|<span data-ttu-id="d5a72-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5a72-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d5a72-108">action</span><span class="sxs-lookup"><span data-stu-id="d5a72-108">action</span></span>|<span data-ttu-id="d5a72-109">Una cadena que especifica la acción que debe emprenderse cuando se produce una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="d5a72-109">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="d5a72-110">Este atributo es del tipo <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="d5a72-110">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d5a72-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d5a72-111">Child Elements</span></span>  

 <span data-ttu-id="d5a72-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d5a72-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d5a72-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d5a72-113">Parent Elements</span></span>  
  
|<span data-ttu-id="d5a72-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="d5a72-114">Element</span></span>|<span data-ttu-id="d5a72-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5a72-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5a72-116">\<behavior> de \<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="d5a72-116">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="d5a72-117">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="d5a72-117">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d5a72-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5a72-118">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>

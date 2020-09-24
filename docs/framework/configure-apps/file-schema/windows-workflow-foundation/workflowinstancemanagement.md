---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: 532d4c31a582b2b0cd90f6f42b20e00790f9ab02
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148664"
---
# \<workflowInstanceManagement>

<span data-ttu-id="32c53-101">Un comportamiento del servicio que permite especificar valores que controlan cómo se ejecutan las instancias de flujo de trabajo, incluida la conservación, el comportamiento de la excepción no controlada y el comportamiento inactivo.</span><span class="sxs-lookup"><span data-stu-id="32c53-101">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceManagement>**  
  
## <a name="syntax"></a><span data-ttu-id="32c53-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="32c53-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32c53-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="32c53-103">Attributes and Elements</span></span>  

 <span data-ttu-id="32c53-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="32c53-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32c53-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="32c53-105">Attributes</span></span>  
  
|<span data-ttu-id="32c53-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="32c53-106">Attribute</span></span>|<span data-ttu-id="32c53-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="32c53-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="32c53-108">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="32c53-108">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="32c53-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="32c53-109">Child Elements</span></span>  

 <span data-ttu-id="32c53-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="32c53-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="32c53-111">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="32c53-111">Parent Elements</span></span>  
  
|<span data-ttu-id="32c53-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="32c53-112">Element</span></span>|<span data-ttu-id="32c53-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="32c53-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32c53-114">\<behavior> de \<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="32c53-114">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="32c53-115">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="32c53-115">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="32c53-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="32c53-116">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>

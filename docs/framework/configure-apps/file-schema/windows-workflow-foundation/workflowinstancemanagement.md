---
description: 'Más información acerca de: <workflowInstanceManagement>'
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: 528c0c923be93d9581b8e3bfccc382eab11c5da1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697925"
---
# \<workflowInstanceManagement>

<span data-ttu-id="921d0-102">Un comportamiento del servicio que permite especificar valores que controlan cómo se ejecutan las instancias de flujo de trabajo, incluida la conservación, el comportamiento de la excepción no controlada y el comportamiento inactivo.</span><span class="sxs-lookup"><span data-stu-id="921d0-102">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceManagement>**  
  
## <a name="syntax"></a><span data-ttu-id="921d0-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="921d0-103">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="921d0-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="921d0-104">Attributes and Elements</span></span>  

 <span data-ttu-id="921d0-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="921d0-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="921d0-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="921d0-106">Attributes</span></span>  
  
|<span data-ttu-id="921d0-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="921d0-107">Attribute</span></span>|<span data-ttu-id="921d0-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="921d0-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="921d0-109">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="921d0-109">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="921d0-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="921d0-110">Child Elements</span></span>  

 <span data-ttu-id="921d0-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="921d0-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="921d0-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="921d0-112">Parent Elements</span></span>  
  
|<span data-ttu-id="921d0-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="921d0-113">Element</span></span>|<span data-ttu-id="921d0-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="921d0-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="921d0-115">\<behavior> de \<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="921d0-115">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="921d0-116">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="921d0-116">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="921d0-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="921d0-117">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>

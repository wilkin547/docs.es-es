---
title: '&lt;endToEndTracing&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1bcd7405c5e3ebf2d1c156ff3bca9f473df9fa35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltendtoendtracinggt"></a><span data-ttu-id="6b90b-102">&lt;endToEndTracing&gt;</span><span class="sxs-lookup"><span data-stu-id="6b90b-102">&lt;endToEndTracing&gt;</span></span>
<span data-ttu-id="6b90b-103">Elemento de configuración que le permite habilitar y deshabilitar aspectos diferentes de traza de un punto de conexión a otro durante el funcionamiento de una aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="6b90b-103">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
 <span data-ttu-id="6b90b-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="6b90b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6b90b-105">\<diagnóstico ></span><span class="sxs-lookup"><span data-stu-id="6b90b-105">\<diagnostic></span></span>  
<span data-ttu-id="6b90b-106">\<endToEndTracing ></span><span class="sxs-lookup"><span data-stu-id="6b90b-106">\<endToEndTracing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b90b-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6b90b-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
   <diagnostics>  
       <endToEndTracing activityTracing="Boolean"  
          messageFlowTracing="Boolean"  
          propagateActivity="Boolean" />  
   </diagnostics>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b90b-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6b90b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6b90b-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6b90b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b90b-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="6b90b-110">Attributes</span></span>  
  
|<span data-ttu-id="6b90b-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="6b90b-111">Attribute</span></span>|<span data-ttu-id="6b90b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b90b-112">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="6b90b-113">Valor booleano que especifica si está habilitada la traza de actividad.</span><span class="sxs-lookup"><span data-stu-id="6b90b-113">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="6b90b-114">Valor booleano que especifica si está habilitada la traza del flujo de mensajes.</span><span class="sxs-lookup"><span data-stu-id="6b90b-114">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="6b90b-115">Valor booleano que especifica si el atributo de propagación está establecido en true.</span><span class="sxs-lookup"><span data-stu-id="6b90b-115">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6b90b-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6b90b-116">Child Elements</span></span>  
 <span data-ttu-id="6b90b-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6b90b-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6b90b-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6b90b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="6b90b-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="6b90b-119">Element</span></span>|<span data-ttu-id="6b90b-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b90b-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6b90b-121">\<diagnóstico ></span><span class="sxs-lookup"><span data-stu-id="6b90b-121">\<diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|<span data-ttu-id="6b90b-122">Define la configuración de WCF para la inspección y el control en tiempo de ejecución para el administrador.</span><span class="sxs-lookup"><span data-stu-id="6b90b-122">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6b90b-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b90b-123">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>  
 <xref:System.ServiceModel.Diagnostics>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>  
 <xref:System.ServiceModel.Configuration.EndToEndTracingElement>  
 [<span data-ttu-id="6b90b-124">Seguimiento to-End</span><span class="sxs-lookup"><span data-stu-id="6b90b-124">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)

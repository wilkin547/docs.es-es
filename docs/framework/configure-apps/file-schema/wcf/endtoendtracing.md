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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a43801f4c45d7ac518c3b24cadc58ffbec40adb4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltendtoendtracinggt"></a><span data-ttu-id="56455-102">&lt;endToEndTracing&gt;</span><span class="sxs-lookup"><span data-stu-id="56455-102">&lt;endToEndTracing&gt;</span></span>
<span data-ttu-id="56455-103">Elemento de configuración que le permite habilitar y deshabilitar aspectos diferentes de traza de un punto de conexión a otro durante el funcionamiento de una aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="56455-103">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
 <span data-ttu-id="56455-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="56455-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="56455-105">\<diagnóstico ></span><span class="sxs-lookup"><span data-stu-id="56455-105">\<diagnostic></span></span>  
<span data-ttu-id="56455-106">\<endToEndTracing ></span><span class="sxs-lookup"><span data-stu-id="56455-106">\<endToEndTracing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56455-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56455-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
   <diagnostics>  
       <endToEndTracing activityTracing="Boolean"  
          messageFlowTracing="Boolean"  
          propagateActivity="Boolean" />  
   </diagnostics>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56455-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="56455-108">Attributes and Elements</span></span>  
 <span data-ttu-id="56455-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="56455-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56455-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="56455-110">Attributes</span></span>  
  
|<span data-ttu-id="56455-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="56455-111">Attribute</span></span>|<span data-ttu-id="56455-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="56455-112">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="56455-113">Valor booleano que especifica si está habilitada la traza de actividad.</span><span class="sxs-lookup"><span data-stu-id="56455-113">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="56455-114">Valor booleano que especifica si está habilitada la traza del flujo de mensajes.</span><span class="sxs-lookup"><span data-stu-id="56455-114">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="56455-115">Valor booleano que especifica si el atributo de propagación está establecido en true.</span><span class="sxs-lookup"><span data-stu-id="56455-115">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56455-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="56455-116">Child Elements</span></span>  
 <span data-ttu-id="56455-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="56455-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="56455-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="56455-118">Parent Elements</span></span>  
  
|<span data-ttu-id="56455-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="56455-119">Element</span></span>|<span data-ttu-id="56455-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="56455-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56455-121">\<diagnóstico ></span><span class="sxs-lookup"><span data-stu-id="56455-121">\<diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|<span data-ttu-id="56455-122">Define la configuración de WCF para la inspección y el control en tiempo de ejecución para el administrador.</span><span class="sxs-lookup"><span data-stu-id="56455-122">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="56455-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="56455-123">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>  
 <xref:System.ServiceModel.Diagnostics>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>  
 <xref:System.ServiceModel.Configuration.EndToEndTracingElement>  
 [<span data-ttu-id="56455-124">Traza de un extremo a otro</span><span class="sxs-lookup"><span data-stu-id="56455-124">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)

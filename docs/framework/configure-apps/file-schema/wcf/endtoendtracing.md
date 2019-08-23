---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 6b23728451a051f21ad3863b9a29e6290c3c837a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919013"
---
# <a name="endtoendtracing"></a><span data-ttu-id="e19d0-101">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="e19d0-101">\<endToEndTracing></span></span>
<span data-ttu-id="e19d0-102">Elemento de configuración que le permite habilitar y deshabilitar aspectos diferentes de traza de un extremo a otro durante el funcionamiento de una aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="e19d0-102">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
 <span data-ttu-id="e19d0-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e19d0-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="e19d0-104">\<> de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="e19d0-104">\<diagnostic></span></span>  
<span data-ttu-id="e19d0-105">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="e19d0-105">\<endToEndTracing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e19d0-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e19d0-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e19d0-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e19d0-107">Attributes and Elements</span></span>  
 <span data-ttu-id="e19d0-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e19d0-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e19d0-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="e19d0-109">Attributes</span></span>  
  
|<span data-ttu-id="e19d0-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="e19d0-110">Attribute</span></span>|<span data-ttu-id="e19d0-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e19d0-111">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="e19d0-112">Valor booleano que especifica si está habilitada la traza de actividad.</span><span class="sxs-lookup"><span data-stu-id="e19d0-112">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="e19d0-113">Valor booleano que especifica si está habilitada la traza del flujo de mensajes.</span><span class="sxs-lookup"><span data-stu-id="e19d0-113">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="e19d0-114">Valor booleano que especifica si el atributo de propagación está establecido en true.</span><span class="sxs-lookup"><span data-stu-id="e19d0-114">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e19d0-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e19d0-115">Child Elements</span></span>  
 <span data-ttu-id="e19d0-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e19d0-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e19d0-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e19d0-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e19d0-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="e19d0-118">Element</span></span>|<span data-ttu-id="e19d0-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e19d0-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e19d0-120">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="e19d0-120">\<diagnostics></span></span>](diagnostics.md)|<span data-ttu-id="e19d0-121">Define la configuración de WCF para la inspección y el control en tiempo de ejecución para el administrador.</span><span class="sxs-lookup"><span data-stu-id="e19d0-121">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e19d0-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="e19d0-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="e19d0-123">Traza de un extremo a otro</span><span class="sxs-lookup"><span data-stu-id="e19d0-123">End-to-End Tracing</span></span>](../../../wcf/diagnostics/tracing/end-to-end-tracing.md)

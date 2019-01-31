---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 1867e307ba004af821045e7d1b5775c470d8a3e8
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266759"
---
# <a name="endtoendtracing"></a><span data-ttu-id="f9743-101">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="f9743-101">\<endToEndTracing></span></span>
<span data-ttu-id="f9743-102">Elemento de configuración que le permite habilitar y deshabilitar aspectos diferentes de traza de un punto de conexión a otro durante el funcionamiento de una aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="f9743-102">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
 <span data-ttu-id="f9743-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f9743-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="f9743-104">\<diagnostic></span><span class="sxs-lookup"><span data-stu-id="f9743-104">\<diagnostic></span></span>  
<span data-ttu-id="f9743-105">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="f9743-105">\<endToEndTracing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9743-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f9743-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9743-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f9743-107">Attributes and Elements</span></span>  
 <span data-ttu-id="f9743-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f9743-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9743-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="f9743-109">Attributes</span></span>  
  
|<span data-ttu-id="f9743-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="f9743-110">Attribute</span></span>|<span data-ttu-id="f9743-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="f9743-111">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="f9743-112">Valor booleano que especifica si está habilitada la traza de actividad.</span><span class="sxs-lookup"><span data-stu-id="f9743-112">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="f9743-113">Valor booleano que especifica si está habilitada la traza del flujo de mensajes.</span><span class="sxs-lookup"><span data-stu-id="f9743-113">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="f9743-114">Valor booleano que especifica si el atributo de propagación está establecido en true.</span><span class="sxs-lookup"><span data-stu-id="f9743-114">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f9743-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f9743-115">Child Elements</span></span>  
 <span data-ttu-id="f9743-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f9743-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f9743-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f9743-117">Parent Elements</span></span>  
  
|<span data-ttu-id="f9743-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="f9743-118">Element</span></span>|<span data-ttu-id="f9743-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="f9743-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9743-120">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="f9743-120">\<diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|<span data-ttu-id="f9743-121">Define la configuración de WCF para la inspección y el control en tiempo de ejecución para el administrador.</span><span class="sxs-lookup"><span data-stu-id="f9743-121">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f9743-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9743-122">See also</span></span>
- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="f9743-123">Traza de un extremo a otro</span><span class="sxs-lookup"><span data-stu-id="f9743-123">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)

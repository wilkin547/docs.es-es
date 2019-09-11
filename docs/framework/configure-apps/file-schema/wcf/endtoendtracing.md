---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 1a274f15800c6a132994a2437943c83982de9de0
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855294"
---
# <a name="endtoendtracing"></a><span data-ttu-id="9351c-101">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="9351c-101">\<endToEndTracing></span></span>
<span data-ttu-id="9351c-102">Elemento de configuración que le permite habilitar y deshabilitar aspectos diferentes de traza de un extremo a otro durante el funcionamiento de una aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="9351c-102">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
<span data-ttu-id="9351c-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9351c-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9351c-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9351c-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9351c-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<diagnóstico >** ](diagnostics.md)</span><span class="sxs-lookup"><span data-stu-id="9351c-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)</span></span>\
<span data-ttu-id="9351c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> endToEndTracing**</span><span class="sxs-lookup"><span data-stu-id="9351c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endToEndTracing>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9351c-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9351c-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9351c-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9351c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9351c-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9351c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9351c-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="9351c-110">Attributes</span></span>  
  
|<span data-ttu-id="9351c-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="9351c-111">Attribute</span></span>|<span data-ttu-id="9351c-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9351c-112">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="9351c-113">Valor booleano que especifica si está habilitada la traza de actividad.</span><span class="sxs-lookup"><span data-stu-id="9351c-113">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="9351c-114">Valor booleano que especifica si está habilitada la traza del flujo de mensajes.</span><span class="sxs-lookup"><span data-stu-id="9351c-114">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="9351c-115">Valor booleano que especifica si el atributo de propagación está establecido en true.</span><span class="sxs-lookup"><span data-stu-id="9351c-115">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9351c-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9351c-116">Child Elements</span></span>  
 <span data-ttu-id="9351c-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9351c-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9351c-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9351c-118">Parent Elements</span></span>  
  
|<span data-ttu-id="9351c-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="9351c-119">Element</span></span>|<span data-ttu-id="9351c-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9351c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9351c-121">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="9351c-121">\<diagnostics></span></span>](diagnostics.md)|<span data-ttu-id="9351c-122">Define la configuración de WCF para la inspección y el control en tiempo de ejecución para el administrador.</span><span class="sxs-lookup"><span data-stu-id="9351c-122">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9351c-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="9351c-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="9351c-124">Traza de un extremo a otro</span><span class="sxs-lookup"><span data-stu-id="9351c-124">End-to-End Tracing</span></span>](../../../wcf/diagnostics/tracing/end-to-end-tracing.md)

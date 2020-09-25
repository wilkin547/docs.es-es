---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 6b50c0c3db644787fe41ee58ced7eb640e7295f1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190025"
---
# \<endToEndTracing>

<span data-ttu-id="43764-101">Elemento de configuración que le permite habilitar y deshabilitar aspectos diferentes de traza de un extremo a otro durante el funcionamiento de una aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="43764-101">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endToEndTracing>**  
  
## <a name="syntax"></a><span data-ttu-id="43764-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43764-102">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="43764-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="43764-103">Attributes and Elements</span></span>  

 <span data-ttu-id="43764-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="43764-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43764-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="43764-105">Attributes</span></span>  
  
|<span data-ttu-id="43764-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="43764-106">Attribute</span></span>|<span data-ttu-id="43764-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="43764-107">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="43764-108">Valor booleano que especifica si está habilitada la traza de actividad.</span><span class="sxs-lookup"><span data-stu-id="43764-108">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="43764-109">Valor booleano que especifica si está habilitada la traza del flujo de mensajes.</span><span class="sxs-lookup"><span data-stu-id="43764-109">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="43764-110">Valor booleano que especifica si el atributo de propagación está establecido en true.</span><span class="sxs-lookup"><span data-stu-id="43764-110">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="43764-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="43764-111">Child Elements</span></span>  

 <span data-ttu-id="43764-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="43764-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="43764-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="43764-113">Parent Elements</span></span>  
  
|<span data-ttu-id="43764-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="43764-114">Element</span></span>|<span data-ttu-id="43764-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="43764-115">Description</span></span>|  
|-------------|-----------------|  
|[\<diagnostics>](diagnostics.md)|<span data-ttu-id="43764-116">Define la configuración de WCF para la inspección y el control en tiempo de ejecución para el administrador.</span><span class="sxs-lookup"><span data-stu-id="43764-116">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="43764-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="43764-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="43764-118">Seguimiento de un extremo a otro</span><span class="sxs-lookup"><span data-stu-id="43764-118">End-to-End Tracing</span></span>](../../../wcf/diagnostics/tracing/end-to-end-tracing.md)

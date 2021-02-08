---
description: 'Más información acerca de: <endToEndTracing>'
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 2ac4a7563d7d7881cdb503e843d34f84fd9c95a9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782122"
---
# \<endToEndTracing>

<span data-ttu-id="57269-102">Elemento de configuración que le permite habilitar y deshabilitar aspectos diferentes de traza de un extremo a otro durante el funcionamiento de una aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="57269-102">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endToEndTracing>**  
  
## <a name="syntax"></a><span data-ttu-id="57269-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57269-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="57269-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="57269-104">Attributes and Elements</span></span>  

 <span data-ttu-id="57269-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="57269-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="57269-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="57269-106">Attributes</span></span>  
  
|<span data-ttu-id="57269-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="57269-107">Attribute</span></span>|<span data-ttu-id="57269-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="57269-108">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="57269-109">Valor booleano que especifica si está habilitada la traza de actividad.</span><span class="sxs-lookup"><span data-stu-id="57269-109">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="57269-110">Valor booleano que especifica si está habilitada la traza del flujo de mensajes.</span><span class="sxs-lookup"><span data-stu-id="57269-110">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="57269-111">Valor booleano que especifica si el atributo de propagación está establecido en true.</span><span class="sxs-lookup"><span data-stu-id="57269-111">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="57269-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="57269-112">Child Elements</span></span>  

 <span data-ttu-id="57269-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="57269-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="57269-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="57269-114">Parent Elements</span></span>  
  
|<span data-ttu-id="57269-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="57269-115">Element</span></span>|<span data-ttu-id="57269-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="57269-116">Description</span></span>|  
|-------------|-----------------|  
|[\<diagnostics>](diagnostics.md)|<span data-ttu-id="57269-117">Define la configuración de WCF para la inspección y el control en tiempo de ejecución para el administrador.</span><span class="sxs-lookup"><span data-stu-id="57269-117">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="57269-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="57269-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="57269-119">Seguimiento de un extremo a otro</span><span class="sxs-lookup"><span data-stu-id="57269-119">End-to-End Tracing</span></span>](../../../wcf/diagnostics/tracing/end-to-end-tracing.md)

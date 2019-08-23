---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b159488efa2a80a9dea625e4c6dfe2f215dfc457
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939183"
---
# <a name="timeouts"></a><span data-ttu-id="51ac4-101">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="51ac4-101">\<timeOuts></span></span>
<span data-ttu-id="51ac4-102">Representa un elemento de configuración que especifica el intervalo de tiempo permitido para que el host del servicio abra o cierre.</span><span class="sxs-lookup"><span data-stu-id="51ac4-102">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="51ac4-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="51ac4-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="51ac4-104">\<client></span><span class="sxs-lookup"><span data-stu-id="51ac4-104">\<client></span></span>  
<span data-ttu-id="51ac4-105">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="51ac4-105">\<endpoint></span></span>  
<span data-ttu-id="51ac4-106">\<> host</span><span class="sxs-lookup"><span data-stu-id="51ac4-106">\<host></span></span>  
<span data-ttu-id="51ac4-107">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="51ac4-107">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51ac4-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="51ac4-108">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51ac4-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="51ac4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="51ac4-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="51ac4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="51ac4-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="51ac4-111">Attributes</span></span>  
  
|<span data-ttu-id="51ac4-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="51ac4-112">Attribute</span></span>|<span data-ttu-id="51ac4-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="51ac4-113">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="51ac4-114">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo permitido para que el host del servicio se cierre.</span><span class="sxs-lookup"><span data-stu-id="51ac4-114">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="51ac4-115">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo permitido para que el host del servicio se abra.</span><span class="sxs-lookup"><span data-stu-id="51ac4-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="51ac4-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="51ac4-116">Child Elements</span></span>  
 <span data-ttu-id="51ac4-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="51ac4-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="51ac4-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="51ac4-118">Parent Elements</span></span>  
  
|<span data-ttu-id="51ac4-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="51ac4-119">Element</span></span>|<span data-ttu-id="51ac4-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="51ac4-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51ac4-121">\<> host</span><span class="sxs-lookup"><span data-stu-id="51ac4-121">\<host></span></span>](host.md)|<span data-ttu-id="51ac4-122">Un elemento de configuración que especifica valores para un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="51ac4-122">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="51ac4-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="51ac4-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="51ac4-124">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="51ac4-124">Hosting</span></span>](../../../wcf/feature-details/hosting.md)

---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b9c67ac03f0eb73a2a4cdd43ab48fe12871a1cc3
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854963"
---
# <a name="timeouts"></a><span data-ttu-id="c14cd-101">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="c14cd-101">\<timeOuts></span></span>
<span data-ttu-id="c14cd-102">Representa un elemento de configuración que especifica el intervalo de tiempo permitido para que el host del servicio abra o cierre.</span><span class="sxs-lookup"><span data-stu-id="c14cd-102">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
<span data-ttu-id="c14cd-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c14cd-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c14cd-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c14cd-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c14cd-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de servicios**](services.md)</span><span class="sxs-lookup"><span data-stu-id="c14cd-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="c14cd-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de servicio**](service.md)</span><span class="sxs-lookup"><span data-stu-id="c14cd-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)</span></span>\
<span data-ttu-id="c14cd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> host**](host.md)</span><span class="sxs-lookup"><span data-stu-id="c14cd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)</span></span>\
<span data-ttu-id="c14cd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Tiempos de espera >**</span><span class="sxs-lookup"><span data-stu-id="c14cd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<timeOuts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c14cd-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c14cd-109">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c14cd-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c14cd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c14cd-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c14cd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c14cd-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="c14cd-112">Attributes</span></span>  
  
|<span data-ttu-id="c14cd-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="c14cd-113">Attribute</span></span>|<span data-ttu-id="c14cd-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c14cd-114">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="c14cd-115">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo permitido para que el host del servicio se cierre.</span><span class="sxs-lookup"><span data-stu-id="c14cd-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="c14cd-116">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo permitido para que el host del servicio se abra.</span><span class="sxs-lookup"><span data-stu-id="c14cd-116">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c14cd-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c14cd-117">Child Elements</span></span>  
 <span data-ttu-id="c14cd-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c14cd-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c14cd-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c14cd-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c14cd-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="c14cd-120">Element</span></span>|<span data-ttu-id="c14cd-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c14cd-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c14cd-122">\<> host</span><span class="sxs-lookup"><span data-stu-id="c14cd-122">\<host></span></span>](host.md)|<span data-ttu-id="c14cd-123">Un elemento de configuración que especifica valores para un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="c14cd-123">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c14cd-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="c14cd-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="c14cd-125">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="c14cd-125">Hosting</span></span>](../../../wcf/feature-details/hosting.md)

---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: b764bc21e9c4555b39c3d096212b6e6bcabb62ff
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855216"
---
# <a name="host"></a><span data-ttu-id="91bec-101">\<> host</span><span class="sxs-lookup"><span data-stu-id="91bec-101">\<host></span></span>
<span data-ttu-id="91bec-102">Especifica los valores para un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="91bec-102">Specifies settings for a service host.</span></span>  
  
<span data-ttu-id="91bec-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="91bec-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="91bec-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="91bec-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="91bec-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de servicios**](services.md)</span><span class="sxs-lookup"><span data-stu-id="91bec-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="91bec-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de servicio**](service.md)</span><span class="sxs-lookup"><span data-stu-id="91bec-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)</span></span>\
<span data-ttu-id="91bec-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> host**</span><span class="sxs-lookup"><span data-stu-id="91bec-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<host>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91bec-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91bec-108">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="91bec-109">Type</span><span class="sxs-lookup"><span data-stu-id="91bec-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91bec-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="91bec-110">Attributes and Elements</span></span>  
 <span data-ttu-id="91bec-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="91bec-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91bec-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="91bec-112">Attributes</span></span>  
 <span data-ttu-id="91bec-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="91bec-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="91bec-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="91bec-114">Child Elements</span></span>  
  
|<span data-ttu-id="91bec-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="91bec-115">Element</span></span>|<span data-ttu-id="91bec-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="91bec-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91bec-117">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="91bec-117">\<baseAddresses></span></span>](baseaddresses.md)|<span data-ttu-id="91bec-118">Una colección de elementos `baseAddress` que especifica las direcciones base utilizada por el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="91bec-118">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="91bec-119">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="91bec-119">\<timeOuts></span></span>](timeouts.md)|<span data-ttu-id="91bec-120">Un elemento de configuración que especifica el intervalo de tiempo permitido para que el host del servicio abra o cierre.</span><span class="sxs-lookup"><span data-stu-id="91bec-120">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="91bec-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="91bec-121">Parent Elements</span></span>  
  
|<span data-ttu-id="91bec-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="91bec-122">Element</span></span>|<span data-ttu-id="91bec-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="91bec-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91bec-124">\<service></span><span class="sxs-lookup"><span data-stu-id="91bec-124">\<service></span></span>](service.md)|<span data-ttu-id="91bec-125">Especifica la configuración de un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="91bec-125">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="91bec-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="91bec-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="91bec-127">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="91bec-127">Hosting</span></span>](../../../wcf/feature-details/hosting.md)

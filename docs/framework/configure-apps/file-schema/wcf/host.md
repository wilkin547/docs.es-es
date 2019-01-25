---
title: '&lt;host&gt;'
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 1fb35058d407d0fbae78092bb4ccd45b0aaa40e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702033"
---
# <a name="lthostgt"></a><span data-ttu-id="34b1f-102">&lt;host&gt;</span><span class="sxs-lookup"><span data-stu-id="34b1f-102">&lt;host&gt;</span></span>
<span data-ttu-id="34b1f-103">Especifica los valores para un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="34b1f-103">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="34b1f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="34b1f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="34b1f-105">\<services></span><span class="sxs-lookup"><span data-stu-id="34b1f-105">\<services></span></span>  
<span data-ttu-id="34b1f-106">\<service></span><span class="sxs-lookup"><span data-stu-id="34b1f-106">\<service></span></span>  
<span data-ttu-id="34b1f-107">\<host ></span><span class="sxs-lookup"><span data-stu-id="34b1f-107">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34b1f-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="34b1f-108">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="34b1f-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="34b1f-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34b1f-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="34b1f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="34b1f-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="34b1f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34b1f-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="34b1f-112">Attributes</span></span>  
 <span data-ttu-id="34b1f-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="34b1f-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="34b1f-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="34b1f-114">Child Elements</span></span>  
  
|<span data-ttu-id="34b1f-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="34b1f-115">Element</span></span>|<span data-ttu-id="34b1f-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="34b1f-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34b1f-117">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="34b1f-117">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="34b1f-118">Una colección de elementos `baseAddress` que especifica las direcciones base utilizada por el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="34b1f-118">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="34b1f-119">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="34b1f-119">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="34b1f-120">Un elemento de configuración que especifica el intervalo de tiempo permitido para que el host del servicio abra o cierre.</span><span class="sxs-lookup"><span data-stu-id="34b1f-120">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="34b1f-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="34b1f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="34b1f-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="34b1f-122">Element</span></span>|<span data-ttu-id="34b1f-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="34b1f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34b1f-124">\<service></span><span class="sxs-lookup"><span data-stu-id="34b1f-124">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="34b1f-125">Especifica la configuración para un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="34b1f-125">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="34b1f-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="34b1f-126">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="34b1f-127">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="34b1f-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)

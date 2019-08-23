---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 21d53df12c2b2d703b771e2b9cb5ee87dafc410e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918706"
---
# <a name="host"></a><span data-ttu-id="ea184-101">\<> host</span><span class="sxs-lookup"><span data-stu-id="ea184-101">\<host></span></span>
<span data-ttu-id="ea184-102">Especifica los valores para un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="ea184-102">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="ea184-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ea184-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="ea184-104">\<> de servicios</span><span class="sxs-lookup"><span data-stu-id="ea184-104">\<services></span></span>  
<span data-ttu-id="ea184-105">\<service></span><span class="sxs-lookup"><span data-stu-id="ea184-105">\<service></span></span>  
<span data-ttu-id="ea184-106">\<> host</span><span class="sxs-lookup"><span data-stu-id="ea184-106">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea184-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea184-107">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="ea184-108">Type</span><span class="sxs-lookup"><span data-stu-id="ea184-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea184-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ea184-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ea184-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ea184-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea184-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="ea184-111">Attributes</span></span>  
 <span data-ttu-id="ea184-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ea184-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ea184-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ea184-113">Child Elements</span></span>  
  
|<span data-ttu-id="ea184-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="ea184-114">Element</span></span>|<span data-ttu-id="ea184-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ea184-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea184-116">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="ea184-116">\<baseAddresses></span></span>](baseaddresses.md)|<span data-ttu-id="ea184-117">Una colección de elementos `baseAddress` que especifica las direcciones base utilizada por el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="ea184-117">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="ea184-118">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="ea184-118">\<timeOuts></span></span>](timeouts.md)|<span data-ttu-id="ea184-119">Un elemento de configuración que especifica el intervalo de tiempo permitido para que el host del servicio abra o cierre.</span><span class="sxs-lookup"><span data-stu-id="ea184-119">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ea184-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ea184-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ea184-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="ea184-121">Element</span></span>|<span data-ttu-id="ea184-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ea184-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea184-123">\<service></span><span class="sxs-lookup"><span data-stu-id="ea184-123">\<service></span></span>](service.md)|<span data-ttu-id="ea184-124">Especifica la configuración de un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ea184-124">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ea184-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea184-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="ea184-126">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="ea184-126">Hosting</span></span>](../../../wcf/feature-details/hosting.md)

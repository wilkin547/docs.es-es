---
title: '&lt;Host&gt;'
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: ec53568e9d1df9ebb04bc299f491e80674950c63
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2018
ms.locfileid: "34233735"
---
# <a name="lthostgt"></a><span data-ttu-id="346e4-102">&lt;Host&gt;</span><span class="sxs-lookup"><span data-stu-id="346e4-102">&lt;host&gt;</span></span>
<span data-ttu-id="346e4-103">Especifica los valores para un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="346e4-103">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="346e4-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="346e4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="346e4-105">\<Servicios ></span><span class="sxs-lookup"><span data-stu-id="346e4-105">\<services></span></span>  
<span data-ttu-id="346e4-106">\<servicio ></span><span class="sxs-lookup"><span data-stu-id="346e4-106">\<service></span></span>  
<span data-ttu-id="346e4-107">\<host ></span><span class="sxs-lookup"><span data-stu-id="346e4-107">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="346e4-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="346e4-108">Syntax</span></span>  
  
```xml  
<host>
    <baseAddresses>  
        <add baseAddress="string" />  
    </baseAddresses>  
    <timeOuts closeTimeout="TimeSpan" openTimeout="TimeSpan">  
</host>  
```  
  
## <a name="type"></a><span data-ttu-id="346e4-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="346e4-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="346e4-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="346e4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="346e4-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="346e4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="346e4-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="346e4-112">Attributes</span></span>  
 <span data-ttu-id="346e4-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="346e4-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="346e4-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="346e4-114">Child Elements</span></span>  
  
|<span data-ttu-id="346e4-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="346e4-115">Element</span></span>|<span data-ttu-id="346e4-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="346e4-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="346e4-117">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="346e4-117">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="346e4-118">Una colección de elementos `baseAddress` que especifica las direcciones base utilizada por el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="346e4-118">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="346e4-119">\<los tiempos de espera ></span><span class="sxs-lookup"><span data-stu-id="346e4-119">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="346e4-120">Un elemento de configuración que especifica el intervalo de tiempo permitido para que el host del servicio abra o cierre.</span><span class="sxs-lookup"><span data-stu-id="346e4-120">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="346e4-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="346e4-121">Parent Elements</span></span>  
  
|<span data-ttu-id="346e4-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="346e4-122">Element</span></span>|<span data-ttu-id="346e4-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="346e4-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="346e4-124">\<servicio ></span><span class="sxs-lookup"><span data-stu-id="346e4-124">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="346e4-125">Especifica la configuración para un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="346e4-125">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="346e4-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="346e4-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="346e4-127">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="346e4-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)

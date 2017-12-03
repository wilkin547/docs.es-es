---
title: '&lt;host&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d498190e7d7c3a6e879c50324e3b973f0f8e8fa6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="lthostgt"></a><span data-ttu-id="1d46b-102">&lt;host&gt;</span><span class="sxs-lookup"><span data-stu-id="1d46b-102">&lt;host&gt;</span></span>
<span data-ttu-id="1d46b-103">Especifica los valores para un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="1d46b-103">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="1d46b-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1d46b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1d46b-105">\<Servicios ></span><span class="sxs-lookup"><span data-stu-id="1d46b-105">\<services></span></span>  
<span data-ttu-id="1d46b-106">\<servicio ></span><span class="sxs-lookup"><span data-stu-id="1d46b-106">\<service></span></span>  
<span data-ttu-id="1d46b-107">\<host ></span><span class="sxs-lookup"><span data-stu-id="1d46b-107">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d46b-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1d46b-108">Syntax</span></span>  
  
```xml  
<host>  
      <baseAddresses>  
         <baseAddress baseAddress="string" />  
      </baseAddresses>  
      <timeOuts closeTimeout="TimeSpan"  
         openTimeout="TimeSpan" >  
</host>  
```  
  
## <a name="type"></a><span data-ttu-id="1d46b-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="1d46b-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1d46b-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1d46b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1d46b-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1d46b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1d46b-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="1d46b-112">Attributes</span></span>  
 <span data-ttu-id="1d46b-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1d46b-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1d46b-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1d46b-114">Child Elements</span></span>  
  
|<span data-ttu-id="1d46b-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="1d46b-115">Element</span></span>|<span data-ttu-id="1d46b-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="1d46b-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1d46b-117">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="1d46b-117">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="1d46b-118">Una colección de elementos `baseAddress` que especifica las direcciones base utilizada por el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="1d46b-118">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="1d46b-119">\<los tiempos de espera ></span><span class="sxs-lookup"><span data-stu-id="1d46b-119">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="1d46b-120">Un elemento de configuración que especifica el intervalo de tiempo permitido para que el host del servicio abra o cierre.</span><span class="sxs-lookup"><span data-stu-id="1d46b-120">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1d46b-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1d46b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="1d46b-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="1d46b-122">Element</span></span>|<span data-ttu-id="1d46b-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="1d46b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1d46b-124">\<servicio ></span><span class="sxs-lookup"><span data-stu-id="1d46b-124">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="1d46b-125">Especifica la configuración para un servicio [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d46b-125">Specifies the settings for a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1d46b-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d46b-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="1d46b-127">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="1d46b-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)

---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 059ea4e637ab906d1fde9807a73ac8341f81c574
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926423"
---
# <a name="baseaddresses"></a><span data-ttu-id="8085b-101">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="8085b-101">\<baseAddresses></span></span>
<span data-ttu-id="8085b-102">Representa una colección de elementos `baseAddress`, que son las direcciones base para un host del servicio en un entorno autohospedado.</span><span class="sxs-lookup"><span data-stu-id="8085b-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="8085b-103">Si una dirección base está presente, los extremos se pueden configurar con direcciones relativas a la dirección base.</span><span class="sxs-lookup"><span data-stu-id="8085b-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="8085b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8085b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8085b-105">\<client></span><span class="sxs-lookup"><span data-stu-id="8085b-105">\<client></span></span>  
<span data-ttu-id="8085b-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="8085b-106">\<endpoint></span></span>  
<span data-ttu-id="8085b-107">\<> host</span><span class="sxs-lookup"><span data-stu-id="8085b-107">\<host></span></span>  
<span data-ttu-id="8085b-108">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="8085b-108">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8085b-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8085b-109">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="8085b-110">Type</span><span class="sxs-lookup"><span data-stu-id="8085b-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8085b-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8085b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8085b-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8085b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8085b-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="8085b-113">Attributes</span></span>  
 <span data-ttu-id="8085b-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8085b-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8085b-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8085b-115">Child Elements</span></span>  
  
|<span data-ttu-id="8085b-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="8085b-116">Element</span></span>|<span data-ttu-id="8085b-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8085b-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8085b-118">\<add></span><span class="sxs-lookup"><span data-stu-id="8085b-118">\<add></span></span>](add-of-baseaddresses.md)|<span data-ttu-id="8085b-119">Un elemento de configuración que especifica las direcciones base usadas por el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="8085b-119">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8085b-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8085b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="8085b-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="8085b-121">Element</span></span>|<span data-ttu-id="8085b-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8085b-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8085b-123">\<> host</span><span class="sxs-lookup"><span data-stu-id="8085b-123">\<host></span></span>](host.md)|<span data-ttu-id="8085b-124">Un elemento de configuración que especifica valores para un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="8085b-124">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8085b-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="8085b-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="8085b-126">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="8085b-126">Hosting</span></span>](../../../wcf/feature-details/hosting.md)

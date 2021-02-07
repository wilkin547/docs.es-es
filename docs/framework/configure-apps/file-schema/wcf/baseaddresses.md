---
description: 'Más información acerca de: <baseAddresses>'
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: a32afc23d4332bad149765a318c3ecdc73f99be0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749693"
---
# \<baseAddresses>

<span data-ttu-id="13b0c-102">Representa una colección de elementos `baseAddress`, que son las direcciones base para un host del servicio en un entorno autohospedado.</span><span class="sxs-lookup"><span data-stu-id="13b0c-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="13b0c-103">Si una dirección base está presente, los extremos se pueden configurar con direcciones relativas a la dirección base.</span><span class="sxs-lookup"><span data-stu-id="13b0c-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<baseAddresses>**  
  
## <a name="syntax"></a><span data-ttu-id="13b0c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13b0c-104">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="13b0c-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="13b0c-105">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13b0c-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="13b0c-106">Attributes and Elements</span></span>  

 <span data-ttu-id="13b0c-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="13b0c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13b0c-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="13b0c-108">Attributes</span></span>  

 <span data-ttu-id="13b0c-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="13b0c-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="13b0c-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="13b0c-110">Child Elements</span></span>  
  
|<span data-ttu-id="13b0c-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="13b0c-111">Element</span></span>|<span data-ttu-id="13b0c-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="13b0c-112">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-baseaddresses.md)|<span data-ttu-id="13b0c-113">Un elemento de configuración que especifica las direcciones base usadas por el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="13b0c-113">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="13b0c-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="13b0c-114">Parent Elements</span></span>  
  
|<span data-ttu-id="13b0c-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="13b0c-115">Element</span></span>|<span data-ttu-id="13b0c-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="13b0c-116">Description</span></span>|  
|-------------|-----------------|  
|[\<host>](host.md)|<span data-ttu-id="13b0c-117">Un elemento de configuración que especifica valores para un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="13b0c-117">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="13b0c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="13b0c-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="13b0c-119">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="13b0c-119">Hosting</span></span>](../../../wcf/feature-details/hosting.md)

---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 3b6cebd178ac5cd30fa034bd961d2d08075771d2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201543"
---
# \<baseAddresses>

<span data-ttu-id="adb93-101">Representa una colección de elementos `baseAddress`, que son las direcciones base para un host del servicio en un entorno autohospedado.</span><span class="sxs-lookup"><span data-stu-id="adb93-101">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="adb93-102">Si una dirección base está presente, los extremos se pueden configurar con direcciones relativas a la dirección base.</span><span class="sxs-lookup"><span data-stu-id="adb93-102">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<baseAddresses>**  
  
## <a name="syntax"></a><span data-ttu-id="adb93-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="adb93-103">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="adb93-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="adb93-104">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="adb93-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="adb93-105">Attributes and Elements</span></span>  

 <span data-ttu-id="adb93-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="adb93-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="adb93-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="adb93-107">Attributes</span></span>  

 <span data-ttu-id="adb93-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="adb93-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="adb93-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="adb93-109">Child Elements</span></span>  
  
|<span data-ttu-id="adb93-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="adb93-110">Element</span></span>|<span data-ttu-id="adb93-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="adb93-111">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-baseaddresses.md)|<span data-ttu-id="adb93-112">Un elemento de configuración que especifica las direcciones base usadas por el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="adb93-112">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="adb93-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="adb93-113">Parent Elements</span></span>  
  
|<span data-ttu-id="adb93-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="adb93-114">Element</span></span>|<span data-ttu-id="adb93-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="adb93-115">Description</span></span>|  
|-------------|-----------------|  
|[\<host>](host.md)|<span data-ttu-id="adb93-116">Un elemento de configuración que especifica valores para un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="adb93-116">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="adb93-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="adb93-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="adb93-118">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="adb93-118">Hosting</span></span>](../../../wcf/feature-details/hosting.md)

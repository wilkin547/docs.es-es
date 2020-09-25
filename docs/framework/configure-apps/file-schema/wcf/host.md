---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 524226cbb826486def18c1b3b66c5b4a3c456dec
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185683"
---
# \<host>

<span data-ttu-id="ce8d4-101">Especifica los valores para un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="ce8d4-101">Specifies settings for a service host.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<host>**  
  
## <a name="syntax"></a><span data-ttu-id="ce8d4-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce8d4-102">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="ce8d4-103">Tipo</span><span class="sxs-lookup"><span data-stu-id="ce8d4-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce8d4-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ce8d4-104">Attributes and Elements</span></span>  

 <span data-ttu-id="ce8d4-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ce8d4-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce8d4-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="ce8d4-106">Attributes</span></span>  

 <span data-ttu-id="ce8d4-107">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ce8d4-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ce8d4-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ce8d4-108">Child Elements</span></span>  
  
|<span data-ttu-id="ce8d4-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="ce8d4-109">Element</span></span>|<span data-ttu-id="ce8d4-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="ce8d4-110">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddresses>](baseaddresses.md)|<span data-ttu-id="ce8d4-111">Una colección de elementos `baseAddress` que especifica las direcciones base utilizada por el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="ce8d4-111">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[\<timeOuts>](timeouts.md)|<span data-ttu-id="ce8d4-112">Un elemento de configuración que especifica el intervalo de tiempo permitido para que el host del servicio abra o cierre.</span><span class="sxs-lookup"><span data-stu-id="ce8d4-112">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ce8d4-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ce8d4-113">Parent Elements</span></span>  
  
|<span data-ttu-id="ce8d4-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="ce8d4-114">Element</span></span>|<span data-ttu-id="ce8d4-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="ce8d4-115">Description</span></span>|  
|-------------|-----------------|  
|[\<service>](service.md)|<span data-ttu-id="ce8d4-116">Especifica la configuración de un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ce8d4-116">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ce8d4-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ce8d4-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="ce8d4-118">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="ce8d4-118">Hosting</span></span>](../../../wcf/feature-details/hosting.md)

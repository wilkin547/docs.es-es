---
description: 'Más información acerca de: <host>'
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: ff240c85af3aab7c1208a6a49b1943f3c6a8cd99
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802286"
---
# \<host>

<span data-ttu-id="e8f2e-102">Especifica los valores para un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="e8f2e-102">Specifies settings for a service host.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<host>**  
  
## <a name="syntax"></a><span data-ttu-id="e8f2e-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8f2e-103">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="e8f2e-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="e8f2e-104">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8f2e-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e8f2e-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e8f2e-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e8f2e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8f2e-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="e8f2e-107">Attributes</span></span>  

 <span data-ttu-id="e8f2e-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e8f2e-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e8f2e-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e8f2e-109">Child Elements</span></span>  
  
|<span data-ttu-id="e8f2e-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8f2e-110">Element</span></span>|<span data-ttu-id="e8f2e-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8f2e-111">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddresses>](baseaddresses.md)|<span data-ttu-id="e8f2e-112">Una colección de elementos `baseAddress` que especifica las direcciones base utilizada por el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="e8f2e-112">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[\<timeOuts>](timeouts.md)|<span data-ttu-id="e8f2e-113">Un elemento de configuración que especifica el intervalo de tiempo permitido para que el host del servicio abra o cierre.</span><span class="sxs-lookup"><span data-stu-id="e8f2e-113">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e8f2e-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e8f2e-114">Parent Elements</span></span>  
  
|<span data-ttu-id="e8f2e-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8f2e-115">Element</span></span>|<span data-ttu-id="e8f2e-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8f2e-116">Description</span></span>|  
|-------------|-----------------|  
|[\<service>](service.md)|<span data-ttu-id="e8f2e-117">Especifica la configuración de un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e8f2e-117">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e8f2e-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8f2e-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="e8f2e-119">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="e8f2e-119">Hosting</span></span>](../../../wcf/feature-details/hosting.md)

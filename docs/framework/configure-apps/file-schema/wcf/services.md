---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: b8cb5075ba41bed5a22b152a231c7213b326a62f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153721"
---
# \<services>

<span data-ttu-id="ef963-101">Los servicios se definen en la sección de `services` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="ef963-101">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="ef963-102">Cada servicio tiene su propia sección de configuración de `service`.</span><span class="sxs-lookup"><span data-stu-id="ef963-102">Each service has its own `service` configuration section.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<services>**  
  
## <a name="syntax"></a><span data-ttu-id="ef963-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef963-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef963-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ef963-104">Attributes and Elements</span></span>  

 <span data-ttu-id="ef963-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ef963-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef963-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="ef963-106">Attributes</span></span>  

 <span data-ttu-id="ef963-107">None</span><span class="sxs-lookup"><span data-stu-id="ef963-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ef963-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ef963-108">Child Elements</span></span>  
  
|<span data-ttu-id="ef963-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef963-109">Element</span></span>|<span data-ttu-id="ef963-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="ef963-110">Description</span></span>|  
|-------------|-----------------|  
|[\<service>](service.md)|<span data-ttu-id="ef963-111">Defina el contrato de servicios, comportamiento y puntos de conexión del servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="ef963-111">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ef963-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ef963-112">Parent Elements</span></span>  
  
|<span data-ttu-id="ef963-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef963-113">Element</span></span>|<span data-ttu-id="ef963-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="ef963-114">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="ef963-115">El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ef963-115">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ef963-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef963-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
